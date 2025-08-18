---
layout: notes
title: "📓3.1: Abstraction & Program Design" 
parent: "3️⃣ Class Creation"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.1](https://runestone.academy/ns/books/published/csawesome2/topic-3-1-abstraction.html) 

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
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, writing **code** & **comments** along with the instructor.

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

## Abstraction

**Abstraction** is the process of simplifying complex systems by focusing only on the essential details and ignoring the irrelevant parts. In computer science, abstraction allows us to manage complexity by breaking problems into smaller, more manageable parts.

---

### Everyday Examples

- **Maps** abstract away unnecessary details about the real world to help you navigate.
- **Car dashboard** abstracts the complex mechanics of the engine into simple gauges and lights.
- **Restaurant menus** abstract the cooking process into named dishes.

---

## Abstraction in Programming

In programming, abstraction is achieved by:

- **Using methods** to hide the steps of a task behind a name.
- **Creating classes** that hide implementation details and expose only useful behaviors.
- **Using constants and variables** to avoid repeating raw values.

---

## Why Abstraction Matters

- **Reduces complexity**: You don’t have to remember all the details at once.
- **Increases reusability**: Methods and classes can be used in different programs.
- **Improves maintainability**: You can change how something works without changing how it’s used.

---

## Example: Without Abstraction

```java
System.out.println("Welcome to the program!");
System.out.println("Enter your name:");
Scanner sc = new Scanner(System.in);
String name = sc.nextLine();
System.out.println("Hello, " + name + "!");
````

This code mixes input, output, and logic without clear separation.

---

## Example: With Abstraction

```java
public static void greetUser() {
    System.out.println("Welcome to the program!");
    System.out.println("Enter your name:");
    Scanner sc = new Scanner(System.in);
    String name = sc.nextLine();
    System.out.println("Hello, " + name + "!");
}
```

Now the details are hidden in the `greetUser()` method, and the main program just calls it.

---

## Summary

* Abstraction means focusing on what something does, not how it does it.
* We use **methods, classes, constants, and variables** to abstract details in programming.
* Abstraction helps with complexity, reusability, and maintainability.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

Why is abstraction important in programming?

* A. It removes all code from a program.
* B. It makes programs shorter without improving clarity.
* C. It helps programmers manage complexity by hiding details. ✅
* D. It makes code harder to read.

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
