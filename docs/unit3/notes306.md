---
layout: notes
title: "📓3.6: Passing & Returning Objects" 
parent: "3️⃣ Class Creation"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.6](https://runestone.academy/ns/books/published/csawesome2/topic-3-6-methods-references.html) 

---

## Passing & Returning References of an Object



---

#### 💻 Coding Challenge: Friends & Birthdays
{:.no_toc}

In this activity, you will create a class `Friend` which keeps track of your friends’ names and birthdays using another class called `Date`. 

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/bwl_apcs_25-26/topic-3-6-methods-references.html"><button type="button" name="button" class="btn">CSAwesome Topic 3.6</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Coding Challenge: Friends and Birthdays** activity in pairs.

---

## ⭐️ Summary

- (AP 3.4.A.3) When a mutable object is a constructor parameter, the instance variable should be initialized with a copy of the referenced object. In this way, the instance variable does not hold a reference to the original object, and methods are prevented from modifying the state of the original object.

- (AP 3.6.A.1) When an argument is an object reference, the parameter is initialized with a copy of that reference; it does not create a new independent copy of the object. If the parameter refers to a mutable object, the method or constructor can use this reference to alter the state of the object. It is good programming practice to not modify mutable objects that are passed as parameters unless required in the specification.
- (AP 3.6.A.2) When the return expression evaluates to an object reference, the reference is returned, not a reference to a new copy of the object.
- (AP 3.6.A.3) Methods cannot access the private data and methods of a parameter that holds a reference to an object unless the parameter is the same type as the method’s enclosing class.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
