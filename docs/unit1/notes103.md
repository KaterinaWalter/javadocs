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
📖 This page is a condensed version of [CSAwesome Lesson 1.3](https://runestone.academy/ns/books/published/csawesome2/topic-1-3-expressions.html) 

---

## Output

Java has two different methods to print output to the screen:

- **`System.out.println(value)`** : prints the value followed by a new line (`ln`)
- **`System.out.print(value)`** : prints the value without advancing to the next line

`System.out.println("Hi there!");` prints out the characters between the first `"` and the second `"` followed by a new line. `"Hi there!"` is called a **string literal**, which is zero to many characters enclosed in double quotes. A **literal** is the code representation of a fixed value, which can be a string or a numerical value.

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**  
Type these lines in your program, run them, and note the output. Then modify them so the `!` prints on the same line as `Hi there` while keeping all three statements.

```java
System.out.print("Hi ");
System.out.println("there");
System.out.print("!");
````

</div>

---

What if you wanted to print out a double quote `"` character? Since the double quote is a special character in Java, you need to put a backslash before it to “escape” it. This is called a **backslash escape sequence**. The same rule applies to printing a backslash itself, and `\n` is a special escape sequence for printing a newline.

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
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

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
Type and run the code below. Notice what happens with `2 / 3`. Then change it so it prints the decimal result by making at least one number a double (e.g., `2.0 / 3`).

```java
System.out.println(2 + 3);
System.out.println(2 - 3);
System.out.println(2 * 3);
System.out.println(2 / 3);
```

</div>

---

Math errors can cause runtime problems. For example, this conversion from centimeters to inches has a **logic error** — it multiplies instead of divides.

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
Fix this so it correctly converts centimeters to inches (`1 inch = 2.54 cm`).

```java
System.out.print("100 centimeters in inches is: ");
System.out.println(100 * 2.54);  // wrong, fix to divide
```

</div>

---

## Compound Expressions

Compound expressions use multiple operators. Java follows **operator precedence** (PEMDAS):
`*`, `/`, and `%` before `+` and `-`, unless parentheses override it.

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
Predict the output, then run:

```java
System.out.println(2 + 3 * 2);
System.out.println((2 + 3) * 2);
System.out.println(2 + (3 * 2));
```

</div>

---

## The Remainder Operator

The `%` operator returns the **remainder** after integer division. Example: `5 % 2` is `1`.

<iframe width="700" height="415" src="https://www.youtube.com/embed/jp-T9lFISlI" frameborder="0" allowfullscreen></iframe>

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
Predict the output, then run:

```java
System.out.println(11 % 10);
System.out.println(3 % 4);
System.out.println(8 % 2);
System.out.println(9 % 2);
```

</div>

> **Note:** If `x` is smaller than `y`, `x % y` is always `x`.

<div class="task" markdown="block">

**Check Your Understanding**
What is the result of `158 % 10`?
What is the result of `3 % 8`?

</div>

---

## Groupwork: Coding Challenge — Pay Calculator

Work with a partner to complete a pay calculator using math expressions and operators.

<div class="task" markdown="block">

**Coding Challenge (Codespaces)**
Fill in the operators or expressions where indicated.

```java
System.out.println("Pay for 4 hours of work at 10 dollars an hour");
System.out.println(4  10);   // fill in operator

System.out.println("Number of hours worked for pay 120 dollars & rate 15 dollars/hour");
System.out.println(120  15); // fill in operator

System.out.println("Pay for 12 hours of work at 7.50 dollars an hour");
System.out.println(        ); // fill in expression

System.out.println("Number of int hours worked for pay 100 dollars & rate 9 dollars/hour");
// add expression

System.out.println("The remainder of 100 dollars divided by 9 dollars/hour");
// add expression
```

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


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
