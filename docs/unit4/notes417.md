---
layout: notes
title: "📓4.17: Recursive Searching & Sorting" 
parent: "4️⃣ Data Collections"
nav_order: 17
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.17]() 

---

# Recursive Searching and Sorting

In previous lessons, we learned about searching and sorting algorithms using iteration (loops) to search or sort arrays and `ArrayLists`. In this lesson, we will take a look at a **recursive binary search** algorithm and a **recursive merge sort** algorithm. Recursion can be used to traverse `String` objects, arrays, and `ArrayList` objects.

---

## Recursive Binary Search

We have already seen two search algorithms using loops:  
- **Linear search** — checks each element in order.  
- **Binary search** — more efficient because it starts at the middle of a **sorted** array or `ArrayList` and eliminates half each pass.

Binary search can be written iteratively (with a loop) or recursively.

**Iterative version:**

```java
public class IterativeBinarySearch {
    public static int binarySearch(int[] elements, int target) {
        int left = 0;
        int right = elements.length - 1;
        while (left <= right) {
            int middle = (left + right) / 2;
            if (target < elements[middle]) {
                right = middle - 1;
            } else if (target > elements[middle]) {
                left = middle + 1;
            } else {
                return middle;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] arr1 = {-20, 3, 15, 81, 432};
        int index = binarySearch(arr1, 81);
        System.out.println(index);
    }
}
````

---

**Recursive version:**

```java
public class RecursiveBinarySearch {
    public static int binarySearch(int[] elements, int target, int left, int right) {
        if (left > right) {
            return -1;
        }
        int middle = (left + right) / 2;
        if (target < elements[middle]) {
            return binarySearch(elements, target, left, middle - 1);
        } else if (target > elements[middle]) {
            return binarySearch(elements, target, middle + 1, right);
        } else {
            return middle;
        }
    }

    public static void main(String[] args) {
        int[] arr1 = {-20, 3, 15, 81, 432};
        int index = binarySearch(arr1, 81, 0, arr1.length - 1);
        System.out.println(index);
    }
}
```

---

## Recursive Merge Sort

Merge sort is a **divide-and-conquer** algorithm:

1. Split the array into halves until arrays of length 1 (base case).
2. Merge sorted halves back together.

```java
public class MergeSort {
    public static void sort(int[] arr) {
        if (arr.length <= 1) return;

        int mid = arr.length / 2;
        int[] left = new int[mid];
        int[] right = new int[arr.length - mid];

        for (int i = 0; i < mid; i++) {
            left[i] = arr[i];
        }
        for (int i = mid; i < arr.length; i++) {
            right[i - mid] = arr[i];
        }

        sort(left);
        sort(right);
        merge(arr, left, right);
    }

    private static void merge(int[] result, int[] left, int[] right) {
        int i = 0, j = 0, k = 0;
        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) {
                result[k++] = left[i++];
            } else {
                result[k++] = right[j++];
            }
        }
        while (i < left.length) {
            result[k++] = left[i++];
        }
        while (j < right.length) {
            result[k++] = right[j++];
        }
    }

    public static void main(String[] args) {
        int[] arr1 = {38, 27, 43, 3, 9, 82, 10};
        sort(arr1);
        for (int num : arr1) {
            System.out.print(num + " ");
        }
    }
}
```

---

## Summary

* **Recursive binary search** works the same as iterative but calls itself on a smaller range.
* **Merge sort** uses recursion to split the array and merge sorted halves.
* Recursion can often make code shorter, but you must have:

  * A **base case** to stop recursion.
  * Recursive calls that move toward that base case.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
