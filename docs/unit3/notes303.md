---
layout: notes
title: "📓3.3: Anatomy of a Java Class" 
parent: "3️⃣ Class Creation"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.3](https://runestone.academy/ns/books/published/csawesome2/topic-3-3-anatomy-of-class.html) 

---

In Java, a **class** defines what an object knows (its attributes) and what it can do (its behaviors). Understanding the structure of a class is key to object-oriented programming.

## Basic Structure of a Class

A Java class typically contains:

1. **Class header** — specifies the class name and access modifier.
2. **Attributes (fields)** — variables that store the state of the object.
3. **Constructors** — special methods that initialize new objects.
4. **Methods** — define behaviors the object can perform.

---

## Example Class

```java
public class Dog {
    // Attributes
    private String name;
    private int age;

    // Constructor
    public Dog(String dogName, int dogAge) {
        name = dogName;
        age = dogAge;
    }

    // Method
    public void bark() {
        System.out.println(name + " says: Woof!");
    }
}
````

---

## Class Header

* Starts with an **access modifier** (`public`, `private`, or none for package-private).
* Followed by the `class` keyword and the class name (capitalized by convention).

Example:

```java
public class Dog { ... }
```

---

## Attributes

* Declared inside the class but **outside** any methods.
* Usually marked `private` to protect them from direct changes.

---

## Constructors

* Special methods with the **same name** as the class.
* Used to set initial values for attributes.
* No return type (not even `void`).

---

## Methods

* Contain the actions or computations for the object.
* Can return a value or be `void` if nothing is returned.
* Use **dot notation** to call a method on an object:
  `myDog.bark();`

---

## Summary

* Classes group related attributes and methods into a single unit.
* A class usually contains **attributes, constructors, and methods**.
* Access modifiers control visibility and encapsulation.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

Which part of a class is responsible for initializing the attributes when an object is created?

* A. Method
* B. Field
* C. Constructor ✅
* D. Class header

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
