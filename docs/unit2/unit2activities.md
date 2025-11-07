---
layout: notes
title: "🎯 Unit 2 Activities" 
parent: "2️⃣ Selection & Iteration"
nav_order: 13
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

<html>
  <details>
    <summary>💻 <strong class="text-green-200">ACTIVITY PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit2-Activity#`
    > Replace `#` with the specific _activity number_.
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!

</div>

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! **Codespaces** are TEMPORARY editing environments, so you need to COMMIT changes properly in order to update the main **repository** for your program. 

_There are multiple steps to saving in GitHub Codespaces:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated main.py`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

  </details>
</html>

---

## 🔮 ACTIVITY #1: Magic 8 Ball

Have you ever used a **Magic 8 ball**? You ask it a yes-no question, and then shake it to get a random answer like ``Signs point to yes!``, ``Very doubtful``, etc. 

{:.highlight} Try out this [Magic 8 Ball Simulator](https://magic-8ball.com/)

_In this activity, we will:_
* Generate and use **random** values correctly.
* Practice **selection** with `if`-`else if`-`else` blocks (chain structures) and **conditions** (`boolean` values or expressions).

### PART A: Printing Randomly-Selected Messages

<div class="task" markdown="block">

Write a **branching** program inside the `main()` method that does the following:

1. Declare a variable called `num` and assign it a **random integer** between 1 to 10, inclusive.
  > To review generating random numbers, see [📓 1.11: Math Class](https://coderina.dev/javadocs/docs/unit1/notes111.html)
2. Use **conditional statements** to test the value of `num` and _print out a different message for each number_.
  > Come up with **10 creative responses** to yes-no questions!

</div>

#### Review: `if`-`else if`-`else`

```java
if ( conditions ) {
  statement1;
}
else if ( condition ) {
  statement2;
}
else {
  statement3;
}
```
> This structure can accomodate more than 3 choices easily – just add an `else if` block for every possibility _after_ the first `if` statement, and _before_ the final `else` block. 


### PART B: Coin Toss

<div class="task" markdown="block">


1. Generate another random number at the top of the program, this time a**random double** between 0–1. Store it in a variable called `luck`.
2. In a **nested** `if` statement, check the value of `luck`. If it is greater than or equal to 0.5, print the message `"LUCKY! 🍀"` 

</div>

<div class="warn" markdown="block">

**Common pitfalls to avoid**

* Off-by-one: `(int) (Math.random() * 10)` gives values between 0–9. Remember to add 1.
* Isolated `if` statements: use `else if` blocks to avoid multiple messages printing out.

</div>
