# Boolean Logic

---

## Prerequisites

- [Nothing](Boolean Logic#boolean-logic)

---

## Contents

Topics to be covered in this lesson:

- Boolean Algebra
    - Basic Definitions
    - Boolean Expressions
    - Boolean Laws
- Logic Gates
    - AND Gate
    - OR Gate
    - NOT Gate
    - NAND Gate
    - NOR Gate
    - XOR Gate
    - XNOR Gate

---

## Boolean Algebra

Boolean algebra is a mathematical system that represents and manipulates logical expressions. It is named after George Boole, who introduced the concept of Boolean algebra in the 19th century.

## Basic Definitions

In Boolean algebra, there are only two values: `True` and `False`. These values are represented by the digits `1` and `0`, respectively.

Boolean algebra operates on these values using logical operators. The three basic logical operators are:

- `AND`: The AND operator returns `True` if both operands are `True`, and `False` otherwise. It is represented by the symbol `&` or the word `AND`.  
  Traditionally it can also be represented as `+` (note that + doesn't mean addition of two numbers)
- `OR`: The OR operator returns `True` if either operand is `True`, and `False` otherwise. It is represented by the symbol `|` or the word `OR`.  
  Traditionally it can also be represented as `x` or `*` (note that * doesn't mean multiplication of two numbers)
- `NOT`: The NOT operator returns the opposite of its operand. If the operand is `True`, it returns `False`. If the operand is `False`, it returns `True`. It is represented by the symbol `!` or the word `NOT`.  
  Traditionally it can also be represented as `-` or `~` (note that - doesn't mean the negation of the number)

With these operations combined we can make all sorts of complex expressions that make up a computer. Yes a computer is just a really complicated series of logic expression.
One could argue that we as humans can also be represented by an even more complicated series of expresions

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

The shift operators (<< and >>) perform a bitwise shift of a value to the left or right. The left shift operator (<<) shifts the bits of a value to the left by the specified number of places, padding the right side with zeros. The right shift operator (>>) shifts the bits of a value to the right by the specified number of places, discarding the shifted bits.

For example, the expression `5 << 2` shifts the binary representation of the value `5` to the left by two places, as shown below:

```101 << 2 = 10100```

The result of the left shift operation is the value `20`.

For example, the expression `20 >> 2` shifts the binary representation of the value `20` to the right by two places, as shown below:

```10100 >> 2 = 101```

The result of the right shift operation is the value `5`.

---

## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Binary addition](Binary Addition#binary-addition)
