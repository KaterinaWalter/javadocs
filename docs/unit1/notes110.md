---
layout: notes
title: "📓1.10: Calling Class Methods" 
parent: "1️⃣ Objects & Methods"
nav_order: 11
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.10](https://runestone.academy/ns/books/published/csawesome2/topic-1-10-calling-class-methods.html) 

---

## Static (Class) Methods

Most of the methods we’ve used so far are `static` methods, also called **class methods**. These methods are associated with the _general class_, which also means that there is **only one copy** of the method. 

{:.highlight}
🎈 A **static (class) method** is like a school-wide event or rule (e.g., the fire drill procedure). There’s only _one copy of the instructions_, and it applies to _everyone_ in the school equally. 

> In contrast: an **instance (non-static) method** is like a student’s personal schedule (e.g., “Sarah goes to math class at 10 AM”). Each student has their _own individual copy_ of that schedule, and you’d need to ask the specific student to know what it is. _More about these types of methods later!_

The `main` method is always `static`, as there can only be **one copy** per Java class.
> The main method is like the school’s opening bell: one universal event that always happens the same way to start the day, no matter which students are present.

#### Template for a Static Method Definition
{:.no_toc}

In the **method header**, the keyword `static` is included before the **return type**: 

```java
// static method header
public static returnType methodName(parameters) {
    // method body
}
```

## Non-Void Methods

Up until now, we have used the keyword `void` as the return type for methods that **do not return a value**. Think of a void method like giving an instruction without expecting anything back.
> _Example:_ If you tell your friend “Turn on the light”, they do it, but they don’t hand you anything in return. That’s a **void** method – it performs an _action_, but there’s no “output” to capture.

However, many methods are **non-void**: think of these kind of like mathematical functions that calculate and `return` a result, given some arguments. 
> _Example:_ If you ask your friend “What’s the temperature outside?”, they give you an answer (a value). That’s a **non-void** method – it _returns something_ you can use.

| ⬛️ **Void Methods** | 🎁 **Non-Void Methods** |
| ------------------  | ----------------------- |
| DO NOT return a value  | `return` a value (output) |
| "Just do an action"  | "Do something AND give me a result" |

![image](Figures/function.png)

In the next lesson, we will look at the `Math` library in Java, but consider a simple **non-void** method that calculates area given length and width:

```java
public static int calcArea(int length, int width) {
    int area = length * width;
    return area;
}
```
> For example, the **method call** ``calcArea(2,3)`` would **return** `6`. What is the _data type_ returned?

<div class="imp" markdown="block">
    
➡️ The `return` statement in a **non-void** method:

* Sends a **value** back to the caller (_output_).
* Must return a **data type** that matches the return type in the method header.
* Ends method execution immediately.

📣 When **calling** non-void methods, you must _do something_ with the `return` value. You can either **store** the output in a variable, or **use it in an expression** directly: 

```java
int y = calcArea(3,5); // store return value
System.out.println(y); 
System.out.println(calcArea(4,2)); // use directly
```

</div>

### Common Errors with Non-Void Methods

1. **Forgetting to use the return value** — If a method returns a value, assign it to a variable or use it in an expression.
2. **Mismatched types** — Ensure the type you store the return value in matches the method’s return type.
3. **Incorrect argument types/order** — Match the method signature exactly.

### Calling Methods from Another Class

In the examples above, we **called** the methods just by using the method name since they were _defined in that same class_. 

However, if we call a method from a _different class_, another Java program, we need to include its **class name**. Class methods are typically called using the class name along with the **dot operator (`.`)**.
> For example, if the ``calcArea`` method is in a class called ``MathFunctions``, we could call it as ``MathFunctions.calcArea()``.  

---

## Summary

- (AP 1.10.A.1) Class methods are associated with the class (not instances of the class which we will see in later lessons). 

- (AP 1.10.A.2) Class methods include the keyword **static** in the header before the method name.

- (AP 1.9.B.1) A void method does not have a return value and is therefore not called as part of an expression.

- (AP 1.9.B.2) A **non-void method** returns a value that is the same type as the **return type** in the header. 

- (AP 1.9.B.2) To use the return value when calling a non-void method, it must be stored in a variable or used as part of an expression. 

- Common errors with methods are mismatches in the order or type of arguments, return values, and forgetting to do something with the value returned from a method. When you call a method that returns a value, you should do something with that value like assigning it to a variable or printing it out.

- (AP 1.10.A.2) Class methods are typically called using the class name along with the dot operator. When the method call occurs in the defining class, the use of the class name is optional in the call.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
