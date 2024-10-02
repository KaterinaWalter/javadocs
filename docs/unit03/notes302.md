---
layout: notes
title: "📓3.2: If Statements" 
parent: "3️⃣ Conditionals"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.2](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-2-ifs.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-3-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## If Statements and Control Flow

The statements in a Java main method normally run or _execute one at a time_ in the order they are found, _from top to bottom_.  **If statements** (also called **conditionals** or **selection**) change the flow of control through the program so that some code is only run when something is true. **If statements** are found in all programming languages as a way to _make choices_. 
* In an if statement, if the condition is `true` then the next statement or a block of statements will execute.
* If the condition is `false` then the next statement or block of statements is skipped.

![image](Figures/Condition.png)

A **conditional** uses the keyword ``if`` followed by a **boolean expression** inside of  an open parenthesis ``(`` and a close parenthesis ``)`` and then followed by a single statement or block of statements. The open curly brace ``{`` and a close curly brace ``}`` are used to group a block of statements together.  

{:.warning}
It is recommended to _always include the curly braces_ even if you have just one statement under the if statement! The questions you will see on the AP exam will usually use curly braces.

<div class="imp" markdown="block">

Examples of `if` statements: 

```java
// A single if statement
if (boolean expression)
  statement;

// A single if statement with {}
if (boolean expression) {
  statement;
}

// An if statement block
if (boolean expression) {
  statement1;
  statement2;
  ...
  statementN;
}
```

> Note that there is no semicolon (`;`) at the end of the **boolean expression** in an if statement, even if it is the end of that line. The semicolon goes at the end of the _whole_ if statement, often on the next line. Or `{ }` are used to mark the beginning and end of the block of code under the if condition.

</div>

---

## ⭐️ Summary

- **if statements** test a _boolean expression_ and if it evaluates to `true`, go on to execute the following statement or block of statements surrounded by curly braces  (``{}``) like below.

```java
// A single if statement
if (boolean expression)
  statement;

// A single if statement with {}
if (boolean expression) {
  statement;
}

// An if statement block
if (boolean expression) {
  statement1;
  statement2;
  ...
  statementN;
}
```

- **Relational operators** (`==`, `!=`, `<`, `>`, `<=`, `>=`) are used in boolean expressions to _compare_ values and arithmetic expressions.

- Conditional (if) statements affect the program's **flow of control** by executing different statements based on the value of a Boolean expression.

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

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
