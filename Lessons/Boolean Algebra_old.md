# Boolean Algebra

---

## Prerequisites

- [Logic Gates](Logic Gates#logic-gates)

---

## Contents

Topics to be covered in this lesson:

- Basic Definitions
- Boolean Expressions
- Boolean Laws

---

## Basic Definitions

In Boolean algebra, there are only two values: `True` and `False`. These values are represented by the digits `1` and `0`, respectively.

Boolean algebra operates on these values using logical operators. The three basic logical operators are:

- `AND`: The AND operator returns `True` if both operands are `True`, and `False` otherwise. It is represented by the symbol `&` or the word `AND`.  
Traditionally it can also be represented as `+` (note that + doesn't mean addition of two numbers)
- `OR`: The OR operator returns `True` if either operand is `True`, and `False` otherwise. It is represented by the symbol `|` or the word `OR`.  
Traditionally it can also be represented as `x` or `*` (note that * doesn't mean multiplication of two numbers)
- `NOT`: The NOT operator returns the opposite of its operand. If the operand is `True`, it returns `False`. If the operand is `False`, it returns `True`. It is represented by the symbol `!` or the word `NOT`.  
Traditionally it can also be represented as `-` or `~` (note that - doesn't mean the negation of the number)

## Boolean Expressions

Boolean expressions are formed by combining Boolean values and logical operators. These expressions work like they would in basic math.  
For example, the expression `True AND False` is a Boolean expression that evaluates to `False`.

Boolean expressions can also include variables, which represent unknown Boolean values. For example, the expression `x AND y` is a Boolean expression that includes the variables `x` and `y`.

## Boolean Laws

There are several laws that hold for all Boolean expressions, regardless of the values of the variables. These laws can be used to simplify Boolean expressions by replacing them with equivalent expressions.

Here are a few examples of Boolean laws:

- `AND` and `OR` are associative, meaning that the order in which the operands are grouped does not affect the result. For example, `(x AND y) AND z` is equivalent to `x AND (y AND z)`.
- The `NOT` operator is distributive over `AND` and `OR`. For example, `NOT (x AND y)` is equivalent to `(NOT x) OR (NOT y)`.
- The `AND` operator has higher precedence than the `OR` operator, meaning that `AND` is evaluated before `OR`. For example, `x AND y OR z` is equivalent to `(x AND y) OR z`.

---

## What Now?

This lesson is over, however here is a list of topics recommended learning next:

- [Bitwise Operations](Bitwise Operations#bitwise-operations)
- [Binary addition](Binary Addition#binary-addition)
