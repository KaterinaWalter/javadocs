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

{:.highlight}
You can actually put in _any kind of objects_ in an ``ArrayList``, including
instances of classes that you write, such as the ``Student``, ``Person``, or
``Pet`` classes from Unit 3.

---

## ArrayList Methods

The following are the ``ArrayList`` methods that you need to know for the AP CSA exam. These are included on the <a href="https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf" target="_blank">AP CSA Java Quick Reference Sheet</a> that you will receive during the exam so you do not need to memorize them. 
> **NOTE:** The `E` in the method headers below stands for the type of the element in the ArrayList; this type `E` can be any Object type.

-  `int size()` returns the **number of elements** in the list

-  `boolean add(E obj)` **appends** obj to the *end* of the list, and also returns true

-  `void add(int index, E obj)` **inserts** obj at the index, moves any current objects at index or beyond to the _right_ (to a higher index), and also returns the replaced element

-  `E remove(int index)` **removes** the item at the index, shifts remaining items to the _left_ (to a lower index), and also returns the replaced element

-  `E get(int index)` returns the **item** in the list at the index

-  `E set(int index, E obj)` **replaces** the item at index with obj, and also returns the replaced element

### ``size()``

As we saw in the last lesson, you can get the **number of items** in a ``ArrayList`` using its ``size()`` method. The ``ArrayList`` starts out empty with a size of 0.

```java
ArrayList<String> list = new ArrayList<String>();
System.out.println( list.size() );
```

{:.highlight}
With arrays, you use the ``length`` field to get the number of items in the array. But, with an ``ArrayList`` you use the ``size()`` method to get the number of items in the ``ArrayList``. The number of items in an empty ``ArrayList`` is 0.
> **AP EXAM NOTE:** You will not be penalized if you mix up ``length`` and ``size()`` in the CSA exam.

### ``add(obj)``

You can **add** values to an ``ArrayList`` using the method ``add(obj)``, which will add the object to the _end_ of the list, just like you would join the end of the line to board a bus.

<div class="task" markdown="block">

Try the code below to see how the list **changes** as each object is added to the end. 

```java
ArrayList<String> nameList = new ArrayList<String>();
nameList.add("Diego");
System.out.println(nameList);
nameList.add("Grace");
System.out.println(nameList);
System.out.println(nameList.size());
```
> Can you add your name to the list and then print out the list?

</div>

When adding Integers to a list, you can use the `Integer` object constructor like ``add(new Integer(5))``... but you can also just add the primitive `int` value directly, like ``add(5)``, and it will be changed into an ``Integer`` object automatically. 
> 📦 This is called **autoboxing**. When you pull an ``int`` value out of a list of ``Integers``, that is called **unboxing**.

{:.highlight}
You can put any kind of **objects** into an ``ArrayList``. Even instances of a class that you wrote! 

For example, here is an ``ArrayList`` of ``Creature``s:
```java
ArrayList<Creature> zoo = new ArrayList<Creature>();
zoo.add(new Creature("Bella", "Unicorn", 15));
zoo.add(new Creature("Bobby", "Bear", 8));
```

### ``add(index,obj)``

There are actually two different ``add`` methods in the ``ArrayList`` class:
1. The ``add(obj)`` method **adds** the passed object to the _end_ of the list.
2. The ``add(index,obj)`` method **inserts** the passed object at the passed `index`, but first _shifts over_ any existing values to higher indices to make room for the new object.

<div class="task" markdown="block">

💬 **DISCUSS:** What will the code below print out? Try figuring it out before running it.
> Remember that `ArrayList`s start at index 0 and that the `add(index,obj)` always takes the index as the first argument.

```java
ArrayList<Integer> list1 = new ArrayList<Integer>();
list1.add(1);
// adds the number 2 to the end of the list
list1.add(2);
// This will add the number 3 at index 1
list1.add(1, 3);
// This will add the number 4 at index 1
list1.add(1, 4);
System.out.println(list1);
System.out.println(list1.size());
```

</div>

### ``remove(index)``

You can also **remove** values from an ``ArrayList`` using the ``remove(index)`` method. It removes the item located at the specified _index_, which affects the underlying array in two ways: all of the other items after that index shift to a lower index, and the size of the ``ArrayList`` is decreased by 1.
> Note that this method is **NON-VOID**: It also _returns_ the item that was removed... in case you need to see it (but usually you don't).

<div class="task" markdown="block">

💬 **DISCUSS:** What will the code below print out? Try figuring it out before running it.

```java
ArrayList<Integer> list2 = new ArrayList<Integer>();
list2.add(1);
list2.add(2);
list2.add(3);
list2.remove(1);
System.out.println(list2);
```
> The ``remove(int index)`` method doesn't remove the object that matches the integer value given. In the example above it doesn't remove the value `1` – it removes the value `2` at **index** `1`.

</div>

### ``get(index)`` and ``set(index, obj)``

You can **get** the object at an index using ``obj = listName.get(index)`` and **set**
the object at an index using ``listName.set(index,obj)``. Both methods require
that the index argument refer to an existing element of the list, i.e. the index
must be greater than or equal to 0 and less than the ``size()`` of the list.

{:.highlight}
Notice that ``ArrayList``s use ``get`` and ``set`` **methods** instead of the `index` **operator** that we use with arrays: ``array[index]``. This is because ``ArrayList`` is an object **class** with *methods*, not a built in type with special support in the language like arrays are.

<div class="task" markdown="block">
  
💬 **DISCUSS:** What will the code below print out? Try figuring it out before running it.

```java
ArrayList<String> nameList = new ArrayList<String>();
nameList.add("Diego");
nameList.add("Grace");
nameList.add("Deja");
System.out.println(nameList.get(0));
System.out.println(nameList.get(1));
nameList.set(1, "John");
System.out.println(nameList);
```
> Can you get the _last_ element in the `nameList` to print it out? Can you set the _first_ element in the list to your name and print out the list?

</div>

### Comparing Arrays and ArrayLists

When do you use arrays and when do you use ``ArrayList``s? Use an array when
you want to store several items of the same type and you know how many items
will be in the array and the items in the array won't change in order or number.
Use an ``ArrayList`` when you want to store several items of the same type and
you don't know how many items you will need in the list or when you want to
remove items from the list or add items to the list while the program is
running.

Here is a comparison of how to create Arrays and ``ArrayList``s:

```java
// Arrays must specify a size!
int[] highScores = new int[5];
String[] names = new String[5];

// ArrayLists are empty to start with
ArrayList<Integer> highScoreList = new ArrayList<Integer>();
ArrayList<String> nameList = new ArrayList<String>();
```

Here is a comparison of how to access and change elements in arrays and
``ArrayList``\ s. Note that ``ArrayList``\ s have a method ``size()`` instead of a
``length`` property, and ``ArrayList``\ s use ``get``/``set`` methods instead of
the index operator (``[]``).

| **Operation** | **array** | **ArrayList** |
| Number of Items | `array.length` | `list.size()` |
| Access | `value = array[index];` | `value = list.get(index);` |
| Modify | `array[index] = value;` | `list.set(index,value)` |

Note that the ``ArrayList`` methods ``add`` and ``remove`` do not have a simple
equivalent in arrays, because they change the total number of elements in the list and
may also shift the positions of other elements.

#### 💻 In-Class Activity
{:.no_toc}

<div class="task" markdown="block">

💬 **DISCUSS:** Why might an `ArrayList` be a more appropriate _data structure_ than an `array` for a **To Do list**?

For each of the following tasks, rewrite the given code to use an `ArrayList` instead of an `array`.

1. Create and populate the data structure:
  ```java
  String[] toDoList = new String[3];
  toDoList[0] = "Do homework";
  toDoList[1] = "Help make dinner";
  toDoList[2] = "Call grandma";
  ```
2. Replace an element at a specified index:
  ```java
  toDoList[1] = "Order pizza";
  ```
3. Check the number of items:
  ```java
  System.out.println(toDoList.length + " things to do!");
  ```
5. Access a value at a specified index:
  ```java
  System.out.println("Here's the first thing to do: " + toDoList[0]);
  ```
4. Remove the first item and shift everything down:
  ```java
  toDoList[0] = toDoList[1];
  toDoList[1] = toDoList[2];
  toDoList[2] = "";
  ```
  > **HINT:** this can all be done in _one method call_ with ArrayList!

</div>


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
