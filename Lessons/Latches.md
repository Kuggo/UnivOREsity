# Latches

---

## Prerequisites

- [Logic Gates](Boolean%20Logic.md#logic-gates)

---

## Contents

Topics to be covered in this lesson:

- [RS Nor Latch](Latches.md#rs-nor-latch)
- [T flip flop](Latches.md#t-flip-flop)
- [D Latch](Latches.md#d-latch)

---

## Introduction


Latches are electronic circuits that can store a binary value, 1 or 0 and are commonly used in digital 
circuits for storing data temporarily.  

They are building blocks used in digital systems to implement state machines, counters, and memory elements.  
Unlike combinational circuits, which output a value solely based on their inputs, sequential circuits have memory, 
and their output depends not only on the input values but also on the current state of the circuit. 
Note that the current state can be interpreted as an input, and the circuit can be analized as combinational.

Most latches we will be seeing generally have an extra input called Enable E, and a Clock C to synchronize the circuits.
A latch with a clock input becomes a flip flop.
However, we will be omiting those for the sake of simplicity. Just keep in mind that the output of 
the flip flop is only updated after a clock signal.  

Latches have generally 2 biproducts, Q and Q̅. Q is the output, and is the negated version of Q (Q = ~Q̅).
In any latch Q̅ can be obtained by inverting Q. For uniformity, we will not be including Q̅ in every truth table. 
Q̅ is mentioned because often it can remove the need for a NOT gate.


## RS Nor Latch

The RS Nor latch is the simplest form of a latch. It is composed of two cross-coupled NOR gates. 
It has two inputs, R (reset) and S (set), and two outputs, Q (the normal output) and Q̅ (the complement output).

When R = 0 and S = 1, the output Q = 1 and Q̅ = 0, and when R = 1 and S = 0, the output Q = 0 and Q̅ = 1. 
When both inputs are 0 or both inputs are 1, the output state is held, and the latch maintains its previous state. 
This is known as the "forbidden" state and should be avoided in any practical design.

The truth table for an RS Nor latch is as follows:

|  R  |  S  |  Q  | Q̅  |
|:---:|:---:|:---:|-----|
|  0  |  0  |  Q  | ~Q  |
|  0  |  1  |  1  | 0   |
|  1  |  0  |  0  | 1   |
|  1  |  1  |  X  | X   |

Where X means the output is indeterminate.

The RS Nor latch can be constructed using NOR gates as explained earlier. Here is a diagram of that implementation:

![RS Nor latch made with Nor gates](../Images/RS%20nor%20latch.png)

## T Flip Flop

The T flip flop, also known as the toggle flip flop, is a single-bit memory cell that can toggle its 
output state based on a trigger signal, T. The circuit has one input, T, and two outputs, Q and Q̅.

The operation of the T flip flop is simple. When T = 0, the output state does not change. 
When T = 1, the output state toggles, i.e., if the previous output was 0, it becomes 1, and if the 
previous output was 1, it becomes 0.

The truth table for a T flip flop is as follows:

|  T  |  Q  |
|:---:|:---:|
|  0  |  Q  |
|  1  | ~Q  |

The D latch can be constructed using an RS Nor latch with both inputs tied together. Here is a diagram of
that implementation:

![T latch made with RS Nor latch](../Images/T%20latch.png)

## D Latch

The D latch, also known as the data latch or delay latch, is a type of latch that stores the input data signal. 
The circuit has one input: `D` and output `Q`.

When the input D changes, the output Q follows it (after the clock signal), maintaining the value of D.
In other words, the output changes as the input changes.

The truth table for a D latch is as follows:

|  D  |  Q  |
|:---:|:---:|
|  0  |  0  |
|  1  |  1  |

The D latch can be constructed using an RS Nor latch with both inputs tied together. Here is a diagram of
that implementation:

![D latch made with RS Nor latch](../Images/d%20latch.png)

---
## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Clocks]()

