---
layout: notes
title: "📓1.5: Casting" 
parent: "1️⃣ Objects & Methods"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.5](https://runestone.academy/ns/books/published/csawesome2/topic-1-5-casting.html) 

---

## Casting

In Java, **type casting** is used to convert values from one type to another. By **casting** we’re “reshaping” the value’s type, similar to reshaping metal during bronze casting—just without the heat.

![Figure 1: Bronze casting changes the shape of the metal.](Figures/bronze-casting.jpg)

The **cast operator** is written in parentheses before an expression, e.g., `(int)` or `(double)`. It _converts_ the expression’s value to the given type.

- `(double) 1 / 3` → `0.33333333` (a `double`)
- `(int) 3.6` → `3` (truncates to an `int`)
- Casting an `int` to `double` adds `.0` (e.g., `3` → `3.0`)
- Casting a `double` to `int` **truncates** the decimal part

<div class="task" markdown="block">

Type these in your program, run, and observe. Then **add one more line** that divides `5` by `2` using a `(double)` cast.

```java
System.out.println(3 / 4);          // int / int
System.out.println(3.0 / 4);        // double / int
System.out.println(3 / 4.0);        // int / double
System.out.println((double) 3 / 4); // cast int to double, then divide
System.out.println((int) 3.0 / 4);  // cast double to int, then divide
// TODO: add a line that divides 5 by 2 using (double) and prints 2.5
````

</div>

When Java divides two `int`s, the result is an `int` with the decimal part **truncated** (not rounded). So `9 / 10` is `0`. In any expression involving a `double`, the result is a `double`. For example, `9.0 / 10` evaluates to `0.9`. This automatic widening from `int` to `double` is sometimes called **contagious**: `double` “wins”.

Casting an `int` to `double` forces a `double` result in mixed expressions—handy when you want non-integer division:

```java
int total; // sum of ints
int count; // how many ints
double average = (double) total / count;
```

A conversion from `int` to `double` is a **widening conversion** (every `int` fits in a `double`).

> **Note:**
> `int`s are always 32-bit signed: from `-2^31` to `2^31 - 1`.
> `Integer.MIN_VALUE` and `Integer.MAX_VALUE` hold these limits.
> Doubles represent wider ranges and can exactly represent consecutive integers up to `±2^53`.

### Rounding by Casting

Values of type ``double`` in the range that can be represented by an ``int`` can
be **rounded** to the nearest ``int`` by adding or subtracting 0.5 and then casting
the result with ``(int)``:

```java
double number;    // positive value from somewhere
double negNumber; // negative value from somewhere

int nearestInt = (int)(number + 0.5);
int nearestNegInt = (int)(negNumber – 0.5);
```

> For example, if you divide ``7.0 / 4.0`` you get ``1.75``. If you cast that to
an ``int``, it will be truncated to ``1``.
> 
> However if we want to round a ``double`` rather than truncating it, adding ``0.5`` will produce a number that
is above the next integer value if the decimal part is greater than ``0.5``, as
it is here. Then casting *that* value to an ``int`` will truncate down.

---

## Range of Values

What about repeating decimals like `3.333333...`? Java `double` values keep about **14–15 significant digits**; beyond that, the number is rounded.

`int` values are stored in **4 bytes** (32 bits).

* Largest `int`: `Integer.MAX_VALUE` → `2147483647`
* Smallest `int`: `Integer.MIN_VALUE` → `-2147483648`

Storing a number outside this range causes an **integer overflow** (compile-time error for too-large literals, or wrap-around for operations). Try it:

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
This literal is too big for `int` and won’t compile. **Fix** it by deleting the last `0` in each number so it compiles and runs.

```java
int id = 2147483650;       // overflow: literal too large
int negative = -2147483650; // overflow: literal too large
System.out.println(id);
System.out.println(negative);
```

</div>

Computers allot a fixed memory size per type. `double` uses **8 bytes** (twice `int`), but precision is still finite. If an expression needs more precision than fits, you get **round-off error**. For example, `2.0/3` prints as approximately `0.6666666666666666`. You can format output to a limited number of decimal places.

<div class="task" markdown="block">

Format a decimal to 2 digits using `printf`:

```java
double number = 10.0 / 3;
System.out.println("Number cut off after 15 digits: " + number);
System.out.println("Number as an int: " + (int) number);
System.out.printf("Formatted number: %.2f", number);
System.out.printf("\nFormatted number: $%.2f\n", number);

// TODO: print 2.0/3 formatted to 2 decimal places
```

</div>


### Coding Challenge: Average 3 Numbers

Work in pairs and switch drivers often. Type three made-up `int` grades, compute the **sum** and **average**, and **cast** to ensure the average is a `double`.

<div class="task" markdown="block">

**Pseudocode steps:**

1. Declare `int grade1, grade2, grade3` and **initialize** them.
2. Declare `int sum`.
3. Declare `double average`.
4. Set `sum` to the total of the three grades.
5. Set `average` to the sum divided by 3 — use **casting** so it’s a `double`.
6. Print the average.

**Starter (write in your file):**

```java
// 1) declare and initialize grades
// int grade1 = ...;
// int grade2 = ...;
// int grade3 = ...;

// 2) declare sum
// int sum;

// 3) declare average as double
// double average;

// 4) compute sum
// sum = grade1 + grade2 + grade3;

// 5) compute average with casting
// average = (double) sum / 3;

// 6) print result
// System.out.println(average);
```

</div>

### Bonus Challenge: Unicode

Java uses **Unicode** for characters (not on the AP exam, but fun!). Many code points (especially emoji) don’t fit in a `char`. Use an `int` code point with `Character.toString(codePoint)` to build a `String`.

<div class="task" markdown="block">

Print characters from different languages and an emoji. Then look up more code points (decimal) and print them.

```java
System.out.println("'A' in ASCII and Unicode: " + Character.toString(65));
System.out.println("Chinese for 'sun': " + Character.toString(11932));
System.out.println("A smiley emoji: " + Character.toString(128512));

// Old style (char) may fail for many code points:
System.out.println("This also works: " + (char) 65);
// System.out.println("But this doesn't: " + (char) 128512); // not reliable

// TODO: print letters from 3 different languages using Character.toString(<decimal code point>)
```

</div>

---

## Summary

- **Type casting** is used to convert a value from one type to another.

- (AP 1.5.A.1) The casting operators ``(int)`` and ``(double)`` can be used to convert from a double value to an int value (or vice versa).

- (AP 1.5.A.2) Casting a ``double`` value to an ``int`` causes the digits to the right of the
  decimal point to be truncated (cut off and thrown away).

- (AP 1.5.A.3) Some code causes int values to be automatically cast (widened) to double values. In expressions involving ``double``\ s, the ``double`` values are contagious,
  causing ``int``\ s in the expression to be automatically converted ("widened") to the
  equivalent ``double`` value so the result of the expression can be computed as
  a ``double``.

- (AP 1.5.A.4) Values of type ``double`` can be rounded to the nearest integer by (int)(x +
  0.5) or (int)(x – 0.5) for negative numbers.

- (AP 1.5.B.1) The constant ``Integer.MAX_VALUE`` holds the value of the largest possible int value. The constant ``Integer.MIN_VALUE`` holds the value of the smallest possible int value.

- (AP 1.5.B.2) Integer values in Java are represented by values of type ``int``, which are
  stored using a finite amount (4 bytes) of memory. Therefore, an int value must
  be in the range from ``Integer.MIN_VALUE`` to ``Integer.MAX_VALUE``,
  inclusive. 

- (AP 1.5.B.3) If an expression would evaluate to an int value outside of the allowed range,
  an **integer overflow** occurs. The result is an int value in the allowed range but not necessarily the value expected.

- (AP 1.5.C.1) Computers allot a specified amount of memory to store data based on the data type. If an expression would evaluate to a double that is more precise than can be stored in the allotted amount of memory, a **round-off error** occurs. The result will be rounded to the representable value. To avoid rounding errors that naturally occur, use int values or round doubles to the precision needed. 

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
