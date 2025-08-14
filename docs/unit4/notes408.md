---
layout: notes
title: "📓4.8: ArrayList Class" 
parent: "4️⃣ Data Collections"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.8]() 

---

# ArrayLists

An **ArrayList** is a resizable list in Java that can store objects. Unlike arrays, ArrayLists can change their size during runtime by adding or removing elements. They are part of the `java.util` package.

**Note:** ArrayLists can only store object references, not primitive types like `int` or `double`. Use wrapper classes such as `Integer` or `Double` instead. Java’s autoboxing feature often handles this conversion automatically.

---

## Importing and Creating ArrayLists

To use ArrayLists, import them:

```java
import java.util.ArrayList;
````

You can also import all classes in `java.util`:

```java
import java.util.*;
```

Create an ArrayList using:

```java
ArrayList<Type> name = new ArrayList<Type>();
```

For example:

```java
ArrayList<String> names = new ArrayList<String>();
```

---

## Adding Items to an ArrayList

Use the `.add()` method to append elements:

<div class="task" markdown="block">

Type this into your Codespace, run it, and observe the output.

```java
import java.util.*;

public class AddExample {
    public static void main(String[] args) {
        ArrayList<String> names = new ArrayList<String>();
        names.add("Diego");
        names.add("Grace");
        names.add("Deja");
        System.out.println(names);
    }
}
```

</div>

---

## Adding and Removing by Index

You can specify the index where an item should be added:

```java
list.add(index, value);
```

To remove an item by index:

```java
list.remove(index);
```

Example:

<div class="task" markdown="block">

Modify and run this code. Try adding items at different indices and removing them.

```java
import java.util.*;

public class AddRemoveExample {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<Integer>();
        numbers.add(1);
        numbers.add(2);
        numbers.add(3);
        numbers.add(1, 5); // inserts 5 at index 1
        System.out.println(numbers);
        numbers.remove(2); // removes element at index 2
        System.out.println(numbers);
    }
}
```

</div>

---

## Getting and Setting Elements

Use `.get(index)` to retrieve an element and `.set(index, value)` to replace it.

<div class="task" markdown="block">

Type this in and make changes to see the results.

```java
import java.util.*;

public class GetSetExample {
    public static void main(String[] args) {
        ArrayList<String> nameList = new ArrayList<String>();
        nameList.add("Diego");
        nameList.add("Grace");
        nameList.add("Deja");
        System.out.println(nameList);
        System.out.println(nameList.get(0));
        System.out.println(nameList.get(1));
        nameList.set(1, "John");
        System.out.println(nameList);
    }
}
```

</div>

---

## Comparing Arrays and ArrayLists

**When to use arrays:**

* You know the number of elements ahead of time
* The order and number of items will not change

**When to use ArrayLists:**

* The number of elements can change
* You need to frequently add or remove items

**Example:**

```java
// Arrays - must specify a size
int[] highScores = new int[5];
String[] names = new String[5];

// ArrayLists - start empty
ArrayList<Integer> highScoreList = new ArrayList<Integer>();
ArrayList<String> nameList = new ArrayList<String>();
```

---

| Operation   | Array Syntax            | ArrayList Syntax           |
| ----------- | ----------------------- | -------------------------- |
| length/size | `array.length`          | `list.size()`              |
| Access      | `value = array[index];` | `value = list.get(index);` |
| Modify      | `array[index] = value;` | `list.set(index, value);`  |

---

## Practice: Convert Array to ArrayList

<div class="task" markdown="block">

Rewrite this code to use an ArrayList instead of an array. Comment why an ArrayList is better for this problem.

```java
import java.util.*;

public class ToDoList {
    public static void main(String[] args) {
        String[] toDoList = new String[3];
        toDoList[0] = "Do homework";
        toDoList[1] = "Help make dinner";
        toDoList[2] = "Call grandma";

        toDoList[1] = "Order pizza";

        System.out.println(toDoList.length + " things to do!");
        System.out.println("Here's the first thing to do: " + toDoList[0]);

        toDoList[0] = toDoList[1];
        toDoList[1] = toDoList[2];
        toDoList[2] = "";

        System.out.println("Here's the next thing to do: " + toDoList[0]);
    }
}
```

</div>

---

## Creating an ArrayList from an Array

```java
import java.util.*;

public class ArrayListFromArray {
    public static void main(String[] args) {
        String[] names = {"Dakota", "Madison", "Brooklyn"};
        ArrayList<String> namesList = new ArrayList<String>(Arrays.asList(names));
        System.out.println(namesList);
    }
}
```

---

## Coding Challenge: FRQ Digits

Construct a `Digits` class that breaks an integer into its digits and stores them in an ArrayList in the correct order.

<div class="task" markdown="block">

Write the constructor using a loop. Use `add(0, value)` to insert at the beginning so digits are in correct order.

```java
import java.util.*;

public class Digits {
    private ArrayList<Integer> digitList;

    public Digits(int number) {
        // initialize digitList
        // use while loop and % / operators to get digits
        // use add(0, digit) to insert at front
    }

    public String toString() {
        return digitList.toString();
    }

    public static void main(String[] args) {
        Digits d1 = new Digits(154);
        System.out.println(d1);
    }
}
```

</div>

---

## Summary

* **ArrayLists** are resizable lists for storing objects.
* Part of `java.util` package.
* Use generics: `ArrayList<E>` to specify type.
* Cannot store primitives directly—use wrapper classes.
* Key methods:

  * `size()`
  * `add(E obj)`
  * `add(int index, E obj)`
  * `remove(int index)`
  * `get(int index)`
  * `set(int index, E obj)`
* Use arrays when size is fixed; ArrayLists when size changes.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
