---
layout: notes
title: "📓3.6: Methods that Pass or Return Objects" 
parent: "3️⃣ Class Creation"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.6]() 

---

## Methods and Object References

When you pass objects to methods in Java, you are passing **references** to those objects, not the actual copies. This means methods can modify the object’s state.

---

## Passing Primitive Types

Primitive types (`int`, `double`, `boolean`, etc.) are **passed by value**—the method gets a copy of the value, and changes do not affect the original.

Example:

```java
public static void changeNumber(int x) {
    x = 10;
}

int num = 5;
changeNumber(num);
System.out.println(num); // still 5
````

---

## Passing Objects

When you pass an object, the **reference** is passed by value, meaning both the method parameter and the original variable point to the same object.

Example:

```java
public static void renameDog(Dog d) {
    d.setName("Max");
}

Dog myDog = new Dog("Buddy", 3);
renameDog(myDog);
System.out.println(myDog.getName()); // prints "Max"
```

---

## Reassigning the Reference

If a method **reassigns** the parameter to a new object, the original variable is unaffected.

Example:

```java
public static void newDog(Dog d) {
    d = new Dog("Charlie", 2);
}

Dog myDog = new Dog("Buddy", 3);
newDog(myDog);
System.out.println(myDog.getName()); // still "Buddy"
```

---

## Summary

* **Primitives**: Passed by value (copy of the data).
* **Objects**: Passed by value of the **reference**—methods can change the object's state.
* Reassigning the parameter inside the method does not change the original reference.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

What happens when you pass an object to a method and modify one of its attributes inside the method?

* A. The original object is unchanged.
* B. The original object’s attribute changes. ✅
* C. A copy of the object is changed.
* D. The object is destroyed after the method finishes.

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
