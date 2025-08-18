---
layout: notes
title: "📓1.13: Constructors - Creating & Initializing Objects" 
parent: "1️⃣ Objects & Methods"
nav_order: 14
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.13](https://runestone.academy/ns/books/published/csawesome2/topic-1-13-constructors.html) 

#### CSAwesome Activities: Turtle Class

<div class="task" markdown="block">

🐢 To explore the concepts from this lesson in code, we'll play around with the `Turtle` class on the CSAwesome website instead of taking notes.  

👉 **GO TO:** <a href="https://runestone.academy/ns/books/published/csawesome2/topic-1-13-constructors.html"><button class="btn">CSAwesome Topic 1.13</button></a>, **SIGN IN** to your account, and complete all the turtle-related **coding activities/challenges** with a partner. 

</div>

---

A Java class defines what objects of the class know (**attributes**) and what they can do (**behaviors**).
Each class has **constructors** which are used to initialize the attributes in a newly created object.
**Constructors** have the same name as the class.

A new object is created with the `new` keyword followed by the class name, which is a call to the constructor (`new ClassName()`).

For example:

```java
// To create a new object and call a constructor:
ClassName variableName = new ClassName(arguments);

World habitat = new World();    // create a new World object
Turtle t = new Turtle(habitat); // create a new Turtle object
```

---

### The World Class Constructors

There can be more than one constructor defined in a class. This is called **overloading** the constructor.

The `World` class has two constructors:

* `World()` — no arguments, creates a default-sized world (640×480 px)
* `World(int width, int height)` — takes two integers to create a world of specific size.

```java
World world1 = new World(); // default size 640x480
World world2 = new World(300, 400); // custom size 300x400
```

---

### The Turtle Class Constructors

The `Turtle` class also has multiple constructors.
It always requires a **world** argument for where the turtle will be drawn.

The default location is the middle of the world. Another constructor allows you to set a specific `(x, y)` location:

```java
Turtle t1 = new Turtle(world1);
Turtle t2 = new Turtle(50, 100, world1);
```

> **Note:** The order of arguments matters — `Turtle(int x, int y, World w)` is **not** the same as swapping them.

---

## **Coding Exercise: Turtle Constructors**

<div class="task" markdown="block">

1. Open your GitHub Codespace.

2. Create a new file named `TurtleConstructorTest.java`.

3. Type this code into your file:

   ```java
   World world1 = new World(300, 300);

   // Turtle in the middle of the world
   Turtle t1 = new Turtle(world1);

   // Try changing the World constructor to 300x400
   // Try placing the turtle in the top-right corner
   // What happens if you mix up argument order?
   t1.turnLeft();

   world1.show(true);
   ```

4. Press **Run** to see the results.

5. Experiment with different constructor arguments and observe where the turtle appears.

</div>

---

## Object Variables and References

New objects are saved in **reference type** variables, which hold a reference to the object in memory.

A special reference value `null` means the variable doesn’t refer to any object yet:

```java
World world1 = new World();
Turtle t1 = null; // no object yet
t1 = new Turtle(world1);
```

---

### Video: Understanding `null`

<iframe width="650" height="415" src="https://www.youtube.com/embed/5fpjgXAV2BU" title="YouTube video" frameborder="0" allowfullscreen></iframe>

---

## Constructor Signatures

When using a class from a library (e.g., `Turtle`), you can look up the **constructor signatures** in the documentation.

A **signature** = constructor name + parameter list (number, types, order).

Constructors are **overloaded** if there are multiple with different signatures.

Example (`Turtle` class):

* `Turtle(World w)`
* `Turtle(int x, int y, World w)`

---

## Arguments, Parameters, and Call by Value

When a constructor like:

```java
new Date(2005, 9, 1)
```

is called:

* **Parameters** = variables in the constructor’s signature (e.g., `year`, `month`, `day`)
* **Arguments** = values passed in (e.g., `2005`, `9`, `1`)

Java passes arguments **by value** (copies).

---

## **Debugging Challenge: Turtle Constructors**

<div class="task" markdown="block">

1. Open your GitHub Codespace.

2. Create a new file `TurtleConstructorDebug.java`.

3. The code below has **multiple errors** — fix them so it runs:

   ```java
   World w = new World(300, 0);
   Turtle t0; 
   Turtle t1 = new Turtle(w);
   Turtle t2 = new Turtle(100, 50, w);

   t0 = new Turtle(w);
   t0.forward();
   t1.turnRight();
   t2.turnLeft();

   w.show(true);
   ```

4. Try changing constructor arguments and see how the turtle positions change.

</div>

---

## **Group Coding Challenge: Custom Turtles**

<div class="task" markdown="block">

1. Open your GitHub Codespace.

2. Create a new file named `CustomTurtleRunner.java`.

3. Type this code:

   ```java
   World world1 = new World(400, 400);

   // 1. Large turtle (150x200) — green body, blue shell, position (150, 300)
   CustomTurtle turtle1 = new CustomTurtle(150, 300, world1, Color.green, Color.blue, 150, 200);
   turtle1.forward();

   // 2. Small turtle (25x50) — red body, yellow shell, position (350, 200)
   CustomTurtle turtle2 = new CustomTurtle(350, 200, world1, Color.red, Color.yellow, 25, 50);
   turtle2.forward();

   // 3. Your own custom turtle!
   CustomTurtle turtle3 = new CustomTurtle(200, 200, world1, Color.orange, Color.pink, 100, 150);
   turtle3.forward();

   world1.show(true);
   ```

4. Experiment with different sizes, positions, and colors.

</div>

---

## Summary

* **Constructors** create and initialize objects.
* They have the same name as the class.
* Use `new ClassName(arguments)` to create an object.
* **No-argument constructors** set default values.
* **Overloaded constructors** have the same name but different parameter lists.
* **Parameters** = variables in the signature.
* **Arguments** = values passed into the constructor.
* Java passes arguments **by value**.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
