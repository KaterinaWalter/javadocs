---
layout: notes
title: "📓1.8: Documentation & Comments" 
parent: "1️⃣ Objects & Methods"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.8](https://runestone.academy/ns/books/published/csawesome2/topic-1-8-comments.html) 

<div style="text-align: center;">
<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong><br>Create a blank Java program to take your class notes in for the next few lessons.<br><em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>
</div>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit1PartB-Notes`
4. For the **description**, write: `Object/reference data types, using methods, Math class, String class`
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

## Comments

**Comments** are written for both the original programmer and other programmers to understand the code and its functionality, but are **ignored by the compiler** and are not executed when the program is run. 

Adding comments to your code helps to make it more *readable* and *maintainable*.
> * In the commercial world, software development is usually a team effort where many programmers will use your code and maintain it for years. Commenting is essential in this kind of environment and a good habit to develop.
> * Comments will also help you to remember what you were doing when you look back to your code a month or a year from now. 

<div class="imp" markdown="block">
   
There are 3 types of **comments** in Java:

1. `//` Single line comment  
2. `/* */` Multiline block comment  
3. `/** */` Java documentation comment  

</div>

The special characters `//` are used to mark the rest of the line as a comment in many programming languages. 

If the comment is going to be multiple lines, we use `/*` to start the comment and `*/` to end the comment.

### Javadoc Comments

There is also a special version of the multi-line comment, `/** */`, called the **documentation comment**. Java has a tool called [javadoc](https://www.tutorialspoint.com/java/java_documentation.htm) that comes with the [Java JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html) and can generate HTML documentation from these comments — for example, see the [String class documentation](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html).

> Although you don’t have to use this for the AP exam, it’s good practice to write documentation comments for your classes, methods, and instance variables.

_Common Javadoc tags:_
- `@author`  Author of the program
- `@since`   Date released
- `@version` Version of program
- `@param`   Parameter of a method
- `@return`  Return value for a method
  
#### Example: Good Commenting
{:.no_toc}

```java
/**
 * MyClass.java
 * @author My Name
 * @since Date
 * This class keeps track of the max score.
 */
public class MyClass {
   private int max = 10; // this keeps track of the max score
   
   /* The print() method prints out the max */
   public void print() {  
      System.out.println(max); 
   }
}
```

#### Practice: Adding Comments
{:.no_toc}

<div class="task" markdown="block">

Copy-paste the code below into your blank Java program, press run, then add comments:

1. Add a **multi-line comment** above the class describing its purpose.
2. Add **single-line comments** before each section: reading input, calculating result, printing output.

```java
import java.util.Scanner;

public class Main {

   public static void main(String[] args) {
      Scanner scan = new Scanner(System.in);
      int num1 = scan.nextInt();
      int num2 = scan.nextInt();
      
      int result = num1 * num2;
      
      System.out.println(num1 + " x " + num2 + " = " + result);
   }
}
```

</div>

---

## Preconditions and Postconditions

Many methods in API libraries have **preconditions** and **postconditions** described in their comments. These assumptions are very useful to other programmers who want to use that method and get the correct results.

<html>
   <dl>
      <dt>Precondition</dt>
      <dd>A condition that must be true for the method to work properly. <em>Example: parameters must not be `null` or out of range.</em></dd>
      <dt>Postcondition</dt>
      <dd>A condition that is true after running the method — describes the outcome, such as what is returned or what state has changed.</dd>
   </dl>
</html>

For example, computing the square root of a negative number is undefined, so the ``Math.sqrt(num)`` Java method, which we will learn later, will return a special value ``NaN`` which stands for "not a number" if num is negative. But since you can't really do anything useful with ``NaN`` it's better to think of ``sqrt`` as having a precondition that says it only works properly if given a positive argument. 
* **Precondition**: `num >= 0` 
* **Postcondition**: Returns the positive square root of `num`.

#### CSAwesome Activities: Turtle Class

<div class="task" markdown="block">

🐢 To explore the concepts from this lesson in code, we'll play around with the `Turtle` class on the CSAwesome website instead of taking notes.  

👉 **GO TO:** <a href="https://runestone.academy/ns/books/published/csawesome2/topic-1-8-comments.html"><button class="btn">CSAwesome Topic 1.8</button></a>, **SIGN IN** to your account, and complete all the turtle-related **coding activities/challenges** with a partner. 

</div>

### Software Validity and Use-Case Diagrams

🧪 Determining the preconditions and postconditions help us to test our code and determine the **validity** of our software. Software validity tests whether the software does what it is supposed to do before it is released.

> Good software testers actually try to break the code! They try all kinds of input to see what the software will do because you never know what users will try or what conditions there will be. 

💡 Preconditions and postconditions can also help us to design better software systems. Software designers often first draw a high-level **Use-Case Diagram** of a system that shows the different ways that a user might interact with a system before they build it. 

![Use Case Diagram of a Restaurant System](Figures/use-case-restaurant.png)

> Here is a simple Use-Case Diagram of a restaurant system. It shows 2 actors in the system: the customer and the staff at the restaurant, and 3 use-cases in circles. A **Use-case** is a particular user interaction or situation in the system or software, and they often become methods in the program.

After drawing a Use-Case Diagram, designers write down the preconditions and the postconditions for each Use-Case. Often the successful post-condition for one use-case becomes the preconditions for the next use-case. _For example:_

- **Preconditions for "Order Food":** Customer enters restaurant. Staff is ready to take the order.
- **Postconditions for "Order Food":** Customer orders the food. Staff takes the order.
- **Preconditions for "Eat Food":** Customer has already ordered food. Staff has delivered food.
- **Postcondition for "Eat Food":** Customer has consumed the food.

<div class="task" markdown="block">

💬 **Discuss:** What are the *preconditions* and *postconditions* of the use-case "Pay for food"? Remember that these are often related to the other use-case conditions "order food" and "eat food".

</div>

### Agile Software Development

There are many different models for software development. 
* The **Waterfall Model**, developed in the 1970s, is a step by step model where each phase is finished before the next phase begins.
  * This model has recently been criticized because it is not very adaptable.
* The more recent **Agile** development model involves _iterative_, _incremental_ development where teams works in short 2-3 week **sprints** to completely develop, test, and release a component of the project to the customer for feedback.
  * It is very adaptable as project requirements change because of early testing, immediate customer feedback and collaboration.

![Waterfall vs Agile Models](Figures/waterfallVsAgile.png)

One very popular type of agile development is called **Scrum**. The following short video describes software development with Scrum.

<iframe width="600" height="400" src="https://www.youtube.com/embed/TRcReyRYIMg" frameborder="0" allowfullscreen></iframe>

<!--

Try this <a href="https://www.agilesparks.com/blog/wake-up-in-the-morning-game/" target="_blank">Wake Up In the Morning Game</a> in groups to practice the iterative and incremental agile development process.

-->

#### Group Challenge: Preconditions in Algorithms
{:.no_toc}

<div class="task" markdown="block">

1. Write down at least 4 steps that a user must do to **purchase a product**, for example a book about Java, in an online store.
2. List the preconditions and postconditions for each step.

**Optional:** Draw a use-case diagram in [Creately.com](https://creately.com)

</div>
 
---

## Summary

- (AP 1.8.A.1) **Comments** are written for both the original programmer and other programmers to understand the code and its functionality, but are ignored by the compiler and are not executed when the program is run. 

- (AP 1.8.A.1) Three types of comments in Java include ``/* */``, which generates a block of comments, ``//``, which generates a comment on one line, and ``/** */``, which are Javadoc comments and are used to create API documentation.

- (AP 1.8.A.2) A **precondition** is a condition that must be true just prior to the execution of a section of program code in order for the method to behave as expected. There is no expectation that the method will check to ensure preconditions are satisfied.

- (AP 1.8.A.3) A **postcondition** is a condition that must always be true after the execution of a section of program code. Postconditions describe the outcome of the execution in terms of what is being returned  or the current value of the attributes of an object.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
