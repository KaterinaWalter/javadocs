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

## APIs, Libraries, Packages

<html>
  <dl>
    <dt>📚 Library</dt>
    <dd>A collection of <strong>prewritten code</strong> (classes) that you can reuse in your own program.</dd>
    <dt>📦 Package</dt>
    <dd>A group of related classes that can be <strong>imported</strong> into a program, like a folder of classes in a library's file directory.</dd>
    <dt>👉 Method</dt>
    <dd>A block of code that performs a specific task, like instructions for a process. Classes often contain many methods.</dd>
    <dt>🖥️ API</dt>
    <dd><strong>Application Programming Interface</strong> refers mainly to a library's documentation that tells the programmer <em>how to use</em> its classes and their methods.</dd>
  </dl>
</html>

APIs and libraries are essential to programming because they allow you to use code that has **already been written** by others. This saves you time and allows you to focus on the specific task you are trying to accomplish.
> The terms library, API, and package are often used _interchangeably_ to mean similar things.

<div class="task" markdown="block">

💬 **Discuss:** Did we use any *libraries* last year in Web Development for either `HTML`, `CSS`, or `JavaScript`? If so, how did we learn how to use someone else's code?

</div>

### The `java.lang` Package

`java.lang` is imported automatically. It includes core classes like `String` and `System`, which we use in `System.out.println`.

Browse the docs:  
- Package summary: <https://docs.oracle.com/javase/8/docs/api/java/lang/package-summary.html>  
- `PrintStream.println` overloads: <https://docs.oracle.com/javase/8/docs/api/java/io/PrintStream.html>

<div class="task" markdown="block">

**Check Your Understanding — `println` overloads**  
How many distinct `println(...)` methods are listed in `PrintStream`?

</div>

<div class="task" markdown="block">

**Multiple Choice — Why use APIs/libraries?**  
What’s the main purpose of APIs and libraries in programming?

A) Write all code from scratch  
B) **Use code written by others** ✅  
C) Create new programming languages  
D) Compile code

</div>

### Turtle Library

The **Turtle** library (by Dr. Barbara Ericson) lets you draw with an animated turtle that moves, turns, and draws lines. A **class** like `Turtle` defines the data (**attributes/fields**) and **behaviors/methods** shared by all turtle-type **objects** you create. 

![image-small](Figures/turtleOOD.png)

<html>
  <dl>
    <dt>Attributes/Fields)</dt>
    <dd>Data the object “knows” (e.g., <code>name</code>, <code>height</code>, <code>width</code>, <code>position</code></dd>
    <dt>Behaviors/Methods</dt>
    <dd>Actions the object “does” (e.g., <code>forward()</code>, <code>turnLeft()</code>)</dd>
  </dl>
</html>

<div class="imp" markdown="block">
  
📣 You **CALL** (activate/run) methods with the **dot operator** (`.`), just like `System.out.println()`:

```java
yertle.forward();
yertle.turnRight();
```
> The code above calls two **methods** on the `yertle` object: first, `forward()` then `turnRight()`. These methods "belong" to the general `Turtle` class definition, but are being used on that specific **object** (_an instance of the class_). 

</div>

#### Reading API Documentation

A quick tip to tell **methods** vs **attributes** in docs:

* **Methods** always have parentheses: `forward()`, `println(...)`.
* **Attributes/fields** don’t: `out`, `length`, `width`.

Docs for a simple Turtle: [SimpleTurtle Documentation](https://www2.cs.uic.edu/~i101/doc/SimpleTurtle.html)

#### CSAwesome Exercises: Turtle Class

<div class="task" markdown="block">

🐢 We will use the `Turtle` class to demonstrate using **objects** visually. 

<a href="https://runestone.academy/ns/books/published/csawesome2/topic-1-7-APIs-and-libraries.html"><button class="btn">CSAwesome 1.7</button></a>

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
