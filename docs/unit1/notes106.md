---
layout: notes
title: "📓1.6: Compound Assignment Operators" 
parent: "1️⃣ Objects & Methods"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.6]() 

---

## Compound Assignment Operators 

Compound assignment operators `+=`, `-=`, `*=`, `/=`, and `%=` are shortcuts that do a math operation **and** an assignment in one step.  
For example, `x += 1` adds 1 to `x` and stores the result back in `x` (same as `x = x + 1`).

{:.highlight}
_If a mnemonic helps:_ the **operator** happens first, then the result is **assigned** back. So it’s `+=` (not `=+`).

Since changing a variable by 1 is so common, Java also has `++` (increment) and `--` (decrement).  
- `x++` is even shorter than `x += 1` or `x = x + 1`.  
- `y--` is the same idea for subtracting 1.

### Operator shortcuts

| Meaning        | Written out      | Compound | Extra concise |
|---|---|---|---|
| add            | `x = x + 1`      | `x += 1` | `x++` |
| subtract       | `x = x - 1`      | `x -= 1` | `x--` |
| multiply       | `x = x * 2`      | `x *= 2` | — |
| divide         | `x = x / 2`      | `x /= 2` | — |
| remainder      | `x = x % 2`      | `x %= 2` | — |

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**  
Type these lines, run, and observe. Then complete the two TODOs.

```java
int score = 0;
System.out.println(score); // 0

score++;                   // +1
System.out.println(score); // 1

score *= 2;                // ×2
System.out.println(score); // 2

int penalty = 5;
score -= penalty / 2;      // 2 - (5/2) -> 2 - 2 -> 0 (integer division)
System.out.println(score); // 0

// 1) Add 3 to score using a compound operator
// score ...

// 2) Divide score by 2 using a compound operator
// score ...
````

</div>

> **Note on `++x` vs `x++` (FYI only):**
> You might see the prefix form (`++x`) in real code. AP CSA won’t require it.
>
> * **Postfix** (`x++`): use the current value, then increment.
> * **Prefix** (`++x`): increment first, then use the value.

---

## Check Your Understanding

<div class="task" markdown="block">

**Trace the variables**
What are the values of `x`, `y`, and `z` after this code?

```java
int x = 0;
int y = 1;
int z = 2;
x--;
y++;
z += y;
```

Choices:
A) x = -1, y = 1, z = 4
B) x = -1, y = 2, z = 3
C) x = -1, y = 2, z = 2
D) x = 0,  y = 1, z = 2
E) **x = -1, y = 2, z = 4** ✅

</div>

<div class="task" markdown="block">

**Trace the variables**
What are the values of `x`, `y`, and `z` after this code?

```java
int x = 3;
int y = 5;
int z = 2;
x = z * 2;
y = y / 2;
z++;
```

Choices:
A) x = 6, y = 2.5, z = 2
B) x = 4, y = 2.5, z = 2
C) x = 6, y = 2,   z = 3
D) x = 4, y = 2.5, z = 3
E) **x = 4, y = 2, z = 3** ✅

</div>

---

## Groupwork: Code Tracing Challenge and Operators Maze

**Code tracing** means simulating a dry run through the program line by line, as if you are the computer.

Use a trace table to track variable values as they change.

Trace this code:

```java
int x = 0;
int y = 5;
int z = 1;
x++;
y -= 3;
z = x + z;
x = y * z;
y %= 2;
z--;
```

<div class="task" markdown="block">

**Write your trace**
Create a trace table (or bullet list) showing the values of `x`, `y`, and `z` after each line.

</div>

Afterward, try the **Operators Maze game**: <a href="https://docs.google.com/document/d/1ZjA8oKeo8FYx2nXX4OOq5lUihopIQQ_HY-eoE5yZkk8/edit?usp=sharing" target="_blank" style="text-decoration:underline">Operators Maze game</a>.

---

## Summary

* (AP 1.6.A.1) **Compound assignment** (`+=`, `-=`, `*=`, `/=`, `%=`) performs the operation using the current value on the left and the value on the right, then assigns the result back to the left variable.
* (AP 1.6.A.2) **Increment** (`++`) and **decrement** (`--`) add or subtract 1 from a numeric variable and store the new value.

---

## Review/Practice for Unit 1 Part 1

**Time: \~90 minutes**

You can now do the following review and practice lessons and the College Board Progress Check for Unit 1 Part 1:

* <a href="unit1a-summary.html" target="_blank">Unit 1a Summary</a>
* <a href="unit1a-practice-mixed-code.html" target="_blank">Unit 1a Practice</a>
* <a href="unit1a-practice-mixed-code-toggle.html" target="_blank">Unit 1a Practice Toggle</a>
* <a href="unit1a-practice-coding.html" target="_blank">Unit 1a Practice Coding</a>
* <a href="Exercises.html" target="_blank">Exercises</a>


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
