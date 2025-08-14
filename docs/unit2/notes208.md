---
layout: notes
title: "📓2.8: for Loops" 
parent: "2️⃣ Selection & Iteration"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.8](https://runestone.academy/ns/books/published/csawesome2/topic-2-8-for-loops.html) 

---


## For Loops

A `for` loop is a **count-controlled loop** — it runs a set number of times. In Java, a `for` loop has three parts inside parentheses:

```java
for (initialization; condition; update) {
    // loop body
}
````

1. **Initialization** – runs once at the start (e.g., `int i = 0`)
2. **Condition** – checked before each iteration; if false, the loop stops
3. **Update** – changes the loop control variable each time

---

## Example: Counting Up

<div class="task" markdown="block">

**Coding Exercise: Count from 1 to 5**

Type this in your Codespace and run it.

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

</div>

---

## Example: Counting Down

<div class="task" markdown="block">

**Coding Exercise: Countdown**

```java
for (int i = 5; i > 0; i--) {
    System.out.println(i);
}
System.out.println("Blastoff!");
```

</div>

---

## Using Loops with Arrays

<div class="task" markdown="block">

**Coding Exercise: Print an Array**

```java
int[] nums = {2, 4, 6, 8};

for (int i = 0; i < nums.length; i++) {
    System.out.println(nums[i]);
}
```

</div>

---

## Choosing While vs. For

* Use a `for` loop when you know exactly how many times to repeat.
* Use a `while` loop when repetition depends on a condition.

---

## Summary

* `for` loops combine initialization, condition, and update in one line.
* Ideal for counting a fixed number of times.
* Loop variable changes each iteration until the condition is false.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

What does this loop print?

```java
for (int i = 0; i < 3; i++) {
    System.out.print(i + " ");
}
```

**Answer:** `0 1 2` — i starts at 0, increments to 2, stops at 3.

</details>

<details>
<summary><strong>Question 2</strong></summary>

Which loop is equivalent to:

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

**Answer:**

```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

</details>



---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
