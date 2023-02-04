# Binary Subtraction

---

## Prerequisites

- [Binary](Binary.md#binary)
- [Binary Addition](Binary%20Addition.md#binary-addition)
- [Binary Negation](Binary%20Negation.md#binary-negation)

---

## Contents

Topics to be covered in this lesson:

- [Using negation to subtract](Binary%20Subtraction.md#using-negation-to-subtract)
- [Subtraction in decimal](Binary%20Subtraction.md#subtraction-in-decimal)
- [Borrow carry subtraction](Binary%20Subtraction.md#borrow-carry-subtraction)

---

## Using negation to subtract

As mentioned previously in the Negation lesson, subtraction can easily be done with addition and negation combined. Afteral ``A - B =  A + (-B)``. Using 2s complement we get ``A + ~B + 1``  
So subtraction using 2s complement can be easily achieved with that method. It is also the most common for ALU and cpus in general.  
One can also subtract using the following method: ``-(-A + B) = A - B``. Using double negation and an addition. One might ask why would there be a need to do subtraction using 2 negations when we can use only one of them.  
We can expand the Negation using 1s (or 2s) complement: ``A - B = -(-A + B) = ~(~A + B)``. Instead of 1 negation and 2 additions, we used 2 negations and 1 addition. Negation is a much faster operation than addition, so in some scenarios this can be a useful technique to apply.

You can end your lesson here or proceed to learn the dedicated algorithm for subtraction without using 2s complement.

## Subtraction in decimal

Before explaining how this method of subtraction works in binary we should first get familiar with the algorithm we use in decimal.
It's likely that one learned this in first grade and does this automatically, but we will do a quick revision:  
When subtracting 2 numbers with several decimal places we don't do the whole subtraction at once.
We first start from the LSD (Least Significant digit) and work our way to the MSD (Most Significant Digit).  
On each iteration we try to subtract the 2 digits, if the answer is negative we must add 10 to it, and send a borrow carry to the next digit. 
When the answer is negative, that means we can't resolve the value of that digit without it afecting the rest of the number (we can't have a negative digit), so to compensate we must counteract it with adding 10.  
Why 10? because that is the base we are working on. By adding 10 to this digit we must compensate it by subtracting 10 in another place of our number. In decimal, when moving to the left each digit is worth 10x the previous. 
With that in mind, we can subtract 1 in the next digit to compensate for the addition of 10. After all ``-1 * 10 = +10``.  

The algorithm can be better explained with the following steps:
1. Subtract digit B from digit A, and if the answer is negative add 10 to it and carry a -1 (borrow).
2. Subtract the borrow from the previous bit and calculate the current values of borrow and sum.
3. While there are digits left advance to the next pair of digits and go to step 1.

Or the process can be easily be visualized in the following GIF:

![Subtraction in Decimal]()

[//]: # (TODO)

## Borrow Carry Subtraction

Now that we understand the algorithm in decimal, let's modify it to work with binary. But first we must figure out subtraction of a single bit:
Reminder that Sum is the current sum of the digit, and borrow is the number sent to the next bit (similar to carry).
``0 - 0 = 0`` Borrow = 0, Sum = 0  
``0 - 1 = 1`` Borrow = 1, Sum = 1 (sum is 1 because ``-1 = -10 + 1``, the -10 will be borrow signal upwards)  
``1 - 0 = 1`` Borrow = 0, Sum = 1  
``1 - 1 = 0`` Borrow = 0, Sum = 0  

Notice that in order to get Borrow we can use the Nimply operation.  
Similarly, Sum can be obtained using the XOR operation.

Essencially this ubtraction algorithm is the same as addition, but instead of doing 'half addition' we do 'half subtraction'. 
Instead of Carry (AND) e use Borrow (Nimply), and sum stays the same.  
Here is a gif to visualize the process of a multi bit binary subtraction using this algorithm.

![Subtraction in Binary]()  

[//]: # (TODO)

---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Subtractors](Subtractors.md#subtractors)

