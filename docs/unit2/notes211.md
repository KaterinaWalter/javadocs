---
layout: notes
title: "📓2.11: Nested Iteration" 
parent: "2️⃣ Selection & Iteration"
nav_order: 11
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.11]() 

---

## Nested Loops

A **nested loop** is a loop inside another loop. The inner loop will run completely every time the outer loop runs once.


### Example: Multiplication Table

<div class="task" markdown="block">

**Coding Exercise: Print a multiplication table**

```java
for (int row = 1; row <= 3; row++) {
    for (int col = 1; col <= 3; col++) {
        System.out.print((row * col) + "\t");
    }
    System.out.println();
}
````

</div>

---

## Understanding Execution

* The **outer loop** controls the rows.
* The **inner loop** controls the columns.
* For each row, the inner loop runs all its iterations before the next row starts.

---

## Example: Pattern Printing

<div class="task" markdown="block">

**Coding Exercise: Print a triangle of `*`**

```java
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

</div>

---

## Example: Nested While Loops

<div class="task" markdown="block">

**Coding Exercise: Coordinate Pairs**

```java
int i = 1;
while (i <= 2) {
    int j = 1;
    while (j <= 3) {
        System.out.println("(" + i + ", " + j + ")");
        j++;
    }
    i++;
}
```

</div>

---

## Summary

* The inner loop runs completely for each iteration of the outer loop.
* Nested loops are useful for working with grids, patterns, or multi-dimensional data.
* Be careful — nested loops can increase run time quickly.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

How many times will `System.out.println("*")` execute?

```java
for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 3; j++) {
        System.out.println("*");
    }
}
```

**Answer:** `12` — 4 outer loop iterations × 3 inner loop iterations.

</details>

<details>
<summary><strong>Question 2</strong></summary>

What does this print?

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 2; j++) {
        System.out.print(i + "-" + j + " ");
    }
}
```

**Answer:** `1-1 1-2 2-1 2-2 3-1 3-2`

</details>

---

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Type a brief **commit message** in the box, for example: `updated Main.java`
3. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
4. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
5. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
