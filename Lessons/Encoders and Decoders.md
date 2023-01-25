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
The following example shows how a 2 bit encoder works:


## Decoders

Decoders do the opposite process as encoders do. Instead of converting from _one hot_ to binary, they convert from binary to _one hot_.  
TODO

---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [ROM]()

