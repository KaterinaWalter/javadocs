---
layout: notes
title: "📓1.9: Method Signatures" 
parent: "1️⃣ Objects & Methods"
nav_order: 10
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.9](https://runestone.academy/ns/books/published/csawesome2/topic-1-9-method-signatures.html) 

---

<!--
"Have you ever had to tell two people with the same first name apart? How did you do it?"
Relate this to how Java tells methods apart using their signatures.

-->

## Methods and Procedural Abstraction

Up until now, all of our code has been in the `main` method, but complex programs are made up of many methods.  

A **method** is a named block of code that performs a task when it is called. (A **block** of code is any section enclosed in `{ }`.) In Java they are called *methods* — as in a method of doing something.

**Procedural abstraction** allows a programmer to use a method without knowing exactly how it works — just like you can drive a car without knowing every engineering detail.

---

## Method Calls

We divide a program into methods to organize the code and avoid repetition.  
A **method call** is when the code "calls out" the method's name to run it. It always includes parentheses `()` and may include data (arguments) inside.

Example:

```java
// Method call
methodName();
````

When a method ends, control returns to the line immediately after the method call.

Every method call is followed by **parentheses**. The parentheses ``()`` after method names are there in case you need to give the method parameters (data) to do its job, which we will see in the next lesson. You must always include the parentheses after the method name.


{:.important}
📣 `object.method();` is used to **call** an object's method!

{:.important}
📣 `object.method(arguments);` is used to call an object's method _and_ provide some **arguments** (actual parameters) to do its job.

### Procedural Abstraction

**Procedural abstraction** allows a programmer to use a method and not worry about the details of how it exactly works. For example, we know that if we hit the brakes, the car will stop, and we can still use the brakes even if we don't really know how they work.

You will learn to write your own methods in Unit 5. In this unit, you should be able to **use** methods already written for you and figure out what they do. 

---

### **Practice: Adding Another Verse to a Song**

<div class="task" markdown="block">

Type this in your Codespace, press run.
Scroll down to the section marked **TODO** and add lines to create a second verse about a duck (or another animal) using the existing `intro()` and `chorus()` methods.

```java
public static void intro() {
    System.out.println("Old MacDonald had a farm");
    chorus();
}

public static void chorus() {
    System.out.println("E-I-E-I-O");
}

public static void main(String[] args) {
    intro();
    System.out.println("And on that farm they had a cow.");
    chorus();
    System.out.println("With a moo moo here and a moo moo there");
    System.out.println("Here a moo, there a moo, everywhere a moo moo");
    
    // TODO:
    // 1. Call intro()
    // 2. Print "And on that farm..." with your animal
    // 3. Call chorus()
    // 4. Print lines with the correct sounds
    // 5. Call intro() again
}
```

</div>

---

## Method Signature, Parameters, and Arguments

A **method header** (or signature with return type) contains:

* **Return type**: The type of value returned (or `void` if nothing is returned).
* **Method name**
* **Parameter list**: variables and their data types.

The **method signature** (in strict terms) is the method name + parameter list (no return type).

Example from `PrintStream`:

* `void println()`
* `void println(String x)`
* `void println(int x)`

### Parameters vs Arguments

* **Parameter**: Variable declared in the method header.
* **Argument**: Actual value passed in when calling the method.

```java
// Method header (parameters)
public static void verse(String animal, String sound) { }

// Method call (arguments)
verse("cow", "moo");
```

---

### **Practice: Add a Verse with Parameters**

<div class="task" markdown="block">

Type this in your Codespace, press run.
Scroll to `main()` and add:

1. `verse("goose", "honk");` then `intro();`
2. Another `verse()` call with an animal/sound of your choice, then `intro();`

```java
public static void intro() {
    System.out.println("Old MacDonald had a farm");
    chorus();
}

public static void chorus() {
    System.out.println("E-I-E-I-O");
}

public static void verse(String animal, String sound) {
    System.out.println("And on this farm, they had a " + animal);
    chorus();
    System.out.println("With a " + sound + " " + sound + " here and a " + sound + " " + sound + " there");
    System.out.println("Here a " + sound + ", there a " + sound + ", everywhere a " + sound + " " + sound);
}

public static void main(String[] args) {
    intro();
    verse("cow","moo");
    intro();
    verse("duck","quack");
    intro();
    // TODO: Add goose + honk, intro, and one more animal + sound
}
```

</div>

---

## Overloading

Methods are **overloaded** when they share the same name but have different parameter lists.

Example: `println()` in `PrintStream`:

* `println()` → prints newline
* `println(String x)` → prints a string
* `println(int x)` → prints an integer

---

## Group Challenge: Song with Parameters

<div class="task" markdown="block">

Write a program that prints 3 verses of *The Ants Go Marching*.
Use `chorus(String num)` and `verse(String num, String action)` methods.
Call them in `main()` with:

1. `"one", "suck a thumb"`
2. `"two", "tie a shoe"`
3. `"three", "climb a tree"`

```java
public static void chorus(String num) {
    System.out.println("The ants go marching " + num + " by " + num + ", hurrah, hurrah");
    System.out.println("The ants go marching " + num + " by " + num + ", hurrah, hurrah");
}

public static void verse(String num, String action) {
    System.out.println("The ants go marching " + num + " by " + num);
    System.out.println("The little one stops to " + action);
    System.out.println("And they all go marching down to the ground");
    System.out.println("To get out of the rain, BOOM! BOOM! BOOM! BOOM!\n");
}

public static void main(String[] args) {
    // TODO: Call chorus and verse 3 times with correct arguments
}
```

</div>

---

## Summary

* **Method**: Named block of code that runs when called.
* **Procedural abstraction**: Use a method without knowing the details of its implementation.
* **main method**: Where program execution begins.
* **Method signature**: Name + ordered list of parameter types.
* **Parameter**: Variable in the method header.
* **Argument**: Value passed when calling a method.
* **Call by value**: Java passes copies of argument values to parameters.
* **Overloading**: Multiple methods with the same name but different parameter lists.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
