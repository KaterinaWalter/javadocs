---
layout: notes
title: "📓4.16: Recursion" 
parent: "4️⃣ Data Collections"
nav_order: 16
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.16]() 

---

# Recursion

**Recursion** is when a method calls itself. It is a form of repetition.

Example:

```java
public static void neverEnd() {
    System.out.println("This is the method that never ends!");
    neverEnd();
}
````

This method will print `"This is the method that never ends!"` and then call itself, which will print out the message again, and then call itself, and so on. This is called **infinite recursion**, which is recursion that never ends.

In practice, it *will* end — by crashing with a `StackOverflowError` because there is a limit to how many times a method can recursively call itself.

---

## Recursive Call

Well-constructed recursive methods contain:

* At least one **base case**, which halts the recursion.
* At least one **recursive call**, which calls the method again with different parameters.

---

## Check Your Understanding

<div class="task" markdown="block">

**Question:** Which line in the method `neverEnd` (shown above) contains the recursive call (the call to the same method)?

**Answer:** Line 4 — `neverEnd();` contains a call to the same method, which makes it a recursive method.

</div>

---

## Is This Recursive?

Consider:

```java
public static int mystery() {
    int total = 0;
    for (int i = 10; i > 0; i--) {
        total = total + i;
    }
    return total;
}
```

**Answer:** No — this is **not** recursive. There is no call to the same method; it uses iteration instead.

---

## Summary

* **Recursion** is when a method calls itself.
* Infinite recursion occurs without a base case to stop it.
* Proper recursion requires:

  * **Base case**: stops recursion.
  * **Recursive call**: moves toward the base case.
* Without a base case, recursion causes a `StackOverflowError`.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
