---
layout: notes
title: "📓1.4: Assignment & Input" 
parent: "1️⃣ Objects & Methods"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.4](https://runestone.academy/ns/books/published/csawesome2/topic-1-4-assignment.html) 

---

## Assignment Statements

**Assignment statements** initialize or change the value stored in a variable using the assignment operator `=`. An assignment statement always has a single variable on the left-hand side. The value of the **expression** on the right is assigned to and stored in the variable on the left.

Instead of saying “equals” for the `=`, say “gets” or “is assigned” to remember that the variable gets the value on the right.  
Example:  
```java
score = 10 * points + 5;
````

Here, `score` is assigned the value of `10 * points + 5`.

<iframe width="700" height="415" src="https://www.youtube.com/embed/MZwIgM__5C8" frameborder="0" allowfullscreen></iframe>

You can set one variable's value to a copy of the value of another variable:

```java
y = x;
```

This does not change the value of the original variable.

---

<div class="task" markdown="block">

**Check Your Understanding**
What will be printed after running this code?

```java
int x = 0;
int y = 1;
int z = 2;
x = y;
y = y * 2;
z = 3;
System.out.println(x);
System.out.println(y);
System.out.println(z);
```

</div>

---

## Data Types in Assignments

Every variable must be assigned a value before it can be used in an expression. That value must be from a compatible data type.

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
The code below will cause a **type mismatch error**. Change one variable’s type so it works, then run it and confirm the output.

```java
int x = 1;
double y = 2.2;
x = 2 * y;
System.out.println(x);
```

</div>

Reference types like `String` can be assigned a new object or `null`:

```java
String str = null;
str = "new object";
```

---

## Adding 1 to a Variable

To increment a score:

```java
score = score + 1;
```

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
Type and run this code. Then try changing it to add `2` instead of `1`.

```java
int score = 0;
System.out.println(score);
score = score + 1;
System.out.println(score);
```

</div>

---

## Input with Variables

Variables allow the same code to work with different values.
We can get user input in Java with the `Scanner` class.

<div class="task" markdown="block">

**Coding Exercise (Codespaces)**
Type and run this code. Try it with different names.

```java
import java.util.Scanner;

System.out.println("Please type in your name:");
Scanner scan = new Scanner(System.in);
String name = scan.nextLine();
System.out.println("Hello " + name);
scan.close();
```

</div>

---

## Groupwork: Coding Challenge – Dog Years

<div class="task" markdown="block">

**Coding Challenge (Codespaces)**
Fill in the missing values and formulas to calculate:

1. Your age from your birth year
2. Your pet’s age from its birth year
3. Your pet’s age in dog years (7 × human years)

Then print all three results with labels.

```java
int currentYear = ;
int birthYear = ;
int dogBirthYear = ;

// Calculate ages
int age = ;
int dogAge = ;
int dogYearsAge = ;

// Print results
```

</div>

<!--
 As a class, brainstorm types of information used by computer programs. What types of data might be entered? How might the information be gathered by the program? (Types of input to programs/apps)
-->

---

## Summary

* **Assignment operator** (`=`) stores the value of the right-hand expression in the left-hand variable.
* Variables must be assigned a compatible type before use.
* A variable is *initialized* the first time it gets a value.
* Reference types can be `null`.
* Expressions have a type based on the types of values and operators.
* The `Scanner` class is one way to get text input.

---

## AP Practice

<div class="task" markdown="block">

**Multiple Choice**
What is printed?

```java
int a = 5;
int b = a / 2;
double c = a / 2.0;
double d = 5 + a / b * c - 2;
System.out.println(d);
```

A. `8`
B. `8.0` ✅
C. `10.5`
D. Incompatible type error

</div>

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
