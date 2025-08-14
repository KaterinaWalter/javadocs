---
layout: notes
title: "📓1.3: Expressions & Output" 
parent: "1️⃣ Objects & Methods"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.3](https://runestone.academy/ns/books/published/csawesome2/topic-1-3-expressions.html) 

---

## Output (Printing)

Java has two different methods to print output to the screen:

- **`System.out.println(value)`** : prints the value _followed_ by a new line (`ln`)
- **`System.out.print(value)`** : prints the value without advancing to the next line

`System.out.println("Hi there!");` prints out the characters between the first `"` and the second `"` followed by a new line. `"Hi there!"` is called a **string literal**, which is zero to many characters enclosed in double quotes. 

<div class="task" markdown="block">

Type these lines in your program, run them, and note the output. Then modify them so the `!` prints on the **same line** as `Hi there` while keeping all three statements.

```java
System.out.print("Hi ");
System.out.println("there");
System.out.print("!");
````

</div>

### Escape Sequences
{:.no_toc}

What if you wanted to print out a double quote `"` character? Since the double quote is a _special character_ in Java, you need to put a backslash before it to “escape” it. This is called a **backslash escape sequence**. The same rule applies to printing a backslash itself, and `\n` is a special escape sequence for printing a newline.

<div class="task" markdown="block">

Type this line and run it to see escape sequences in action.

```java
String message = "Here is a backslash quote \" and a backslashed backslash (\\) "
               + "Backslash n \n prints out a new line.";
System.out.println(message);
```

</div>

---

## Expressions and Operators

**Arithmetic expressions** consist of numeric values, variables, and arithmetic operators that evaluate to a single numerical value. For example, `2 + 3` evaluates to 5.

Java uses:

* `+` (addition)
* `-` (subtraction)
* `*` (multiplication)
* `/` (division)

If both operands are integers, division will **truncate** (drop) the decimal part. If at least one operand is a double, the result will be a double.

<!--
The basic arithmetic operators of +, −, /, and * are similar to what students have experienced in math class or when using a calculator.  Have students come up with expressions using all 4 of the mathematical operators stated above. First round they should be using numbers only, second round, they should be using variables only and defining each variable.
Example:  Round 1:    4 + 4 / 3 - 6 * 4    Round 2: x = 4, y = 3 and x + x / y - 6 *x
Have the students simplify the expression by hand and then enter their expressions into a compiler and find an answer. Discuss how the answers are different and why.
-->

<div class="task" markdown="block">

Type and run each line of code below: 

```java
System.out.println(2 + 3);
System.out.println(2 - 3);
System.out.println(2 * 3);
System.out.println(2 / 3);
```

Notice what happened with `2 / 3`. Change it so it prints the decimal result by making at least one number a double (e.g., `2.0 / 3`).

</div>

**Mathematical errors** sometimes lead to runtime errors in code. 
> For example, when the Hubble Space Telescope was launched to space in 1990, a math error in a formula caused it to point in the wrong direction! It missed its target stars by about half a degree, which is about the width of the moon as seen from Earth.

<div class="task" markdown="block">

Fix the **logic error** so it correctly converts centimeters to inches (`1 inch = 2.54 cm`).

```java
System.out.print("100 centimeters in inches is: ");
System.out.println(100 * 2.54); 
```

</div>

### Compound Expressions

**Compound expressions** use multiple operators. 

<div class="important" markdown="block">
  
Java follows **operator precedence** (PEMDAS):
`*`, `/`, and `%` _compute before_ `+` and `-`, unless parentheses `( )` override it.

</div>

<br>

<div class="task" markdown="block">

Predict the output, then run:

```java
System.out.println(2 + 3 * 2);
System.out.println((2 + 3) * 2);
System.out.println(2 + (3 * 2));
```

</div>

### The Remainder `%` Operator

The `%` operator, sometimes called "modulo" or "modulus", returns the **remainder** after using _truncating integer division_. 

![image](Figures/mod-py.png)

> The left example shows `2 % 3` returns `2` and the right example shows shows `5 % 2` returns `1`. Remember when you first learned long division, before they taught you about decimals, how when you did a long division that didn’t divide evenly, you gave the answer as the _number of even divisions_ and the _remainder_. That **remainder** is what is returned by this operator.

<iframe width="700" height="415" src="https://www.youtube.com/embed/jp-T9lFISlI" frameborder="0" allowfullscreen></iframe>

<div class="task" markdown="block">

Predict the output, then run:

```java
System.out.println(11 % 10);
System.out.println(3 % 4);
System.out.println(8 % 2);
System.out.println(9 % 2);
```
> **Note:** If `x` is smaller than `y`, `x % y` is always `x`.

</div>


---

## Summary

* (AP 1.3.A.1) `System.out.print` and `System.out.println` display output.
* (AP 1.3.B.1) A **literal** is a fixed value in code.
* (AP 1.3.B.2) A **string literal** is text in double quotes.
* (AP 1.3.B.3) **Escape sequences** like `\"`, `\\`, and `\n` have special meaning in strings.
* (AP 1.3.C.1) **Arithmetic expressions** use numbers, variables, and operators.
* (AP 1.3.C.2) Operators: `+`, `-`, `*`, `/`, `%`.
* (AP 1.3.C.3) Integer division truncates; use a double for decimal results.
* (AP 1.3.C.4) `%` gives the remainder.
* (AP 1.3.C.5) Compound expressions follow operator precedence.
* (AP 1.3.C.6) Integer division by zero causes an `ArithmeticException`.

---

<!-- 
## AP Practice

<div class="task" markdown="block">

**Multiple Choice**
What is printed?

```java
System.out.print("Java is ");
System.out.println("fun ");
System.out.print("and cool!");
```

✅ Correct:

```
Java is fun
and cool!
```

</div>

<div class="task" markdown="block">

**Multiple Choice**
What does this print?

```java
System.out.println(5 + 5 / 2 * 3 - 1);
```

✅ Correct: `10` — Equivalent to `(5 + ((5 / 2) * 3) - 1)` with truncating integer division.

</div>
-->

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
