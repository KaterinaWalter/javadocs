---
layout: notes
title: "📓3.9: this Keyword" 
parent: "3️⃣ Class Creation"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.9](https://runestone.academy/ns/books/published/csawesome2/topic-3-9-this.html) 

---

In Java, the keyword `this` refers to the **current object** — the one whose method or constructor is being executed.

---

## Uses of `this`

### 1. Referencing Instance Variables

When a method parameter has the same name as an instance variable, `this` can be used to distinguish between them.

```java
public class Dog {
    private String name;

    public Dog(String name) {
        this.name = name; // 'this.name' refers to the instance variable
    }
}
````

---

### 2. Calling Another Constructor

`this()` can be used inside a constructor to call another constructor in the same class.

```java
public class Dog {
    private String name;
    private int age;

    public Dog(String name) {
        this(name, 0); // calls the two-parameter constructor
    }

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

---

### 3. Passing the Current Object

You can pass `this` as an argument to another method or constructor.

```java
public class Dog {
    public void register() {
        Registry.addDog(this); // passes the current Dog object
    }
}
```

---

## Why `this` Is Useful

* Clarifies references when variable names conflict.
* Allows constructor chaining.
* Makes it easier to pass the current object to other methods or classes.

---

## Summary

* `this` refers to the **current object**.
* Use it to **distinguish variables**, **call other constructors**, or **pass the object**.
* Improves clarity and flexibility in object-oriented code.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

In the constructor `public Dog(String name) { this.name = name; }`, what does `this.name` refer to?

* A. The method parameter `name`
* B. The instance variable `name` ✅
* C. A local variable `name`
* D. A static variable `name`

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
