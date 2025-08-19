---
layout: notes
title: "📓1.12: Java Objects" 
parent: "1️⃣ Objects & Methods"
nav_order: 13
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.12](https://runestone.academy/ns/books/published/csawesome2/topic-1-12-objects.html) 

---

## Objects: Instances of Classes

Java is an **object-oriented programming** language. That means that one of the primary ways of designing and organizing a Java program is in terms of **objects**. Objects combine _data_, and the _code that operates on that data_, into a single unit.

To create objects, we first define a **class** which provides a _template_ for creating the objects. 
> In Java, _all_ programs are built out of classes. This is why every Java program starts with the keywords `public class`.

<div class="task" markdown="block">

🐈‍⬛ Let's say you wanted to create a virtual model of a cat café, populated with tons of kitties of all sizes and colors. You can start by writing a `Cat` **class** that defines a generic cat **object**. To do this, you need to think very _generally_ about what cats are, what characteristics they have, and what they can do. 

💬 **Discuss:** 
* What are some common _attributes_ of cats?
* What are some _behaviors_?

![image-small](Figures/catsLabelled.png)
 
</div>

In this unit, you will learn the vocabulary of object-oriented programming and how to _create_ and _use_ objects of a class written for you. In later units, you will learn to write your own classes.

### Classes & Objects

{:.highlight}
A class is a **template** for a specific kind of object (of a particular _classification_). You can also think of a class as **defining a custom data type**. 

_Real-life analogies:_
* A **blueprint** of a house used to construct multiple homes
* A **cookie cutter** used to create cookies
  > The cookie cutter (**class**) can be used to create as many cookies (**objects**) as you want. The cookies are the same shape, but can have different decorations (_attribute values_).

![image-small](Figures/blueprint.png)
![image-small](Figures/cookieCutterLabelled.png)

In this lesson, we will use the class ``Turtle`` to make animated turtle objects. Just like you use ``int`` to declare variables that hold numbers, you can use ``Turtle`` to declare many variables, animated turtle objects, who are **instances** of the ``Turtle`` class. 

_Example:_
```java
// Declaring 2 Turtle-type objects called yertle and myrtle
Turtle yertle;
Turtle myrtle;
```

#### Video: Classes & Objects
{:.no_toc}

<iframe width="650" height="415" src="https://www.youtube.com/embed/64DOwDu5SVo" frameborder="0" allowfullscreen></iframe>

### Attributes & Behaviors

A **class** defines:

<html>
  <dl>
    <dt>Attributes/Fields</dt>
    <dd><strong>Data</strong> the object “knows” (e.g., <code>name</code>, <code>age</code>, <code>color</code></dd>
    <dt>Behaviors/Methods</dt>
    <dd><strong>Actions</strong> the object “does” (e.g., <code>meow()</code>, <code>eatTreats()</code>) or what can be done to it.</dd>
  </dl>
</html>

#### Video: Attributes & Behaviors
{:.no_toc}

_Example:_ The `Belt` class described in the video below has 3 instance variables (attributes), and each belt object can have different values for them.

<iframe width="650" height="415" src="https://www.youtube.com/embed/Y9vn6u3901Y" frameborder="0" allowfullscreen></iframe>

#### CSAwesome Activities: Turtle Class

A **class** like `Turtle` defines the data (**attributes/fields**) and **behaviors/methods** shared by all turtle-type **objects** you create. 

![image-small](Figures/turtleOOD.png)

> This diagram of a turtle shows some of the generic `Turtle` **attributes** like `name`, `width`, `height`, `color` in the body of the turtle and its **methods** like `forward()`, `backward()`, written around the turtle. 

<div class="task" markdown="block">

🐢 To explore the concepts from this lesson in code, we'll play around with the `Turtle` class on the CSAwesome website instead of taking notes.  

👉 **GO TO:** <a href="https://runestone.academy/ns/books/published/csawesome2/topic-1-12-objects.html"><button class="btn">CSAwesome Topic 1.12</button></a>, **SIGN IN** to your account, and complete all the turtle-related **coding activities/challenges** with a partner. 

</div>

---

## Summary

- (AP 1.12.A.1) A **class** defines a new data type (a classification). It is the formal implementation, or blueprint, of the *attributes* and *behaviors* of the objects of that class.

- (AP 1.12.A.1) An **object** is a specific **instance** of a class with defined attributes. Objects are declared as variables of a class type.

- (AP 1.12.B.1) A variable of a reference type holds an object reference, which can be thought of as the memory address of that object.

- An **attribute** or **instance variable** is data the object knows about itself. For example a turtle object knows the direction it is facing or its color.

- A **behavior** or **method** is something that an object can do.  For example a turtle object can go forward 100 pixels.

- (AP 1.12.A.2) All classes in Java are subclasses of the **Object** class.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
