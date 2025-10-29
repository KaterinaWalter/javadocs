---
layout: notes
title: "📓2.2: Boolean Expressions" 
parent: "2️⃣ Selection & Iteration"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.2](https://runestone.academy/ns/books/published/csawesome2/topic-2-2-booleans.html) 

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
3. Specify the **repository name**: `CS2-Unit-2-A-Notes`
4. For the **description**, write: `Selection/Conditionals (boolean expressions, if-else statements)`
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

## Boolean Variables & Expressions

* **Boolean variables** are data containers of type `boolean` that can only store either `true` or `false` as values.
  * _Example:_ `boolean lightsOn = true;` 
* **Boolean expressions** are statements with comparisons/tests that need to be _evaluated_, but will ultimately result in only `true` or `false`.
  * _Example:_
  ```java
  boolean passing = (grade > 60);
  ```
  > `(grade > 60)` is the **boolean expression** that evaluates to `true` if the value of the variable `grade` is greater than 60, or `false` otherwise. That result can be stored in a **boolean variable** like `passing`.

{:.highlight}
❓ **Boolean expressions** are like simple _questions_ where "yes or no" are the only possible _responses_.

### Testing Equality `==`, `!=`

The **relational operators** ``==`` (equal) and ``!=`` (not equal) can be used to _compare_ two values. Expressions that include relational operators are _evaluated_ and **return** a `true` or `false` boolean value. 

{:.warning}
The **assignment operator**, ONE ``=`` sign, _changes_ the value of a variable. The **equality operator**, TWO ``==`` equal signs, are used to _test_ if a variable holds a certain value, without changing its value!

<div class="task" markdown="block">

🔮 **Predict:** What will the code below print out? Try to guess before you run it! Then, add a line of code that _re-assigns_ the `yourAge` variable to 17, and print the boolean expression for whether `yourAge` is equals `drivingAge`.

```java
int yourAge = 15;
int drivingAge = 17;
// 1. Will these print true or false?
System.out.println(yourAge == drivingAge);
System.out.println(yourAge != drivingAge);
// 2. Set yourAge to a new value of 17
// 3. Print whether yourAge equals drivingAge
```
</div>

#### Comparing Primitives vs. References

Watch the following video which shows what happens in memory as **primitive data types** like ``int`` and **reference (object) types** like ``Dog`` are compared with ``==`` in a physical model of Java memory:

<iframe width="650" height="415" src="https://www.youtube.com/embed/bO9bejT0jwE?si=a1fY3hrwlivxC043" frameborder="0" allowfullscreen></iframe>

{:.highlight}
So, we can also use ``==`` or ``!=`` to test if two **reference** values, like ``Turtle`` and ``String`` objects, _refer to the exact same object_ stored in memory. 

![image](Figures/turtleEquality.png)
> * In the figure above, we are creating two separate ``Turtle`` objects called ``juan`` and ``mia``. _They do NOT refer to same object or turtle!_
> * Then, we create a reference variable called ``friend`` that is set to ``mia``. The turtle ``mia`` will have two ways (**references** or **aliases**) to name her – she's both ``mia`` and ``friend``, and these variables _point to the same object_ (same ``Turtle``) in memory. 

### Relational Operators `<`, `<=`, `>`, `>=`

The **relational operators** below in Java are used to compare _numeric_ values or arithmetic expressions: 

| Operator | Description |
| --- | ----------- |
| ``<``  | Less than |
| ``>``  | Greater than |
| ``<=`` | Less than or equal to |
| ``>=`` | Greater than or equal to |
| ``==`` |  Equals |
| ``!=`` | Does not equal |

> Java only allows these **operators** to be used with _primitive_ type numbers (`int` and `double`), but for _reference/object_ types like `String`, uses the **methods** ``.compareTo()`` and ``.equals()``.

{:.highlight}
🐊 If you have trouble telling ``<`` and ``>`` apart, use the “hungry alligator” mnemonic: think of ``<`` and ``>`` as the mouths of **hungry alligators** which always want to _eat the bigger number_. A ``<`` or ``>`` expression is only ``true`` if the alligator is in fact about to eat the bigger number.

To remember the correct **order** of the two characters in ``<=`` and ``>=``, just
write them in the same order you would say them out loud in English: “less than or equal
to” not “equal to or less than”.

<div class="task" markdown="block">

🔮 **Predict:** What will the value of `result` be after execution? 

```java
boolean result = (5 % 3 == 0) != (3 > 5);
```

</div>

### Testing with Remainder `%`

Here are some common **boolean expressions** that are very useful in coding, noting that the **remainder** operator (`%`) is used in many of them:

- Test if a number is **positive**: `number > 0` returns true
- Test if a number is **negative**: `number < 0` returns true
- Use the remainder operator it to check for **divisibility by 2**:
  - If ``num % 2 != 0`` is true → ``num`` is **odd**
  - If ``num % 2 == 0`` is true → ``num`` is **even**
- You can also use remainder to check if a number is a **evenly divisible** by any another number:
  - If ``num1 % num2 == 0`` is true → ``num1`` is a **multiple** of ``num2``
- Use it to get the **last digit** from an integer number: ``int digit = num % 10;``
- Use it to get the number of minutes **left over** when you convert a total number of minutes to hours and minutes:
  ```java
  int totalMins = 345;
  int hrs = totalMins / 60;  // Number of whole hours
  int mins = totalMins % 60; // Number of mins left over
  ```

{:.warning}
Because Java's ``%`` is a _remainder_ operator, not a true [modulo](https://en.wikipedia.org/wiki/Modulo) operator, you should always use ``num % 2 != 0`` to **check if a number is odd**. You cannot accurately check if a number is odd with the expression ``num % 2 == 1``. 

> That expression breaks with _negative_ numbers. ``num % 2 != 0`` will be ``true`` if ``num`` is positive and odd and ``false`` when ``num`` is even, both of which are correct. HOWEVER if ``num`` is _negative_ and odd, its remainder when divided by 2 is -1, not 1, and this expression will (incorrectly) evaluate to ``false``. 

#### Relational Operators Game
{:.no_toc}

<div class="task" markdown="block">

🎲 Try the game below to practice! Click on _Relationals_, evaluate the relational expression and click on **None**, **All**, or the **numbers** that make the expression `true`. Check on _Compound_ for an added challenge.

<iframe height="700px" width="100%" style="margin-left:10%;max-width:80%" src="https://csa-games.netlify.app/"></iframe>

</div>

<!--

## Testing Equality (`==`)

The relational operators `==` and `!=` (not equal) can be used to compare values. They return true or false boolean values.

**Note:** One `=` sign changes the value of a variable. Two `==` equal signs are used to test if a variable holds a certain value, without changing its value!

<iframe width="700" height="400" src="https://www.youtube.com/embed/bO9bejT0jwE" frameborder="0" allowfullscreen></iframe>

The following code shows how `==` is used with primitive types like `int`.

<div class="task" markdown="block">

**Coding Exercise**

Type this in your Codespace, press run, and see what happens. Then:

1. Add code that sets `year` to 15.
2. Print out whether `age` equals `year`.
3. Print out whether `age` does not equal `year`.

```java
int age = 15;
int year = 14;
// Will this print true or false?
System.out.println(age == year);
// Will this print true or false?
System.out.println(age != year);

// Your code here
```

</div>

We can also use `==` or `!=` to test if two reference values, like `Turtle` and `String` objects, refer to the same object.

![Turtle Reference Equality](Figures/turtleEquality.png)

<div class="task" markdown="block">

**Coding Exercise**

Type this in your Codespace, press run, and then:

1. Create another `Turtle` variable `friend2` and set it to `juan`.
2. Print whether `friend2 == juan`.
3. Print whether `friend2 == friend`.

```java
World world = new World(300, 300);
Turtle juan = new Turtle(world);
Turtle mia = new Turtle(world);

// Will these print true or false?
System.out.println(juan == mia);
Turtle friend = mia; // alias for mia
System.out.println(friend == mia);

// Your code here
```

</div>

## Relational Operators (`<`, `>`)

The **relational operators** below are used to compare numeric values or arithmetic expressions in Java:

* `<` Less than
* `>` Greater than
* `<=` Less than or equal to
* `>=` Greater than or equal to
* `==` Equals
* `!=` Does not equal

Think of `<` and `>` as arrows: the pointy end should point to the smaller value. Or use the “hungry alligator” mnemonic—they eat the bigger number.

<div class="task" markdown="block">

**Coding Exercise**

Type this in your Codespace, press run, then:

1. Set `year` to 15.
2. Print whether `age` is less than or equal to `year`.

```java
int age = 15;
int year = 14;
// Will these print true or false?
System.out.println(age < year);
System.out.println(age > year);

// Your code here
```

</div>

**Boolean** variables or expressions have **true** or **false** values. For example:

```java
// Test if a number is positive
(number > 0)
// Test if a number is negative
(number < 0)
```

<div class="task" markdown="block">

**Check Your Understanding**

Match the boolean expression to what it is testing:

* `x > 0` → x is positive
* `x == y` → x equals y
* `x < 0` → x is negative
* `x != y` → x does not equal y
* `x < y` → x is less than y
* `x > y` → x is greater than y
* `x >= y` → x is greater than or equal to y

</div>

## Testing with Remainder (`%`)

The remainder operator `%` can test whether a number is even, odd, or divisible by another number:

```java
(number % 2 == 0) // even
(number % 2 != 0) // odd
(number % x == 0) // divisible by x
```

<div class="task" markdown="block">

**Coding Exercise**

Type this in your Codespace, press run, then:

1. Add a line to check if `age1` is divisible by 3.

```java
int age1 = 15;
int age2 = 16;

System.out.println("Remainder of " + age1 + "/2 is " + (age1 % 2));
System.out.println("Remainder of " + age2 + "/2 is " + (age2 % 2));
System.out.println("Is " + age1 " even? " + (age1 % 2 == 0));
System.out.println("Is " + age2 " even? " + (age2 % 2 == 0));

// Your code here
```

</div>

**Note:** In Java, `%` is a remainder operator, not a true modulo operator. Always use `num % 2 != 0` to check for odd numbers.

## Coding Challenge: Prime Numbers

We encourage you to do this activity as a POGIL group activity or using Think-Pair-Share.

<div class="task" markdown="block">

Write methods to:

* Test if a number is positive, negative, odd, even, or divisible by another number.
* Use these methods to check if 5, 6, and 7 are prime.

```java
public static boolean isPositive(int number) {
    return (number > 0);
}

public static boolean isNegative(int number) {
    return (number < 0);
}

public static boolean isOdd(int number) {
    return (number % 2 != 0);
}

public static boolean isEven(int number) {
    return (number % 2 == 0);
}

public static boolean isDivisible(int number, int divisor) {
    return (number % divisor == 0);
}
```

</div>

**Check Your Understanding:**

* Is 5 prime? ✅ Yes.
* Is 6 prime? ❌ No.
* Is 7 prime? ✅ Yes.
* Are all odd numbers prime? ❌ No (example: 9).
* Are all even numbers not prime? ❌ No (example: 2).

Prime numbers are very useful in encryption algorithms.

## AP Practice

<details>
  <summary><strong>Question 1</strong></summary>

```java
boolean x = (5 % 3 == 0) == (3 > 5);
```

* A. `true`
* B. `false`

**Answer:** A (`true`). Explanation: `(5 % 3 == 0)` is `false` and `(3 > 5)` is `false`, so `false == false` is `true`.

</details>

<details>
  <summary><strong>Question 2</strong></summary>

When is the expression below `true`?

```java
(x >= 10) == (y < 12)
```

* A. Only when `x >= 10` and `y < 12`
* B. Only when `x < 10` and `y >= 12`
* C. When both are `true` or both are `false`
* D. Never

**Answer:** C. Both sides must have the same truth value. Example `true==true`: `x = 10, y = 11`. Example `false==false`: `x = 9, y = 12`.

</details>

-->

---

## Summary

- (AP 2.2.A.1) Values or expressions can be compared using the relational operators ``==`` and ``!=`` to determine whether the values are the same. With primitive types, this compares the actual primitive values. With reference types, this compares the object references.
- (AP 2.2.A.2) Numeric values or expressions can be compared using the relational operators (``<``, ``>``, ``<=``, ``>=``) to determine the relationship between the values.
- (AP 2.2.A.3) An expression involving relational operators evaluates to a ``Boolean`` value of ``true`` or ``false``.	
- The remainder operator ``%`` can be used to test for divisibility by a number. For example, ``num % 2 == 0`` can be used to test if a number is even.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
