# Binary Addition

---

## Prerequisites

- [Binary](binary#binary)

---

## Contents

Topics to be covered in this lesson:

- Addition in decimal
- Carry and Sum
- Addition using RCA algorithm

---

## Addition in Decimal

Before explaining How addition works in binary we should first get familiar with the algorithm we use.
It's likely that one learned this in first grade and does this automatically, but we will do a quick revision:  
When adding 2 numbers with several decimal places we don't do the whole addition at once. 
We first start from the LSD (Least Significant digit) and work our way to the MSD (Most Significant Digit).  
When adding 2 digits together `A + B = C`, our answer C lays in the interval: `0 <= C <= 18`. However, this poses a little problem: C may not be a digit, but be a 2 digit answer.
Because it's really useful to only work with digits, we separate the answer of a single digit addition (`A + B = C`) into 2 answers: The Carry and the Sum.  

### Carry and Sum

The Sum is the right digit of our answer.  
The Carry is the left digit of our asnwer (note: if the asnwer only has 1 digit, there is an implicit 0 as the left digit). The carry will need to be moved into its apropriate position (1 to the left of the Sum).  
We will see some examples:  
- ``1 + 2 = 03`` Carry = 0, Sum = 3  
- ``9 + 7 = 16`` Carry = 1, Sum = 6

Another thing to keep in mind is that we can't add 3 numbers at once. Addition is an operation that only takes 2 inputs.
If we want to add 3 numbers ``A + B + C`` we must separate it into 2 additions ``(A + B) + C``.

### Addition using the RCA algorithm

With all of this in mind we can finally take a look at how we can add 2 multi digit numbers:  
1. Starting from the LSD we add the 2 digits, and we get the Carry and Sum
2. We set Sum as the first digit of our final output
3. We go to the next 2 digits, and we add them (A + B)
4. We add the previous carry to the previous result ((A + B) + Carry)
5. We get our new Carry and Sum from the pevious result. If we have more digits we go back to step 3.

RCA stands for ripple carry adder, a circuit that adds numbers. The algorithm we just saw, is what the circuit does, hence calling it ripple carry addition algorithm.   
Let's apply those same rules on the example ``365 + 437``:

![Decimal Addition Step by Step](..\gifs\Addition_decimal1.gif)
 

## Binary Addition

### Half Addition

For the same algorithm to work again we need to define how to add single bit numbers in binary, then by using the algorithm we can use several single bit additions to add multi bit numbers.
Adding single bit numbers is called half addition.  
In binary this problem is decently simple: only 2 possible values for each input, and only 2 inputs, so that's in total 4 combinations.  
``0 + 0 = 00`` Carry = 0, Sum = 0  
``0 + 1 = 01`` Carry = 0, Sum = 1  
``1 + 0 = 01`` Carry = 0, Sum = 1  
``1 + 1 = 10`` Carry = 1, Sum = 0  

Notice that in order to get Carry we can use an AND operation.  
Similarly, Sum can be obtained using the XOR operation.  

### Full addition

As demonstrated earlier, from basic single digit addition, one can add muit digit numbers. In binary the same applies.  
Once defined how Sum and Carry are obtained we can follow the outlines steps (same as before, but in binary language).
Note that The first carry is always zero because there are no previous digits.

1. Starting at the LSB
2. Half add the A and B bits.
3. Half add that with the carry of the previous bit, obtaining the new Sum and Carry
4. If there are more bits to add advance to the next bits, and repeat from step 2.

Here is how that algorithm can be applied in the following addition: ``5 + 3``, or in binary ``0b0101 + 0b0011``

![Binary Addition Step by Step](..\gifs\Addition_binary.gif)

---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Binary Negation](Binary%20Negation.md#binary-negation)
- [Adders](Adders.md#adders)

