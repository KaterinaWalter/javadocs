---
layout: notes
title: "📓1.7: APIs & Libraries" 
parent: "1️⃣ Objects & Methods"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.7](https://runestone.academy/ns/books/published/csawesome2/topic-1-7-APIs-and-libraries.html) 

---

We have already been using `System.out.println()` to print text to the screen. That method belongs to the `Java API` – the **Application Programming Interface** for Java’s standard **libraries** and **packages**.

<html>
  <dl>
    <dt>Library</dt>
    <dd>A collection of <strong>prewritten code</strong> (classes) that you can reuse in your own program.</dd>
    <dt>Package</dt>
    <dd>A group of related classes that can be <strong>imported</strong> into a program, like a folder of classes in a library's file directory.</dd>
    <dt>Method</dt>
    <dd>A block of code that performs a specific task/process. Classes often contain many methods.</dd>
    <dt>API</dt>
    <dd><strong>Application Programming Interface</strong> refers to a library's documentation that tells the programmer <em>how to use</em> its classes and their methods.</dd>
  </dl>
</html>

APIs and libraries are essential to programming because they allow you to use code that has **already been written** by others. This saves you time and allows you to focus on the specific task you are trying to accomplish.
> The terms library, API, and package are often used _interchangeably_ to mean similar things.

<div class="task" markdown="block">

💬 **Discuss:** Did we use any *libraries* last year in Web Development for either `HTML`, `CSS`, or `JavaScript`? If so, how did we learn how to use someone else's code?

</div>

---

## `java.lang` package

`java.lang` is imported automatically. It includes core classes like `String` and `System`, which we use in `System.out.println`.

Browse the docs:  
- Package summary: <https://docs.oracle.com/javase/8/docs/api/java/lang/package-summary.html>  
- `PrintStream.println` overloads: <https://docs.oracle.com/javase/8/docs/api/java/io/PrintStream.html>

<div class="task" markdown="block">

**Check Your Understanding — `println` overloads**  
How many distinct `println(...)` methods are listed in `PrintStream`?

**Answer:** `10` (one for each supported parameter type).

</div>

<div class="task" markdown="block">

**Match the vocabulary**  
- A collection of classes written by other programmers → **library**  
- A collection of related classes organized to be imported → **package**  
- A specification describing how to use a library → **API**  
- The building blocks of Java and OOP → **class**  
- A block of code that performs a specific task → **method**

</div>

<div class="task" markdown="block">

**Multiple Choice — Why use APIs/libraries?**  
What’s the main purpose of APIs and libraries in programming?

A) Write all code from scratch  
B) **Use code written by others** ✅  
C) Create new programming languages  
D) Compile code

</div>

---

## Turtle library (intro)

The **Turtle** library (by Dr. Barbara Ericson) lets you draw with an animated turtle that moves, turns, and draws lines. A **class** like `Turtle` defines the data (**attributes/fields**) and **behaviors/methods** shared by all turtle objects you create.

![](Figures/turtleOOD.png)

- **Attributes** (fields): data the object “knows” (e.g., `name`, `height`, `width`, position).  
- **Behaviors** (methods): actions the object “does” (e.g., `forward()`, `turnLeft()`).

Docs for a simple Turtle: <https://www2.cs.uic.edu/~i101/doc/SimpleTurtle.html>

You call methods with the **dot operator** (`.`), just like `System.out.println(...)`:

```java
yertle.forward();
yertle.turnRight();
````

<div class="task" markdown="block">

**Run Some Code (Codespaces)**
In your Java program:

1. Create a `World` and a `Turtle` named `yertle` in that world.
2. Move `yertle` forward, turn right, then **add one more** `forward()` call.
3. Show the world/animation according to the starter you’re using.

Example method calls to add (after you’ve created the objects):

```java
yertle.forward();
yertle.turnRight();
// Add one more forward:
yertle.forward();
```

</div>

<div class="task" markdown="block">

**Check Your Understanding**

1. When a turtle is first created, which way does it face?
   **North** ✅

2. In the program above, what *kind* of thing is `Turtle`?
   **Class** ✅

3. What kind of thing is `turnRight`?
   **Method** ✅

4. What kind of thing is the turtle’s position in the world?
   **Attribute (field)** ✅

</div>

---

## Reading API docs quickly

A quick tip to tell **methods** vs **attributes** in docs:

* **Methods** always have parentheses: `forward()`, `println(...)`.
* **Attributes/fields** don’t: `out`, `length`, `width`.

---

## Parsons-style “L” drawing (concept walkthrough)

To draw a sideways “L”, you would:

1. Do the setup (create `World`, create `Turtle`).
2. `turnRight()`
3. `forward()`
4. `turnLeft()`
5. `forward(50)`
6. Show the world.

(If you’re practicing with a Parsons tool, arrange those lines in that order and ignore distractors like `right()` or missing parentheses.)

---

## Groupwork: Turtle Drawing

Make **yertle** draw a shape—square, zigzag, or a block letter—by combining `forward()` with `turnRight()`/`turnLeft()` multiple times. Pair up and iterate!

Handy methods:

* `yertle.forward();`
* `yertle.turnLeft();`
* `yertle.turnRight();`
* `yertle.backward();`
* `yertle.penUp();`
* `yertle.penDown();`

<div class="task" markdown="block">

**Coding Challenge (Codespaces)**
Add a sequence of method calls to draw a shape. Aim for at least **4 moves** and **3 turns**.

```java
// Example outline for a square (tweak distances as you like)
yertle.forward();
yertle.turnRight();
yertle.forward();
yertle.turnRight();
yertle.forward();
yertle.turnRight();
yertle.forward();
```

</div>

---

## Summary

* (AP 1.7.A.1) **Libraries** are collections of classes written by others.
* (AP 1.7.A.1) An **API** describes how to use those classes.
* (AP 1.7.A.1) Good **documentation** is essential for understanding a class’s attributes and behaviors.
* (AP 1.7.A.1) Classes are organized into **packages** that you can import.
* (AP 1.7.A.1) A **class** defines a reference type; you create **objects** (instances) from it.
* (AP 1.7.A.2) **Attributes (fields)** are the object’s data; **behaviors (methods)** are what it can do.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
