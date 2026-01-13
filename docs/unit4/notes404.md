---
layout: notes
title: "📓4.4: Array Traversals" 
parent: "4️⃣ Data Collections"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.4](https://runestone.academy/ns/books/published/csawesome2/topic-4-4-array-traversal.html) 

---

## Traversing Arrays with For Loops

### Index Variables

In the last lesson, we mentioned that you can use a variable for the index of an array. You can even do math with that index and have an arithmetic expression inside the [], like below.

```java
  // highScores array declaration
  int[] highScores = { 10, 9, 8, 8};
  // use a variable for the index
  int index = 3;
  // modify array value at index
  highScores[index] = 11;
  // print array value at index
  System.out.println(  highScores[index] );
  System.out.println(  highScores[index - 1] );
```
> 💬 **DISCUSS:** What does the code above print out? You can follow the code in this <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayWithIndexVar%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20//%20highScores%20array%20declaration%0A%20%20%20%20%20%20int%5B%5D%20highScores%20%3D%20%7B%2010,%209,%208,%208%7D%3B%0A%20%20%20%20%20%20//%20use%20a%20variable%20for%20the%20index%0A%20%20%20%20%20%20int%20index%20%3D%203%3B%0A%20%20%20%20%20%20//%20modify%20array%20value%20at%20index%0A%20%20%20%20%20%20highScores%5Bindex%5D%20%3D%2011%3B%0A%20%20%20%20%20%20//%20print%20array%20value%20at%20index%0A%20%20%20%20%20%20System.out.println%28%20%20highScores%5Bindex%5D%20%29%3B%0A%20%20%20%20%20%20System.out.println%28%20%20highScores%5Bindex%20-%201%5D%20%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline"> Java Visualizer</a> and look at the image depicting the array below.

![image](Figures/arraywithindex.png)

<div class="task" markdown="block">

What do you think the following code will print out? First trace through it on paper keeping track of the array and the index variable. Then, run it to see if you were right. You can also follow it in the <a href="http://www.pythontutor.com/visualize.html#code=%20public%20class%20Test1%0A%20%20%20%7B%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20String%5B%20%5D%20names%20%3D%20%7B%22Jamal%22,%20%22Emily%22,%20%22Destiny%22,%20%22Mateo%22,%20%22Sofia%22%7D%3B%20%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20int%20index%20%3D%201%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex%20-%201%5D%29%3B%0A%20%20%20%20%20%20%20%20index%2B%2B%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex%5D%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex/2%5D%29%3B%0A%20%20%20%20%20%20%20%20names%5Bindex%5D%20%3D%20%22Rafi%22%3B%0A%20%20%20%20%20%20%20%20index--%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex%2B1%5D%29%3B%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline">Java Visualizer</a>.

```java
String[] names = {"Jamal", "Emily", "Destiny", "Mateo", "Sofia"};

int index = 1;
System.out.println(names[index - 1]);
index++;
System.out.println(names[index]);
System.out.println(names[index / 2]);
names[index] = "Rafi";
index--;
System.out.println(names[index + 1]);
```

</div>

### For Loop to Traverse Arrays

We can use iteration with a standard **for loop** to "visit" each element of an array.  This is called **traversing** the array. Just start the index at **0** and loop while the index is less than the **length** of the array. 

{:.highlight}
Note that the variable **i** (short for _index_) is often used in loops as the **loop counter variable** and is used here to access each element of an array with its index (position).

![image](Figures/arrayForLoop.png)

For example, here is a loop traversing the ``highScores`` array to print every score. Follow the code below in the <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayLoop%0A%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%0A%20%20%20%20%7B%0A%0A%20%20%20%20%20%20%20%20int%5B%5D%20highScores%20%3D%20%7B%2010,%209,%208,%208%7D%3B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20highScores.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%20%20highScores%5Bi%5D%20%29%3B%0A%20%20%20%20%20%20%20%20%7D%20%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline">Java Visualizer</a>.

```java
  int[] highScores = { 10, 9, 8, 11};
  for (int i = 0; i < highScores.length; i++) {
      System.out.println(  highScores[i] );
  }
```

{:.highlight} 
Using a variable as the index is a powerful **data abstraction** feature because it allows us to use loops with arrays where the loop counter variable is the index of the array! This allows our code to generalize to work for the whole array.

<div class="task" markdown="block">

What do you think the following code will print out? First trace through it on paper keeping track of the array and the index variable. Then, run it to see if you were right. 

```java
String[] names = {"Jamal", "Emily", "Destiny", "Mateo", "Sofia"};

for (int i = 0; i < names.length; i++) {
  System.out.println(names[i]);
}
```

> Try adding your name and a friend's name to the array names and run the code again. Did the code work without changing the loop?

</div>

### Modifying Values in an Array

The following code demonstrates a loop that changes the values in an array. In this code, the array is passed as an **argument** to the static methods in the class. You can try the code in the <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayLoop%0A%20%20%20%7B%0A%0A%20%20%20%20%20//%20What%20does%20this%20method%20do%3F%0A%20%20%20%20%20%20public%20static%20void%20multAll%28int%5B%5D%20values,%20int%20amt%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20values.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20values%5Bi%5D%20%3D%20values%5Bi%5D%20*%20amt%3B%0A%20%20%20%20%20%20%20%20%7D%20%0A%20%20%20%20%20%20%7D%20%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20//%20What%20does%20this%20method%20do%3F%0A%20%20%20%20%20%20public%20static%20void%20printValues%28int%5B%5D%20values%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20values.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%20%20values%5Bi%5D%20%29%3B%0A%20%20%20%20%20%20%20%20%7D%20%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%5D%20numArray%20%3D%20%20%7B2,%206,%207,%2012,%205%7D%3B%0A%20%20%20%20%20%20%20%20multAll%28numArray,%202%29%3B%0A%20%20%20%20%20%20%20%20printValues%28numArray%29%3B%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline">Java Visualizer</a>.

```java
public static void multAll(int[] values, int amt) {
  for (int i = 0; i < values.length; i++) {
    values[i] = values[i] * amt;
  }
}

public static void printValues(int[] values) {
  for (int i = 0; i < values.length; i++) {
    System.out.println(values[i]);
  }
}

public static void main(String[] args) {
  int[] numArray = {2, 6, 7, 12, 5};
  multAll(numArray, 2);
  printValues(numArray);
}
```
> 💬 **DISCUSS:** What do these methods do? Trace through it, keeping track of the array values and the output.

{:highlight} 
Arrays in Java are **objects**, so the array variables are references to an address in memory. When an array is passed as an argument to a method, the **name** of the array refers to its **address** in memory. Therefore, any changes to the array in the method _will affect the original array_. 
> Since arrays can be very large, we do not want to copy them entirely when we pass them into methods.

### Looping Backwards

⬅️ You don't have to loop through an array from the front to the back, you can loop by starting at the **final index** of the array and move toward the front during each time through the loop. 

In the example below, the method ``getIndexOfLastSmallerItem`` returns the index of the last element in the array that is smaller than the given argument (the "target"). 

```java
public static int getIndexOfLastSmallerItem(int[] values, int target) {

  for (int index = values.length - 1; index >= 0; index--) {
    if (values[index] < target) {
      return index;
    }
  }
  return -1;
}
```

> The **return** statement inside the loop **stops** the execution of the loop and the method and returns the index that is found immediately back to the main method. It returns `-1` if there is no number in the array that is smaller than the given number.

<div class="task" markdown="block">

Can you add another method that finds the index of the last element **greater** than the target, instead of smaller, and have your `main` method print out a test of it? 
  
Call this method `getIndexOfLastGreaterItem` and give it 2 **arguments** and a **return** value like the method above.

</div>

### Common Errors When Looping Through an Array
{:.no_toc}

**Off by one** errors, where you go off the array by 1 element, are easy to make when traversing an array which result in an `ArrayIndexOutOfBoundsException` being thrown.

When attempting to process ("visit") all array elements, be careful to **start** at the first index which is ``0`` and **end** at the last index.
* Usually loops are written so that the index starts at 0, and continues while the index is less than ``arrayName.length`` since (``arrayName.length - 1``) is the index for the last element in the array.
  * Make sure you do not use ``<=`` instead of ``<``! If the index is less than 0 or greater than (``arrayName.length - 1``), an `ArrayIndexOutOfBoundsException` will be  thrown. 

---

## Traversing Arrays with For-Each Loops

There is a special kind of loop that can be used with arrays that is called an **enhanced for loop** or a **for-each loop**. This loop is much easier to write because it _does not involve an index variable_ or the use of the `[]`. It just sets up a variable that is set to each **value** in the array successively. This type of loop can only be used with arrays and some other collections of items like ArrayLists which we will see in the next unit.

To set up a for-each loop, use `for (type variable : arrayname)` where the type is the type for elements in the array, and read it as "_for each variable value in arrayname_". 

{:.highlight}
Use the enhanced for-each loop with arrays whenever you can, because it _cuts down on errors_! You can use it whenever you need to **loop through all the elements** of an array, don't need to know their **index**, and don't need to **change** their values. It automatically starts by "visiting" the first item in the array (the one at index `0`) and continues through, _in order_, to the last item in the array. 

See the examples below in Java that loop through both an `int` and a `String` array:

```java
  int[] highScores = { 10, 9, 8, 8};
  String[] names = {"Jamal", "Emily", "Destiny", "Mateo"};

  // for each loop: for each value in highScores
  // for (type variable : arrayname)
  for (int value : highScores) {
      // Notice no index or [ ], just the variable value!
      System.out.println( value );
  }
  // for each loop with a String array to print each name
  // the type for variable name is String!
  for (String name : names) {
      System.out.println( name );
  }
```
> Add another high score and another name to the arrays and run again!

### For-Each Loop Limitations

What if we had a loop that _incremented_ all the elements in the array. Would that work with an enhanced for-each loop? Unfortunately not! 

Because only the **temporary variable** in the loop changes, _not the real array values_. We would need an **indexed** loop to modify array elements. Try this code in the [Java Visualizer](http://www.pythontutor.com/visualize.html#code=%20%20%20public%20class%20IncrementLoop%0A%20%20%20%7B%20%20%20%20%20%20%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%20%5D%20values%20%3D%20%7B6,%202,%201,%207,%2012,%205%7D%3B%0A%20%20%20%20%20%20%20%20//%20Can%20this%20loop%20increment%20the%20values%3F%0A%20%20%20%20%20%20%20%20for%20%28int%20val%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20val%2B%2B%3B%0A%20%20%20%20%20%20%20%20%20%20System.out.println%28%22New%20val%3A%20%22%20%2B%20val%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20//%20Print%20out%20array%20to%20see%20if%20they%20really%20changed%0A%20%20%20%20%20%20%20%20for%20%28int%20v%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20System.out.print%28v%20%2B%20%22%20%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0) and step through the code to see why it doesn't work.

<div class="warn" markdown="block">

**Enhanced for-each** loops CANNOT be used in all situations! Only use for-each loops when you want to loop through *all* the values in an array, _without changing_ their values.
  
- 🚫 Do not use for-each loops if you need to keep track of the **index**.
- 🚫 Do not use for-each loops if  you need to **change values** in the array.
- 🚫 Do not use for-each loops if you want to loop through only part of an array or in a different order.

</div>

---

#### 💻 In-Class Activity: SpellChecker
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-4-4-array-traversal.html"><button type="button" name="button" class="btn">CSAwesome Topic 4.4</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: SpellChecker** activity in pairs.

</div>

#### 🎲 Practice Game: Loops with Arrays
{:.no_toc}

Try the game below to practice! Click on **Arrays** and click on the element of the `*` array that would be printed out by the given code. If you're stuck, check on Labels to see the indices. We encourage you to work in pairs and see how high a score you can get.

<html>
        <iframe height="700px" width="100%" style="margin-left:10%;max-width:80%" src="https://csa-games.netlify.app/"></iframe>
    <script>      window.scrollTo(0, 0);</script>
</html>

---

## ⭐️ Summary

- (AP 4.4.A.1) **Traversing an array** is when repetition statements are used to access all or an ordered sequence of elements in an array.
- (AP 4.4.A.2) Traversing an array with an indexed ``for`` loop or ``while`` loop requires elements to be accessed using their indices.
- In ``for`` and ``while`` loops, make sure the index for an array starts at 0 and end at the number of elements − 1.  **Off by one** errors are easy to make when traversing an array, resulting in an **ArrayIndexOutOfBoundsException** being thrown.

- An **enhanced for loop**, also called a **for each loop**, can be used to loop through an array without using an index variable.

- To set up a for-each loop, use **for (type variable : arrayname)** where the type is the type for elements in the array, and read it as "for each variable value in arrayname".

- (AP 4.4.A.3) An enhanced ``for`` loop header includes a variable, referred to as the enhanced ``for`` loop variable. For each iteration of the enhanced ``for`` loop, the enhanced ``for`` loop variable is assigned a copy of an element without using its index.

- (AP 4.4.A.4) Assigning a new value to the enhanced ``for`` loop variable does not change the value stored in the array. (So, you can't change an array using the enhanced for loop.)
- (AP 4.4.A.5) When an array stores object references, the attributes can be modified by calling methods on the enhanced ``for`` loop variable. This does not change the object references stored in the array. (So, you can change the attributes of an object in an array using the enhanced for loop.)
- (AP 4.4.A.6) Code written using an enhanced ``for`` loop to traverse elements in an array can be rewritten using an indexed ``for`` loop or a ``while`` loop.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
