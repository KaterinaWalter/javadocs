---
layout: notes
title: "📓1.11: The Math Class" 
parent: "1️⃣ Objects & Methods"
nav_order: 12
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.11](https://runestone.academy/ns/books/published/csawesome2/topic-1-11-Math.html) 

---

Games would be boring if the same thing happened each time you played the game. **Random** numbers can be used in games to generate different outcomes each time the game is played. In Java, the `Math.random()` method is used to generate a random number.

There are lots of mathematical methods in the `Math` class that you might want to use in your programs, like `Math.pow(2,3)` which calculates 2 to the power of 3, which is 8.

The `Math` class is part of the `java.lang` package. Classes in the `java.lang` package are available by default. The `Math` methods are **class methods** (or **static** methods) which means you can call them by just using `ClassName.methodName()`.

---

## Mathematical Functions

[**AP CSA Java Quick Reference Sheet**](https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf)  
[**Math Class Javadocs**](https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html)

The `Math` class contains the following methods that are in the AP CSA subset:

- `int abs(int)` → Absolute value of an int
- `double abs(double)` → Absolute value of a double
- `double pow(double, double)` → First parameter raised to the power of the second
- `double sqrt(double)` → Positive square root of a double
- `double random()` → Double between 0.0 (inclusive) and 1.0 (exclusive)

Example:

```java
System.out.println(Math.abs(-4));     // 4
System.out.println(Math.sqrt(9));     // 3.0
System.out.println(Math.pow(3, 2));   // 9.0
````

---

<div class="task" markdown="block">

**Try It — Using `Math` Methods**

Type this in your Codespace, press **Run**, and modify it so that it:

1. Computes the absolute value of `-4`
2. Computes the square root of `9`
3. Computes `3` raised to the power of `2`

```java
System.out.println(Math.abs(-2));
System.out.println(Math.sqrt(4));
System.out.println(Math.pow(2, 3));
```

</div>

---

## Random Numbers

The `Math.random()` method returns a double between 0 (inclusive) and 1 (exclusive).

Example:

```java
System.out.println(Math.random());
System.out.println(Math.random());
```

---

<div class="task" markdown="block">

**Try It — Stretching Random Numbers**

Type this in your Codespace, press **Run**, and observe the range of values.

```java
System.out.println(Math.random() * 10);
System.out.println(Math.random() * 10);
```

</div>

---

### Casting to Integers

```java
// rnd is an integer in the range 0–9
int rnd = (int)(Math.random() * 10);

// rnd is an integer in the range 1–10
int rnd2 = (int)(Math.random() * 10) + 1;
```

---

<div class="task" markdown="block">

**Try It — Random Integer from 1 to 10**

Type this in your Codespace, press **Run**, and change the code so it returns a random integer from 1 to 10.

```java
System.out.println((int)(Math.random() * 10));
```

</div>

---

## Coding Challenge — Random Numbers

You have a combination lock with 3 numbers from 0 up to 40 (exclusive).

1. Use `Math.random()` to generate and print 3 integers in that range.
2. Use `Math.pow()` to compute the total number of possible combinations.

---

<div class="task" markdown="block">

**Challenge: Combination Lock Generator**

Type this in your Codespace, press **Run**, and complete the TODOs.

```java
// 1. Generate 3 integers from 0–39 using Math.random() and print them
// 2. Calculate 40^3 using Math.pow() and print the result
```

</div>

---

## Bonus Challenge — Dancing Turtles

Using `Math.random()`, make a turtle move to random (x, y) coordinates and change to random colors (0–255 RGB values) 10 times.

---

<div class="task" markdown="block">

**Challenge: Random Dancing Turtle**

Type this in your Codespace (with the turtle graphics library), press **Run**, and complete the TODOs.

```java
// Loop 10 times:
// 1. Choose random x from 20 to 480
// 2. Choose random y from 20 to 380
// 3. Move turtle to (x, y)
// 4. Choose random RGB color values (0–255)
// 5. Set turtle color
```

</div>

---

## Summary

* **`Math` is in `java.lang`** — no import needed.
* All methods are **static** and called with `Math.methodName()`.
* AP subset: `abs(int)`, `abs(double)`, `pow(double,double)`, `sqrt(double)`, `random()`.
* `(int)(Math.random() * range) + min` → random int in a range.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
