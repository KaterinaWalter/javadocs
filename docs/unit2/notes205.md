---
layout: notes
title: "📓2.5: Compound Boolean Expressions" 
parent: "2️⃣ Selection & Iteration"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.5](https://runestone.academy/ns/books/published/csawesome2/topic-2-5-compound-ifs.html) 

---

## And (`&&`), Or (`||`), and Not (`!`)

What if you want two things to be true before the body of the conditional is executed? Use `&&` (logical **and**) to join two Boolean expressions. The body will only execute if **both** are true.

<div class="task" markdown="block">

**Coding Exercise: Logical AND**

Test different combinations of `cleanedRoom` and `didHomework` to see when `"You can go out"` is printed.

```java
boolean cleanedRoom = true;
boolean didHomework = false;

if (cleanedRoom && didHomework) {
    System.out.println("You can go out");
} else {
    System.out.println("No, you can't go out");
}
````

</div>

---

Use `||` (logical **or**) when you want the body to execute if **at least one** condition is true.

<div class="task" markdown="block">

**Coding Exercise: Logical OR**

Test different combinations of `hasMoney` and `hasRide` to see when `"You can go to the mall"` is printed.

```java
boolean hasMoney = true;
boolean hasRide = false;

if (hasMoney || hasRide) {
    System.out.println("You can go to the mall");
} else {
    System.out.println("You can't go to the mall");
}
```

</div>

---

## Truth Tables

Logical expressions can be summarized in **truth tables** showing every possible combination of inputs and the resulting output.

Example for `&&` (**and**):

| A     | B     | A && B |
| ----- | ----- | ------ |
| true  | true  | true   |
| true  | false | false  |
| false | true  | false  |
| false | false | false  |

Example for `||` (**or**):

| A     | B     | A \|\| B |
| ----- | ----- | -------- |
| true  | true  | true     |
| true  | false | true     |
| false | true  | true     |
| false | false | false    |

---

## Using `!` (Logical NOT)

`!` negates a boolean expression — it makes `true` become `false` and `false` become `true`.

<div class="task" markdown="block">

**Coding Exercise: Logical NOT**

Run the code and change `isRaining` to see how negation changes the output.

```java
boolean isRaining = true;

if (!isRaining) {
    System.out.println("Let's go outside!");
} else {
    System.out.println("Better stay inside!");
}
```

</div>

---

## Combining AND, OR, and NOT

Compound expressions can be combined in one condition. Use parentheses to control order of evaluation.

<div class="task" markdown="block">

**Coding Exercise: Complex Condition**

Test different values of `hasTicket`, `onGuestList`, and `over18` to see when entry is allowed.

```java
boolean hasTicket = true;
boolean onGuestList = false;
boolean over18 = true;

if ((hasTicket || onGuestList) && over18) {
    System.out.println("You can enter the event");
} else {
    System.out.println("Sorry, no entry");
}
```

</div>

---

## Summary

* `&&` is true only if **both** operands are true.
* `||` is true if **at least one** operand is true.
* `!` reverses a boolean value.
* Use parentheses for clarity and to control precedence.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

What does this print if `a = true` and `b = false`?

```java
if (a && b) {
    System.out.println("yes");
} else {
    System.out.println("no");
}
```

**Answer:** `no` — because `a && b` is `true && false`, which is `false`.

</details>

<details>
<summary><strong>Question 2</strong></summary>

What does this print if `a = true` and `b = false`?

```java
if (a || b) {
    System.out.println("yes");
} else {
    System.out.println("no");
}
```

**Answer:** `yes` — because `a || b` is `true || false`, which is `true`.

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
