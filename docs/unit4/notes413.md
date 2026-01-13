---
layout: notes
title: "📓4.13: 2D Array Algorithms" 
parent: "4️⃣ Data Collections"
nav_order: 13
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.13](https://runestone.academy/ns/books/published/csawesome2/topic-4-13-2Darray-algorithms.html) 

---

### 2D Array Algorithms

All of the array **algorithms** can be applied to 2D arrays too. For example, *counting* and *searching* algorithms work very similarly. 

#### 🧮 Counting/Accumulating
{:.no_toc}

**Method Definition:**
```java
public static int getTotalForRow(int row, int[][] a) {
  int total = 0;
  for (int col = 0; col < a[0].length; col++) {
    total = total + a[row][col];
  }
  return total;
}
```
**Method Call (in `main`):**
```java
public static void main(String[] args) {
  int[][] matrix = { {1, 2, 3}, {4, 5, 6}};
  System.out.println(getTotalForRow(0, matrix));
}
```

<div class="task" markdown="block">

💻 Can you complete the method called ``getTotalForCol`` that computes the total for a column? To do this, you must loop through the `row`s. The array's `length` will tell you how many _rows_ you have, while the length of the array's first element will tell you how many _columns_.

```java
public static int getTotalForCol(int col, int[][] a) {
  int total = 0;
  // Add a loop here to total a column col

  return total;
}
```

</div>

#### 🔍 Linear Search
{:.no_toc}

The **linear (sequential) search algorithm** for a 2D array iterates through all of the _rows_ and _columns_ until either the **target** value is found, or the entire 2D array has been traversed without finding the target. 

**Method Definition:**
```java
public static boolean search(int[][] array, int value) {
  boolean found = false;
  for (int row = 0; row < array.length; row++) {
    for (int col = 0; col < array[0].length; col++) {
      if (array[row][col] == value) {
        found = true;
      }
    }
  }
  return found;
}
```
**Method Call (in `main`):**
```java
public static void main(String[] args) {
  int[][] matrix = { {3, 2, 3}, {4, 3, 6}, {8, 9, 3}, {10, 3, 3}};
  System.out.println(search(matrix, 10));
  System.out.println(search(matrix, 11));
}
```

<div class="task" markdown="block">

💻 Can you change the method's code to work for a `String` 2D array instead of an `int` array? Note that the **indices** `row` and `col` will still be integers.

```java
// In the MAIN method, try these:
String[][] matrix2 = { {"a","b","c"},{"d","e","f"} };
System.out.println(search(matrix2, "b"));
```

</div>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
