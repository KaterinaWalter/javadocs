---
layout: notes
title: "📓2.12: Loop Runtime Analysis" 
parent: "2️⃣ Selection & Iteration"
nav_order: 12
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.12]() 

---

## Informal Runtime Analysis of Loops

When we analyze loops informally, we focus on two skills:

* **Tracing**: Step through a loop and keep track of variable values as they change.
* **Counting iterations**: Determine how many times a loop (or nested loops) will execute its body.

These skills help you predict output, find bugs, and reason about runtime at a high level.

**Note:** A **trace table** is a simple table where each column is a variable and each row shows the values after each pass through the loop.

---

## Example 1: Trace a `while` Loop

Consider the following code. Trace it and record the values of `var1` and `var2` each time through the loop.

```java
int var1 = 0;
int var2 = 2;

while ((var2 != 0) && ((var1 / var2) >= 0)) {
    var1 = var1 + 1;
    var2 = var2 - 1;
}
```

![Trace table showing var1 and var2 values each pass](Figures/whileLoopTrace.png)

<div class="task" markdown="block">

**Check Your Understanding**

What are the values of `var1` and `var2` when the code finishes executing?

* A. `var1 = 1, var2 = 1`
* B. `var1 = 2, var2 = 0` ✅
* C. `var1 = 3, var2 = -1`
* D. `var1 = 0, var2 = 2`
* E. Division-by-zero runtime error

**Why:** The loop stops when `var2 == 0` (short-circuiting prevents the division from evaluating when `var2` is 0), so the final state is `var1 = 2`, `var2 = 0`.

</div>

---

## Example 2: Build a Trace Table

You can make tracing easier by drawing a table:

|    Pass # | var1 | var2 |
| --------: | ---: | ---: |
| 0 (start) |    0 |    2 |
|         1 |    1 |    1 |
|         2 |    2 |    0 |

Stop when the loop condition becomes `false`.

---

## Counting Loop Iterations

### Single `for` or `while`

* A loop like `for (int i = 0; i < N; i++)` runs **N** times.
* A loop like `while (x > 0) { x--; }` runs once per decrement until `x == 0`.

### Nested Loops

Multiply the number of iterations of each loop if the inner loop runs fully for each outer iteration.

```java
int i = 0;
while (i <= 4) {
  for (int j = 0; j < 3; j++) {
    System.out.println("Hi!");
  }
  i++;
}
```

* Outer loop: `i = 0, 1, 2, 3, 4` → **5** iterations
* Inner loop: `j = 0, 1, 2` → **3** iterations each time
* Total prints: **5 × 3 = 15**

<div class="task" markdown="block">

**Check Your Understanding**

How many times is `"Hi!"` printed by the program above?

* A. 3
* B. 5
* C. 8
* D. 12
* E. 15 ✅

</div>

---

## Tips for Informal Analysis

* **Initialization, condition, update**: Check all three—off-by-one errors often hide here.
* **Short-circuit logic**: For `&&` and `||`, later subexpressions may not evaluate—this can prevent errors (like division by zero) or change counts.
* **Early exits**: `break`, `return`, or condition changes inside the loop alter iteration counts.
* **State changes**: Make sure the loop variable actually changes so you don’t create an infinite loop.

---

## Practice: Write and Trace

<div class="task" markdown="block">

1. Write a loop that prints the first `N` multiples of 7 on one line.
2. Create a trace table for `sum` and `i` in the loop below. Predict and then run.

```java
int sum = 0;
for (int i = 1; i <= 4; i++) {
    sum += i;       // add i to sum
}
System.out.println(sum);
```

</div>

---

## Summary

* Use **trace tables** to follow variable changes through loop iterations.
* Count iterations by examining **initialization**, **condition**, and **update**.
* For **nested loops**, multiply iteration counts when appropriate.
* Be mindful of **short-circuit evaluation** and **early exits** that affect execution.

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
