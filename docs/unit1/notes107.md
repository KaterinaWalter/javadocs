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

<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong> Create a blank Java program to take your class notes in for the next few lessons. <em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit1PartB-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, writing **code** & **comments** along with the instructor.

</div>

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! **Codespaces** are TEMPORARY editing environments, so you need to COMMIT changes properly in order to update the main **repository** for your program. 

_There are multiple steps to saving in GitHub Codespaces:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

</details>

</html>


---

<!--
Begin with a question: "Who do you think wrote the code to make System.out.println work?
Use System.out.println("Hello, World!"); in Java.
Explain that this method is part of the java.lang package, which is automatically available in every Java program.
James Gosling and his team at Sun Microsystems developed Java and the java.lang library that comes with Java.
Ask:  How do we know how to use System.out.println the right way?”
Show the Java doc for https://docs.oracle.com/en/java/javase/22/docs/api/java.base/java/io/PrintStream.html and see if you can find the println methods.
-->

We’ve already been using `System.out.println()` to print text. That method lives in the Java **API**—the Application Programming Interface for Java’s standard libraries.

- A **library** is a collection of prewritten code (classes) you can reuse.
- An **API** tells you how to use that library—names of classes, methods, parameters, etc.
- A **package** groups related classes to avoid name conflicts and to organize a library.

Using APIs and libraries means you don’t reinvent the wheel—you stand on the shoulders of other programmers.

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
