---
layout: notes
title: "📓3.3: Anatomy of a Java Class" 
parent: "3️⃣ Class Creation"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.3](https://runestone.academy/ns/books/published/csawesome2/topic-3-3-anatomy-of-class.html) 

<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong> Create a blank Java program to take your class notes in for the next few lessons. <em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit3-Notes`
4. For the **description**, write: `Class creation for objects`
5. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
6. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
7. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
8. 📝 Take notes in this Codespace during class, writing **code** & **comments** along with the instructor.

</div>

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! **Codespaces** are TEMPORARY editing environments, so you need to COMMIT changes properly in order to update the main **repository** for your program. 

_There are multiple steps to saving in GitHub Codespaces:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

</details>

</html>


---

In Java, a **class** defines what an object knows (its attributes) and what it can do (its behaviors). Understanding the structure of a class is key to object-oriented programming.

## Basic Structure of a Class

A Java class typically contains:

1. **Class header** — specifies the class name and access modifier.
2. **Attributes (fields)** — variables that store the state of the object.
3. **Constructors** — special methods that initialize new objects.
4. **Methods** — define behaviors the object can perform.

---

## Example Class

```java
public class Dog {
    // Attributes
    private String name;
    private int age;

    // Constructor
    public Dog(String dogName, int dogAge) {
        name = dogName;
        age = dogAge;
    }

    // Method
    public void bark() {
        System.out.println(name + " says: Woof!");
    }
}
````

---

## Class Header

* Starts with an **access modifier** (`public`, `private`, or none for package-private).
* Followed by the `class` keyword and the class name (capitalized by convention).

Example:

```java
public class Dog { ... }
```

---

## Attributes

* Declared inside the class but **outside** any methods.
* Usually marked `private` to protect them from direct changes.

---

## Constructors

* Special methods with the **same name** as the class.
* Used to set initial values for attributes.
* No return type (not even `void`).

---

## Methods

* Contain the actions or computations for the object.
* Can return a value or be `void` if nothing is returned.
* Use **dot notation** to call a method on an object:
  `myDog.bark();`

---

## Summary

* Classes group related attributes and methods into a single unit.
* A class usually contains **attributes, constructors, and methods**.
* Access modifiers control visibility and encapsulation.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

Which part of a class is responsible for initializing the attributes when an object is created?

* A. Method
* B. Field
* C. Constructor ✅
* D. Class header

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
