---
layout: notes
title: "📓4.3: Array Creation & Access" 
parent: "4️⃣ Data Collections"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.3](https://runestone.academy/ns/books/published/csawesome2/topic-4-3-array-basics.html) 

<div style="text-align: center;">
<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong><br>Create a blank Java program to take your class notes in for the next few lessons.<br><em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>
</div>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit4PartA-Notes`
4. For the **description**, write: `1D Array data collections, using text files`
5. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
6. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
7. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
8. 📝 Take notes in this Codespace during class, writing **code** & **comments** along with the instructor.

</div>

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! **Codespaces** are TEMPORARY editing environments, so you need to COMMIT changes properly in order to update the main **repository** for your program. 

_There are multiple steps to saving in GitHub Codespaces:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

</details>

</html>


---

# Array Creation and Access

To keep track of 10 exam scores, we could declare 10 separate variables:

```java
int score1, score2, score3, … , score10;
````

But what if we had 100 exam scores? That would be a lot of variables! Most programming languages have a simple **data structure** for a collection of related data that makes this easier. In many block-based programming languages like App Inventor and Scratch, this is called a **list**. In Java and many programming languages, this is called an **array**.

An **array** is a block of memory that stores a collection of data items (**elements**) of the same type under one name. Arrays are useful whenever you have many elements of data of the same type that you want to keep track of, but you don't need to name each one. Instead, you use the array name and a number (called an **index**) for the position of an item in the array.

You can make arrays of `int`, `double`, `String`, and even classes that you have written, like `Student`.

Here’s a [video](https://youtu.be/G7aF-OuLfl4) that introduces the concept of an array and gives an example.

<iframe width="700" height="400" src="https://www.youtube.com/embed/G7aF-OuLfl4" frameborder="0" allowfullscreen></iframe>

---

An array is like a row of small lockers, except that you can’t cram lots of stuff into it — you can only store one value in each locker.

![A row of lockers](Figures/rowLockers.jpg)

You can store a value in an array using an **index** (location in the array). An array index is like a locker number — it helps you find a particular place to store or retrieve something.

---

## Index Basics

Arrays and lists in most programming languages start counting elements at **0**. This means:

* The first element is at index `0`.
* The second element is at index `1`.
* The last element is at index `array.length - 1`.

**Example:**

```java
int[] scores = {90, 85, 78, 92};
System.out.println(scores[0]); // prints 90
System.out.println(scores[3]); // prints 92
```

If you try to use an index less than `0` or greater than `array.length - 1`, you will get an **ArrayIndexOutOfBoundsException**.

---

## Activity: Image Array

<div class="task" markdown="block">

Type this in your Codespace, press run, and experiment with the `index` variable:

```java
public class ImageEx {
    public static void main(String[] args) {
        String[] images = {
            "cow.jpg", "kitten.jpg", "puppy.jpg", "pig.jpg", "reindeer.jpg"
        };

        ImageEx obj = new ImageEx();
        int index = 0; // change this to show a different image
        obj.printHTMLimage(images[index]);
    }

    public void printHTMLimage(String filename) {
        String baseURL = "https://raw.githubusercontent.com/bhoffman0/CSAwesome/master/_sources/Unit6-Arrays/6-1-images/";
        System.out.print("<img src=" + baseURL + filename + " width=500px />");
    }
}
```

1. Change `index` to show the puppy image, then the reindeer.
2. Try all images — what indices did you use?
3. Replace `index` with a random number: `(int)(Math.random() * images.length)`.

</div>

---

## Coding Challenge: Countries Array

![US Map](array-images/US.jpg)

<div class="task" markdown="block">

1. Create 4 parallel arrays for:

   * Countries: China, Egypt, France, Germany, India, Japan, Kenya, Mexico, United Kingdom, United States
   * Capitals
   * Languages
   * Image filenames
2. Add more entries for countries you are interested in.
3. Pick a random index using `Math.random()` and array `.length`.
4. Print the country, its capital, its language, and its image using that index.

</div>

---

## Arrays of Objects

You can create arrays of objects just like you create arrays of primitives. You must call the constructor for each object when initializing the array.

**Example:**

```java
ClassName[] array = new ClassName[size];
array[index] = new ClassName();
array[index].method();
```

---

## Activity: Turtle Array

<div class="task" markdown="block">

```java
import java.awt.*;

public class TurtleArray {
    public static void main(String[] args) {
        World world = new World(300, 300);
        Turtle[] turtarray = new Turtle[2];
        turtarray[0] = new Turtle(world);
        turtarray[1] = new Turtle(world);
        turtarray[0].forward();
        turtarray[1].turnLeft();
        turtarray[1].forward();
        world.show(true);
    }
}
```

**Task:**

1. Change the array size to `3`.
2. Add another turtle at index 2.
3. Make the new turtle turn right and move forward.

</div>

---

## Community Challenge: Array of Your Class

<div class="task" markdown="block">

1. Copy your class from [Lesson 3.5](../Unit3-Class-Creation/topic-3-5-methods.html#groupwork-design-a-class-for-your-community).
2. Create an array of 3 objects of your class.
3. Initialize each element using your class constructor.
4. Call the `print` method for each object.

</div>

---

## Summary

* **(AP 4.3.A.1)** Arrays store multiple values of the same type — primitives or object references.
* **(AP 4.3.A.2)** The size is fixed at creation and accessed via `.length`.
* **(AP 4.3.A.3)** When created with `new`, elements are initialized to default values (`0`, `0.0`, `false`, or `null`).
* **(AP 4.3.A.4)** Initializer lists can create and populate arrays in one step.
* **(AP 4.3.A.5)** Square brackets `[]` are used to access or modify elements by index.
* **(AP 4.3.A.6)** Valid indices are `0` to `length - 1`; accessing outside this range throws an error.

---

## AP Practice

**Example Problem:**

```java
public void mystery(int[] a, int i) {
    a[i] = a[i-1] * 2;
}
```

If `array` is `{4, 10, 15}`, `mystery(array, 2)` → `{4, 10, 20}`.

---

## Arrays Game

Try this [array practice game](https://csa-games.netlify.app/).
Click **Arrays** and guess which element will be printed. Turn on Labels if needed.

<iframe height="700px" width="100%" style="margin-left:10%;max-width:80%" src="https://csa-games.netlify.app/"></iframe>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
