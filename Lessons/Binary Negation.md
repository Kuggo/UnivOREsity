# Binary Negation

---

## Prerequisites

- [Binary](Binary.md#binary)

---

## Contents

Topics to be covered in this lesson:

- [Why is negation important?](Binary%20Negation.md#why-is-negation-important)
- [1s complement](Binary%20Negation.md#1s-complement)
- [2s complement](Binary%20Negation.md#2s-complement)

---

## Why is negation important?

When one is working with addition of positive numbers, the result of the operation will always be a positive number. 
However, when dealing with Negation/Subtraction of positive numbers, our answers will also be negative. But the problem is that we don't have yet learned a way to represent negative numbers, as binary only represents positive integers.  
Negation is the process of inverting the number to its negative form, and as such, it will be extremely important in solving our problem.  
It is also important to note that Subtraction can be done by combining addition with subtraction: ``A - B = A + (-B)``

In our daily lives we use 2 extra characters besides the 10 digits: the ``-`` and ``+``. That format is called Signed Magnitude. A number represented in this system will have 2 parts:  
The sign, which is either ``+`` or ``-``. Generally we don't write the `+` as a number is positive by default.
The magnitude, which is how _big_ a number is. It's often called the absolute value.

However, this system is not very good for computers and binary. We saw that computers used binary because they could only represent 2 states. If that is the case we can easily add a 3rd or 4th symbol for them to represent, so we must find a better way.

## 1s complement?

1s Complement is a system that aims to solve this problem. A way to represent negative numbers within a certain range efficiently for computers.  
For an N bit number, one can obatin its negative form by inverting 1s to 0s, and 0s to 1s on all bits (bitwise operation NOT).  
Example: ``-5 = ~0b0101 = 0b1010``  
You might think that there is a problem. ``0b1010`` is the representation for 10! How can we tell if that is a -5 or a 10??
The answer might surprise you with how simple it is: There is no such conflict. Allow me to clarify:  
N bits can represent $$2^N$$ diferent combinations. In unsigned integers that is the range: $$ \left] 0, 2^N-1 \right[ $$.  
Since we are using the same number of bits, we cannot keep the same number of positive values if we want to represent negatives. We should have equally many negative and positive numbers. So we will use our upper half of combinations available to represent negative numbers.
The positive numbers will go from $$ \left] 0, 2^{N-1} - 1 \right[ $$.  
The negative numbers will be using the range $$ \left] 2^{N-1}, 2^N - 1 \right[ $$ to represent the negative numbers in the range $$ \left] -(2^{N-1} - 1), -0 \right[ $$.  
That means the whole range of 1s complement is $$ \left] -(2^{N-1} - 1), 2^{N-1} - 1 \right[ $$.
To help you visually understand the concept here is an example with how it will work 4 bits:  
``0000`` -> 0  
``0001`` -> 1  
``0010`` -> 2  
``0011`` -> 3  
``0100`` -> 4  
``0101`` -> 5  
``0110`` -> 6  
``0111`` -> 7  
``1000`` -> -7  
``1001`` -> -6  
``1010`` -> -5  
``1011`` -> -4  
``1100`` -> -3  
``1101`` -> -2  
``1110`` -> -1  
``1111`` -> -0

The advantages of 1s complement is that negating is extremely simple. The disadvantages are the following:  
Notice how 1s complement has a representation of negative zero? that is wasting 1 combination but the worst part is that, it ruins our calculations if our result is not negative.  
Take the example: ``3 + -5`` or ``0b0011 + 0b1010``. That will be equal to ``0b1101`` which is -2, as expected.  
Now, take this example: ``5 + -3`` or ``0b0101 + 0b1100``. That will be equal to ``0b0001`` which is 1 and not 2 as one should expect.
When you add numbers in 1s complement and one of the inputs is negative and the answer is positive (0 counts as positive), you must add 1 to the final result to correct it.  
Example: ``7 + -6`` or ``0b0111 + 0b1001`` is equal to ``0b0000``. Because 0 is positive, we must add 1, and we get our answer 1.

## 2s complement?

2s Complement is an alternative to 1s complement, that fixes all problems related to it.  
Essencially all the problems described above come from the fact that we have a -0 between -1 and 0. So how can we remove it?  
Instead of going from -0 to -7 we can move that range to -1 to -8 (specifically in 4 bits).
Let's take a look at the representations of 2s complement:
``0000`` -> 0  
``0001`` -> 1  
``0010`` -> 2  
``0011`` -> 3  
``0100`` -> 4  
``0101`` -> 5  
``0110`` -> 6  
``0111`` -> 7  
``1000`` -> -8  
``1001`` -> -7  
``1010`` -> -6  
``1011`` -> -5  
``1100`` -> -4  
``1101`` -> -3  
``1110`` -> -2  
``1111`` -> -1

How is this achieved? after a number was converted to 1s complement we add 1 to move all the representations 1 value. -0 is now gone. But what happens if we negate 0? what number will we get if we don't have a -0?  
``-0b0000 = ~0b0000 + 1 = 0b1111 + 1 = 0b10000 = 0b0000`` Note: the 1 in the left was removed due to being an overflow (when working with a fixed number of bits)  
Lets look at a final example of it being used to add 2 numbers in 2s complement format:  
``5 + -3`` or ``0b0101 + ~0b0011 + 1 = 0b0101 + 0b1100 + 1 = 0b0101 + 0b1101 = 0b0010`` which is 2 as expected  
``3 + -5`` or ``0b0011 + ~0b0101 + 1 = 0b0011 + 0b1010 + 1 = 0b0011 + 0b1101 = 0b1110`` which is -2 as expected

The range for 2s complement is $$ \left] -2^{N-1}, 2^{N-1} -1 \right[ $$.

---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Binary Subtraction](Binary%20Subtraction.md#binary-subtraction)
- [Subtractors](Adders#adders)

