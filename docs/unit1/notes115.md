---
layout: notes
title: "📓1.15: The String Class" 
parent: "1️⃣ Objects & Methods"
nav_order: 16
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.15](https://runestone.academy/ns/books/published/csawesome2/topic-1-15-strings.html) 

---

**Strings** in Java are objects of the `String` class. Strings represent _sequences of characters_ and are used to store text like names, addresses, or messages. The `String` class is part of the `java.lang` package, which is available by default in all Java programs.

![image](Figures/stringbracelet.png)

> **Note:** Class names in Java, like `String`, begin with a capital letter. All primitive types (`int`, `double`, `boolean`) begin with a lowercase letter. This is one way to tell the difference between primitive types and class types.

<!--
STRING BRACELET ACTIVITY?

String Methods and tell students that strings are indexed starting at 0. Bring scrabble or banagram tiles to class or have students cut out squares from paper to write letters on. Working in pairs, have students create or write down a long word like “CSAwesome” or “extraordinary” with the tiles. Ask them which index or indices substrings within the large string start and end. For example, what index does the substring “Awesome” start and end in the string “CSAwesome”?
-->

---

### String References

<div class="task" markdown="block">

Type this in your Codespace, press run, and see what it prints:

```java
String greeting = null;
System.out.println(greeting);
```

</div>

The code above declares an object variable named `greeting` and sets it to `null` to show that it doesn't refer to any object yet. Printing it will display `null`.

Object variables **refer** to objects in memory. A reference is like a contact in your phone — it lets you find someone without knowing exactly where they are. The value is `null` until the object is created.

---

In Java, there are two main ways to create a `String` object:

```java
String greeting = new String("Hello"); // Using new and constructor
```

Or with a **string literal**:

```java
String greeting = "Hello"; // Using quotes directly
```

Both create a `String` in memory and store a reference in the variable.

---

<div class="task" markdown="block">

Create two new strings, `firstName` and `lastName`.

* One should use a string literal.
* The other should use `new String(...)`.
* Print them along with the greetings.

```java
String greeting1 = "Hello!";
String greeting2 = new String("Welcome!");

System.out.println(greeting1);
System.out.println(greeting2);
```

</div>

---

<div class="task" markdown="block">

Now that `greeting` refers to an actual object, try asking it what class created it:

```java
String greeting = "Hello";
Class currClass = greeting.getClass();
System.out.println(currClass);

Class parentClass = currClass.getSuperclass();
System.out.println(parentClass);
```

</div>

This prints:

```
class java.lang.String
class java.lang.Object
```

* The `java.lang` part is the package name.
* Every Java class has **one** parent (superclass).
* All classes ultimately inherit from `Object`.

---

### String Operators – Concatenation

Strings can be added together (**concatenated**) with `+` or `+=`:

* `+` combines values to form a new `String`.
* `+=` appends to the existing value (also creates a new String, since Strings are immutable).

<div class="task" markdown="block">

Add a last name variable and append it, then add extra exclamation points.

```java
String start = "Happy Birthday";
String name = "Jose";
String result = start + " " + name;
result += "!";
System.out.println(result);
```

</div>

> **Note:** Spaces aren’t added automatically. Add `" "` manually if you want them.

---

Primitive values and other objects can also be concatenated.
Numbers will be turned into strings when joined with a `String`.

<div class="task" markdown="block">

Guess the output before running:

```java
String message = "12" + 4 + 3;
System.out.println(message);
```

Then modify it so `4 + 3` is calculated before converting to a string.

</div>

Without parentheses, this prints `1243`. With `(4 + 3)` it would print `127`.

---

### String Index and Length

Strings hold characters at positions (**indexes**) starting at 0.
Example: `"Hello world"` has length 11, last index 10.

> The first character is at index `0`, the last at `length - 1`.
> Accessing outside this range throws `IndexOutOfBoundsException`.

---

### Common String Methods for AP CSA

* `int length()` – returns number of characters.
* `String substring(int from, int to)` – returns from `from` index up to (but not including) `to`.
* `String substring(int from)` – returns from `from` to end.
* `int indexOf(String str)` – returns starting index of `str` or -1.
* `boolean equals(String other)` – true if characters match exactly.
* `int compareTo(String other)` – returns:

  * negative if less than `other`
  * 0 if equal
  * positive if greater

---

<div class="task" markdown="block">

Run and observe:

```java
String message1 = "This is a test";
String message2 = "Hello Class";

System.out.println(message1.length());
System.out.println(message2.length());

System.out.println(message1.substring(0, 3));
System.out.println(message1.substring(2, 3));
System.out.println(message1.substring(5));

System.out.println(message1.indexOf("is"));
System.out.println(message1.indexOf("Hello"));
System.out.println(message2.indexOf("Hello"));

System.out.println(message2.toLowerCase());
System.out.println(message2.toUpperCase());
```

</div>

---

<div class="task" markdown="block">

This code **breaks** the substring preconditions.
Fix it so it prints `"o"`:

```java
String str = "hello";
System.out.println(str.substring(-1, 10));
```

</div>

---

### Comparing Strings – `compareTo` and `equals`

* `compareTo` compares alphabetically.
* `equals` checks for exact match.
* Both are **case-sensitive**.

<div class="task" markdown="block">

```java
String message = "Hello!";

System.out.println(message.compareTo("Hello!"));
System.out.println(message.compareTo("And"));
System.out.println(message.compareTo("Zoo"));

System.out.println(message.equals("Hello!"));
System.out.println(message.equals("hello!"));
```

</div>

---

### Common Mistakes with Strings

1. Thinking `substring` includes the last index.
2. Forgetting Strings are **immutable**.
3. Using invalid indices.
4. Calling methods on a `null` reference (NullPointerException).
5. Using `==` to compare Strings instead of `.equals`.
6. Assuming uppercase and lowercase are equal.

<div class="task" markdown="block">

Fix this code so it works as intended:

```java
String str1 = "Hello!";

// First letter
System.out.println("The first letter in " + str1 + ":" + str1.substring(1, 1));

// Last character
System.out.println("The last char. in " + str1 + ":" + str1.substring(8));

// Lowercase
str1.toLowerCase();
System.out.println("In lowercase: " + str1);
```

</div>

---

### Coding Challenge – Pig Latin

**Rule:** Move the first letter to the end and add `"ay"`.

<div class="task" markdown="block">

Write code for `pigLatin` method so:

* `"java"` → `"avajay"`
* `"pig"` → `"igpay"`

```java
String word = "pig";
// your code here
```

</div>

---

### Summary

* `String` represents text, created with literals or constructors.
* Immutable — methods return new strings.
* Can concatenate with `+` or `+=`.
* Can combine with primitives (auto-converted) or objects (`toString` called).
* Index starts at 0, last is `length - 1`.
* Key methods: `length`, `substring`, `indexOf`, `equals`, `compareTo`.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
