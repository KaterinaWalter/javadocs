---
layout: notes
title: "📓4.5: Array Algorithms" 
parent: "4️⃣ Data Collections"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.5]() 

---

# Implementing Array Algorithms

In this lesson, you will study common algorithms using arrays and loops and practice FRQ (Free Response Question) problems.

**Common algorithms you should know for the AP CSA exam (AP 4.5.A.1):**
- Compute a sum or average of array elements
- Determine the minimum or maximum value in an array
- Search for a particular element in the array
- Determine if at least one element has a particular property
- Determine if all elements have a particular property
- Determine the number of elements having a particular property
- Access all consecutive pairs of elements
- Determine the presence or absence of duplicate elements
- Shift or rotate elements left or right
- Reverse the order of the elements

---

## Accumulator Pattern for Sum/Average

The **accumulator pattern** iterates through a set of values using a loop and updates an accumulator variable with those values.

**Steps:**
1. Initialize the accumulator variable before the loop.
2. Loop through the values.
3. Update the accumulator variable inside the loop.
4. Print or use the accumulated value after the loop.

---

**Example – Sum of an Array:**

```java
int[] nums = {5, 10, 15, 20};
int sum = 0;

for (int i = 0; i < nums.length; i++) {
    sum += nums[i];
}

System.out.println("Sum: " + sum);
````

---

**Example – Average of an Array:**

```java
int sum = 0;
for (int value : nums) {
    sum += value;
}
double average = (double) sum / nums.length;
System.out.println("Average: " + average);
```

---

<div class="task" markdown="block">

**Practice:**

1. Write a program that computes the sum of an array of doubles.
2. Modify it to compute the average.
3. Test with different arrays.

</div>

---

## Determining All Odd Values

We can write a method that returns `true` if all the values in an array are odd. First, create a helper function `isEven` that returns `true` or `false` for one value, using `%`.

<div class="task" markdown="block">

Type this into your Codespace, press **Run**, and test:

```java
public class Test1
{
    public static boolean isEven(int value)
    {
        // TODO: return true if value is even, false otherwise
        return true;
    }

    public static boolean allOdd(int[] array)
    {
        // TODO: loop through array and return false if any value is even

        // if all odd, return true
        return true;
    }
    
    public static void main(String[] args)
    {
        int[] a1 = {1, 3, 6};
        int[] a2 = {1, 3, 5};
        System.out.println(allOdd(a1)); // expected: false
        System.out.println(allOdd(a2)); // expected: true
    }
}
```

</div>

---

## Pairs and Duplicates in an Array

**Check for duplicates next to each other:**

```java
for (int i = 0; i < values.length - 1; i++) {
    if (values[i] == values[i + 1]) {
        return true;
    }
}
return false;
```

**Check for duplicates anywhere in the array:**

```java
for (int i = 0; i < values.length; i++) {
    for (int j = i + 1; j < values.length; j++) {
        if (values[i] == values[j]) {
            return true;
        }
    }
}
return false;
```

---

<div class="task" markdown="block">

**Practice – Adjacent Sum Pairs:**
Write a method `sumPairs10(nums)` that returns `true` if there are at least two items in the array `nums` that are **adjacent** and add up to 10. Otherwise, return `false`.

```java
public class Pairs
{
    public static boolean sumPairs10(int[] nums)
    {
        // TODO: check if two adjacent numbers add up to 10
        return false;
    }

    public static void main(String[] args)
    {
        int[] nums1 = {1, 2, 8};
        System.out.println(sumPairs10(nums1)); // expected: true

        int[] nums2 = {2, 1, 2};
        System.out.println(sumPairs10(nums2)); // expected: false
    }
}
```

</div>

---

<div class="task" markdown="block">

**Practice – No Duplicates:**
Write a method `noDups(nums)` that returns `true` if there are **no repeated elements** in the array `nums`. It should return `false` if a duplicate is found (use nested loops).

```java
public class Pairs
{
    public static boolean noDups(int[] nums)
    {
        // TODO: check for duplicates using nested loops
        return true;
    }

    public static void main(String[] args)
    {
        int[] nums1 = {1, 2, 8};
        System.out.println(noDups(nums1)); // expected: true

        int[] nums2 = {3, 3, 3};
        System.out.println(noDups(nums2)); // expected: false
    }
}
```

</div>

---

## Rotating Array Elements

**Right rotation example:**

* `{6, 2, 5, 3}` → `{3, 6, 2, 5}`

We can use a temporary array to store the rotated elements, or do it in place.

---

<div class="task" markdown="block">

**Practice – Rotate Left:**
This code rotates array elements to the left in place. Try it and then modify it to rotate **right** instead (hint: use a backward loop).

```java
public class Rotate
{
    public static void main(String[] args)
    {
        int[] values = {6, 2, 1, 7, 12, 5};
        int first = values[0];
        for (int i = 0; i < values.length; i++)
        {
            if (i < values.length - 1) {
                values[i] = values[i + 1];
            }
            else {
                values[i] = first;
            }
        }
        for (int val : values) {
            System.out.print(val + " ");
        }
    }
}
```

</div>

---

## Reversing an Array

Reversing swaps elements from the ends inward using a temporary variable.

```java
// swap array[i] and array[j]
int temp = array[i];
array[i] = array[j];
array[j] = temp;
```

---

<div class="task" markdown="block">

**Practice – Reverse an Array:**
Write a method `reverse` that reverses an array of Strings **in place**.

```java
import java.util.Arrays;

public class ReverseTest
{
    public static void reverse(String[] array)
    {
        // TODO: reverse array using temp variable
    }

    public static void main(String[] args)
    {
        String[] a1 = {"p","a","w","s"};
        reverse(a1);
        System.out.println(Arrays.toString(a1)); // expected: [s, w, a, p]
    }
}
```

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
