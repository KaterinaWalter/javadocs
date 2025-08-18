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

Up until now, all of our code has been written as statements in the `main` method, but complex programs are made up of many **methods**. We divide a program into methods to organize the code and avoid repetition. 

<html>
    <dl>
        <dt>Method</dt>
        <dd>A named block of code that performs a task/process when it is called.</dd>
    </dl>
</html>

A **block** of code is any section enclosed in `{ }`. These _named blocks of code_ go by many names in different programming languages: _functions_, _procedures_, _subroutines_, etc. In Java they are called **methods**, as in a method of doing something. 
> In this unit, you will learn how to use methods written by other programmers. In latter units, you will learn how to write your own methods.

<html>
    <dl>
        <dt>Procedural Abstraction</dt>
        <dd>Allowing a programmer to use a method without knowing exactly how it works, i.e. "abstracting away" the details.</dd>
    </dl>
</html>

**Procedural abstraction** means we can use a method that someone else wrote without knowing exactly how it works. We just need to know the method's name to call it and what it needs to do its job.
> For example, we don't need to know how a car exactly works in order to drive. We know that if we hit the brakes, the car will stop; we can still use the brakes even if we don't really know how they exactly work. 

### Method Calls

📣 A **method call** is when the code "calls out" a method's name to run it. It always includes parentheses `()` and may include data (arguments) inside.
```java
methodName();
````
> For example, when we write the statement ``System.out.println("Hello World");``, we are _calling_ the ``println()`` _method_ to print out the text "Hello World".

Every method call is followed by **parentheses**. The parentheses ``()`` after method names are there in case you need to give the method some **parameters/data** to do its job, which we will see in the next lesson.

{:.highlight}
✋ A method call **interrupts** the _sequential execution_ of statements, causing the program to first execute the statements in the method before continuing. Once the last statement in the method has been executed or a `return` statement is executed, the flow of control is returned to the point immediately following where the method was called.

#### Example: Old MacDonald Song
{:.no_toc}

This Java [visualization](https://pythontutor.com/render.html#code=public%20class%20OldMacDonaldSong%0A%7B%0A%20%20%20%20public%20static%20void%20intro%28%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Old%20MacDonald%20had%20a%20farm%22%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20chorus%28%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22E-I-E-I-O%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20intro%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.print%28%22And%20on%20that%20farm%20they%20had%20a%20cow.%22%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.print%28%22With%20a%20moo%20moo%20here%20and%20a%20moo%20moo%20there%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.print%28%22Here%20a%20moo,%20there%20a%20moo,%20everywhere%20moo%20moo%22%29%3B%0A%20%20%20%20%20%20%20%20intro%28%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false) shows how a song can be divided up into methods. Click on the **next** button below the code to step through the code and watch the red arrow jump to the method that is being run. 
> Execution in Java always begins in the ``main`` method in the current class. Then, the **flow of control** skips from method to method as they are called. Notice that when a method ends, it returns to the line right after the method call. 

<div class="task" markdown="block">

Go into edit mode in the **Visualizer** and scroll down to the `main()` method. Add lines of code to the main method for the second verse of the Old MacDonald Song:
1. Call the method `intro()`
2. Print out the line "And on that farm..." with a duck or another animal
3. Call the method `chorus()`
4. Print out the lines with the appropriate animal sounds
5. Call the method `intro()` again

</div>

### Method Header/Signature

When using methods in a library or API, we can look up the **method signature** (or **method header**) in its documentation.  A **method header** is the first line of a method that includes the method name, the return type, and the parameter list of parameters and their data types. The **return type** is the type of value that the method returns; in this lesson, we'll just look at **void** return types which means the method doesn't return anything. The **method signature** is the method header without the return type, just the method name and its parameter list.  The **parameter list** is a list of variables and their data types that are passed to the method when it is called. The parameter list is enclosed in parentheses and separated by commas; it can be empty with no parameters although the parentheses must be present. 

For example, the ``PrintStream`` class documented in [Oracle - Java Documentation](https://docs.oracle.com/javase/8/docs/api/java/io/PrintStream.html) contains the following method signatures for ``println`` that we use in ``System.out.println()``: 

- ``void println()`` which has an empty parameter list with no parameters 
- ``void println(String x)`` which will print out a ``String`` value
- ``void println(int x)`` which will print out an ``int`` value

We can call these methods with the appropriate arguments to print out the value we want. The **argument** is the actual value that is passed to the method when it is called.  Here are the method calls that correspond to the method signatures above:

- ``System.out.println();`` // prints a newline
- ``System.out.println("Hello World");`` // prints a String
- ``System.out.println(42);`` // prints an int

Compare the method signature of ``println(String x)`` with the method call ``println("Hello World");`` below. The method signature contains the method name and the parameter type and variable. The method call contains only the method name and the argument value. The argument must be compatible with the data type of the parameter in the method signature and is saved in the parameter variable when the method is called. Many people use the terms parameter and argument interchangeably.

![image](Figures/method-parts.png)

### Parameters vs Arguments

We can make methods even more powerful and more abstract by giving them parameters for data that they need to do their job. A **parameter** (sometimes called a **formal parameter**) is a variable declared in the header of a method or constructor and can be used inside the body of the method. This allows values or arguments to be passed and used by a method. An **argument** (sometimes called an **actual parameter**) is a value that is passed into a method when the method is called and is saved in the parameter variable. 

* **Parameter**: Variable declared in the method header.
* **Argument**: Actual value passed in when calling the method.

When a method is called, the right method definition is found by checking the **method signature** or **header** at the top of the method definition to match the method name, the number of arguments, the data types for the arguments and the return type. A method signature for a method with parameters consists of the method name and the ordered list of parameter types. A method signature for a method without parameters consists of the method name and an empty parameter list.

```java
// Method signature (parameters)
public static void verse(String animal, String sound) { }

// Method call (arguments)
verse("cow", "moo");
```

![image](Figures/args2paramsFarm.png)
> Here's what that looks like with the two method calls above. The arguments like "cow" and "moo" are saved into the parameter variables ``animal`` and ``sound`` with each method call.

Java uses **call by value** when it passes arguments to methods. This means that a copy of the value in the argument is saved in the parameter variable. Call by value initializes the parameters with copies of the arguments. If the parameter variable changes its value inside the method, the original value outside the method is not changed.

### Overloading Methods

Methods are **overloaded** when they share the same name but have different **parameter** lists. The compiler determines which method to call based on the number and types of **arguments** passed to the method. 

_Example:_ `println()` in `PrintStream`:

* `println()` → prints newline
* `println(String x)` → prints a string
* `println(int x)` → prints an integer

---

## Summary

- (AP 1.9.A.1) A **method** is a named block of code that only runs when it is called. A block of code is any section of code that is enclosed in braces.

- (AP 1.9.A.1) **Procedural abstraction** allows a programmer to use a method by knowing what the method does even if they do not know how the method was written.

- (AP 1.9.B.5) A method call interrupts the sequential execution of statements, causing the program to first execute the statements in the method before continuing. Once the last statement in the method has been executed or a return statement is executed, the flow of control is returned to the point immediately following where the method was called.

- (AP 1.9.A.2) A **parameter** is a variable declared in the header of a method or constructor and can be used inside the body of the method. This allows values or arguments to be passed and used by a method or constructor. 

- (AP 1.9.A.2) A **method signature** for a method with parameters consists of the method name and the ordered list of parameter types. A method signature for a method without parameters consists of the method name and an empty parameter list.

- (AP 1.9.B.3) An **argument** is a value that is passed into a method when the method is called. The arguments passed to a method must be compatible in number and order with the types identified in the parameter list of the method signature. When calling methods, arguments are passed using call by value. 

- (AP 1.9.B.3) **Call by value** initializes the parameters with copies of the arguments.

- (AP 1.9.B.4) Methods are said to be **overloaded** when there are multiple methods with the same name but different signatures.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
