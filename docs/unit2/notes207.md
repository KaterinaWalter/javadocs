---
layout: notes
title: "📓2.7: while Loops" 
parent: "2️⃣ Selection & Iteration"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.7](https://runestone.academy/ns/books/published/csawesome2/topic-2-7-while-loops.html) 

<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong> Create a blank Java program to take your class notes in for the next few lessons. <em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit2PartB-Notes`
4. For the **description**, write: `Iteration/repetition (while loops, for loops)`
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

## While Loops

When you play a song, you can set it to loop — meaning when it reaches the end, it starts over from the beginning. A **loop** in programming, also called **iteration** or **repetition**, repeats one or more statements. Without loops, your programs would quickly become very long because you’d have to repeat code manually.

Programming uses three main control structures to build algorithms:  
1. **Sequence** – running code in order.  
2. **Selection** – using `if` statements to choose between paths.  
3. **Repetition** – using loops to repeat code.

A `while` loop executes its body **as long as** a boolean condition is true. When the condition becomes false, the loop exits and the program continues after the loop.

---

## Example: While Loop

<div class="task" markdown="block">

**Coding Exercise: Countdown**

Type this in your Codespace, run it, and observe the output.

```java
int count = 5;

while (count > 0) {
    System.out.println(count);
    count = count - 1;
}

System.out.println("Blastoff!");
````

</div>

---

## Infinite Loops

If the loop’s condition never becomes false, you get an **infinite loop**.

<div class="task" markdown="block">

**Debug Exercise: Stop the Infinite Loop**

This loop never ends. Fix it so it counts down to 0.

```java
int count = 5;

while (count > 0) {
    System.out.println(count);
    // missing update statement!
}

System.out.println("Done");
```

</div>

---

## Sentinel Loops

A **sentinel loop** runs until a special value (sentinel) is entered.

<div class="task" markdown="block">

**Coding Exercise: Sentinel Loop**

This program reads integers until the user enters `-1`.

```java
import java.util.Scanner;

public class SentinelExample {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int number = 0;

        while (number != -1) {
            System.out.print("Enter a number (-1 to quit): ");
            number = scan.nextInt();
        }

        System.out.println("Done");
    }
}
```

</div>

---

## Summary

* A `while` loop repeats code while its condition is true.
* Without an update to make the condition false, you get an infinite loop.
* A sentinel loop stops when a special value is entered.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

What will this print?

```java
int x = 0;
while (x < 3) {
    System.out.print(x + " ");
    x++;
}
```

**Answer:** `0 1 2` — the loop runs while `x` is 0, 1, and 2.

</details>

<details>
<summary><strong>Question 2</strong></summary>

What’s wrong with this loop?

```java
int x = 0;
while (x < 3) {
    System.out.println("Hello");
}
```

**Answer:** It’s an infinite loop because `x` never changes inside the loop.

</details>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
