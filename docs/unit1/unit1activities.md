---
layout: notes
title: "🎯 Unit 1 Activities" 
parent: "1️⃣ Objects & Methods"
nav_order: 17
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
3. Specify the **repository name**: `CS2-Unit1-Activity#`
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

## 🤪 ACTIVITY #1: MadLibs

In this activity, you'll be creating your own **MadLibs** game using Java! A MadLibs story is a short story where certain words are left out, and players fill in the blanks with their own words (like nouns, verbs, adjectives, etc.), making the story fun and creative. You will write a story, replace some words with variables, and ask the user to fill in those blanks by gathering input using a `Scanner` object.

#### Reminders
{:.no_toc}
* Strings in Java are **objects** of the `String` class that hold _sequences of characters_.
* String objects can be created by using **string literals** (`String s = “hi”;`) or by calling the String class constructor (`String t = new String(“bye”);`).
* String objects can be **concatenated** using the `+` or `+=` operator, resulting in a new String object.
* Primitive values can be **concatenated** with a String object. _This causes implicit conversion of the values to String objects._

### PART A: Create a MadLibs Story

<div class="task" markdown="block">

1. Come up with a fun story to use for MadLibs. Yours should be long enough to include at least **10 variables**. Choose nouns, verbs, adjectives, etc., that you want the user to fill in, and decide how many blanks you’ll need.
> _Example:_ "Today, I went to the PLACE to VERB with my ADJECTIVE NOUN. It was a ADJECTIVE day, and we had lots of fun!"
2. In your `main` method, **declare variables** for the parts of the story that the user will input. For each _blank_ in the story, you'll need a variable.
> _Example:_ `String adjective1;`
3. Use a Scanner object to take user input, using the code example below for help.
```java
// Add to TOP of program before the class:
import java.util.Scanner;
// In the main method:
// Construct the Scanner - only do this once
Scanner scan = new Scanner(System.in);
// Take input for each variable!!!
System.out.print("Enter an adjective: ");
adjective1 = scan.nextLine();
```
4. Use string **concatenation** to combine the user's input with your story.
> _Example:_ `String story = "It was a " + adjective1 + " day";`
5. **Print** out your story!
> It may be easier to separate each sentence into its own variable, then use the appropriate method to print them out (either all together or on separate lines). 

</div> 

### PART B: Mix it up with Methods
<div class="task" markdown="block">
  
1. Manipulate some of the string variables with `String` class methods such as `.substring()`. Use at least **3 String class methods** total.
2. Take numerical input (`int` and `double`) by using the `Scanner` class methods: `scan.nextInt()` or `scan.nextDouble()`, for at least 2 of the variables in your story. 
3. Before including those numbers in your story, run a `Math` class method on them to manipulate the numbers however you'd like. You should use at **least 2 Math class methods** total here, and possibly `Math.random()` to include a random number somewhere in the story.  

</div> 

#### Extensions
{:.no_toc}

* Add more variables to make your story longer and funnier.
* Format the output to make it look like a paragraph using `\n` for new lines.
* Include emojis to make the story visually interesting!

---


