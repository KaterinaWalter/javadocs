---
layout: notes
title: "📓3.5: Writing Methods" 
parent: "3️⃣ Class Creation"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.5]() 

---

## Methods

A **method** is a named block of code that performs a specific task. Methods are used to define the behaviors of a class and can be called from other parts of a program.

---

## Why Use Methods?

- **Reusability**: Write code once, use it multiple times.
- **Organization**: Break large programs into smaller, manageable pieces.
- **Readability**: Clear names make code easier to understand.

---

## Method Structure

```java
accessModifier returnType methodName(parameters) {
    // method body
}
````

**Example:**

```java
public void bark() {
    System.out.println("Woof!");
}
```

---

## Returning Values

Some methods compute a result and return it.

```java
public int getAge() {
    return age;
}
```

The `returnType` matches the type of value returned. Use `void` if the method does not return anything.

---

## Parameters

* Allow you to pass information into a method.
* Declared in parentheses after the method name.

Example:

```java
public void setName(String newName) {
    name = newName;
}
```

---

## Calling Methods

Use **dot notation**:

```java
Dog myDog = new Dog("Buddy", 3);
myDog.bark();
myDog.setName("Max");
System.out.println(myDog.getAge());
```

---

## Summary

* Methods define the actions a class can perform.
* Use parameters to pass information and return types to send results back.
* Use `void` when no value is returned.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

Which of the following correctly defines a method that takes no parameters and returns nothing?

* A. `public bark() { ... }`
* B. `public void bark { ... }`
* C. `public void bark() { ... }` ✅
* D. `public bark(void) { ... }`

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
