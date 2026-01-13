---
layout: notes
title: "📓4.10: ArrayList Algorithms" 
parent: "4️⃣ Data Collections"
nav_order: 10
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.10](https://runestone.academy/ns/books/published/csawesome2/topic-4-10-arraylist-algorithms.html) 

---

## ArrayList Algorithms

Like with arrays, there are standard `ArrayList` *algorithms* that utilize **traversals**.

- 🔍 **Searching Algorithms:**
  - Determine the _minimum_ value in a list
  - Determine the _maximum_ value in a list
  - Search for a _specific element_ in the list
- ➕ **Acculumator Patterns:**
  - Compute a _sum_ of list elements
  - Compute an _average_ of list elements
  - Determine the _number of elements_ meeting specific _criteria_
- 🧪 **Testing Properties:**
  - Determine if _at least one element_ has a particular _property_
  - Determine if _all elements_ have a particular _property_
  - Determine the presence (or absence) of _duplicate_ elements
- ↔️ **Manipulating List Order:**
  - _Shift/Rotate_ elements to the left or right
  - _Reverse_ the order of the elements

<div class="imp" markdown="block">
  
🔁 There are two common **array traversal loops** that can be used for these algorithms.

1. **Enhanced for** (for-each) loops visit _EVERY ITEM_ in sequential order:
  ```java
  for (Type obj : list) {
      if (obj ....) {
          ...
      }
  }
  ```
2. **Standard for** loops keep track of the current _INDEX_ – offering more flexibility (modify values, traversing in different order, etc):
  ```java
  for (int i=0; i < list.size(); i++) {
      if (list.get(i) ....) {
         ...
      }
  }
  ```


</div>

#### 💻 In-Class Activity: ArrayList Algorithms
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-4-10-arraylist-algorithms.html"><button type="button" name="button" class="btn">CSAwesome Topic 4.10</button></a> 
2. Make sure you **SIGN IN**!
3. Complete all **Coding Exercises** in groups. 

</div>



---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
