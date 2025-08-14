---
layout: notes
title: "📓1.1: Algorithms, Programming, Compilers" 
parent: "1️⃣ Objects & Methods"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Lesson 1.1](https://runestone.academy/ns/books/published/csawesome2/topic-1-1-intro-algorithms.html) 

---

What do Android phones, Minecraft, and Netflix have in common? They're all coded in Java! Many of the apps you use in an Android phone or tablet are written in Java. If you've used App Inventor before, those apps are translated to Java before they are run on a phone or tablet. Netflix uses Java for some of its software too. Java is a **programming language** that is used worldwide to create software that we all use.

<iframe width="700" height="400" src="https://www.youtube.com/embed/Fc-BQzPbJmU" frameborder="0" allowfullscreen></iframe>

---

## Algorithms

**Algorithms** define step-by-step processes in order to complete a task or solve a problem. Algorithms are used in many areas of life, not just in computer science. For example, a recipe is an algorithm for cooking a meal. A set of directions to a friend's house is an algorithm for getting there. In computer science, algorithms are used to solve problems and to create software.

Algorithms can be used to plan and design code by writing the steps down in English or another language or in a diagram or in **pseudocode**, which is writing simplified code on paper. It's important to plan the algorithm step by step where each step can be implemented by a line of code. **Sequencing** defines an order for when steps in a process are completed. Steps in a process are completed one at a time.

<div class="task" markdown="block">

**Check Your Understanding**  
Write an algorithm for someone (maybe a robot) to make a peanut butter and jelly sandwich. Include at least 5 precise steps in order. Have someone act it out. Were your instructions precise enough?

</div>

---

## First Java Program

Every program in Java is written as a **class**. Java is an **object-oriented language**, and **classes** and **objects** created from classes are the basic building blocks in object-oriented programming.

Inside the class, there can be a **main method** that starts the program. A **method** is a block of code that performs a specific task. The main method is the entry point for the program. In other programming languages, methods are called functions or procedures.

Here’s a template for a simple Java program with a main method:

```java
public class MyClass
{
    public static void main(String[] args)
    {
        // Put your code here!
    }
}
````

> **Note:** In Java every open curly brace `{` must have a matched close curly brace `}`.

<div class="task" markdown="block">

**Coding Exercise**
Type out this line of code in your program in GitHub Codespaces, press **Run**, note the output, then change it to print your name.

```java
System.out.println("Hi there!");
```

</div>

---

## Compiling and Running Java Programs

An **Integrated Development Environment (IDE)** is often used to write programs because it provides tools for a programmer to write, compile, and run code.

Computers don't actually speak Java, so we have to **compile** (translate) Java source files into class files, which a computer can understand and run. A **compiler** checks your code for errors and translates it to executable code.

---

## Java Keywords

**Keywords** are reserved words that have special meaning in Java. Keywords such as `public`, `class`, and `void` must be in lowercase, but class names such as `System` and `String` are capitalized.

Lines in a Java program that express a complete action must end with a semicolon (`;`). Such a line is called a **statement**.

---

## Syntax Errors and Debugging

**Syntax errors** are reported by the compiler if your Java code is not correctly written. Examples:

* Missing semicolon `;`
* Missing closing curly brace `}`
* Missing closing quote `"`

Informally, a syntax error is called a **bug**, and the process of removing errors is called **debugging**.

![Grace Hopper's log showing a real bug, 1947](Figures/firstbug.jpg)

---

## Reading Error Messages

Example error message:

```
FirstClass.java:5: error: unclosed string literal
       System.out.println("Hi there!);
                          ^
1 error
```

The filename, line number, error type, and caret `^` help locate the issue.

<div class="task" markdown="block">

**Coding Exercise: Compile Time Error 1**
In GitHub Codespaces, type the code below, run it, and look at the error message. Then fix it so it prints `Hi there!`.

```java
System.out.println("Hi there!);
```

</div>

<div class="task" markdown="block">

**Coding Exercise: Compile Time Error 2**
In GitHub Codespaces, type the code below, run it, and look at the error message. Then fix it so it prints `Hi there!`.

```java
System.out.println("Hi there!";
```

</div>

<div class="task" markdown="block">

**Coding Exercise: Compile Time Error 3**
This program has two errors. In GitHub Codespaces, type the line below, run it, and fix both errors so it prints `Hi there!`.

```java
system.out.println("Hi there!")
```

</div>

---

## Run-time Errors

**Run-time errors** occur after compilation when the program is running.
Example: dividing by zero.

<div class="task" markdown="block">

**Coding Exercise**
In GitHub Codespaces, type these two lines into your program and run it. What happens? Why?

```java
System.out.println("It makes no sense to divide a number by zero!");
System.out.println(3/0);
```

</div>

A **logic error** is a mistake in the algorithm or program that causes unexpected behavior.

---

## Comments

In Java:

* Single-line comment: `// comment`
* Multi-line comment:

  ```java
  /* comment text */
  ```

Example:

```java
/* MyClass.java
   Programmer: My Name
   Date:
*/
int max = 10; // this keeps track of the max score
```

---

## Summary

* **Algorithms**: Step-by-step processes for solving a problem.
* **Sequencing**: The order of steps.
* **IDE**: Tool to write, compile, and run code.
* **Compiler**: Translates Java into code the computer can run.
* **Syntax Error**: Rules of the language not followed.
* **Logic Error**: Algorithm causes incorrect results.
* **Run-time Error**: Error while running the program.
* **Exception**: A run-time error that interrupts program execution.

Basic Java program:

```java
public class MyClass
{
    public static void main(String[] args)
    {
        System.out.println("Hi there!");
    }
}
```

---

## AP Practice

<div class="task" markdown="block">

Consider:

```java
System.out.println("Roses are red, ")      // Line 1;
System.out.println("Violets are blue, ")  // Line 2;
System.out.println("Unexpected '}' on line 32. ")  // Line 3;
```

To produce:

```
Roses are red,
Violets are blue,
Unexpected '}' on line 32.
```

**Question:** Which change will make this output correct?
✅ **Answer:** Put the semicolon after the `)` on each line, not inside the comment.

</div>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
