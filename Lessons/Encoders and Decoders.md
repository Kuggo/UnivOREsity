# Encoders and Decoders

---

## Prerequisites

- [Binary](Binary.md#binary)
- [Logic Gates](Boolean%20Logic.md#logic-gates)

---

## Contents

Topics to be covered in this lesson:

- [Encoders](Encoders%20and%20Decoders.md#encoders)
- [Decoders](Encoders%20and%20Decoders.md#decoders)

---

## Encoders

Encoders are a simple way to convert information represented in one format to another.  
Generally by default encoders encode from _one hot_ to binary. However, if specified there can be encoders from decimal to binary following certain algorithms that won't be described here.  

_One hot_ works in the following way: there are several inputs that represent diferent values, and only **one** of the inputs is on at a give time. These inputs are also generally ordered, but it's not a requirement for it to be considered _one hot_.  
One can think of this system as unary, but only the left most bit is on at any time. 

Now that we are familiar with _one hot_ we will understand why it is used so often on encoders. If we are sure that 2 wires never turn on at the same time we don't need to worry about multiple wires interfearing. In a way a single input is not aware of what others will do because they won't ever be connected. And if every input can function without needing to be aware of their neighbours, then building them becomes a very easy and repetitive pattern stacked in parallel.  
Let's suppose the bits of our binary output will be named using O<sub>n</sub> (n being the index of the bit, starting from 0), and our inputs are named using decimal numbers starting from 0...
The following example shows how a 2 bit encoder works:  
0 -> `00`  
1 -> `01`  
2 -> `10`  
3 -> `11`  

The letters were mapped to binary numbers. When looking to individual bits we can see what connections are done.
Let's use a table to make visualizing what conections are done easily.

| Input | O<sub>1</sub> | O<sub>0</sub> |
|:-----:|:-------------:|:-------------:|
|   0   |       ❌       |       ❌       |
|   1   |       ❌       |       ✅       |
|   2   |       ✅       |       ❌       |
|   3   |       ✅       |       ✅       |

We can now see that 0 is not connected to anything (the default value of an unmodified bit is 0), while 3 is connected to every bit.  
I will also take the time to show a schematic of the encoder presented above:

![2-bit encoder](../Images/2b%20encoder.png)

Now the remaining question is how to make an encoder for any bit length? That can be done by repeating the pattern we have been using:  
We take the input we want our encoder to encode to, and connect it so that the correct bits turn on in the output. If we wish that the bit turns on, we connect our input to that bit, if not we skip that bit and do this until all bits were checked.

## Decoders

Decoders do the opposite process as encoders do. Instead of converting from _one hot_ to binary, they convert from binary to _one hot_.  
One decoder decodes a single combination of binary, so it will turn on only when the exact combination of 1s and 0s were inputed. In order to get a decoder that decodes all combinations, one must build all of these single decoders in parallel with all the different combinations.  
This is usefull to keep in mind because there is a chance that our inputs only go from a certain range, so building the rest of the decoders for the rest of the combinations outside that range would be pointless.  

Now our only task is to understand how to decode a specific combination of 1s and 0s. To reduce the problem at hand, lets think of a 2 bit binary number.
If there is a binary 0 with 2 bits, that means both inputs are off. Do you remember of any logic gate that turned on when both inputs were off?  
NOR gate is the correct answer.  

What about detecting the number 3 (0b11)? Do you know of any logic gate that turns on when both inputs are on?  
AND gate is the correct answer.  

If we apply DeMorgan's law we can see that AND is basically the same gate as NOR, just with the inputs inverted. That is due to those logic gates detecting opposite combinations of inputs.
But if you take NOR as the default gate, you can use a general formula to get the correct combination. For N bits, build an N bit NOR gate and for every bit that is expected to be a 1 invert that input.  
We can look at a table showing when we invert the inputs for the NOR gate (❌ means not invert, and ✅ meaning invert):

|     Input     |  0  |  1  | 2   | 3   |
|:-------------:|:---:|:---:|-----|-----|
| O<sub>0</sub> |  ❌  |  ✅  | ❌   | ✅   |
| O<sub>1</sub> |  ❌  |  ❌  | ✅   | ✅   |

Here is the schematic for a single decoder for the number 13 (0b1101):

![Schematic of a 4-bit decoder for the number 13](../Images/4b%2013%20decoder.png)


---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [ROM]()

