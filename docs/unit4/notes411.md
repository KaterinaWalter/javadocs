---
layout: notes
title: "📓4.11: 2D Array Creation & Access" 
parent: "4️⃣ Data Collections"
nav_order: 11
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.11](https://runestone.academy/ns/books/published/csawesome2/topic-4-11-2Darrays.html) 

---

# 2D Arrays

A **2D array** is an array of arrays, useful for representing grids, tables, or matrices. In Java, a 2D array is declared as:

```java
int[][] matrix;
````

You can think of a 2D array as rows and columns, like a spreadsheet.

---

## Declaring and Initializing 2D Arrays

You can declare and initialize a 2D array in several ways:

```java
int[][] nums = new int[3][4]; // 3 rows, 4 columns
```

This creates a 3-by-4 grid of integers, all initialized to 0.

You can also initialize with values:

```java
int[][] nums = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};
```

---

## Accessing Elements

Use two indices: the first for the row, the second for the column.

```java
System.out.println(nums[1][2]); // prints 7
```

Rows and columns are zero-indexed.

---

## Traversing a 2D Array

**Nested for loops** are commonly used to traverse 2D arrays.

```java
for (int row = 0; row < nums.length; row++) {
    for (int col = 0; col < nums[row].length; col++) {
        System.out.print(nums[row][col] + " ");
    }
    System.out.println();
}
```

---

## Enhanced for Loops with 2D Arrays

You can use enhanced `for` loops for each row, then for each element in the row.

```java
for (int[] row : nums) {
    for (int val : row) {
        System.out.print(val + " ");
    }
    System.out.println();
}
```

---

## Practice: Fill a 2D Array

<div class="task" markdown="block">

**Instructions:**
Create a `3x3` integer 2D array and fill it with numbers from 1 to 9 in order. Then print it using nested loops.

```java
public class FillArray {
    public static void main(String[] args) {
        int[][] nums = new int[3][3];
        // Fill with numbers 1 to 9
        // Print the array
    }
}
```

</div>

---

## 2D Arrays with Objects

2D arrays can hold objects as well as primitives.

```java
String[][] seatingChart = new String[2][3];
seatingChart[0][0] = "Alice";
seatingChart[0][1] = "Bob";
```

---

## Jagged Arrays

In Java, 2D arrays are arrays of arrays, so each row can have a different length.

```java
int[][] jagged = {
    {1, 2},
    {3, 4, 5},
    {6}
};
```

---

## Example: Tic-Tac-Toe Board

<div class="task" markdown="block">

Create a 3x3 `String` 2D array to represent a tic-tac-toe board. Fill it with `"-"` to represent empty spaces, then print it.

```java
public class TicTacToe {
    public static void main(String[] args) {
        String[][] board = new String[3][3];
        // Fill and print board
    }
}
```

</div>

---

## Summary

* A **2D array** is an array of arrays: `type[][] name`.
* Access elements with `array[row][col]`.
* Traverse with nested loops.
* Rows can have different lengths (jagged arrays).
* Can store primitives or objects.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
