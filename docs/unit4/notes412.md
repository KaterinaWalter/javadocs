---
layout: notes
title: "📓4.12: 2D Array Traversals" 
parent: "4️⃣ Data Collections"
nav_order: 12
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.12](https://runestone.academy/ns/books/published/csawesome2/topic-4-12-2Darray-traversal.html) 

---

# 2D Array Traversals: Nested Loops

In this lesson, you will learn how to use nested loops to traverse 2D arrays.

---

## Nested Loops

Nested iteration statements (loops) are used to traverse and access all or an ordered sequence of elements in a 2D array.  
Since 2D arrays are stored as arrays of arrays, the way 2D arrays are traversed using `for` loops and enhanced `for` loops is similar to 1D arrays.

Here is an example of a **nested for loop** to traverse all elements of a 2D array:

```java
int[][] array = { {1, 2, 3}, {4, 5, 6} };
for (int row = 0; row < array.length; row++) {
    for (int col = 0; col < array[0].length; col++) {
        System.out.println(array[row][col]);
    }
}
````

---

## Coding Exercise: Calculating Average in a 2D Array

<div class="task" markdown="block">

**Instructions:**

1. Review the code below — it calculates the average of all elements in a 2D array.
2. Add another row of numbers to `matrix`. Will the loops traverse this row too?
3. Run and observe.
4. Use CodeLens to trace through the code and confirm.

```java
public class Test1 {
    public static double getAverage(int[][] a) {
        double total = 0;
        int value = 0;
        for (int row = 0; row < a.length; row++) {
            for (int col = 0; col < a[0].length; col++) {
                value = a[row][col];
                total = total + value;
            }
        }
        return total / (a.length * a[0].length);
    }

    public static void main(String[] args) {
        int[][] matrix = { {1, 2, 3}, {4, 5, 6} };
        System.out.println(getAverage(matrix));
    }
}
```

</div>

---

## Traversing with Enhanced For Loops

You can also use **enhanced for loops** to traverse 2D arrays. Each `row` is itself a 1D array, and the inner loop iterates over each element in that row.

```java
int[][] array = { {1, 2, 3}, {4, 5, 6} };
for (int[] row : array) {
    for (int value : row) {
        System.out.println(value);
    }
}
```

---

## Challenge: Find the Maximum Value

<div class="task" markdown="block">

**Instructions:**
Write a method `findMax` that takes a 2D array of integers and returns the largest value.

```java
public static int findMax(int[][] arr) {
    // Your code here
}
```

Test with:

```java
int[][] nums = { {3, 5, 1}, {4, 8, 2} };
System.out.println(findMax(nums)); // Expected: 8
```

</div>

---

## Summary

* **Nested loops** are used to traverse 2D arrays.
* Outer loop goes over rows, inner loop goes over columns.
* **Enhanced for loops** can simplify traversal when you don't need row/column indices.
* Be aware of the dimensions: `array.length` gives rows, `array[0].length` gives columns.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
