---
layout: notes
title: "📓2.3: if Statements" 
parent: "2️⃣ Selection & Iteration"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.3](https://runestone.academy/ns/books/published/csawesome2/topic-2-3-ifs.html) 

---

## One-Way Selection with `if`

**If statements** (also called **conditionals** or **conditional blocks**) are found in all programming languages as a way to choose between different paths in an algorithm. An if statement is a type of *selection* structure that interrupts the usual sequential execution. It affects the flow of control by executing different segments of code based on the value of a **boolean expression** (also called the **condition**).

* `if` the **condition** is `true`, then the next statement (or block of statements) will _execute_.
* `if` the **condition** is `false`, then the next statement (or block of statements) is _skipped_. 

![image-small](Figures/Condition.png)

### Syntax of an `if` Statement

An **if statement** begins with the keyword ``if`` followed by a **boolean expression** (_condition_) inside of an open parenthesis ``(`` and a close parenthesis ``)`` and then followed on the next line by either a single statement, or a block of statements. The open curly brace ``{`` and a close curly brace ``}`` are used to **group a block of statements** together.  

<div class="imp" markdown="block">

✋ Examples of `if` statements for **one-way selection**: 

```java
// A single if statement
if (boolean expression)
  statement;

// A single if statement with {}
if (boolean expression) {
  statement;
}

// A block if statement ({} required)
if (boolean expression) {
  statement1;
  statement2;
  ...
  statementN;
}
```

> Note that there is no semicolon (`;`) at the end of the **boolean expression** (_condition_) in an if statement, because it is not the end of an instruction. Curly braces (`{ }`) are used to mark the beginning and end of the conditional's **body**, the block of code that's _dependent_ on the **condition**.

</div>

Consider the example below. Imagine that your cell phone wanted to remind you to take an umbrella `if` it was currently raining in your area when it detected that you were leaving the house:

```java
boolean isRaining = true;
if (isRaining) {
  System.out.println("Take an umbrella! ☔️");
}
System.out.println("Drive carefully");
```
> The variable ``isRaining`` is a boolean variable that is either `true` or `false`. If it is true then the message ``Take an umbrella!`` will be printed and then execution will continue with the next statement which will print ``Drive carefully``.

### Relational Operators in Conditions

Most if statements have a boolean expression that uses **relational operators** like `==`, `!=`, `<`, `>`, `<=`, `>=`, as we saw in the last lesson.

```java
double grade = 85.0;
if (grade > 60.0) {
  System.out.println("Congrats, you passed!");
}
System.out.println("Summer school is always an option...");
```

{:.warning}
A common mistake in if statements is using `=` instead of `==` in the condition. You should always use `==` in the condition of an if statement to test a variable. One equal sign (`=`) _assigns_ a value to a variable, and two equal signs (`==`) _test_ if a variable has a certain value.

## Two-Way Selection with `if-else`

What if you want to pick between two possibilities? If you are trying to decide between a couple of things to do, you might flip a coin and do one thing if it lands as heads and another if it is tails. This is an example of **two-way selection**. 

A **two-way selection** involves two connected conditional blocks: an `if` statement controlled by a **boolean expression** (_condition_), followed by a corresponding `else` statement. It executes the `if` body when the **condition** is true, and the `else` body when false.

![image](Figures/Condition-two.png)

### Syntax of an `if-else` Block

<div class="imp" markdown="block">
  
🔀 If you want to decide between **two possibilities**, use a `if` statement followed by `else`:

```java
// if-else block
if (boolean expression) {
    statement1;
    statement2;
}
else {
    otherStatement;
    anotherStatement;
}
```

</div>

<div class="task" markdown="block">

Type the code below, press run, and then:

1. Change `isHeads` to `false`.
2. See what prints before `"after conditional"`.

```java
boolean isHeads = true;
if (isHeads) {
    System.out.println("Let's go to the game");
}
else {
    System.out.println("Let's watch a movie");
}
System.out.println("after conditional");
```

</div>

### Common Errors with Conditional Blocks

Here are some rules to follow with if statements to avoid some common errors:

   - Always use curly braces (``{`` and ``}``) to enclose the block of statements under the if condition. Java doesn't care if you indent the code—it goes by the ``{ }``.

   - Don't put in a semicolon ``;`` after the first line of the if statement, ``if (test);``. The ``if`` statement is a multiline block of code that starts with the ``if`` condition and then ``{`` the body of the if statement ``}``.

   - Always use ``==``, not ``=``, in the condition of an if statement to test a variable. One ``=`` assigns, two ``==`` tests!

   - The ``else`` statement matches with the closest ``if`` statement. If you want to match an ``else`` with a different ``if`` statement, you need to use curly braces to group the ``if`` and ``else`` together.

---

## Summary

- (AP 2.3.A.1) Selection statements change the sequential execution of statements.

- (AP 2.3.A.2) An **if statement** is a type of selection statement that affects the flow of control by executing different segments of code based on the value of a Boolean expression.

- (AP 2.3.A.3) A one-way selection (if statement) is used when there is a segment of code to execute under a certain condition. In this case, the body is executed only when the Boolean expression is true.

- **if statements** test a boolean expression and if it is true, go on to execute the body which is the following statement or block of statements surrounded by curly braces  (``{}``) like below.

```java
    if (boolean expression){
       Do Statement1;
       Do Statement2;
       ...
       Do StatementN;
    }
```
- **Relational operators** (`==`, `!=`, `<`, `>`, `<=`, `>=`) are used in boolean expressions to compare values and arithmetic expressions.

- If statements can be followed by an associated **else** part to form a 2-way branch:
```java
    if (boolean expression){
        Do statement;
    }
    else
    {
        Do other statement;
    }
```
- (AP 2.3.A.4) A two-way selection (if-else statement) is used when there are two segments of code—one to be executed when the Boolean expression is true and another segment for when the Boolean expression is false. In this case, the body of the if is executed when the Boolean expression is true, and the body of the else is executed when the Boolean expression is false.

<!--
**If statements** are found in all programming languages as a way to choose between different paths in an algorithm. An if statement is a type of **selection** statement that changes the sequential execution. It affects the flow of control by executing different segments of code based on the value of a **Boolean expression**.

If you’ve used block programming (Scratch, App Inventor, etc.), you’ve probably seen if-blocks before. Here’s a comparison:

![Comparison of App Inventor if block, AP CSP ifs, and Java if statements](Figures/BlocksIfComparison.png)

## One-Way Selection

A **one-way selection** (`if` statement) is used when there is a segment of code to execute under a certain condition. The body is executed only when the Boolean expression is true; otherwise, it is skipped.

![Order of execution in a conditional](Figures/Condition.png)

**Syntax:**

```java
// Single if
if (boolean expression)
    doStatement;

// If with block
if (boolean expression) {
    statement1;
    statement2;
}
````

Always use curly braces `{ }`, even for one statement.

---

## Two-Way Selection

If you want to pick between **two possibilities**, use `if` followed by `else`:

```java
// If-else block
if (boolean expression) {
    statement1;
    statement2;
} else {
    otherStatement;
    anotherStatement;
}
```

A **two-way selection** executes the `if` body when the condition is true, and the `else` body when false.

![Order of execution in if/else](Figures/Condition-two.png)

<div class="task" markdown="block">

**Coding Exercise: Coin Flip**

Type in your Codespace, press run, and then:

1. Change `isHeads` to `false`.
2. See what prints before `"after conditional"`.

```java
boolean isHeads = true;
if (isHeads) {
    System.out.println("Let's go to the game");
} else {
    System.out.println("Let's watch a movie");
}
System.out.println("after conditional");
```

</div>

---

<div class="task" markdown="block">

**Coding Exercise: Driver's License**

Test this with two values of `age`:

* Current code allows licenses at `16`.
* Change it so licenses can be obtained at `15`.

```java
int age = 16;
if (age >= 16) {
    System.out.println("You can get a driver's license in most states!");
} else {
    System.out.println("Sorry, you need to be older.");
}
```

</div>

---

<div class="task" markdown="block">

**Coding Exercise: Score Feedback**

Add an `else` that prints `"Good job!"` if `score > 20`. Test with values above and below 20.

```java
int score = 8;
if (score <= 9) {
    System.out.println("Try for a higher score!");
}
// Your else here
```

</div>

---

## Common Errors with If Statements

* Always use `{ }` to group statements.
* Don’t put a semicolon after `if (condition);`
* Use `==` for comparison, not `=`.
* An `else` pairs with the **closest** preceding `if`.

<div class="task" markdown="block">

**Fix the Code: Missing Curly Braces**

Only print `"Wear a coat"` and `"Wear gloves"` when `isCold` is true.

```java
boolean isCold = false;
if (isCold = true);
    System.out.println("Wear a coat");
    System.out.println("Wear gloves");
```

</div>

---

## Group Challenge: Magic 8 Ball

Have the program:

1. Pick a random number from 1–8.
2. Use if statements to print a matching response.
3. Add a coin toss method that prints `"Lucky!"` or `"No Luck!"`.

![Magic 8 Ball](Figures/Magic_eight_ball.png)

---

## AP Practice

<details>
<summary><strong>AP 2-3-1</strong></summary>

```java
int speed = 35;
boolean rain = false;

if (rain) {
   speed -= 10;
}
if (rain == false) {
  speed += 5;
}
if (speed > 35) {
   speed = speed - 2;
}
System.out.println(speed);
```

**Answer:** `38` — First if is false; second and third are true.

</details>

<details>
<summary><strong>AP 2-3-2</strong></summary>

```java
int x = 5;
if (x < 5) {
   x = 3 * x;
}
if (x % 2 == 1) {
   x = x / 2;
}
System.out.print(2 * x + 1);
```

**Answer:** `5` — First if false; second if true (x becomes 2); output is `2*2+1=5`.

</details>

<details>
<summary><strong>AP 2-3-if-else</strong></summary>

```java
if (x >= 80) {
   System.out.println("High");
}
if (x >= 50) {
   System.out.println("Middle");
} else {
   System.out.println("Low");
}
```

**Answer:** `80` — Prints both `"High"` and `"Middle"`, showing a logic error.
To fix, chain with `else if`.

</details>

## Summary

* Selection statements change sequential execution.
* `if` executes a block only if a condition is true.
* `if-else` chooses between two paths.
* Always test both branches of an `if-else`.

-->

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
