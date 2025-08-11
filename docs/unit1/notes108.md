---
layout: notes
title: "📓1.8: Documentation, Comments, Preconditions" 
parent: "1️⃣ Objects & Methods"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.8]() 

---

Comments don’t run—they _explain_. Your future self (and your teammates) will thank you.

## Types of comments

1) `//` single‑line  
2) `/* ... */` multi‑line block  
3) `/** ... */` Javadoc (for API‑style docs)

Javadoc can be turned into HTML docs using `javadoc` (part of the JDK). It’s common to place Javadoc above **classes** and **methods** and to use tags like `@author`, `@since`, `@version`, `@param`, `@return`.

### Example

```java
/**
 * MyClass.java
 * @author Your Name
 * @since 2025-01-01
 * This class keeps track of the max score.
 */
public class MyClass {
    private int max = 10; // tracks the max score

    /** Prints the current max. */
    public void print() {
        System.out.println(max);
    }
}
````

> IDEs often render comments in italics/gray to make them easy to spot.

---

<div class="task" markdown="block">

### Check Your Understanding — comment types

Match each comment form:

* **single-line** → `//`
* **multi-line** → `/* ... */`
* **Javadoc** → `/** ... */`

</div>

---

## Mini exercise — add helpful comments

Create a `Multiply.java` that reads two ints and prints their product. Add:

* A **multi-line Javadoc** block above the class describing its purpose.
* **Single-line** comments above the input, the calculation, and the print.

Starter outline:

```java
import java.util.Scanner;

/** 
 * Multiply: reads two integers and prints num1 x num2 = result.
 * Add your author/date here if you like.
 */
public class Multiply {
    public static void main(String[] args) {
        // Read two numbers
        Scanner scan = new Scanner(System.in);
        int num1 = scan.nextInt();
        int num2 = scan.nextInt();

        // Compute product
        int result = num1 * num2;

        // Print formatted result
        System.out.println(num1 + " x " + num2 + " = " + result);
        scan.close();
    }
}
```

---

## Preconditions and postconditions

* A **precondition** must be true before code runs (what your method *expects*).
* A **postcondition** is guaranteed after it runs (what your method *promises*).

APIs often document both. A method may not check its preconditions—it can assume callers satisfy them.

**Examples:**

* Division requires the **divisor ≠ 0** (precondition).
* `Math.sqrt(x)` expects **x ≥ 0**. If not, Java returns `NaN` (not a number); practically, think of the precondition as *non‑negative input*.

### Try it

```java
public class SqRoot {
    public static void main(String[] args) {
        double num = 9;              // change from negative to non-negative
        System.out.println(Math.sqrt(num));
    }
}
```

* Precondition for `sqrt`: the argument is ≥ 0.
* Postcondition: the return value squared (within floating‑point error) is the original argument.

---

## Preconditions in a library method (Turtle)

A Turtle library’s `forward(int pixels)` typically has a precondition like:

* **0 ≤ pixels ≤ (world width/height limit)**

If you give a value outside the range, the method may clamp it so the turtle stays visible (a reasonable postcondition).

```java
/**
 * Moves the turtle forward.
 * @param pixels distance to move, in the current heading
 * Preconditions: 0 ≤ pixels ≤ world bounds
 * Postconditions: turtle moves forward, remains within world
 */
public void forward(int pixels) { ... }
```

<div class="task" markdown="block">

### Turtle preconditions (thought experiment)

* What happens if you try `forward(-50)`?
* What about a huge value (e.g., `forward(1_000_000)`)—does it clamp to the edge or ignore it?

(If you’re using the Swing Turtle from earlier lessons, test and observe; otherwise, reason about expected behavior using the documentation above.)

</div>

---

## Software validity, use‑case diagrams (context)

Not on the AP exam, but useful in practice:

* **Validity/testing**: Does the software do what it should? Break it on purpose (violating preconditions) to discover edge cases.
* **Use‑case diagrams**: Show how users interact with a system. Each use case can list preconditions and postconditions; often the postcondition of one becomes the precondition of the next.

**Restaurant example**

* *Order Food* → Post: order placed
* *Eat Food* → Pre: order placed and delivered; Post: food eaten
* *Pay for Food* → (see short answer below)

<div class="task" markdown="block">

### Short Answer — “Pay for Food”

Give reasonable preconditions/postconditions.

**Sample answer:**

* *Preconditions*: Food has been ordered and delivered; the bill is prepared; payment method is available.
* *Postconditions*: Payment is processed; receipt is issued; customer balance due is \$0.

</div>

---

## Agile at a glance

* **Waterfall**: sequential phases; less adaptable to change.
* **Agile (Scrum)**: short 2–3 week **sprints**, build/test/release small increments; frequent customer feedback → highly adaptable.

---

## Groupwork — Preconditions for an online purchase

List **4 steps** (use cases) to purchase a product online (e.g., a Java book) and, for each, write preconditions and postconditions. Typical steps:

1. **Browse/Search Product**

   * Pre: user can access site
   * Post: product page visible

2. **Add to Cart**

   * Pre: product is in stock
   * Post: cart contains product, quantity updated

3. **Checkout**

   * Pre: cart has items; user provides shipping info
   * Post: order summary with totals displayed

4. **Pay**

   * Pre: valid payment method; total calculated
   * Post: payment authorized; order confirmed

Feel free to make a simple use‑case diagram if you like.

---

## Summary

* (AP 1.8.A.1) **Comments** help humans; the compiler ignores them. Types: `//`, `/*...*/`, `/**...*/`.
* (AP 1.8.A.2) A **precondition** must be true just before execution; methods may assume it rather than check it.
* (AP 1.8.A.3) A **postcondition** must be true just after execution; it states the outcome (return value or object state).

---

### AP Practice

**Which preconditions are reasonable for:**

```java
/** Adds extra-credit to score. */
public double computeScore(double score, double extraCredit) {
    double totalScore = score + extraCredit;
    return totalScore;
}
```

**Answer:**

* `/* Precondition: score >= 0 */` ✅
* `/* Precondition: extraCredit >= 0 */` ✅
  (others are not appropriate)


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
