---
layout: notes
title: "📓2.6: Comparing Boolean Expressions" 
parent: "2️⃣ Selection & Iteration"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.6](https://runestone.academy/ns/books/published/csawesome2/topic-2-6-comparing-booleans.html) 

---

## Equivalent Boolean Expressions

What if you heard a rumor about a senior at your high school? And then you heard that the rumor wasn't true - it wasn't a senior at your high school. Which part of "a senior at your high school" wasn't true? Maybe they weren't a senior? Or maybe they didn't go to your high school? You could write this as a logic statement like below using **negation** (``!``) and the **and** (``&&``) operator since both parts have to be true for the whole statement to be true.

```java
a = "senior"
b = "at our high school"

!(a && b)

// This means it is not true that (a) it is a senior
// and (b) someone at our high school.
```

### De Morgan's Laws

De Morgan's Laws were developed by Augustus De Morgan in the 1800s.  They show how to simplify the negation of a complex boolean expression, which is when there are multiple expressions joined by an **and** (``&&``) or **or** (``||``), such as ``(x < 3) && (y > 2)``. When you negate one of these complex expressions, you can simplify it by flipping the operators and end up with an equivalent expression. De Morgan's Laws state the following equivalencies. Here's an easy way to remember De Morgan's Laws: **move the NOT inside, AND becomes OR** and **move the NOT inside, OR becomes AND**.

![image](Figures/demorgan.png)

In Java, De Morgan's Laws are written with the following operators:
-  ``!(a && b)`` is equivalent to ``!a || !b``
-  ``!(a || b)`` is equivalent to ``!a && !b``

Going back to our example above, `not(a senior AND at our high school)` is equivalent to `not(a senior) OR not(at our high school)` using De Morgan's Laws:

```
a = "senior"
b = "at our high school"

!(a && b) is equivalent to !a || !b
```
        

You can also simplify negated boolean expressions that have relational operators like ``<``, ``>``, ``==``. You can move the negation inside the parentheses by flipping the relational operator to its opposite sign. For example, not (c equals d) is the same as saying c does not equal d.  An easy way to remember this is **To move the NOT, flip the sign**. Notice that ``==`` becomes ``!=``, but ``<`` becomes ``>=``,  ``>`` becomes ``<=``, ``<=`` becomes ``>``, and ``>=`` becomes ``<`` where the sign is flipped and an equal sign may also be added or removed.

  - ``!(c == d)`` is equivalent to ``c != d``
  - ``!(c != d)`` is equivalent to ``c == d``
  - ``!(c < d)`` is equivalent to ``c >= d``
  - ``!(c > d)`` is equivalent to ``c <= d``
  - ``!(c <= d)`` is equivalent to ``c > d``
  - ``!(c >= d)`` is equivalent to ``c < d``

### Truth Tables

Although you do not have to memorize De Morgan's Laws for the CSA Exam, you should be able to show that two boolean expressions are equivalent. One way to do this is by using truth tables. 

For example, we can show that ``!(a && b)`` is equivalent to ``!a || !b`` by constructing the truth table below and seeing that they give identical results for the 2 expressions (the last 2 columns in the table below are identical!).

| a     | b     | `!(a && b)` | `!a \|\| !b` |
|-------|-------|-----------|----------|
| true  | true  | false     | false    |
| false | true  | true      | true     |
| true  | false | true      | true     |
| false | false | true      | true     |

### Simplifying Boolean Expressions

Often, you can simplify boolean expressions to create equivalent expressions. For example, applying De Morgan's Laws to ``!(x < 3 && y > 2)`` yields ``!(x < 3) || !(y > 2)`` as seen in the figure below. This can then be simplified further by flipping the relational operators to remove the not.  So, ``!(x < 3) || !(y > 2)`` is simplified to ``(x >= 3 || y <= 2)`` where the relational operators are flipped and the negation is removed. These two simplification steps are seen below.

![image](Figures/demorganex.png)

<!--
## Comparing Booleans

You can compare booleans directly with `==` and `!=`.  
- `==` checks if two boolean values are equal.  
- `!=` checks if they are not equal.

<div class="task" markdown="block">

**Coding Exercise: Boolean Comparison**

Test both `true` and `false` values for `isSunny` and `isWarm`.

```java
boolean isSunny = true;
boolean isWarm = false;

if (isSunny == true) {
    System.out.println("It's sunny");
}

if (isWarm != true) {
    System.out.println("It's not warm");
}
````

</div>

---

## Logical Equivalences

Certain boolean expressions can be rewritten without changing their meaning. This is useful for simplifying logic and avoiding common mistakes.

Example:

```java
!(x < 5)
```

is equivalent to:

```java
x >= 5
```

---

## De Morgan’s Laws

De Morgan’s Laws show how to distribute `!` (NOT) over `&&` (AND) and `||` (OR):

1. `!(A && B)` is the same as `!A || !B`
2. `!(A || B)` is the same as `!A && !B`

**Mnemonic:** Negating flips the operator and negates each condition.

---

### Example 1

```java
!(x > 0 && y > 0)
```

is equivalent to:

```java
x <= 0 || y <= 0
```

---

### Example 2

```java
!(x > 0 || y > 0)
```

is equivalent to:

```java
x <= 0 && y <= 0
```

---

## Practice with De Morgan’s Laws

<div class="task" markdown="block">

**Coding Exercise: Applying De Morgan**

Rewrite each condition using De Morgan’s Laws.

```java
boolean raining = true;
boolean cold = false;

if (!(raining && cold)) {
    System.out.println("Nice weather");
}

if (!(raining || cold)) {
    System.out.println("Perfect weather");
}
```

* First if: `!raining || !cold`
* Second if: `!raining && !cold`

</div>

---

## Summary

* Use `==` and `!=` to compare booleans directly.
* Negating a compound condition flips the operator (`&&` ↔ `||`) and negates each part.
* De Morgan’s Laws are helpful for simplifying conditions and avoiding logic errors.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

Which of the following is equivalent to `!(a && b)`?

A. `!a || !b`
B. `!a && !b`
C. `a || b`

**Answer:** **A** — De Morgan’s Law: `!(A && B)` ≡ `!A || !B`.

</details>

<details>
<summary><strong>Question 2</strong></summary>

Which of the following is equivalent to `!(a || b)`?

A. `!a || !b`
B. `!a && !b`
C. `a && b`

**Answer:** **B** — De Morgan’s Law: `!(A || B)` ≡ `!A && !B`.

</details>

-->

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
