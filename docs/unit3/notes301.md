---
layout: notes
title: "📓3.1: Abstraction & Program Design" 
parent: "3️⃣ Class Creation"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.1](https://runestone.academy/ns/books/published/csawesome2/topic-3-1-abstraction.html) 

---

## Abstraction

**Abstraction** is the process of simplifying complex systems by focusing only on the essential details and ignoring the irrelevant parts. In computer science, abstraction allows us to manage complexity by breaking problems into smaller, more manageable parts.

---

### Everyday Examples

- **Maps** abstract away unnecessary details about the real world to help you navigate.
- **Car dashboard** abstracts the complex mechanics of the engine into simple gauges and lights.
- **Restaurant menus** abstract the cooking process into named dishes.

---

## Abstraction in Programming

In programming, abstraction is achieved by:

- **Using methods** to hide the steps of a task behind a name.
- **Creating classes** that hide implementation details and expose only useful behaviors.
- **Using constants and variables** to avoid repeating raw values.

---

## Why Abstraction Matters

- **Reduces complexity**: You don’t have to remember all the details at once.
- **Increases reusability**: Methods and classes can be used in different programs.
- **Improves maintainability**: You can change how something works without changing how it’s used.

---

## Example: Without Abstraction

```java
System.out.println("Welcome to the program!");
System.out.println("Enter your name:");
Scanner sc = new Scanner(System.in);
String name = sc.nextLine();
System.out.println("Hello, " + name + "!");
````

This code mixes input, output, and logic without clear separation.

---

## Example: With Abstraction

```java
public static void greetUser() {
    System.out.println("Welcome to the program!");
    System.out.println("Enter your name:");
    Scanner sc = new Scanner(System.in);
    String name = sc.nextLine();
    System.out.println("Hello, " + name + "!");
}
```

Now the details are hidden in the `greetUser()` method, and the main program just calls it.

---

## Summary

* Abstraction means focusing on what something does, not how it does it.
* We use **methods, classes, constants, and variables** to abstract details in programming.
* Abstraction helps with complexity, reusability, and maintainability.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

Why is abstraction important in programming?

* A. It removes all code from a program.
* B. It makes programs shorter without improving clarity.
* C. It helps programmers manage complexity by hiding details. ✅
* D. It makes code harder to read.

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
