---
layout: notes
title: "📓2.9: Implementing Selection & Iteration Algorithms" 
parent: "2️⃣ Selection & Iteration"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.9](https://runestone.academy/ns/books/published/csawesome2/topic-2-9-loop-algorithms.html) 

---


Loops are not just for counting — they can perform many common algorithmic patterns, such as accumulating totals, finding maximums, or searching for a value.


## Accumulator Pattern

An **accumulator** keeps a running total as the loop iterates.

<div class="task" markdown="block">

**Coding Exercise: Sum 1 to 5**

```java
int sum = 0;

for (int i = 1; i <= 5; i++) {
    sum = sum + i;
}

System.out.println("Sum is " + sum);
````

</div>

---

## Counter Pattern

A **counter** counts how many times something happens.

<div class="task" markdown="block">

**Coding Exercise: Count Even Numbers**

```java
int count = 0;

for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        count++;
    }
}

System.out.println("Number of even integers: " + count);
```

</div>

---

## Finding the Maximum

<div class="task" markdown="block">

**Coding Exercise: Largest Number in Array**

```java
int[] nums = {5, 9, 2, 7, 3};
int max = nums[0];

for (int i = 1; i < nums.length; i++) {
    if (nums[i] > max) {
        max = nums[i];
    }
}

System.out.println("Max is " + max);
```

</div>

---

## Searching for a Value

<div class="task" markdown="block">

**Coding Exercise: Search Array for Target**

```java
int[] nums = {3, 6, 9, 12};
int target = 9;
boolean found = false;

for (int i = 0; i < nums.length; i++) {
    if (nums[i] == target) {
        found = true;
    }
}

System.out.println("Found? " + found);
```

</div>

---

## Summary

* **Accumulator**: running total.
* **Counter**: counts matches.
* **Maximum finder**: tracks largest value.
* **Search**: checks for target presence.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

What will this print?

```java
int sum = 0;
for (int i = 0; i < 4; i++) {
    sum += i;
}
System.out.println(sum);
```

**Answer:** `6` — because `0 + 1 + 2 + 3 = 6`.

</details>

<details>
<summary><strong>Question 2</strong></summary>

What does this code do?

```java
int count = 0;
for (int i = 1; i <= 10; i++) {
    if (i % 2 != 0) {
        count++;
    }
}
System.out.println(count);
```

**Answer:** Counts the odd numbers from 1 to 10, so it prints `5`.

</details>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
