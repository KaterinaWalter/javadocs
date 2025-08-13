---
layout: notes
title: "📓3.4: Writing Constructors" 
parent: "3️⃣ Class Creation"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.4]() 

---

## Constructors

A **constructor** is a special method used to initialize new objects. It sets the starting state of an object’s attributes when it is created.

---

## Key Features

- **Same name as the class**
- **No return type** (not even `void`)
- Can take parameters to set initial values
- Called automatically when `new` is used

---

## Example

```java
public class Dog {
    private String name;
    private int age;

    // Constructor
    public Dog(String dogName, int dogAge) {
        name = dogName;
        age = dogAge;
    }
}
````

Usage:

```java
Dog myDog = new Dog("Buddy", 3);
```

---

## Default Constructors

* If you do not write any constructor, Java provides a **default constructor** with no parameters.
* If you write **any** constructor, Java does **not** create the default one automatically.

Example of default constructor:

```java
public class Dog {
    private String name;
    private int age;

    // Default constructor
    public Dog() {
        name = "Unknown";
        age = 0;
    }
}
```

---

## Multiple Constructors

A class can have multiple constructors with different parameter lists (**constructor overloading**).

```java
public class Dog {
    private String name;
    private int age;

    public Dog() {
        name = "Unknown";
        age = 0;
    }

    public Dog(String dogName) {
        name = dogName;
        age = 0;
    }

    public Dog(String dogName, int dogAge) {
        name = dogName;
        age = dogAge;
    }
}
```

---

## Summary

* Constructors set the **initial state** of an object.
* They have the **same name** as the class and no return type.
* Overloading allows multiple ways to create an object.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

What happens if you write a constructor that takes parameters but do not include a no-argument constructor?

* A. Java creates a no-argument constructor automatically.
* B. You cannot create objects without passing arguments. ✅
* C. The class will not compile.
* D. The default constructor will still be available.

</details>

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
