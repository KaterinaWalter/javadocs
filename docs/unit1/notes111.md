---
layout: notes
title: "📓1.11: The Math Class" 
parent: "1️⃣ Objects & Methods"
nav_order: 12
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.11](https://runestone.academy/ns/books/published/csawesome2/topic-1-11-Math.html) 

---

## The Math Class

Games would be boring if the same thing happened each time you played the game. **Random** numbers can be used in games to generate different outcomes each time the game is played. In Java, the `Math.random()` method is used to generate a random number.

There are lots of mathematical methods in the `Math` class that you might want to use in your programs, like `Math.pow(2,3)` which calculates 2 to the power of 3, which is 8.

The `Math` class is part of the `java.lang` package. Classes in the `java.lang` package are available by default. The `Math` methods are **class (static) methods** which means you can call them by just using `ClassName.methodName()`.

<!--
Play Rock-Paper-Scissors with student volunteers: Enter the following command into the Coding Exercise window to generate a random integer from 1 to 3, inclusive. 
System.out.println( (int) (Math.random()*3 + 1));
Ask one student at a time to challenge the computer in a game of Rock-Paper-Scissors. You can have students choose at the same time you run the command or the student can turn their back. Explain that a computer choice of 1 =  Paper, 2 = Rock, &  3 = Scissors 

Ask students to share aloud other situations where it  would be necessary to generate random numbers…other games, lottery, etc.
-->

### Mathematical Functions

The ``Math`` class contains the following **methods** that are in the AP CSA subset. There are many more ``Math`` methods, outside of what you need on the AP exam, that you can find in the [Math class Javadocs](https://devdocs.io/openjdk~17/java.base/java/lang/math).

| Method      | Output |
| ----------- | ----------- |
| ``int abs(int)``| Returns the **absolute value** of an int value (which is the value of a number without its sign, for example ``Math.abs(-4)`` = 4) |
| ``double abs(double)``   | Returns the **absolute value** of a double value |
| ``double pow(double, double)`` | Returns the value of the first parameter **raised to the power** of the second parameter |
| ``double sqrt(double)`` |  Returns the **positive square root** of a double value |
| ``double random()`` |  Returns a random double value **greater than or equal to 0.0 and less than 1.0** (_not inclusive!_) |


{:.highlight}
All the ``Math`` methods that you may need to use or understand on the AP exam are listed in the [AP CSA Reference Sheet](https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf) that you can use during the exam.

These Math methods are mathematical functions that **compute new values** from their arguments. 

#### Absolute Value
{:.no_toc}

``Math.abs`` takes a single argument, either a ``double`` or an ``int`` and returns a value of the same type which is the **absolute value** of the argument. The absolute value is the positive value of the number without its sign or its distance from 0. 

```java
Math.abs(45);    // returns 45
Math.abs(-45);   // returns 45
Math.abs(33.3);  // returns 33.3
Math.abs(-33.3); // returns 33.3
```

#### Exponentiation
{:.no_toc}

``Math.pow`` takes two argument, both ``double``s and returns a ``double`` which is the first argument **raised to the power** of the second argument.

```java
Math.pow(2 , 3); // returns 8.0
Math.pow(10, 6); // returns 1000000.0
Math.pow(2, -3); // returns 0.125
```

#### Square Root
{:.no_toc}

``Math.sqrt`` takes an ``double`` argument and returns a positive ``double`` value which is the square root of the argument. 
> For example, the square root of 9 is 3 because 3 squared is 9.

```java
Math.sqrt(9); // returns 3.0
```

<div class="imp" markdown="block">
   
Since these methods calculate and _return_ a **value**, you need to _use_ that value, for example in an assignment statement or in a print statement to see the result. 

_For example:_

```java
System.out.println("The square root of 9 is " + Math.sqrt(9));
```

</div>

### Random Numbers

{:.highlight}
🎲 The ``Math.random()`` method returns a `double` number **greater than or equal to 0.0**, and **less than 1.0**.

When we talk about ranges of numbers, sometimes we need to be precise about whether the ends of the range are part of the range. When we need to be **precise** about this we’d say that it returns a number between 0, *inclusive*, and 1, *exclusive*, meaning *include* 0 but *exclude* 1. Lots of ranges in Java are expressed this way, as you’ll see later on with an inclusive bottom and exclusive top.

> For example, ``Math.random`` returns a number between 0 and 1, but does that mean it can return exactly 0? Or exactly 1?
> 
> As it turns out, it can return 0.0, but never returns 1.0.

#### MANIPULATING THE RETURN VALUE
{:.no_toc}

Getting a number between 0, inclusive, and 1, exclusive, may not seem all that useful. But we can expand the range easily enough by manipulating the output (adding, subtracing, multiplying or dividing the return value). And often we want a random integer, with nothing after the decimal point. Easy enough—casting a ``double`` to an ``int`` will throw away any values after the decimal point. For example:

```java
    // rnd is an integer in the range 0-9 (from 0 up to 10).
    int rnd = (int)(Math.random()*10);  
```

Finally, what if we want a number in a range that doesn’t start with 0, say a
number from 1 to 10 (including 10) instead of from 0 to 9 (including 9)? Since
the size of the two ranges is the same, with ten numbers in each, all we need to
do is shift from the range we’ve generated into the range we want. In other
words, add the difference between the two ranges, 1 in this case.    

```java
    // rnd is an integer in the range 1-10 (including 10).
    int rnd = (int)(Math.random()*10) + 1; 
```
    
<div class="important" markdown="block">
  
* `Math.random()` returns a random number between 0.0-0.99.
* `(int)(Math.random()*range) + min` moves the random number into a range starting from a minimum number.
* The **range** of possible values is: `(max - min + 1)`.
    
</div>

Here are some examples that move a random number into a specific range.

```java
// Math.random() returns a random number between 0.0-0.99.
double rnd = Math.random();

// rnd1 is an integer in the range 0-9 (including 9).
int rnd1 = (int)(Math.random()*10);

// rnd2 is in the range 1-10 (including 10). The parentheses are necessary!
int rnd2 = (int)(Math.random()*10) + 1;

// rnd3 is in the range 5-10 (including 10). The range is 10-5+1 = 6.
int rnd3 = (int)(Math.random()*6) + 5;

// rnd4 is in the range -10 up to 9 (including 9). The range is doubled (9 - -10 + 1 = 20) and the minimum is -10.
int rnd4 = (int)(Math.random()*20) - 10;
```

So the general recipe for generating a random is to first stretch the value from
``Math.random()`` until it’s in the right size range by multiplying by the size
of the range. Then if you want an integer value, cast to ``int`` to discard the
part after the decimal point. Then shift the value up by adding the minimum
value. 


---

## Summary

- (AP 1.11.A.1) The ``Math`` class is part of the ``java.lang`` package. Classes in the ``java.lang`` package are available by default.

- (AP 1.11.A.2) The Math class contains only class (static) methods. They can be called using **Math**.method(); for each method.

- (AP 1.11.A.2) The following static Math methods are part of the Java Quick Reference:

  - **int abs(int)** : Returns the absolute value of an int value (which means no negatives).
  - **double abs(double)** : Returns the absolute value of a double value.
  - **double pow(double, double)** : Returns the value of the first parameter raised to the power of the second parameter.
  - **double sqrt(double)** :  Returns the positive square root of a double value.
  - **double random()** :  Returns a double value greater than or equal to 0.0 and less than 1.0 (not including 1.0)!

- (AP 1.11.A.3) The values returned from ``Math.random()`` can be manipulated to produce a random int or double in a defined range.

- **(int)(Math.random() * range) + min** moves the random number into a range starting from a minimum number. The range is the **(max - min + 1)**. For example, to get a number in the range of 5 to 10, use the range 10-5+1 = 6 and the min number 5: ``(int)(Math.random()*6) + 5``.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
