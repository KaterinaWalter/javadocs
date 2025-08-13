---
layout: notes
title: "📓3.8: Scope & Access" 
parent: "3️⃣ Class Creation"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.8]() 

---


**Scope** refers to where a variable can be _accessed_ in a program.  
**Access modifiers** determine which parts of a program can use a variable or method.



## Variable Scope

- **Local variables**: Declared inside a method, only accessible within that method.
- **Instance variables**: Declared inside a class but outside any method, accessible to all methods in that class.
- **Class (static) variables**: Declared with `static`, shared by all objects.

Example:

```java
public class Example {
    private int instanceVar = 10; // instance scope

    public void method() {
        int localVar = 5; // local scope
        System.out.println(localVar);
    }
}
````

---

## Access Modifiers

* `public`: Accessible from any other class.
* `private`: Accessible only within the same class.
* `protected`: Accessible within the same package and subclasses.
* No modifier: Package-private (accessible only within the same package).

---

## Example

```java
public class Person {
    public String name;       // public: accessible anywhere
    private int age;          // private: only inside this class

    public Person(String n, int a) {
        name = n;
        age = a;
    }

    public int getAge() {     // provides controlled access
        return age;
    }
}
```

---

## Best Practices

* Keep variables **private** and use getter/setter methods to control access.
* Use the most restrictive access modifier possible to reduce unintended interactions.

---

## Summary

* **Scope**: Where a variable exists and can be used.
* **Access modifiers**: Control who can see or modify a variable or method.
* Favor `private` for encapsulation and maintainability.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

What is the scope of a variable declared inside a method?

* A. Class scope
* B. Local scope ✅
* C. Global scope
* D. Instance scope

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
