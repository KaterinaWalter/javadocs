---
layout: notes
title: "📓4.15: Sorting Algorithms" 
parent: "4️⃣ Data Collections"
nav_order: 15
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.15](https://runestone.academy/ns/books/published/csawesome2/topic-4-15-sorting.html) 

---

# Sorting Algorithms

There are many sorting algorithms to put an array or `ArrayList` elements in alphabetic or numerical order. **Selection sort** and **insertion sort** are iterative sorting algorithms that can be used to sort elements in an array or `ArrayList`.  

For the AP CSA exam, you need to know:

- **Selection sort** — repeatedly selects the smallest (or largest) element from the unsorted portion of the list and swaps it into its correct (final) position in the sorted portion of the list.
- **Insertion sort** — inserts an element from the unsorted portion into its correct (but not necessarily final) position in the sorted portion by shifting elements to make room.
- **Merge sort** — recursively splits the array into halves until arrays of one element remain (base case), then merges the sorted halves. Merge sort will be covered in Lesson 4.17.

---

## Selection Sort

Selection sort usually starts at index 0, looks through the array to find the smallest value’s index, and swaps it with index 0. Then it repeats for index 1, index 2, and so on, until the array is sorted.

<iframe width="700" height="400" src="https://www.youtube.com/embed/Ns4TPTC8whw" frameborder="0" allowfullscreen></iframe>

Here’s an example:

```java
public static void selectionSort(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        // swap
        int temp = arr[minIndex];
        arr[minIndex] = arr[i];
        arr[i] = temp;
    }
}
````

---

## Insertion Sort

Insertion sort builds the sorted list one element at a time, inserting each new element into its correct position in the already-sorted portion.

```java
public static void insertionSort(int[] arr) {
    for (int i = 1; i < arr.length; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
```

---

## Comparing Selection and Insertion Sort

* **Selection sort**: fewer swaps, but always scans the entire remaining list.
* **Insertion sort**: may do fewer comparisons if the list is nearly sorted.
* Both have worst-case time complexity `O(n^2)`.

---

## Practice: Sorting with Both Methods

<div class="task" markdown="block">

**Instructions:**

1. Create an array of integers.
2. Sort it using selection sort and print the result.
3. Sort it using insertion sort and print the result.
4. Compare the output.

</div>

---

## Summary

* **Selection sort** — finds smallest, swaps into place; simple but slow for large data.
* **Insertion sort** — builds sorted section by inserting into correct spot.
* **Merge sort** — efficient divide-and-conquer algorithm (covered in Lesson 4.17).

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
