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
📖 This page is a condensed version of [CSAwesome Topic 1.6](https://runestone.academy/ns/books/published/csawesome2/topic-1-6-compound-operators.html) 

---

## Compound Assignment Operators 

<div class="task" markdown="block">

💬 As a class, brainstorm some examples of how people use **shortcuts**.
  
</div>

Compound assignment operators `+=`, `-=`, `*=`, `/=`, and `%=` are shortcuts that do a math operation **and** an assignment in one step.  
> For example, `x += 1` adds 1 to `x` and stores the result back in `x` (same as `x = x + 1`).

{:.highlight}
_If a mnemonic helps:_ the **operator** happens first, then the result is **assigned** back. So it’s `+=` (not `=+`).

Since changing a variable by 1 is so common, Java also has `++` (_increment_) and `--` (_decrement_) extra concise operator.  
- `x++` is even shorter than `x += 1` or `x = x + 1`.  
- `y--` is the same idea for subtracting 1.

### Operator Shortcuts

| Meaning        | Written out      | Compound | Extra Concise |
|---|---|---|---|
| add            | `x = x + 1`      | `x += 1` | `x++` |
| subtract       | `x = x - 1`      | `x -= 1` | `x--` |
| multiply       | `x = x * 2`      | `x *= 2` | — |
| divide         | `x = x / 2`      | `x /= 2` | — |
| remainder      | `x = x % 2`      | `x %= 2` | — |

<div class="task" markdown="block">

Type each of these lines, run, and observe. Then complete the two TODOs.

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
```

</div>

#### Code Tracing

**Code tracing** means simulating a run through the program line by line, as if you are the computer. 

Use a trace table (or bullet points) to _track variable values_ as they change and **predict** output.

<div class="task" markdown="block">

🔮 **Predict:** What are the values of `x`, `y`, and `z` after this code?

```java
int x = 0;
int y = 1;
int z = 2;
x--;
y++;
z += y;
```

</div>

<br>

<div class="task" markdown="block">

🔮 **Predict:** What are the values of `x`, `y`, and `z` after this code?

```java
int x = 3;
int y = 5;
int z = 2;
x = z * 2;
y = y / 2;
z++;
```

</div>

Try the **Operators Maze game**: <a href="https://docs.google.com/document/d/1ZjA8oKeo8FYx2nXX4OOq5lUihopIQQ_HY-eoE5yZkk8/edit?usp=sharing" target="_blank" style="text-decoration:underline">Operators Maze game</a>.

---

## Summary

* (AP 1.6.A.1) **Compound assignment** (`+=`, `-=`, `*=`, `/=`, `%=`) performs the operation using the current value on the left and the value on the right, then assigns the result back to the left variable.
* (AP 1.6.A.2) **Increment** (`++`) and **decrement** (`--`) add or subtract 1 from a numeric variable and store the new value.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
