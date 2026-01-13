---
layout: notes
title: "📓4.8: ArrayList Class" 
parent: "4️⃣ Data Collections"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.8](https://runestone.academy/ns/books/published/csawesome2/topic-4-8-arraylists.html) 

---

## ArrayLists

In the last unit, we learned about using arrays to hold **collections** of related data. However arrays are not very _flexible_. Most notably, the size of an array is established at the time of creation and cannot be changed. What if you **don't know how big** the collection of data will be? What if you want to both **add** and **remove** items from a collection? 
> For example, if you wanted to represent a shopping list, you might _add to the list_ throughout the week and _remove things from the list_ while you are shopping. You probably would not know how many items will be on the list at the beginning of the week.

![image](Figures/lists.jpg)

{:.highlight}
You can use ``ArrayList`` instead of arrays whenever you don't know the size of the array you need or you know that you will add and remove items and may need to change the array’s size _dynamically_ during run time. An ``ArrayList`` is **mutable**, meaning it can change during run time by adding and removing objects from it.

<html>
<dl>
  <dt>ArrayList</dt>
  <dd>A re-sizable collection. It is called <code>ArrayList</code> because it stores the items that have been added to it in an underlying <strong>array</strong>. But it also takes care of keeping track of how many items have been added to the array and it will create a new bigger array under the covers when needed to hold more items.
  </dd>
</dl>
</html>

<html>
<dl>
  <dt>Mutable</dt>
  <dd>Can <strong>change</strong> during run time by adding and removing objects from it.
  </dd>
</dl>
</html>

### Packages and Imports

The ``ArrayList`` _class_ is in the ``java.util`` _package_. A **package** is a set or library of related classes. The classes we have used until now, such as ``String`` and ``Math``, are in the special package ``java.lang`` whose classes are always available in any Java program. Other packages, such as ``java.util``, provide classes that can only be used either by **importing** them or (much more rarely) by referring to them by their full name which includes the package as a prefix. 

<div class="imp" markdown="block">

Import statements have to come _before_ the `class` definition in a Java source file and serve to tell Java which class you mean when you use a short name like ``ArrayList``. To import just one class we use a single ``import`` of the fully-qualified name of the class like this:

```java
import java.util.ArrayList;
```
> **AP EXAM NOTE:** Don't worry about adding `import` statements on the exam. Any that you need will be provided for you.

</div>

After such an import statement, anywhere ``ArrayList`` is used as a **class name** in the file it will be taken to mean ``java.util.ArrayList``.

### Declaring and Creating ArrayLists

{:.important}
To declare a ArrayList use ``ArrayList<Type> name`` where *Type*, called a **type parameter** is the type of objects you want to store in the ArrayList.

For example a variable naming an ``ArrayList`` meant to hold ``String``s is declared as ``ArrayList<String>`` as shown in the code below. 
> You can declare a variable to just be of type ``ArrayList``, with no type parameter, and it’ll be approximately the same as if you had declared ``ArrayList<Object>``, but it is good practice to specify the type of objects you intend to store in an ``ArrayList`` as it allows the compiler to find errors that would otherwise be missed until run time.

```java
// ArrayList<Type> name = new ArrayList<Type>();
// An ArrayList of Strings:
ArrayList<String> shoppingList = new ArrayList<String>();
```
> As with other reference types, **declaring** a ``ArrayList`` variable doesn't actually _create_ a ``ArrayList`` object in memory. It only creates a variable that can refer to a ``ArrayList`` or ``null``. To actually create a ``ArrayList`` we must invoke a **constructor** such as ``new ArrayList<String>()``.

You can get the **number of items** in a ``ArrayList`` using the ``size()`` method. Notice that a newly constructed ``ArrayList`` is empty and thus has a size of 0. 

{:.highlight}
``ArrayList``s can only hold **reference types** (objects) like ``String``. Since they can’t hold primitive types like ``int`` and ``double``, if we want a collection of numbers we need to use the wrapper classes ``Integer`` or ``Double``. 

### Using `Integer` & `Double` wrapper classes

You can also create ArrayLists of integer and double values. However, you have
to use ``Integer`` or ``Double`` as the type parameter because ``ArrayList``\ s
can only hold objects, not primitive values. All primitive types must be
**wrapped** in objects before they are added to an ArrayList. For example,
``int`` values can be wrapped in ``Integer`` objects, ``double`` values can be
wrapped in ``Double`` objects. However this normally happens automatically
thanks to autoboxing.

```java
ArrayList<Integer> numList = new ArrayList<Integer>();
ArrayList<Double> decimalList = new ArrayList<Double>();
```

You can actually put in _any kind of objects_ in an ``ArrayList``, including
instances of classes that you write, such as the ``Student``, ``Person``, or
``Creature`` classes from Unit 5.

### `Array` vs. `ArrayList` 

| Operation   | Array Syntax            | ArrayList Syntax           |
| ----------- | ----------------------- | -------------------------- |
| length/size | `array.length`          | `list.size()`              |
| Access      | `value = array[index];` | `value = list.get(index);` |
| Modify      | `array[index] = value;` | `list.set(index, value);`  |


---

## ⭐️ Summary

- **ArrayLists** are re-sizable lists that allow adding and removing items to
  change their size during run time.

- (AP 4.8.A.4) The ``ArrayList`` class is part of the ``java.util`` package. An ``import`` statement can be used to make this class available for use in the program.(import ``java.util.ArrayList`` or ``java.util.*``).

- (AP 4.8.A.1) An ``ArrayList`` object is **mutable** in size and contains object references. (Mutable means that it can change by adding and removing items from it.

- (AP 4.8.A.2) The ``ArrayList`` constructor ``ArrayList()`` constructs an empty list (of size 0).

- (AP 4.8.A.3) Java allows the generic type ``ArrayList<E>``, where the generic type ``E`` specifies the type of the elements. (Without it, the type will be ``Object``). When ``ArrayList<E>`` is specified, the types of the reference parameters and
  return type when using its methods are type ``E``.

- (AP 4.8.A.3) ``ArrayList<E>`` is preferred over ``ArrayList`` (which creates an list of type ``Object``). For example, ``ArrayList<String> names = new ArrayList<String>();`` allows the compiler to find errors that would otherwise be found at run time.

- ``ArrayList``\ s cannot hold primitive types like ``int`` or ``double``, so
  you must use the wrapper classes ``Integer`` or ``Double`` to put numerical
  values into an ``ArrayList``. However autoboxing usually takes care of that
  for you.

- (AP 4.8.A.6) The indices for an ``ArrayList`` start at ``0`` and end at the number of elements ``- 1``.

- (AP 4.8.A.5) The following ArrayList methods, including what they do and when they are used, are part of the Java Quick Reference:

  - **int size()** : Returns the number of elements in the list
  - **boolean add(E obj)** : Appends obj to end of list; returns true
  - **void add(int index, E obj)** : Inserts obj at position index (0 <= index <= size), moving elements at position index and higher to the right (adds 1 to their indices) and adds 1 to size
  - **remove(int index)** — Removes element from position index, moving elements at position index + 1 and higher to the left (subtracts 1 from their indices) and subtracts 1 from size; returns the element formerly at position index
  - **E get(int index)** : Returns the element at position index in the list
  - **E set(int index, E obj)** : Replaces the element at position index with obj; returns the element formerly at position index




---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
