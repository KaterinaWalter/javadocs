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
📖 This page is a condensed version of [CSAwesome Topic 4.5](https://runestone.academy/ns/books/published/csawesome2/topic-4-5-array-algorithms.html) 

---

## Array Algorithms (FRQs)

In this lesson, you will study different Free Response Questions and responses that develop algorithms using arrays.


Here are some common **algorithms** that you should be familiar with for the AP CSA exam:

- 🔍 **Searching Algorithms:**
  - Determine the _minimum_ value in an array
  - Determine the _maximum_ value in an array
  - Search for a _specific element_ in the array
- ➕ **Acculumator Patterns:**
  - Compute a _sum_ of array elements
  - Compute an _average_ of array elements
  - Determine the _number of elements_ meeting specific _criteria_
- 🧪 **Testing Properties:**
  - Determine if _at least one element_ has a particular _property_
  - Determine if _all elements_ have a particular _property_
  - Determine the presence (or absence) of _duplicate_ elements
- ↔️ **Manipulating Array Order:**
  - _Shift/Rotate_ elements to the left or right
    > Requires keeping track of the current **INDEX**!
  - _Reverse_ the order of the elements
    > Requires keeping track of the current **INDEX**!

<div class="imp" markdown="block">
  
🔁 There are two common **array traversal loops** that can be used for these algorithms.

1. **Enhanced for** (for-each) loops visit _EVERY ITEM_ in sequential order:
  ```java
  for (int value : array) {
      if (value ....) {
          ...
      }
  }
  ```
2. **Standard for** loops keep track of the current _INDEX_ – offering more flexibility (modify values, traversing in different order, etc):
  ```java
  for (int i=0; i < array.length; i++) {
      if (array[i] ....) {
         ...
      }
  }
  ```


</div>

#### 💻 In-Class Activity: Array Algorithms
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-4-5-array-algorithms.html"><button type="button" name="button" class="btn">CSAwesome Topic 4.5</button></a> 
2. Make sure you **SIGN IN**!
3. Complete all **Coding Exercises** in groups.

</div>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
