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

## Traversing 2D Arrays with Nested Loops

Since 2D arrays are really arrays of arrays, you can use **nested loops** to iterate through all elements in an array. We first loop through each of the rows (the "_inner arrays_"), and then loop through all the values inside each inner array.

![image](Figures/ArrayRowsAndCols.png)

### Enhanced For-Each Loops

An **enhanced for-each** loop "visits" each item in an array sequentially. Notice the type of the outer loop array variable - it is an array that will hold each row, `String[]` in the example below for a 2D String array. The `type` of the variables in the for-each loops must match the type of the array. 

```java
String[][] data;

// ENHANCED FOR-EACH nested loops to traverse 2D array
for (String[] rowArray : data) {
  for (String colValue : rowArray) {
    System.out.println(colValue);
  }
}
```
> In this case the ``for (String[] rowArray : array)`` means to loop through each element of the _outer_ array (`data`) which will set the current ``rowArray`` to the current array of columns. Then the _inner_ loop iterates through the _inner_ array (the current "column"), printing each of the values (`colValue`).

<div class="warn" markdown="block">

_**DATA TYPES:**_ To traverse with enhanced for-each loops, the variable of the _outer_ loop must be the `type` of each **row** - which is a 1D `array`. The _inner_ enhanced for loop variable must be the same `type` as the **elements** stored in the array.

</div>

### Standard For Loops

When writing **nested loops** to traverse a 2D array, **for-each** loops like above are much simpler since you don't have to use the indices and the `[]`'s, but you can only use them if you are NOT going to **modify the values** in an array. 

If you _do_ need to change values, or keep track of the index for another reason, stick to a **standard (indexed) for** loop:

```java
// STANDARD/INDEXED FOR nested loops to traverse 2D array
for (int row = 0; row < data.length; row++) {
  for (int col = 0; col < data[row].length; col++) {
    System.out.println(data[row][col]);
  }
}
```

<div class="imp" markdown="block">

* `array.length` provides the number of **rows** in a 2D array
* `array[0].length` provides the number of **columns**
  > The length of the _inner_ array (`array[0]` is the first _row_)

</div>

#### Looping through a Subset
{:.no_toc}

You can loop through a _subset_ (smaller portion) of a 2D array as long as you use a **standard for loop**. You just change the _starting_ and _ending_ bounds for your loops: 

```java
int[][] matrix = { {3, 2, 3}, {4, 3, 6}, {8, 9, 3}, {10, 3, 3}};

for (int row = 1; row < 3; row++) {
  for (int col = 0; col <= 2; col++) {
    System.out.println(matrix[row][col]);
  }
}
```
> 💬 **DISCUSS:** What do you think the above code will print out? Which part of the `matrix` 2D array?

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

## ⭐️ Summary 


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
