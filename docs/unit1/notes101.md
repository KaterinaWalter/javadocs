---
layout: notes
title: "📓1.1: Algorithms, Programming, Compilers" 
parent: "1️⃣ Objects & Methods"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.1](https://runestone.academy/ns/books/published/csawesome2/topic-1-1-intro-algorithms.html) 

---

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit1A-Notes`
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

☕️ What do Android phones, Minecraft, and Netflix have in common? They're all coded in `Java`! Many of the apps you use in an Android phone or tablet are written in Java. Netflix uses Java for some of its software too. Java is a **programming language** that is used worldwide to create software that we all use.


#### INTRODUCTORY ACTIVITY
{:.no_toc}

<div class="task" markdown="block">

1. Form pairs, then pick a role:
  - 🗣️ **Instructor**: Will give simple verbal instructions on how to draw some _secret thing_, without revealing what the thing is.
  - ✍️ **Drawer**: Will follow the instructions to create the drawing _exactly_ as the instructor describes.
2. **DRAWERS** leave the room while **INSTRUCTORS** are told about the secret thing to draw. 
3. When the partner returns, move your chairs so you are sitting **back-to-back** with your teammate.  
4. If you are the **DRAWER**:  
   - Have a blank sheet of paper and a pencil or pen ready.  
   - You will not know what you are drawing.  
   - DO NOT ask any questions during the instructions!  
5. If you are the **INSTRUCTOR**:  
   - Give directions step-by-step, as detailed as possible.
   - You can only describe _shapes_, _sizes_, and _positions_. 
   - DO NOT use any specific words for objects, body parts, comparisons, etc!!!
6. Once the drawing is complete, **hand it in**, then move your chairs back to normal.
7. 💬 As a group, go through each of the drawings and **discuss**:  
   - Was the drawing _correct_? Can you tell what it is?
   - How _precise_ did the instructions need to be?  
   - Did the _order_ of the instructions matter?  
   - What problems came from _vague_ language?

</div>


## Algorithms

**Algorithms** define _step-by-step processes_ in order to complete a specific task or solve a problem in a certain way. Algorithms are used in many areas of life, not just in computer science: 
* A recipe is an algorithm for cooking a meal.
* A set of directions to a friend's house is an algorithm for getting there.

Algorithms can be used to plan and design code by writing the steps down in English or another language or in a diagram or in **pseudocode**, which is writing simplified code on paper. It's important to plan the algorithm step by step where each step can be implemented by a line of code. **Sequencing** defines an order for when steps in a process are completed. Steps in a process are _completed one at a time_.

<!--
<div class="task" markdown="block">

**Check Your Understanding**  
Write an algorithm for someone (maybe a robot) to make a peanut butter and jelly sandwich. Include at least 5 precise steps in order. Have someone act it out. Were your instructions precise enough?

</div>
-->

## Java Programs (Classes)

Every program in Java is written as a **CLASS**. Java is an **object-oriented language**, and **classes** and **objects** created from classes are the basic building blocks in object-oriented programming.

Inside the class, there can be a **main method** that starts the program. 
* A **method** is a block of code that performs a specific task.
* In other programming languages, methods are called _functions_ or _procedures_.
* The `main()` method is the _entry point_ for the program.

<div class="important" markdown="block">
  
Template for a simple Java program with a `main()` method:

```java
public class MyClass
{
    public static void main(String[] args)
    {
        System.out.println("Hi there!");
    }
}
```

> **Note:** In Java every open curly brace `{` must have a matched close curly brace `}`.

</div>

### Compiling and Running Java Programs

An **Integrated Development Environment (IDE)** is often used to write programs because it provides tools for a programmer to write, compile, and run code.

{:.highlight}
Computers don't actually speak Java, so we have to **compile** (_translate_) our `.java` source files into `.class` files, which a computer can understand and run. A **compiler** checks your code for errors and translates it to _executable_ code.

> _From the intro activity:_
> 
> * The 🗣️ **INSTRUCTOR** represents the <span class="highlighter">source code</span> - all the statements we write in a `.java` file.
> * The ✍️ **DRAWER** represents the <span class="highlighter">execution</span> of a program.
> * The way the drawer _interprets_ the instructions is like the <span class="highlighter">compiler</span>.  

### Java Syntax Overview

Every programming language has its own **syntax**, which is like its "grammar" rules. Here are some of Java's most important rules: 

* **Single-line comment**: `// comment`
* **Multi-line comment**:
  ```java
  /* comment text */
  ```
* **Keywords** are _reserved_ words that have special meaning in Java. Keywords such as `public`, `class`, and `void` must be in lowercase, but class names such as `System` and `String` are capitalized.

* Lines in a Java program that express a complete action must end with a semicolon (`;`). Such a line is called a **statement**.
  > You can think of the semicolon (``;``) in Java like a period (``.``) in English. The same way you use a period to end a sentence in English, you use a semicolon to end a statement in Java.

{:.warning}
Note also that not *every* line of Java ends with a semicolon! If the line starts a **block** like an `if` statement, there is no semicolon before the opening curly brace ``{`` nor one after the closing ``}``.

#### Syntax Errors and Debugging

**Syntax errors** are reported by the **compiler** if your Java code is not correctly written. Syntax errors cause a program's execution to STOP ✋🛑, either _before_ the program starts running or at a certain point _during_ the run. 
> In contrast, a **logic error** would be an issue in a _working_ algorithm or program that causes unexpected behavior. 

_Examples of common syntax errors:_

* Missing semicolon `;` at the end of a **statement**
* Missing closing curly brace `}` around a **block**
* Missing closing quote `"` around a `String`

🐞 Informally, a syntax error is called a **bug**, and the process of removing errors is called **debugging**.

![Grace Hopper's log showing a real bug, 1947](Figures/firstbug.jpg)
> An early computer science pioneer [Grace Hopper](https://en.wikipedia.org/wiki/Grace_Hopper) documented a real bug, a moth that flew into a computer in 1947!

#### Compile-Time Errors
{:.no_toc}

_Example error message:_
```
MyClass.java:5: error: unclosed string literal
       System.out.println("Hi there!);
                          ^
1 error
```
> The filename, line number, error type, and caret `^` help locate the issue.

{:.warning}
Error messages aren't always 100% accurate about _where_ the error actually is;
sometimes you actually need to change something a bit earlier in the program
and sometimes a bit later. But the **line number** is the best place to start
looking.

After the line number, you will find the actual **error type**. These
can be kind of cryptic at first, but they almost always contain
some useful 🔍 **clues**, like in the example above:
* `unclosed string literal` - you may not know what a string literal is (yet) but “unclosed” suggests _something_ was opened and then not closed.
* The caret (``^``) under the line of code is positioned to point at exactly _where_ in the line the Java compiler thinks the problem is. In this case it’s pointing at the
quotation mark (``”``) before “Hi”...

<div class="task" markdown="block">

1. Type out the code below exactly, run it, and look at the **error message**. Then fix it so it prints `Hi there!`.
  ```java
  System.out.println("Hi there!);
  ```
2. Repeat for this line of code, making sure to look at the error message before fixing it:
  ```java
  System.out.println("Hi there!";
  ```
3. This version has TWO errors. Can you fix them?
  ```java
  system.out.println("Hi there!")
  ```

</div>


#### Run-Time Errors
{:.no_toc}

Some errors cannot be detected by the compiler. These are called **run-time errors**. These errors occur _while the program is running_, after the code has been compiled. 
> They can be caused by a variety of things, such as dividing by zero or trying to read from a file that doesn't exist or a logic error in the code.

⚠️ An **exception** is a type of run-time error that occurs as a result of an unexpected error that was not detected by the compiler. It _interrupts the normal flow_ of the program’s execution.

<div class="task" markdown="block">

Type these two lines into your program and run it. What happens? Why?

```java
System.out.println("It makes no sense to divide a number by zero!");
System.out.println(3/0);
```

</div>

---

## Summary

- (AP 1.1.A.1) **Algorithms** define step-by-step processes to follow when completing a task or solving a problem. These algorithms can be represented using written language or diagrams.

- (AP 1.1.A.2) **Sequencing** defines an order for when steps in a process are completed. Steps in a process are completed one at a time.

- (AP 1.1.B.1) An **Integrated Development Environment (IDE)** is often used to write programs because it provides tools for a programmer to write, compile, and run code.

- A basic Java program looks like the following:
  ```java
     public class MyClass
     {
         public static void main(String[] args)
         {
             System.out.println("Hi there!");
         }
     }
  ```
- A Java program starts with **public class NameOfClass { }**. If you are using your own files for your code, each class should be in a separate file that matches the class name inside it, for example NameOfClass.java.

- Most Java classes have a main method that will be run automatically. It looks like this: **public static void main(String[] args) { }**.

- The **System.out.println()** method displays information given inside the parentheses on the computer monitor.

- Java statements end in ``;`` (semicolon). ``{ }`` are used to enclose blocks of code. ``//`` and ``/* */`` are used for comments.

- (AP 1.1.B.2) A **compiler** translates Java code into a class file that can be run on your computer and checks code for some errors. Errors detectable by the compiler need to be fixed before the program can be run. 

- (AP 1.1.C.1) A **syntax error** is a mistake in the program where the rules of the programming language are not followed. These errors are detected by the compiler. Some things to check for are ``;`` at end of lines containing complete statements and matching ``{ }``, ``()``, and ``""``.

- (AP 1.1.C.2) A **logic error** is a mistake in the algorithm or program that causes it to behave incorrectly or unexpectedly. These errors are detected by testing the program with specific data to see if it produces the expected outcome.

- (AP 1.1.C.3) A **run-time error** is a mistake in the program that occurs during the execution of a program. Run-time errors typically cause the program to terminate abnormally.

- (AP 1.1.C.4) An **exception** is a type of run-time error that occurs as a result of an unexpected error that was not detected by the compiler. It interrupts the normal flow of the program’s execution.

<!--

#### AP Practice
{:.no_toc}

<div class="task" markdown="block">

Consider:

```java
System.out.println("Roses are red, ")      // Line 1;
System.out.println("Violets are blue, ")  // Line 2;
System.out.println("Unexpected '}' on line 32. ")  // Line 3;
```

To produce:

```
Roses are red,
Violets are blue,
Unexpected '}' on line 32.
```

**Question:** Which change will make this output correct?

</div>

-->
---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
