---
layout: notes
title: "📓4.11: 2D Array Creation & Access" 
parent: "4️⃣ Data Collections"
nav_order: 11
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.11](https://runestone.academy/ns/books/published/csawesome2/topic-4-11-2Darrays.html) 

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
3. Specify the **repository name**: `CS2-Unit4PartC-Notes`
4. For the **description**, write: `2D Array data collections`
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

## Two-Dimensional (2D) Arrays

We have only worked with one-dimensional arrays so far, which have a single row of elements. But in the real world, data is often represented in a **two-dimensional table** with **rows** and **columns**. Programming languages can also represent arrays this way with multiple dimensions. A `two-dimensional (2D) array` has _rows_ and _columns_. 
> A 2D array in Java is actually _an array of arrays_!

Arrays in Java can store many items of the same type.  You can even store items in **two-dimensional** (2D) arrays which are arrays that have both **rows** and **columns**.  A **row** has horizontal elements.  A **column** has vertical elements.  In the picture below there are 3 rows of lockers and 6 columns.

![image](Figures/2DLockers.jpg)

Two dimensional arrays are especially useful when the data is naturally organized in rows and columns like in a spreadsheet, bingo, battleship, theater seats, classroom seats, or a picture.  In battleship, letters map to the rows (A is the first row, B is the second row, and so on) and the column indices start with 1.


### Array Storage

Many programming languages actually store two-dimensional array data in nested one-dimensional arrays. The typical way to do this is to store all the data for the first _row_, with each spot referring to a _column_, followed by all the data for the second row, and so on. This is called **row-major** order.  
> Some languages store all the data for the first column followed by all the data for the second column and so on.  This called **column-major** order.

![image](Figures/rowMajor.png)

Java actually stores a two-dimensional array as an _array of arrays_. Each element of the **outer** array has a _reference_ to each **inner** array. 

{:.highlight}
The **outer** array can be thought of as the *rows* and the **inner** arrays as the *columns*.

![image](Figures/ArrayRowsAndCols.png)

> The picture above shows a 2D array that has 3 *rows* and 7 *columns*. Notice that the array indices start at `0` and end at the `length - 1`.

### Declaring 2D Arrays

To **declare** a 2D array, specify the `type` of elements that will be stored in the array, then double brackets (``[][]``) to show that it is a 2D array of that type, then at least one space, and then a `name` for the array.  

```java
int[][] ticketInfo;
String[][] seatingChart;
```
> Note that the declarations above just name the variable and say what type of array it will reference. *The declarations do not create the array*.  Arrays are **objects** in Java, so any variable that declares an array holds a **reference** to an object. If the array hasn't been created yet and you try to print the value of the variable, it will print `null` (meaning it doesn't reference any object yet).

To **create** an array use the `new` keyword, followed by a space, then the type, and then the number of rows in square brackets followed by the number of columns in square brackets, like this ``new int[numRows][numCols]``.

```java
ticketInfo = new int[2][3];
seatingChart = new String[3][2];
```
> The code above creates a 2D array with 2 rows and 3 columns named ``ticketInfo`` and a 2D array with 3 rows and 2 columns named ``seatingChart``.

{:.highlight}
The **total** number of elements in a 2D array is the _number of rows_ **times** the _number of columns_.

### Set Value(s) in a 2D Array

When arrays are created, their contents are automatically **initialized** to `0` for numeric types, `null` for object references, and `false` for type boolean. 

<div class="imp" markdown="block">
    
To explicitly **set a value** in a 2D array, you can use _assignment statements_ with the `name` of the array followed by the `row` index in square brackets followed by the `column` index in square brackets, and then an ``=`` followed by a value:

```java
// Initialize the 2D array
int[][] data = new int[2][3];
// Set value of the first item
data[0][0] = 15;
```

</div>

### Initializer Lists for 2D Arrays

You can also **initialize (set)** the values for the array when you first create it.  In this case you _don't need to specify the size_ of the array, it will be determined from the values you give.  

<div class="imp" markdown="block">
    
The code below uses an **initializer list** to create a value-filled array called ``ticketInfo`` with 2 rows and 3 columns. It also creates an array called ``seatingInfo`` with 3 rows and 2 columns.

```java
int[][] ticketInfo = { {25,20,25}, {25,20,25} };
String[][] seatingInfo = { {"Jamal", "Maria"}, {"Jake", "Suzy"}, {"Emma", "Luke"} };
```

</div>
> 💬 **DISCUSS:** What is the value at ``seatingInfo[2][1]`` after the code above executes?

### Get a Value from a 2D Array

To **get** the value in a 2D array give the `name` of the array followed by the `row` and `column` indices in square brackets. 

```java
int[][] ticketInfo = { {25,20,25}, {25,20,25} };
String[][] seatingInfo = { {"Jamal", "Maria"}, {"Jake", "Suzy"}, {"Emma", "Luke"} };
int value = ticketInfo[1][0];
String name = seatingInfo[0][1];
```
> The code above will get the `int` value at row index 1 and column index 0 from ``ticketInfo``. It will also get the `String` value at row index 0 and column index 1 from ``seatingChart``.

#### 💻 In-Class Activity: ASCII Art
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-4-11-2Darrays.html"><button type="button" name="button" class="btn">CSAwesome Topic 4.11</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: ASCII Art** activity in pairs.

</div>

---

## ⭐️ Summary

- (AP 4.11.A.1) A **2D array** is stored as an array of arrays. Therefore, the way 2D arrays are created and indexed is similar to 1D array objects. The size of a 2D array is established at the time of creation and cannot be changed. 2D arrays can store either primitive data or object reference data. Nonrectangular 2D array objects (with varying column length for each row) are outside the scope of the AP Computer Science A course and exam.

- 2D arrays are declared and created with the following syntax: ``datatype[][] variableName = new datatype[numberRows][numberCols]``;

- (AP 4.11.A.2)	When a 2D array is created using the keyword ``new``, all of its elements are initialized to the default values for the element data type. The default value for ``int`` is ``0``, for ``double`` is ``0.0``, for ``boolean`` is ``false``, and for a reference type is ``null``.

- (AP 4.11.A.3) The initializer list used to create and initialize a 2D array consists of initializer lists that represent 1D arrays; for example, ``int[][] arr2D = { {1, 2, 3}, {4, 5, 6} };``.

- (AP 4.11.A.4) The square brackets ``[row][col]`` are used to access and modify an element in a 2D array. For the purposes of the AP exam, when accessing the element at ``arr[first][second]``, the ``first`` index is used for rows, the ``second`` index is used for columns.

- **Row-major order** refers to an ordering of 2D array elements where traversal occurs across each row, while **column-major order** traversal occurs down each column.

- (AP 4.11.A.5)	A single array that is a row of a 2D array can be accessed using the 2D array name and a single set of square brackets containing the row index.
- (AP 4.11.A.6) The number of rows contained in a 2D array can be accessed through the ``length`` attribute. The valid row index values for a 2D array are ``0`` through one less than the number of rows or the length of the array, inclusive. The number of columns contained in a 2D array can be accessed through the ``length`` attribute of one of the rows. The valid column index values for a 2D array are ``0`` through one less than the number of columns or the length of any given row of the array, inclusive. For example, given a 2D array named ``values``, the number of rows is ``values.length`` and the number of columns is ``values[0].length```. Using an index value outside of these ranges will result in an ``ArrayIndexOutOfBoundsException``.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
