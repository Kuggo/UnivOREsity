# Binary

---

## Prerequisites

- [Nothing](binary#binary)

---

## Contents

Topics to be covered in this lesson:

- Why use Binary?
- How does it work?
- Translating from binary to decimal
- Translating from decimal to binary
- How many numbers can be represented with binary?
- How does this apply to other bases?

---

## Why use Binary?

Binary is a system of representing numbers using only two symbols: 0 and 1. These symbols are often called "bits". The reason for using only 2 digits is that hardware can only have two states, 'on' and 'off'.  
When talking about numbers in different bases, we must have a way to distinguish between which base we are representing that number with. So to fix that problem, we prefix ``0b`` when the number is in binary and ``0d`` when its in decimal. Other bases like hexadecimal and octal use ``0x`` and ``0o`` respectively.  
Here are the prefixes being used to distinguish which number we mean:  
``0b101 = 5 (five)``  
``0o101 = 65 (sixty five)``  
``0d101 = 101 (one hundred and one)``  
``0x101 = 257 (two hundred and fifty seven)``

## How does it work?

In a binary system, each digit represents a power of 2, that means each digit doubles its value when going to the left. The rightmost digit represents 1 (2^0), the next digit to the left represents 2 (2^1), and so on.  
For example, the binary number 101 represents the decimal number ``1*2^2 + 0*2^1 + 1*2^0 = 1*4 + 0*2 + 1*1 = 4 + 1 = 5``.

## Translating from decimal to binary

To translate a decimal number to binary, you can see what bit has the biggest value that is still below our number, and then subtract our number with the value of that bit. And we repeat this process until we have our asnwer.  
Here is an example: what is the representation of 21 in binary?
- The biggest bit we can fit is 16 (0b10000) because 32 would be too much. We now subtract the two and we get ``21 - 16 = 5``  
- Repeating the same process we find out that 4 is the biggest value we can fit below 5 so we add 4 (0b100) to our result (0b10100) and subtract ``5 - 4 = 1``
- Lastly we have that 1 is the lowest bit, so we can add that in to our result (0b10101) and ``1 - 1 = 0``, so we can stop now

To translate a decimal number to binary, you can also use the following method:
1. Divide the number by 2
2. Write down the remainder (0 or 1)
3. Repeat step 1 and 2 until the quotient becomes 0
4. The remainders, read from bottom to top, give the binary representation of the decimal number.

For example, to translate the decimal number 10 to binary, you would do the following:

* 10 / 2 = 5 with a remainder of 0, so the first digit is 0.
* 5 / 2 = 2 with a remainder of 1, so the second digit is 1.
* 2 / 2 = 1 with a remainder of 0, so the third digit is 0.
* 1 / 2 = 0 with a remainder of 1, so the last digit is 1.

The final binary representation is 1010.

## How many numbers can be represented with binary?

The number of unique numbers that can be represented with a certain number of bits is 2^n, where n is the number of bits.  
For example, using 4 bits, allows you to represent 2^4 = 16 unique combination of numbers. The minimum is the number that corresponds to the binary representation of having just zeros in the number, and the maximum is just having ones in the representation of the number.  
The minimum number we can represent is 0, and the maximum we can represent will be ``(2^n) - 1``  
For example: using 4 bits the minimum we have is 0 and the max is 16-1 which is 15

## How does this apply to other bases?

The same principles apply to other number bases, such as decimal (base 10) or hexadecimal (base 16). 
However, instead of powers of 2, the digits represent powers of the base.  
For example, in decimal, each digit represents a power of 10. In hexadecimal, each digit represents a power of 16. The process of converting between different bases is similar to the process of converting between binary and decimal, but with different base-specific calculations. It's worth noting that it is simpler to convert decimal to binary or viceversa than to convert decimal to hexadecimal or viceversa.
One might wonder why do we use different bases. The reason is convenience. Decimal is used because we have 10 fingers in our hands. Octal and Hexadecimal are used because 8 and 16 are powers of 2, so translating between these bases and binary is extremely easy.
The number `0x13` can be represented easily. The representation of the number 3 in 4 bits (for hexadecimal, and 3 bits for octal) is `0b0011`.  
The representation of 1 is ``0b0001``, so we join our representations, and we get that ``0x13 = 00010011``. The same applies the other way.

---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Binary addition](Binary Addition#binary-addition)
