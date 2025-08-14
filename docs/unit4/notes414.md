---
layout: notes
title: "📓4.14: Searching Algorithms" 
parent: "4️⃣ Data Collections"
nav_order: 14
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.14](https://runestone.academy/ns/books/published/csawesome2/topic-4-14-searching.html) 

---

# Searching Algorithms

Computers store vast amounts of data. One of the strengths of computers is their ability to find things quickly. This ability is called **searching**. For the AP CSA exam, you need to know both **linear (sequential) search** and **binary search** algorithms.

<iframe width="700" height="400" src="https://www.youtube.com/embed/DHLCXXX1OtE" frameborder="0" allowfullscreen></iframe>

- **Linear search** is a standard algorithm that checks each element in order until the desired value is found or all elements in the array or `ArrayList` have been checked. Linear search can begin from either end of the array or `ArrayList`.
- **Binary search** can only be used on **sorted** data. It checks the middle value to determine if it’s less than, equal to, or greater than the target, then narrows the search accordingly — cutting the search space in half each time.

If binary search requires sorted data, how can you sort it? There are many sorting algorithms, which we will cover in the next lesson.

---

## Linear Search

Linear (or sequential) search works on *unsorted* data. It starts at the first element and walks through the array or `ArrayList` until it finds the target, returning its index. If the search reaches the end without finding the value, it usually returns `-1`.

<div class="task" markdown="block">

**GitHub Codespaces Instructions:**  
Type this code in your Codespace, press run, and then modify it to search for a different value.

```java
public class LinearSearchExample {
    public static int linearSearch(int[] array, int target) {
        for (int i = 0; i < array.length; i++) {
            if (array[i] == target) {
                return i; // found
            }
        }
        return -1; // not found
    }

    public static void main(String[] args) {
        int[] nums = {4, 8, 15, 16, 23, 42};
        System.out.println("Index of 15: " + linearSearch(nums, 15)); // Expected: 2
    }
}
````

</div>

---

## Binary Search

Binary search only works on **sorted** data. The algorithm:

1. Looks at the middle element.
2. If it’s the target, you’re done.
3. If the target is less, search the left half.
4. If the target is greater, search the right half.
5. Repeat until found or search space is empty.

<div class="task" markdown="block">

**GitHub Codespaces Instructions:**
Type this code in your Codespace, press run, and then test with different sorted arrays and targets.

```java
public class BinarySearchExample {
    public static int binarySearch(int[] array, int target) {
        int low = 0;
        int high = array.length - 1;
        
        while (low <= high) {
            int mid = (low + high) / 2;
            if (array[mid] == target) {
                return mid; // found
            } else if (array[mid] < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return -1; // not found
    }

    public static void main(String[] args) {
        int[] nums = {4, 8, 15, 16, 23, 42};
        System.out.println("Index of 15: " + binarySearch(nums, 15)); // Expected: 2
    }
}
```

</div>

---

## Summary

* **Linear search** works on unsorted data; checks each element in turn.
* **Binary search** works only on sorted data; repeatedly halves the search range.
* Binary search is faster than linear search for large, sorted datasets.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
