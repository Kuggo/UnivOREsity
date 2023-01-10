# Boolean Logic

---

## Prerequisites

- [Nothing](Boolean%20Logic.md#boolean-logic)

---

## Contents

This Lesson is split into 3 sections (to avoid a lot of redundancy), each one with its own sub topics.  
Topics to be covered in this lesson:

- [Boolean Algebra](Boolean%20Logic.md#boolean-algebra)
    - [Basic Definitions](Boolean%20Logic.md#basic-definitions)
    - [Boolean Expressions](Boolean%20Logic.md#boolean-expressions)
    - [Boolean Laws](Boolean%20Logic.md#boolean-laws)
      - [Idempotent Law](Boolean%20Logic.md#idempotent-law)
      - [Absorvent and Neutral Elements](Boolean%20Logic.md#absorvent-and-neutral-elements)
      - [Association and Distribuition](Boolean%20Logic.md#association-and-distribuition)
      - [DeMorgan's Laws](Boolean%20Logic.md#demorgans-laws)
- [Logic Gates](Boolean%20Logic.md#logic-gates)
    - [NOT gate](Boolean%20Logic.md#not-gate)
    - [OR gate](Boolean%20Logic.md#or-gate)
    - [NOR gate](Boolean%20Logic.md#nor-gate)
    - [AND gate](Boolean%20Logic.md#and-gate)
    - [NAND gate](Boolean%20Logic.md#nand-gate)
    - [XOR gate](Boolean%20Logic.md#xor-gate)
    - [XNOR gate](Boolean%20Logic.md#xnor-gate)
    - [Imply gate](Boolean%20Logic.md#imply-gate)
    - [Nimply gate](Boolean%20Logic.md#nimply-gate)
- [Bitwise Logic](Boolean%20Logic.md#bitwise-logic)
    - [Shift Operators](Boolean%20Logic.md#shift-operators--)

---

## Boolean Algebra

Boolean algebra is a mathematical system that represents and manipulates logical expressions. It is named after George Boole, who introduced the concept of Boolean algebra in the 19th century.

## Basic Definitions

In Boolean algebra, there are only two values: `True` and `False`. These values are represented by the digits `1` and `0`, respectively.

Boolean algebra operates on these values using logical operators. The three basic logical operators are:

- `AND`: The AND operator returns `True` if both operands are `True`, and `False` otherwise. It is represented by the symbol `&` or the word `AND`.  
  Traditionally it can also be represented as `x` or `*` (note that * doesn't mean multiplication of two numbers)
- `OR`: The OR operator returns `True` if either operand is `True`, and `False` otherwise. It is represented by the symbol `|` or the word `OR`.  
  Traditionally it can also be represented as `+` (note that + doesn't mean addition of two numbers)
- `NOT`: The NOT operator returns the opposite of its operand. If the operand is `True`, it returns `False`. If the operand is `False`, it returns `True`. It is represented by the symbol `!` or the word `NOT`.  
  Traditionally it can also be represented as `-` or `~` (note that - doesn't mean the negation of the number)

With these operations combined we can make all sorts of complex expressions that make up a computer. Yes a computer is just a really complicated series of logic expression.
One could argue that we as humans can also be represented by an even more complicated series of expresions

## Boolean Expressions

Boolean expressions are formed by combining Boolean values and logical operators. These expressions work like they would in basic math.  
For example, the expression `True AND False` is a Boolean expression that evaluates to `False`.

Boolean expressions can also include variables, which represent unknown Boolean values. For example, the expression `x AND y` is a Boolean expression that includes the variables `x` and `y`.

## Boolean Laws

There are several laws that hold for all Boolean expressions, regardless of the values of the variables. These laws can be used to simplify Boolean expressions by replacing them with equivalent expressions.

The simplest law is called double inversion. Having the `NOT` operator applied to another `NOT` operator is the same as not having them. For example, `NOT(NOT X)` is equivalent to `X`.

### Association and Distribuition

- `AND` and `OR` are associative, meaning that the order in which the operands are grouped does not affect the result.  
For example, `(x AND y) AND z` is equivalent to `x AND (y AND z)`.
- The `NOT` operator is distributive over `AND` and `OR`.  
For example, `NOT (x AND y)` is equivalent to `(NOT x) OR (NOT y)`.
- The `AND` operator has higher precedence than the `OR` operator, meaning that `AND` is evaluated before `OR`.  
For example, `x AND y OR z` is equivalent to `(x AND y) OR z`.

### Idempotent law

This law states that doing an operation with the same element will result in the same element.
- `X AND X` is equivalent to `X`
- `X OR X` is equivalent to `X`

### Absorvent and Neutral Elements

The absorvent element is an element that when operated with will absorve the result to be itself (independent of what the other input is).  
The absorvent element of AND operation is `0`. For example, `X AND 0` is equivalent to `0`.
The absorvent element of OR operation is `1`. For example, `X OR 1` is equivalent to `1`.

The neutral element is an element that when operated with will not interfear with the result (result will be the other input).  
The neutral element of AND operation is `1`. For example, `X AND 1` is equivalent to `X`.
The neutral element of OR operation is `0`. For example, `X OR 0` is equivalent to `X`.

### DeMorgan's laws

In terms of Boolean algebra, DeMorgan's laws state that:
- NOT(A OR B) = NOT A AND NOT B
- NOT(A AND B) = NOT A OR NOT B

These laws provide a way to simplify logical expressions by swapping conjunction for disjunction or vice versa.

---

## Logic Gates

Logic gates are the base of all circuits. They are the simplest form of logic, and each performs one logic operation.  
We use logic operations every day unconsciously. The names of those operations are the words we use in our speech.  
As long as you can do that logic operation using a circuit (doesn't have to use electricity) you have a logic gate, and you can build anything you would otherwise be able to with conventional circuits.
There are a bit more logic gates than the classical boolean operators meantioned above, but they are not required and can be replaced with combinations of those boolean operators. We however still include those to simplify our system.

### NOT Gate

The NOT gate produces an output of `1` if the input is `0`, and `0` otherwise.

### OR Gate

The NOR gate produces an output of `1` only if both of its inputs are `0`, and `0` otherwise.

### NOR Gate

The NOR gate is a combination of the OR and NOT gates. It produces an output of `1` only if both of its inputs are `0`, and `0` otherwise.

### AND Gate

The AND gate produces an output of `1` if any of its inputs are `0`, and `0` otherwise.

### NAND Gate

The NAND gate is a combination of the AND and NOT gates. It produces an output of `1` if any of its inputs are `0`, and `0` otherwise.

### XOR Gate

The XOR (exclusive OR) gate produces an output of `1` if its inputs are different, and `0` otherwise.

### XNOR Gate

The XNOR (exclusive NOR) gate is the opposite of the XOR gate. It produces an output of `1` if its inputs are the same, and `0` otherwise.

### Imply Gate
The imply gate (->) is a conditional logical operator that outputs a `1` if the input on the left is `0` or if the inputs on the left and right are the same and a `0` if the input on the left is `1` and the input on the right is `0`.  
`A -> B` is equivalent to `NOT(A) OR B`

### Nimply Gate
The nimply gate is the opposite of the imply gate. It outputs a `0` if the input on the left is `0` or if the inputs on the left and right are the same, and a `1` if the input on the left is `1` and the input on the right is `0`.

## Bitwise Logic

Bitwise operations are a set of operations that work on individual bits in a value. They are often used to manipulate values at a low level, such as for manipulation of individual bits in a data word.  
If we consider that each bit is a boolean value, then a bitwise operation is having the same boolean operation being applied to every bit of our binary represented number.

### AND (&)

The AND operator (&) performs a bitwise AND operation on two values. It compares each bit of the first value to the corresponding bit of the second value, and if both bits are `1`, the corresponding result bit is set to `1`. Otherwise, the corresponding result bit is set to `0`.

For example, the expression `5 & 3` performs a bitwise AND on the binary representations of the values `5` and `3`, as shown below:

```0101 & 0011 = 0001```

The result of the AND operation is the value `1`.

### OR (|)

The OR operator (|) performs a bitwise OR operation on two values. It compares each bit of the first value to the corresponding bit of the second value, and if either bit is `1`, the corresponding result bit is set to `1`. Otherwise, the corresponding result bit is set to `0`.

For example, the expression `5 | 3` performs a bitwise OR on the binary representations of the values `5` and `3`, as shown below:

```0101 | 0011 = 0111```

The result of the OR operation is the value `7`.

### XOR (^)

The XOR operator (^) performs a bitwise XOR (exclusive OR) operation on two values. It compares each bit of the first value to the corresponding bit of the second value, and if one but not both bits is `1`, the corresponding result bit is set to `1`. Otherwise, the corresponding result bit is set to `0`.

For example, the expression `5 ^ 3` performs a bitwise XOR on the binary representations of the values `5` and `3`, as shown below:

```0101 ^ 0011 = 0110```

The result of the XOR operation is the value `6`.

### NOT (~)

The NOT operator (~) performs a bitwise NOT operation on a value. It inverts each bit in the value, changing `1` to `0` and `0` to `1`.

For example, the expression `~5` performs a bitwise NOT on the binary representation of the value `5`, as shown below:

```~0101 = 1010```

The result of the NOT operation is the value `2`.

### Shift Operators (<<, >>)

The shift operators represented by `<<` `>>` dont have equivalent operations in boolean logic. Instead of performing a logical operation, they perform a bitwise shift of a value to the left or right, which means moving the binary representation of a number a certain number of bits to left/right. The left shift operator (<<) shifts the bits of a value to the left by the specified number of places, padding the right side with zeros. The right shift operator (>>) shifts the bits of a value to the right by the specified number of places, discarding the shifted bits.

For example, the expression `5 << 2` shifts the binary representation of the value `5` to the left by two places, as shown below:

```101 << 2 = 10100```

The result of the left shift operation is the value `20`.

For example, the expression `20 >> 2` shifts the binary representation of the value `20` to the right by two places, as shown below:

```10100 >> 2 = 101```

The result of the right shift operation is the value `5`.

The shift operation is of extreme importance because it's simple to perform, but it can really impact the kind of algorithms it can be used for.  
Look at this analogy in decimal. When asked the value of any number multiplied by 10, we can know instantly its result because it's just shifting our value! Tha same applies to dividing by 10, because it's just shifting the other way.
In binary the same applies, but 10 in binary is 2 so the trick works when multiplying by 2 or dividing by 2.  
By shifting by a certain amount you are actually multiplying or dividing by 2 the number of places you shift. So left shift by 3 places it's actually multiplying by 8. (You can go back to the previous examples and understand that this is the case)

---

## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Binary addition](Binary%20Addition.md#binary-addition)
