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
📖 This page is a condensed version of [CSAwesome Topic 4.13]() 

---

# Implementing 2D Array Algorithms

All of the array algorithms can be applied to 2D arrays too.

There are standard algorithms that utilize 2D array traversals to:

- Determine a minimum or maximum value of all the elements or for a designated row, column, or other subsection.
- Compute a sum or average of all the elements or for a designated row, column, or other subsection.
- Determine if at least one element has a particular property in the entire 2D array or for a designated row, column, or other subsection.
- Determine if all elements of the 2D array or a designated row, column, or other subsection have a particular property.
- Determine the number of elements in the 2D array or in a designated row, column, or other subsection having a particular property.
- Access all consecutive pairs of elements.
- Determine the presence or absence of duplicate elements in the 2D array or in a designated row, column, or other subsection.
- Shift or rotate elements in a row left or right or in a column up or down.
- Reverse the order of the elements in a row or column.

---

## Traversal Patterns

With 1D arrays, many algorithms follow this pattern:

```java
// 1D Array Traversal
for (int value : array) {
    if (value ...) {
        ...
    }
}

for (int i = 0; i < array.length; i++) {
    if (array[i] ...) {
        ...
    }
}
````

With 2D arrays, you need **nested loops** to traverse rows and columns. Indexed `for` loops give more control, but you can also use enhanced `for` loops.

```java
// 2D Array Traversal (indexed)
for (int row = 0; row < array.length; row++) {
    for (int col = 0; col < array[0].length; col++) {
        if (array[row][col] ...) {
            ...
        }
    }
}

// 2D Array Traversal (enhanced)
for (int[] row : array) {
    for (int value : row) {
        if (value ...) {
            ...
        }
    }
}
```

---

## Example: Find the Largest Value

<div class="task" markdown="block">

**Instructions:**

1. Study the code — it finds the largest value in a 2D array.
2. Modify it to find the smallest value instead.
3. Test with your own 2D array.

```java
public static int findLargest(int[][] a) {
    int largest = a[0][0];
    for (int row = 0; row < a.length; row++) {
        for (int col = 0; col < a[0].length; col++) {
            if (a[row][col] > largest) {
                largest = a[row][col];
            }
        }
    }
    return largest;
}
```

</div>

---

## Example: Compute an Average

<div class="task" markdown="block">

**Instructions:**

1. Fill in the missing code to compute the average of all values in the 2D array.

```java
public static double average(int[][] a) {
    int total = 0;
    int count = 0;
    for (int row = 0; row < a.length; row++) {
        for (int col = 0; col < a[0].length; col++) {
            total += a[row][col];
            count++;
        }
    }
    return (double) total / count;
}
```

</div>

---

## Example: Count Elements with a Property

<div class="task" markdown="block">

**Instructions:**
Write a method `countPositive` that counts how many elements in a 2D array are positive.

```java
public static int countPositive(int[][] a) {
    int count = 0;
    for (int row = 0; row < a.length; row++) {
        for (int col = 0; col < a[0].length; col++) {
            if (a[row][col] > 0) {
                count++;
            }
        }
    }
    return count;
}
```

</div>

---

## Summary

* **Nested loops** are essential for 2D array algorithms.
* You can adapt 1D algorithms like `min`, `max`, `sum`, and `count` for 2D arrays.
* Traversals can be done with indexed or enhanced `for` loops.
* Many problems break down into:

  1. Initializing a variable (`min`, `max`, `sum`, `count`).
  2. Traversing with nested loops.
  3. Updating the variable based on a condition.
  4. Returning the result.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
