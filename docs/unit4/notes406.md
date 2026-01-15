---
layout: notes
title: "📓4.6: Using Text Files" 
parent: "4️⃣ Data Collections"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.6](https://runestone.academy/ns/books/published/csawesome2/topic-4-6-input-files.html) 

---

## Using Text Files

📁 Files are used to **store data in software** that we use every day. For example, when you play a game on your computer, your game progress is saved in a file. The next time you play that game, your game progress is loaded in from that file, so you can continue where you left off. In this lesson, you will learn how to _read in_ data from a file in Java.

<html>
  <dl>
    <dt>File</dt>
    <dd>Storage for data that <em>persists</em> when the program is not running. The data in a file can be retrieved during program execution.</dd>
  </dl>
</html>

For example in a previous lesson, you created a ``SpellChecker`` class that reads in a dictionary **text file** into an **array** of words, and a ``spellcheck`` method that uses this array to verify if a word is spelled correctly. 

{:.highlight}
👍 **BENEFITS**: Input files, like the dictionary, enable us to handle large amounts of data _efficiently_. Instead of manually typing data into our program every time it runs, we can store the data in a file and read it as needed. Another benefit of using files is the ability to _separate_ the data from the code, allowing for more flexible and **modular software design**. 

### ``File``, ``Scanner``, and ``IOException`` Classes

A file can be connected to the program using the ``File`` and ``Scanner`` classes. These classes must be imported in from libraries; the ``Scanner`` class is in the ``java.util`` package and ``File`` is in the ``java.io`` package.
> `io` stands for **input/output**! 

📂 A file can be **opened** by creating a ``File`` object, using the name of the file or the complete path to the file, as the argument of the constructor, for example ``str`` is the pathname to the file like "data.txt" in ``new File(String str)``.

```java
import java.io.*;
...
File myFile = new File("data.txt");
```

🖨️ After opening a file, the  ``Scanner`` class can be used to _"read in"_ the data from the file, line by line. 
> **NOTE**: The ``Scanner`` class is part of the ``java.util`` package and has a constructor that takes a ``File`` object as an argument to create an input stream from the file.

But what if you misspell the file name or the file does not exist? The ``Scanner`` constructor will throw a ``FileNotFoundException`` if it cannot find the file. This is a type of ``IOException``, which is a general **error** that is also thrown when the input does not match expectations.  
> * We've seen other **exceptions** before, like ``ArrayIndexOutOfBoundsException`` and ``NullPointerException``.
> * Exceptions are a way for Java to handle runtime errors that occur during program execution.
> * When an exception is thrown, the program stops executing and the exception is *thrown* back to the calling method. If the exception is not handled, the program will terminate. 

<div class="imp" markdown="block">
  
When using the ``File`` class, Java requires that you indicate _what to do_ if the file with the provided name _cannot be opened_. Java uses ``try/catch`` blocks to handle exceptions, but you can use the ``throws`` keyword in the method header to indicate that the method may "throw" an **exception**, instead of handling it right away. 

One way to accomplish this is to add ``throws IOException`` to the header of the method that uses the file. If the file name is invalid, the program will terminate. The **throws IOException** statement is added to the end of the method header. 

</div>

Here is an example that sets up an input file in the main method and throws an exception:


```java
import java.io.*;
import java.util.*;

public class FileIO {
// Notice "throws IOException" in the header below
public static void main(String[] args) throws IOException {
    File myFile = new File("data.txt");
    Scanner scan = new Scanner(myFile);
    ...
    scan.close();
  }
}
```

### Reading Data with `Scanner` Methods

🖨️ Once the file is opened, the data can be **read** (loaded in) using ``Scanner`` methods. For example, the method, ``nextLine`` will read the next line of input and returns it as a ``String``. 

Here are the **methods** used in the Scanner file to read all types of input, whether from the keyboard, a file, or other: 

Here is the requested information organized into a Markdown table for better readability.

#### Scanner Class Methods
{:.no_toc}

| Method | Description |
| --- | --- |
| `Scanner(File f)` | The constructor that accepts a `File` object to read data from a file. |
| `String nextLine()` | Returns the next line of text up until the end of the line. Returns `null` if no next line exists. |
| `String next()` | Returns the next `String` up until a whitespace character is encountered. |
| `int nextInt()` | Returns the next `int`. Throws `InputMismatchException` if the next token is not an integer. **Note:** Does not consume the newline character. |
| `double nextDouble()` | Returns the next `double`. Throws `InputMismatchException` if the next token is not a double. |
| `boolean nextBoolean()` | Returns the next `boolean`. Throws `InputMismatchException` if the next token is not a boolean. |
| `boolean hasNext()` | Returns `true` if there is another token to read; `false` otherwise. |
| `void close()` | Closes the input stream and releases associated resources. |

Here's an example of the ``nextInt`` method being used to read from the **keyboard**:

```java
Scanner scan = new Scanner(System.in);
int num1 = scan.nextInt();
int num2 = scan.nextInt();
              
int result = num1 * num2;
              
System.out.println(num1 + " x " + num2 + " = " + result); 
scan.close();
```
> The code above will read in the 2 numbers below it and multiply them. Try changing the input to decimal numbers like 2.5 and run to see the ``InputMismatchException``. Then, change the code to use ``nextDouble()`` instead of ``nextInt()`` and change the variables to type ``double`` to read in decimal numbers.

<div class="warn" markdown="block">

Notice that the ``nextInt()`` and ``nextDouble()`` methods read in a number, but leave any **space** or **newline** characters on the input stream. This can cause problems if you have input to read in multiple lines! 

Using ``nextLine()`` and the other ``Scanner`` methods together on the same input source sometimes requires code to _adjust_ for the methods’ different ways of handling **whitespace**. 
> Java programmers will often add in an extra call to ``scan.nextLine();`` to read in the rest of the line after reading in a number.  

</div>

### Loop to Read in a File

A ``while`` loop is usually used to read in a file with multiple lines. The loop can use the method ``hasNext`` as the loop condition to detect if the file still contains elements to
read. A loop with this condition will terminate when there are no more lines to read in the file. After the loop is finished reading the data, the ``close`` method from Scanner should be called to close the file.

```java
   while (scan.hasNext())
   {
      String line = scan.nextLine();
      ...
   }
   scan.close();
```

### Save File Data into an Array

We can save a file line by line into an array. In the ``SpellChecker`` class, we read the data file of words into a dictionary array with the following code. Note that we had to know the number lines or words in the file to declare an array of the right size. We'll learn about better data structures like the ``ArrayList`` in the next lessons where we do not need to know the size of the data in advance. 

```java
   String[] dictionary = new String[10000];
   int i = 0;
   while(scan.hasNext())
   {
        String line = scan.nextLine();
        dictionary[i] = line;
        i++;
    }
```



---

## ⭐️ Summary

- (AP 4.6.A.1) A **file** is storage for data that persists when the program is not running. The data in a file can be retrieved during program execution.
- (AP 4.6.A.2) A file can be connected to the program using the ``File`` and ``Scanner`` classes.
- (AP 4.6.A.3) A file can be opened by creating a ``File`` object, using the name of the file as the argument of the constructor. ``File(String str)`` is the ``File`` constructor that accepts a ``String`` file name to open for reading, where ``str`` is the pathname for the file.
- (AP 4.6.A.4) When using the ``File`` class, it is required to indicate what to do if the file with the provided name cannot be opened. One way to accomplish this is to add ``throws IOException`` to the header of the method that uses the file. If the file name is invalid, the program will terminate.
- (AP 4.6.A.5) The ``File`` and ``IOException`` classes are part of the ``java.io`` package. An ``import`` statement must be used to make these classes available for use in the program.

- (AP 4.6.A.6) The following ``Scanner`` methods and constructor—including what they do and when they are used—are part of the Java Quick Reference provided during the AP CSA exam:

    - ``Scanner(File f)`` the Scanner constructor that accepts a File for reading.
    - ``int nextInt()`` returns the next int read from the file or input source. If the next ``int`` does not exist, it will result in an ``InputMismatchException``. Note that this method does not read the end of the line, so the next call to ``nextLine()`` will return the rest of the line which will be empty.
    - ``double nextDouble()`` returns the next double read from the file or input source. If the next ``double`` does not exist, it will result in an ``InputMismatchException``.
    - ``boolean nextBoolean()`` returns the next Boolean read from the file or input source. If the next ``boolean`` does not exist, it will result in an ``InputMismatchException``.
    - ``String nextLine()`` returns the next line of text up until the end of the line as a ``String`` read from the file or input source; returns the empty string if called immediately after another ``Scanner`` method like ``nextInt`` that is reading from the file or input source;returns null if there is no next line.
    - ``String next()`` returns the next String up until a white space read from the file or input source. 
    - ``boolean hasNext()`` returns true if there is a next item to read in the file or input source; false otherwise.
    - ``void close()`` closes the input stream.

- (AP 4.6.A.7) Using ``nextLine`` and the other ``Scanner`` methods together on the same input source sometimes requires code to adjust for the methods’ different ways of handling whitespace.


- (AP 4.6.A.8) The following additional ``String`` method—including what it does and when it is used—is part of the Java Quick Reference provided during the AP CSA Exam:

    - ``String[] split(String del)`` returns a ``String`` array where each element is a substring of ``this String``, which has been split around matches of the given expression ``del``.
    - For example, ``String[] data = line.split(",");`` splits a line from a csv file along the commas and saves the substrings into the array ``data``. 

- (AP 4.6.A.9) A ``while`` loop can be used to detect if the file still contains elements to read by using the ``hasNext`` method as the condition of the loop.
- (AP 4.6.A.10) A file should be closed when the program is finished using it. The ``close`` method from ``Scanner`` is called to close the file.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
