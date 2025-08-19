---
layout: notes
title: "📓1.13: Constructors" 
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

---

## Constructors – Creating & Initializing Objects

A Java class defines what objects of the class know (**attributes**) and what they can do (**behaviors**). Each class has **constructors** which are special methods used to _initialize_ the attributes for a newly created object. 

{:.highlight}
**Constructors** always have the _same name as the class_! 

A new object instance is created with the `new` keyword followed by the class name, which is a call to the constructor (`new ClassName()`).

<div class="imp" markdown="block">
    
🏗️ Syntax pattern to construct a `new` **object** instance:

```java
ClassName variableName = new ClassName(parameters);
```
> * **Right side of `=`:** _declaring_ a variable of type `ClassName`
> * **Left side of `=`:** _assigning_ values by calling a _constructor_ 

</div>

**Examples:**
```java
World habitat = new World();    // create a new World object
Turtle t = new Turtle(habitat); // create a new Turtle object
```

### The `World` Class Constructors

There can be _more than one constructor_ defined in a class. This is called **overloading** the constructor. 

{:.important}
Constructors are considered **overloaded** when there are multiple constructors, but the constructors have different _signatures_. They can differ in the number, type, and/or order of parameters (_input_). Think of overloading constructors as providing different ways of "setting up" an object, depending on how much information you want to specify about the object.

The `World` class has two constructors:

* `World()` — no arguments, creates a default-sized world (640×480 px)
* `World(int width, int height)` — takes two integers to create a world of specific size.

```java
World world1 = new World(); // default size 640x480
World world2 = new World(300, 400); // custom size 300x400
```

### The `Turtle` Class Constructors

The `Turtle` class also has multiple constructors.
It always requires a **world** argument for where the turtle will be drawn.

The default location is the middle of the world. Another constructor allows you to set a specific `(x, y)` location:

```java
Turtle t1 = new Turtle(world1);
Turtle t2 = new Turtle(50, 100, world1);
```

> **Note:** The order of arguments matters — `Turtle(int x, int y, World w)` is **not** the same as swapping them.

{:.highlight}
🗺️ The Turtle world does not use the Cartesian coordinate system with `(0,0)` in in the middle the screen. Instead: `(0,0)` is at the **top left corner** of the screen, `x` increases to the right, and `y` increases towards the bottom of the screen.

### Object Variables and References

New objects are saved in **reference type** variables, which hold a reference to the object in memory.

A special reference value `null` means the variable doesn’t refer to any object yet:

```java
World world1 = new World();
Turtle t1 = null; // no object yet
t1 = new Turtle(world1);
```

#### Video: Understanding `null`
{:.no_toc}

<iframe width="650" height="415" src="https://www.youtube.com/embed/5fpjgXAV2BU" title="YouTube video" frameborder="0" allowfullscreen></iframe>

### Constructor Signatures

When using a class from a library (e.g., `Turtle`), you can look up the **constructor signatures** in the documentation.

A **signature** = constructor name + parameter list (number, types, order).

Constructors are **overloaded** if there are multiple with different signatures.

Example (`Turtle` class):

* `Turtle(World w)`
* `Turtle(int x, int y, World w)`

### Arguments, Parameters, and Call by Value

When a constructor like:

```java
new Date(2005, 9, 1)
```

is called:

* **Parameters** = variables in the constructor’s signature (e.g., `year`, `month`, `day`)
* **Arguments** = values passed in (e.g., `2005`, `9`, `1`)

Java passes arguments **by value** (copies).

#### CSAwesome Activities: Turtle Class

<div class="task" markdown="block">

🐢 To explore the concepts from this lesson in code, we'll play around with the `Turtle` class on the CSAwesome website instead of taking notes.  

👉 **GO TO:** <a href="https://runestone.academy/ns/books/published/csawesome2/topic-1-13-constructors.html"><button class="btn">CSAwesome Topic 1.13</button></a>, **SIGN IN** to your account, and complete all the turtle-related **coding activities/challenges** with a partner. 

</div>

---

## Summary

- (AP 1.13.A.1) A class contains **constructors** that are called with the keyword ``new`` to create objects and initialize its attributes. 

- (AP 1.13.A.1) **Constructors** have the same name as the class.

- (AP 1.13.C.1) An object is typically created using the keyword new followed by a call to one of the class’s constructors. ``new ClassName()`` creates a new object of the specified class and calls a constructor.

- (AP 1.13.B.1) The new object is saved in a variable of a **reference type** which holds an object reference or null if there is no object.

- (AP 1.13.A.2) A **constructor signature** consists of the constructor’s name, which is the same as the class name, and the ordered list of parameter types. 

- (AP 1.13.A.2) The **parameter list**, in the header of a constructor, lists the types of the values that are passed and their variable names.

- (AP 1.13.A.3) Constructors are said to be **overloaded** when there are multiple constructors with different signatures. They must differ in the number, type, or order of parameters.

- A **no-argument constructor** is a constructor that doesn't take any passed in values (arguments).

- (AP 1.13.C.2) **Parameters** allow constructors to accept values to establish the initial values of the attributes of the object.

- (AP 1.13.C.3) A constructor **argument** is a value that is passed into a constructor when the constructor is called. The arguments passed to a constructor must be compatible in order and number with the types identified in the parameter list in the constructor signature. 

- (AP 1.13.C.3) When calling constructors, arguments are passed using call by value. **Call by value** initializes the parameters with copies of the arguments.

- (AP 1.13.C.4) A constructor call interrupts the sequential execution of statements, causing the program to first execute the statements in the constructor before continuing. Once the last statement in the constructor has been executed, the flow of control is returned to the point immediately following where the constructor was called.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
