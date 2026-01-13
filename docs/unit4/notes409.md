---
layout: notes
title: "📓4.9: ArrayList Traversals" 
parent: "4️⃣ Data Collections"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.9](https://runestone.academy/ns/books/published/csawesome2/topic-4-9-arraylist-traversal.html) 

---

## Traversing ArrayLists with Loops

🔁 ``ArrayList``s can be **traversed** with ``while`` loops and both standard and enhanced ``for`` loops much the same way we use those constructs to loop over an array.

### Enhanced For-Each Loop

You can use a enhanced ``for`` loop to traverse _all of the items_ in an ``ArrayList``, just like you do with an array when you only care about the **values** in the list and **not their indices**. 

An example is shown below:

```java
ArrayList<Integer> myList = new ArrayList<Integer>();
myList.add(50);
myList.add(30);
myList.add(20);
int total = 0;
for (Integer value : myList) {
  total += value;
}
System.out.println("Sum of all elements: " + total);
```
> 💬 **DISCUSS:** What does the following code do? Guess before you run it. Then, add another enhanced for each loop that _computes the product_ of all the elements in myList by multiplying them. Print out the product after the new loop.

Note however that you CANNOT use the enhanced ``for`` loop if you want to **add** or **remove** elements while traversing an ``ArrayList``. If an ``ArrayList`` is modified, such as by calling the ``add`` or ``remove`` methods, while it is being looped over, it will cause the loop to throw a ``ConcurrentModificationException``. If you need to modify an ``ArrayList`` while looping over it, you’ll need to use a regular ``while`` or ``for`` loop.

<div class="warn" markdown="block">

**Enhanced for-each** loops are often convenient but CANNOT be used in all situations! Only use for-each loops when you want to loop through *all* the values in an `ArrayList`, in _sequential_ order, _without making changes_.
  
- 🚫 Do not use for-each loops if you need to **modify values** in the list.
- 🚫 Do not use for-each loops if you need to keep track of the current **index**.
- 🚫 Do not use for-each loops for non-sequential traversals (like iterating through only part of a list, or in a different order).

</div>

### Standard For Loop

You can also use a ``while`` loop or a regular ``for`` loop to process list elements accessed using an index. ``ArrayList`` indices starts at 0 just like array indices, but instead of using the **index operator** ``[]`` to access elements, you use the ``get(index)`` **method** to get the value at the index and ``set(index,value)`` **method** to set the element at an index to a new value.

{:.warning}
🚨 If you try to use an index that is **outside of the range** of `0` to the number of `elements − 1` in an ArrayList, your code will throw an ``IndexOutOfBoundsException``, similar to the ``ArrayIndexOutOfBoundsException`` thrown with Arrays.

```java
for (int i = 0; i <= myList.size(); i++) {
  total = total + myList.get(i);
}
System.out.println(total);
```
> 💬 **DISCUSS:** The code above will throw an ``IndexOutOfBoundsException``. Can you fix it?

### While Loop

The example below demonstrates a ``while`` loop that removes a name from a list:

```java
ArrayList<String> nameList = new ArrayList<String>();
nameList.add("Amun");
nameList.add("Lily");
nameList.add("Donnie");
nameList.add("Lily");

boolean found =   // true or false?
int index = 0;
while (index < nameList.size()) {
  if ("Lily".equals(nameList.get(index))) {
    nameList.remove(index);
    found =    // true or false?
  }
  else {
    index++;
  }
}
```

> Be careful when you **remove** items from a list while you **loop** through it! Notice how
the method above only increments the `index` _if an item was not removed_ from the
list. This is because removing an item from a list will shift the remaining
items to the _left_ (lower index), so if you increment the index in all cases you will skip the
elements immediately after each element you remove.

#### 💻 In-Class Activity: FRQ Word Pairs
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-4-9-arraylist-traversal.html"><button type="button" name="button" class="btn">CSAwesome Topic 4.9</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: FRQ Word Pairs** in groups.

</div>

---

## ⭐️ Summary

- (AP 4.9.A.1) Traversing an ``ArrayList`` is when iteration or recursive statements are used to access all or an ordered sequence of the elements in an ``ArrayList``.
- ``ArrayList``\ s can be traversed with an enhanced ``for`` loop, a ``while``
  loop, or a regular ``for`` loop using an index.
- (AP 4.9.A.2) Deleting elements during a traversal of an ``ArrayList`` requires the use of special techniques to avoid skipping elements (since ``remove`` moves all the
  elements above the removed index down.)
- (AP 4.9.A.3) Attempting to access an index value outside of its range will result in an ``IndexOutOfBoundsException``. (The indices for an ``ArrayList`` start at 0 and end at the number of elements − 1).
- (AP 4.9.A.4) Changing the size of an ``ArrayList`` while traversing it using an enhanced ``for`` loop can result in a ``ConcurrentModificationException``. Therefore, when using an enhanced ``for`` loop to traverse an ``ArrayList``, you should not add or remove elements.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
