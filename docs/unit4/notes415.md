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

## Sorting Algorithms

There are many **sorting algorithms** to put an `array` or `ArrayList` elements in _alphabetical_ or _numerical_ order. We will show these algorithms below for arrays. The three sorting algorithms that you need to know for the AP CSA exam are:

1. **Selection Sort** - Select the _smallest item_ from the current location on to the end of the array and _swap_ it with the value at the current position. Do this from index `0` to the array `length - 1`.
  > You don't have to process the last element in the array, it will already be sorted when you compare the prior element to the last element.
2. **Insertion Sort** - Insert the _next unsorted element_ in the already sorted part of the array by moving larger values to the right. Start at index `1` and loop through the entire array.
3. **Merge Sort** - Break the elements into two parts and _recursively_ sort each part. An array of one item is sorted (base case). Then merge the two sorted arrays into one.
  > Merge Sort will be covered in Unit 10.

### Selection Sort

The **selection sort** that you need to know for the exam starts at index `0` and looks through the entire array keeping track of the _index of the smallest value_ in the array, and then _swaps_ the value at the smallest index with the value at index 0. Then it does the same thing for index 1, then 2, and so on until it reaches the length of the array minus one. At this point the array is sorted in **ascending** order.

<iframe width="560" height="315" src="https://www.youtube.com/embed/g-PGLbMth_g?si=N_YyodtHasxVEsF8" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<div class="imp" markdown="block">
  
🔍 To _identify_ a **Selection Sort** look for the following:

* A **nested for loop** with the _outer_ loop starting at `0` and ending when the index reaches `length - 1`
* The **index of the smallest value** should start at the _outer_ loop index
* The _inner_ loop should start at the _outer_ loop `index + 1` and iterate through the whole array
* If the **value** in the array at the _index_ of the inner loop is _less than_ the value at the smallest index, then **reset** the smallest index to the index of the _inner_ loop
* **Swap** the value at the _outer_ loop index and the smallest value (the one at the smallest value index)

</div>

The code for ``selectionSort`` below is from the AP CSA course description:

```java
public static void selectionSort(int[] elements) {
    for (int j = 0; j < elements.length - 1; j++) {
        int minIndex = j;
        for (int k = j + 1; k < elements.length; k++) {
            if (elements[k] < elements[minIndex]) {
                minIndex = k;
            }
        }
        int temp = elements[j];
        elements[j] = elements[minIndex];
        elements[minIndex] = temp;
    }
}
```

👯 Here is a folk dance video that demonstrates the **selection sort** process:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ns4TPTC8whw?si=LaJ1QeBRrH5ecawu" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Insertion Sort

The **insertion sort** that you need to know for the exam starts at index `1` and *inserts* the value at index 1 into its correct place in the **already sorted part** (the part to the _left_ of the current index). It moves any value _larger_ than the value stored in `temp` to the _right_, until it either finds the appropriate place to put `temp` OR gets to the front of the array.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JU767SDMDvA?si=CD9wJ7AnHo65a3RF" title="YouTube video player" frameborder="0" allow="accelerometer;  clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<div class="imp" markdown="block">
  
🔍 To _identify_ an **Insertion Sort** look for the following:

* An _outer_ `for` loop that starts at index `1` and iterates through the entire array
* **Storing** the element value at the _outer_ loop index in `temp`
* **Setting** the possible index to the _outer_ loop index
* An _inner_ `while` loop that loops while the possible index is _greater than_ `0` AND the value in `temp` is _less than_ the value at the possible index minus one
* Set the **value** at the possible index to the one to the _left_ of it (the one at possible index minus one)
* **Decrement** the possible index (subtract one from it)
* When the `while` loop ends, set the value at the possible index to `temp`

</div>

The code for ``insertionSort`` below is from the AP CSA course description:

```java
public static void insertionSort(int[] elements) {
    for (int j = 1; j < elements.length; j++) {
        int temp = elements[j];
        int possibleIndex = j;
        while (possibleIndex > 0 && temp < elements[possibleIndex - 1]) {
            elements[possibleIndex] = elements[possibleIndex - 1];
            possibleIndex--;
        }
    elements[possibleIndex] = temp;
    }
}
```

👯 Here is a folk dance video that demonstrates the **insertion sort** process:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ROalU379l3U?si=dyUVAag8YDyD_Wbk" title="YouTube video player" frameborder="0" allow="accelerometer;  clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


#### 💻 In-Class Activity: Sort Runtimes
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-4-15-sorting.html"><button type="button" name="button" class="btn">CSAwesome Topic 4.15</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Sort Runtimes** in groups.

</div>

---

## ⭐️ Summary
- (AP 4.15.A.1)	Selection sort and insertion sort are iterative sorting algorithms that can be used to sort elements in an array or ``ArrayList``.
- (AP 4.15.A.2)	**Selection sort** repeatedly selects the smallest (or largest) element from the unsorted portion of the list and swaps it into its correct (and final) position in the sorted portion of the list.
- (AP 4.15.A.3)	**Insertion sort** inserts an element from the unsorted portion of a list into its correct (but not necessarily final) position in the sorted portion of the list by shifting elements of the sorted portion to make room for the new element.
- Informal run-time comparisons of program code segments can be made using statement execution counts.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
