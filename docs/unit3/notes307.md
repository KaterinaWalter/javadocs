---
layout: notes
title: "📓3.7: Class (static) Variables & Methods" 
parent: "3️⃣ Class Creation"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.7]() 

---

In Java, the keyword `static` means a variable or method belongs to the **class** rather than to individual objects.

## Static Variables

- Shared by all objects of the class.
- Only one copy exists, regardless of how many objects are created.
- Can be used for **constants** or **counters**.

Example:

```java
public class Student {
    private String name;
    private static int studentCount = 0;

    public Student(String n) {
        name = n;
        studentCount++;
    }

    public static int getStudentCount() {
        return studentCount;
    }
}
````

Usage:

```java
Student s1 = new Student("Alex");
Student s2 = new Student("Jordan");
System.out.println(Student.getStudentCount()); // prints 2
```

---

## Static Methods

* Can be called without creating an object.
* Cannot access **instance variables** directly (since they belong to objects, not the class).
* Often used for utility methods.

Example:

```java
public class MathHelper {
    public static int square(int num) {
        return num * num;
    }
}
```

Usage:

```java
int result = MathHelper.square(5); // returns 25
```

---

## Summary

* **Static variables**: Shared data for all objects of the class.
* **Static methods**: Called on the class itself, not an object.
* Useful for constants, counters, and utility methods.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

Which of the following is true about static methods?

* A. They can directly use instance variables.
* B. They can be called without creating an object. ✅
* C. They are slower than instance methods.
* D. They must always return a value.

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
