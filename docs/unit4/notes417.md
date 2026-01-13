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
📖 This page is a condensed version of [CSAwesome Topic 4.17](https://runestone.academy/ns/books/published/csawesome2/topic-4-17-recursive-search-sort.html) 

---

## Recursive Searching & Sorting Algorithms

In this lesson, we will take a look at a **recursive binary search** algorithm and a **recursive merge-sort** algorithm.

### Recursive Binary Search

We've learned about two search algorithms, **Linear Search** and **Binary Search**. Linear search searches for an element in an array or `ArrayList` by checking each element in order. 
> Binary search is more efficient (faster) because it starts at the **middle** of a sorted array or `ArrayList` and **eliminates half** of the array or `ArrayList` each pass through the algorithm.

Binary search only works on **sorted** data! It can be written with _iteration_ (using a loop) like below, or _recursively_.

```java
public static int binarySearch(int[] elements, int target) {
  int left = 0;
  int right = elements.length - 1;
  while (left <= right) {
    int middle = (left + right) / 2;
    if (target < elements[middle]) {
      right = middle - 1;
    }
    else if (target > elements[middle]) {
      left = middle + 1;
    }
    else {
      return middle;
    }
  }
  return -1;
}
```
> Watch the iterative binary search code running in the [Java Visualizer](http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=++public+class+SearchTest%0A++%7B%0A+++++%0A+++++/**+%0A++++++*+Find+the+index+of+a+value+in+an+array+of+integers+sorted+in+ascending+order.%0A++++++*+%40param+elements+an+array+containing+the+items+to+be+searched.+Precondition%3A+items+in+elements+are+sorted+in+ascending+order.%0A++++++*+%40param+target+the+item+to+be+found+in+elements.%0A++++++*+%40return+an+index+of+target+in+elements+if+target+found%3B%0A++++++*+-1+other+wise.%0A++++++*/%0A+++++public+static+int+binarySearch(int%5B%5D+elements,+int+target)+%7B%0A++++++++int+left+%3D+0%3B%0A++++++++int+right+%3D+elements.length+-+1%3B%0A++++++++while+(left+%3C%3D+right)+%0A++++++++%7B%0A+++++++++++int+middle+%3D+(left+%2B+right)+/+2%3B+%0A+++++++++++if+(target+%3C+elements%5Bmiddle%5D)%0A+++++++++++%7B%0A++++++++++++++right+%3D+middle+-+1%3B%0A+++++++++++%7D%0A+++++++++++else+if+(target+%3E+elements%5Bmiddle%5D)+%0A+++++++++++%7B%0A++++++++++++++left+%3D+middle+%2B+1%3B+%0A+++++++++++%7D%0A+++++++++++else+%7B%0A++++++++++++++return+middle%3B+%0A+++++++++++%7D%0A+++++++++%7D%0A+++++++++return+-1%3B%0A++++++%7D%0A++++++%0A++++++public+static+void+main(String%5B%5D+args)%0A++++++%7B%0A+++++++++int%5B%5D+arr1+%3D+%7B-20,+3,+15,+81,+432%7D%3B%0A++++++++%0A+++++++++//+test+when+the+target+is+in+the+array%0A+++++++++int+index+%3D+binarySearch(arr1,-20)%3B%0A+++++++++System.out.println(index)%3B%0A++++++++%0A+++++++++//+test+when+the+target+is+not+in+the+array%0A+++++++++index+%3D+binarySearch(arr1,53)%3B%0A+++++++++System.out.println(index)%3B%0A+++++++%7D%0A++%7D%0A&mode=display&curInstr=0).

{:.highlight}
Note that you can write solutions to many problems using either **recursion** or **iteration**. Iteration is usually preferred and more efficient, but recursive solutions can be elegant and require less code.

Let's write a **recursive version** of Binary Search with the method signature `boolean binarySearch(int[] array, int startIndex, int endIndex, int target)`.
> 💬 **DISCUSS:**
> * What recursive _method call_ would search the array from index 0 to the middle index?
> * What's the **base case** for a recursive version of Binary Search (when we want the recursion to stop)? Remember that in binary search, we always _check the middle element first_ when looking for a target element from a `startIndex` to an `endIndex`.

Here is the Java code for a recursive binary search:

```java
public static int recursiveBinarySearch(int[] array, int start, int end, int target) {
  int middle = (start + end) / 2;

  // base case: check middle element
  if (target == array[middle]) {
    return middle;
  }
  // base case: check if we've run out of elements
  if (end < start) {
    return -1; // not found
  }
  // recursive call: search start to middle
  if (target < array[middle]) {
    return recursiveBinarySearch(array, start, middle - 1, target);
  }
  // recursive call: search middle to end
  if (target > array[middle]) {
    return recursiveBinarySearch(array, middle + 1, end, target);
  }
  return -1;
}
```
> Try the recursive binary search code in this [Java visualizer link](https://cscircles.cemc.uwaterloo.ca/java_visualize/#code=++public+class+RecursiveBinarySearch%0A++%7B%0A+++++public+static+int+recursiveBinarySearch(int%5B%5D+array,+int+target,+int+start,+int+end)%0A+++++%7B%0A+++++++int+middle+%3D+(start+%2B+end)/2%3B%0A%09+++%0A+++++++if+(target+%3D%3D+array%5Bmiddle%5D)+%7B%0A%09%09%09return+middle%3B%0A%09+++%7D%09%0A%09+++if(end+%3C+start)%7B%0A%09%09%09+return+-1%3B+//+not+found%0A%09++++%7D+%0A%09%09%0A%09++++if+(target+%3C+array%5Bmiddle%5D)%7B%0A%09%09%09return+recursiveBinarySearch(array,+target,+start,+middle+-+1)%3B%0A%09%09%7D%0A%09%09%0A%09%09if+(target+%3E+array%5Bmiddle%5D)%7B%0A%09%09%09return+recursiveBinarySearch(array,+target,+middle+%2B+1,+end)%3B%0A%09%09%7D%0A%0A%09%09return+-1%3B%0A+++%7D%0A%0A+++public+static+void+main(String%5B%5D+args)%0A+++%7B%0A++++++int%5B%5D+array+%3D+%7B+3,+7,+12,+19,+22,+25,+29,+30+%7D%3B%0A++++++int+foundIndex+%3D+recursiveBinarySearch(array,25,0,array.length)%3B%0A++++++System.out.println(%2225+was+found+at+index+%22+%2B+foundIndex)%3B%0A+++%7D%0A++%7D&mode=display&curInstr=28).


### Recursive Merge Sort

In [Unit 7](https://coderina.dev/javadocs/docs/unit07/notes706.html), we looked at two sorting algorithms, **Selection Sort** and **Insertion Sort**. In this lesson, we will look at a third sorting algorithm, **Merge Sort**, which uses _recursion_. 
> Merge Sort is actually more efficient (faster) than Selection Sort and Insertion Sort because it _divides the problem in half_ each time like binary search. This is called a **divide and conquer** algorithm.

Here is a short video that describes how merge sort works:

<iframe width="560" height="315" src="https://www.youtube.com/embed/4VqmGXwpLqc?si=SqwsIIKCX_yfDhps" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Here's a video that shows merge sort with cards:

<iframe width="560" height="315" src="https://www.youtube.com/embed/AMJjtTo1LLE?si=jax7DRz91MSkmq69" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

A merge sort **recursively splits** the values to be sorted in half until _there is only one value to be sorted_, and then it **merges** the two sorted lists into one sorted list.  
> The code shown below uses a second array the same size as the original array for merging the values in order. Then it copies all of the sorted values back into the original array.

<div class="imp" markdown="block">
  
🔍 To identify a **merge sort algorithm** look for the following:

* 3 methods: `mergeSort`, `mergeSortHelper`, and `merge`
* `mergeSortHelper` is **recursive**

</div>

```java
public class MergeSort {

  public static void mergeSort(int[] elements) {
    int n = elements.length;
    int[] temp = new int[n];
    mergeSortHelper(elements, 0, n - 1, temp);
  }

  private static void mergeSortHelper(int[] elements, int from, int to, int[] temp) {
    if (from < to)  {
      int middle = (from + to) / 2;
      mergeSortHelper(elements, from, middle, temp);
      mergeSortHelper(elements, middle + 1, to, temp);
      merge(elements, from, middle, to, temp);
    }
  }

  private static void merge(int[] elements, int from, int mid, int to, int[] temp) {
    int i = from;
    int j = mid + 1;
    int k = from;

    while (i <= mid && j <= to) {
      if (elements[i] < elements[j]) {
        temp[k] = elements[i];
        i++;
      }
      else {
        temp[k] = elements[j];
        j++;
      }
      k++;
    }

    while (i <= mid) {
      temp[k] = elements[i];
      i++;
      k++;
    }

    while (j <= to) {
      temp[k] = elements[j];
      j++;
      k++;
    }

    for (k = from; k <= to; k++) {
      elements[k] = temp[k];
    }
  }
}
```  

> You can see this executing using the [Java visualizer for merge sort](http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=++import+java.util.Arrays%3B%0A++%0A++public+class+SortTest%0A++%7B%0A+++++public+static+void+mergeSort(int%5B%5D+elements)+%0A+++++%7B%0A++++++++int+n+%3D+elements.length%3B%0A++++++++int%5B%5D+temp+%3D+new+int%5Bn%5D%3B+%0A++++++++mergeSortHelper(elements,+0,+n+-+1,+temp)%3B%0A+++++%7D%0A+++++%0A+++++private+static+void+mergeSortHelper(int%5B%5D+elements,+int+from,+int+to,+int%5B%5D+temp)%0A+++++%7B%0A+++++++++if+(from+%3C+to)%0A+++++++++%7B%0A++++++++++++int+middle+%3D+(from+%2B+to)+/+2%3B+%0A++++++++++++mergeSortHelper(elements,+from,+middle,+temp)%3B+%0A++++++++++++mergeSortHelper(elements,+middle+%2B+1,+to,+temp)%3B+%0A++++++++++++merge(elements,+from,+middle,+to,+temp)%3B%0A+++++++++%7D%0A+++++%7D%0A+++++%0A+++++private+static+void+merge(int%5B%5D+elements,+int+from,+int+mid,+int+to,+int%5B%5D+temp)%0A+++++%7B%0A++++++++int+i+%3D+from%3B+%0A++++++++int+j+%3D+mid+%2B+1%3B+%0A++++++++int+k+%3D+from%3B%0A++++++++%0A++++++++while+(i+%3C%3D+mid+%26%26+j+%3C%3D+to)+%0A++++++++%7B%0A+++++++++++if+(elements%5Bi%5D+%3C+elements%5Bj%5D)+%0A+++++++++++%7B%0A++++++++++++++temp%5Bk%5D+%3D+elements%5Bi%5D%3B%0A++++++++++++++i%2B%2B%3B+%0A+++++++++++%7D%0A+++++++++++else+%0A+++++++++++%7B%0A++++++++++++++temp%5Bk%5D+%3D+elements%5Bj%5D%3B%0A++++++++++++++j%2B%2B%3B+%0A+++++++++++%7D%0A+++++++++++k%2B%2B%3B+%0A++++++++%7D%0A%0A++++++++while+(i+%3C%3D+mid)+%0A++++++++%7B%0A+++++++++++temp%5Bk%5D+%3D+elements%5Bi%5D%3B+%0A+++++++++++i%2B%2B%3B%0A+++++++++++k%2B%2B%3B%0A++++++++%7D%0A++++++++%0A++++++++while+(j+%3C%3D+to)+%0A++++++++%7B%0A+++++++++++temp%5Bk%5D+%3D+elements%5Bj%5D%3B+%0A+++++++++++j%2B%2B%3B%0A+++++++++++k%2B%2B%3B%0A++++++++%7D%0A++++++++%0A++++++++for+(k+%3D+from%3B+k+%3C%3D+to%3B+k%2B%2B)+%0A++++++++%7B%0A+++++++++++elements%5Bk%5D+%3D+temp%5Bk%5D%3B+%0A++++++++%7D%0A+++++%7D%0A++++++++%0A++++++%0A+++++public+static+void+main(String%5B%5D+args)%0A+++++%7B%0A++++++++int%5B%5D+arr1+%3D+%7B86,+3,+43%7D%3B%0A++++++++System.out.println(Arrays.toString(arr1))%3B%0A++++++++mergeSort(arr1)%3B%0A++++++++System.out.println(Arrays.toString(arr1))%3B%0A+++++%7D%0A++%7D&mode=display&curInstr=0).

✍️ You can trace through a merge sort algorithm given an array by using parentheses or curly braces to show how the **array is divided into subarray**s and then **merged**. 

For example, here is how you could write down the trace of ``mergeSort(arr1)`` where `arr1 = {86, 3, 43, 5}`:

```
1. Split 1: { {86, 3} , {43, 5} }
2. Split 2: { { {86},{3}} , { {43},{5}} }
3. Merge 1: { {3, 86} , {5,43} }
4. Merge 2: { 3, 5, 43, 86 }
```

---

## ⭐️ Summary

- (AP 4.17.A.1)	Recursion can be used to traverse ``String`` objects, arrays, and ``ArrayList`` objects.
	
- (AP 4.17.B.1)	Data must be in sorted order to use the binary search algorithm. **Binary search** starts at the middle of a sorted array or ``ArrayList`` and eliminates half of the array or ``ArrayList`` in each recursive call until the desired value is found or all elements have been eliminated.
- (AP 4.17.B.2) Binary search is typically more efficient than linear search.
- (AP 4.17.B.3) The binary search algorithm can be written either iteratively or recursively.

- (AP 4.17.C.1) **Merge sort** is a recursive sorting algorithm that can be used to sort elements in an array or ``ArrayList``.

- (AP 4.17.C.2)	Merge sort repeatedly divides an array into smaller subarrays until each subarray is one element and then recursively merges the sorted subarrays back together in sorted order to form the final sorted array.
  
---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
