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
📖 This page is a condensed version of [CSAwesome Topic 2.6]() 

---

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
