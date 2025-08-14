---
layout: notes
title: "📓4.10: ArrayList Algorithms" 
parent: "4️⃣ Data Collections"
nav_order: 10
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.10]() 

---

# ArrayList Algorithms

In this lesson, you'll learn common algorithms for working with `ArrayList` objects. These involve traversing the list and applying some operation on each element.

## Finding Minimum or Maximum

We can traverse an `ArrayList` to determine the minimum or maximum value. For example, the following method finds the minimum value in an `ArrayList` of integers.

<div class="task" markdown="block">

**GitHub Codespaces Instructions:**  
Type this in your Codespace, press run, and observe the output. Modify the loop to find the **maximum** value instead.

```java
import java.util.*;

public class TestMin {
    public static int findMin(ArrayList<Integer> nums) {
        int min = nums.get(0);
        for (int val : nums) {
            if (val < min) {
                min = val;
            }
        }
        return min;
    }

    public static void main(String[] args) {
        ArrayList<Integer> values = new ArrayList<>(Arrays.asList(5, 7, 2, 9, -1));
        System.out.println("Expected Result:\t -1");
        System.out.println("Your Result:\t\t " + findMin(values));
    }
}
```

</div>

---

## Computing a Sum or Average

We can compute the sum of all elements, then divide by the size to find the average.

<div class="task" markdown="block">

**Try it:** Write a method `average` that returns the average of the integers in an `ArrayList<Integer>`.

```java
import java.util.*;

public class TestAverage {
    public static double average(ArrayList<Integer> nums) {
        // Add code here
        return 0;
    }

    public static void main(String[] args) {
        ArrayList<Integer> values = new ArrayList<>(Arrays.asList(2, 4, 6, 8));
        System.out.println("Expected Result:\t 5.0");
        System.out.println("Your Result:\t\t " + average(values));
    }
}
```

</div>

---

## Checking for an Element with a Property

We can determine if **at least one** element meets a condition. This method returns `true` if at least one number is odd:

```java
for (int num : nums) {
    if (num % 2 != 0) {
        return true;
    }
}
return false;
```

Similarly, to check if **all** elements meet a condition, return `false` as soon as you find one that doesn't.

---

## Counting Elements with a Property

To count how many elements have a particular property, initialize a counter and increment it when the property is found.

<div class="task" markdown="block">

**Your turn:** Write a method `countOdd` that returns the number of odd numbers in an `ArrayList<Integer>`.

```java
import java.util.*;

public class TestCountOdd {
    public static int countOdd(ArrayList<Integer> nums) {
        // Add code here
        return 0;
    }

    public static void main(String[] args) {
        ArrayList<Integer> values = new ArrayList<>(Arrays.asList(1, 5, 7, 9, -2, 3, 2));
        System.out.println("Expected Result:\t 5");
        System.out.println("Your Result:\t\t " + countOdd(values));
    }
}
```

</div>

---

## Pairs and Duplicates

You can traverse **pairs** of elements in an `ArrayList` with nested loops.
Example: check for duplicates.

<div class="task" markdown="block">

**Try it:** Write `hasDuplicates` that returns `true` if there are any duplicate integers.

```java
import java.util.*;

public class TestDuplicates {
    public static boolean hasDuplicates(ArrayList<Integer> nums) {
        // Add code here
        return false;
    }

    public static void main(String[] args) {
        ArrayList<Integer> values1 = new ArrayList<>(Arrays.asList(0, 1, 2, 3, 4));
        ArrayList<Integer> values2 = new ArrayList<>(Arrays.asList(0, 1, 2, 2, 4));
        System.out.println("Expected Result: false, true");
        System.out.println("Your Result: " + hasDuplicates(values1) + ", " + hasDuplicates(values2));
    }
}
```

</div>

---

## Shifting / Rotating

We can rotate elements left or right by moving the values.
Example: rotating right by one.

<div class="task" markdown="block">

**Your turn:** Write `rotateLeft` that rotates integers in an `ArrayList` left by one position.

```java
import java.util.*;

public class TestRotate {
    public static void rotateLeft(ArrayList<Integer> nums) {
        // Add code here
    }

    public static void main(String[] args) {
        ArrayList<Integer> values = new ArrayList<>(Arrays.asList(1, 5, 7));
        rotateLeft(values);
        System.out.println("Expected Result: [5, 7, 1]");
        System.out.println("Your Result: " + values);
    }
}
```

</div>

---

## Reversing an ArrayList

We can reverse an `ArrayList` by adding each element to the front of a new list.

<div class="task" markdown="block">

**Try it:** Complete `reverse` to return an `ArrayList` with the reversed order.

```java
import java.util.*;

public class TestReverse {
    public static ArrayList<Integer> reverse(ArrayList<Integer> list) {
        ArrayList<Integer> reversed = new ArrayList<>();
        // Add code here
        return reversed;
    }

    public static void main(String[] args) {
        ArrayList<Integer> values = new ArrayList<>(Arrays.asList(0, 1, 2, 3));
        ArrayList<Integer> result = reverse(values);
        System.out.println("Expected Result:\t [3, 2, 1, 0]");
        System.out.println("Your Result:\t\t " + result);
    }
}
```

</div>

---

## Multiple or Parallel Data Structures

Sometimes algorithms require traversing two or more lists in parallel.

<div class="task" markdown="block">

**Try it:** Complete the loop to sum grades from two `ArrayList<Integer>` objects.

```java
import java.util.*;

public class ParallelTests {
    public static void main(String[] args) {
        ArrayList<Integer> test1Grades = new ArrayList<>(Arrays.asList(100, 80, 70));
        ArrayList<Integer> test2Grades = new ArrayList<>(Arrays.asList(100, 70, 90));
        double total = 0;

        // Add loop here to sum both lists' grades into total

        int numberOfGrades = test1Grades.size() * 2;
        System.out.println("Average over two tests: " + total / numberOfGrades);
    }
}
```

</div>

---

## Summary

* There are standard `ArrayList` algorithms that use traversals to:

  * Determine a minimum or maximum value
  * Compute a sum or average
  * Determine if at least one element has a property
  * Determine if all elements have a property
  * Count elements with a property
  * Access all consecutive pairs
  * Check for duplicates
  * Shift or rotate
  * Reverse the order
  * Insert or delete elements
* Some algorithms require traversing multiple structures in parallel.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
