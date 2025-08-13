---
layout: notes
title: "📓2.10: Implementing String Algorithms" 
parent: "2️⃣ Selection & Iteration"
nav_order: 10
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.10]() 

---


Loops are often used for **String Traversals** or **String Processing** algorithms where the code steps through a string character by character. In previous lessons, we learned to use `String` objects and built-in string methods to process strings. In this lesson, we will write our own loops to process strings.

There are standard string algorithms to:

- Find if one or more substrings has a particular property
- Determine the number of substrings that meet specific criteria
- Create a new string with the characters reversed

Remember that strings are a sequence of characters where each character has an index starting from 0.

---

## Traversing a String

To loop through a string:

```java
String str = "hello";
for (int i = 0; i < str.length(); i++) {
    char c = str.charAt(i);
    System.out.println(c);
}
````

---

## Example: Counting Vowels

<div class="task" markdown="block">

**Coding Exercise: Count the vowels in a string**

```java
String str = "hello world";
int count = 0;

for (int i = 0; i < str.length(); i++) {
    char c = str.charAt(i);
    if ("aeiou".indexOf(c) != -1) {
        count++;
    }
}

System.out.println("Number of vowels: " + count);
```

</div>

---

## Example: Reversing a String

<div class="task" markdown="block">

**Coding Exercise: Reverse a string**

```java
String str = "Java";
String reversed = "";

for (int i = str.length() - 1; i >= 0; i--) {
    reversed += str.charAt(i);
}

System.out.println("Reversed: " + reversed);
```

</div>

---

## Summary

* Strings can be traversed with loops, accessing each character with `charAt()`.
* Common algorithms: search, count, and reverse.
* Remember that string indices start at 0 and go to `length() - 1`.

---

## AP Practice

<details>
<summary><strong>Question 1</strong></summary>

What is printed by:

```java
String s = "abc";
for (int i = 0; i < s.length(); i++) {
    System.out.print(s.charAt(i) + " ");
}
```

**Answer:** `a b c`

</details>

<details>
<summary><strong>Question 2</strong></summary>

Write a loop that counts the number of uppercase letters in a string `str`.

**Answer:**

```java
int count = 0;
for (int i = 0; i < str.length(); i++) {
    if (Character.isUpperCase(str.charAt(i))) {
        count++;
    }
}
```

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
