---
layout: notes
title: "📓4.4: Array Traversals" 
parent: "4️⃣ Data Collections"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.4]() 

---

# Array Traversals

In this lesson, we will learn how to traverse an array using a loop. **Traversing** an array means visiting each element of the array. We can use a loop to visit each element of an array and perform some operation on it.

---

## Index Variables

You can use a variable for the index of an array. You can even use arithmetic expressions inside the square brackets `[]`.

```java
int[] highScores = { 10, 9, 8, 8 };
int index = 3;
highScores[index] = 11;
System.out.println(highScores[index]);
System.out.println(highScores[index - 1]);
````

[Visualize this code](http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayWithIndexVar%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20int%5B%5D%20highScores%20%3D%20%7B%2010,%209,%208,%208%7D%3B%0A%20%20%20%20%20%20int%20index%20%3D%203%3B%0A%20%20%20%20%20%20highScores%5Bindex%5D%20%3D%2011%3B%0A%20%20%20%20%20%20System.out.println%28highScores%5Bindex%5D%29%3B%0A%20%20%20%20%20%20System.out.println%28highScores%5Bindex%20-%201%5D%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0).

---

## Traversing with a For Loop

```java
int[] nums = { 5, 10, 15, 20, 25 };

for (int i = 0; i < nums.length; i++) {
    System.out.println(nums[i]);
}
```

---

## Traversing in Reverse

```java
for (int i = nums.length - 1; i >= 0; i--) {
    System.out.println(nums[i]);
}
```

---

## Enhanced For Loop (For-Each)

```java
for (int value : nums) {
    System.out.println(value);
}
```

**Advantages:** Shorter and easier to read when you only need to access elements.
**Limitations:** Cannot modify array elements directly.

---

## Traversing Arrays of Objects

You can traverse arrays of objects with either an indexed for loop or an enhanced for loop.

**Example – Student Array Search:**

<div class="task" markdown="block">

1. Create a `findAndPrint(String name)` method that:

   * Uses an enhanced for loop to find a matching student by name.
   * Prints that student’s info.
2. Call it from `main` to test.

```java
public class StudentArray {
    private Student[] array;

    public StudentArray(int size) {
        array = new Student[size];
    }

    public void add(int i, Student s) {
        array[i] = s;
    }

    public void print() {
        for (Student s : array) {
            System.out.println(s);
        }
    }

    public static void main(String[] args) {
        StudentArray roster = new StudentArray(3);
        roster.add(0, new Student("Skyler", "skyler@sky.com", 123456));
        roster.add(1, new Student("Ayanna", "ayanna@gmail.com", 789012));
        roster.add(2, new Student("Dakota", "dak@gmail.com", 112233));
        roster.print();
    }
}

class Student {
    private String name, email;
    private int id;

    public Student(String n, String e, int i) {
        name = n;
        email = e;
        id = i;
    }

    public String getName() { return name; }
    public String getEmail() { return email; }
    public int getId() { return id; }

    public String toString() {
        return id + ": " + name + ", " + email;
    }
}
```

</div>

---

## Coding Challenge: Spell Checker

![Spell Checker](Figures/spellcheck.png)

<div class="task" markdown="block">

1. Write `print10()` to print the first 10 words of the `dictionary` array.
2. Write `spellcheck(String word)` to return `true` if the word is in the dictionary, otherwise `false`.
3. *(Optional)* Write `printStartsWith(String firstLetters)` to print all dictionary words that start with given letters.

```java
import java.io.*;
import java.nio.file.*;
import java.util.*;

public class SpellChecker {
    private String[] dictionary = new String[10000];

    public void print10() { /* your code */ }
    public boolean spellcheck(String word) { /* your code */ }

    public SpellChecker() throws IOException {
        List<String> lines = Files.readAllLines(Paths.get("dictionary.txt"));
        dictionary = lines.toArray(dictionary);
    }

    public static void main(String[] args) throws IOException {
        SpellChecker checker = new SpellChecker();
        // checker.print10();
        // System.out.println(checker.spellcheck("cat"));
    }
}
```

</div>

---

## Community Challenge: Array Loop

<div class="task" markdown="block">

1. Copy your class from [Lesson 4.3](../Unit4-Data-Collections/topic-4-3-array-basics.html#groupwork-design-an-array-of-objects-for-your-community).
2. Create an array of 3 objects of your class.
3. Initialize them using your constructor.
4. Write a loop to print each object.

</div>

---

## Summary

* **(AP 4.4.A.1)** Traversing an array means visiting each element in order.
* **(AP 4.4.A.2)** Indexed loops require using element indices.
* **(AP 4.4.A.3)** Enhanced for loop variables store copies of elements.
* **(AP 4.4.A.4)** Assigning to an enhanced loop variable does not change the array.
* **(AP 4.4.A.5)** You can change object attributes in arrays using methods inside an enhanced for loop.

---

## Arrays Game

[Play the Arrays Game](https://csa-games.netlify.app/) to practice array traversal.

<iframe height="700px" width="100%" style="margin-left:10%;max-width:80%" src="https://csa-games.netlify.app/"></iframe>



---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
