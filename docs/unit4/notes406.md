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

For example in a previous lesson, you created a ``SpellChecker`` class that reads in a dictionary file into an array of words, and a ``spellcheck`` method that uses this array to verify if a word is spelled correctly. 

#### Benefits of using input files:
{:no_toc}

* Input files, like the dictionary, enable us to handle large amounts of data _efficiently_. Instead of manually typing data into our program every time it runs, we can store the data in a file and read it as needed.
* Another benefit of using files is the ability to _separate_ the data from the code, allowing for more flexible and **modular software design**. 

### Java ``File``, ``Scanner``, and ``IOException`` Classes

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

   public class FileIO 
   {
      // Notice "throws IOException" in the headerbelow
      public static void main(String[] args) throws IOException
      {
         File myFile = new File("data.txt");
         Scanner scan = new Scanner(myFile);
         ...

         scan.close();
      }
   }
```

### Reading in Data with Scanner

🖨️ Once the file is opened, the data can be **read** using ``Scanner`` methods. For example, the method, ``nextLine`` will read the next line of input and returns it as a ``String``. 

Here are the **methods** used in the Scanner file to read all types of input, whether from the keyboard, a file, or other: 

- ``Scanner(File f)`` the Scanner constructor that accepts a File for reading.
- ``String nextLine()`` returns the next line of text up until the end of the line as a String read from the file or input source; returns null if there is no next line.
- ``String next()`` returns the next String up until a white space is read from the file or input source. 
- ``int nextInt()`` returns the next int read from the file or input source. If the next ``int`` does not exist, it will result in an ``InputMismatchException``. Note that this method does not read the end of the line, so the next call to ``nextLine()`` will return the rest of the line which will be empty.
- ``double nextDouble()`` returns the next double read from the file or input source. If the next ``double`` does not exist, it will result in an ``InputMismatchException``.
- ``boolean nextBoolean()`` returns the next Boolean read from the file or input source. If the next ``boolean`` does not exist, it will result in an ``InputMismatchException``.
- ``boolean hasNext()`` returns true if there is a next item to read in the file or input source; false otherwise.
- ``void close()`` closes the input stream.

Here's an example of the ``nextInt`` method being used to read from the keyboard:

```java
Scanner scan = new Scanner(System.in);
int num1 = scan.nextInt();
int num2 = scan.nextInt();
              
int result = num1 * num2;
              
System.out.println(num1 + " x " + num2 + " = " + result); 
scan.close();
```
> The code above will read in the 2 numbers below it and multiply them. Try changing the input below the code to decimal numbers like 2.5 and run to see the ``InputMismatchException``. Then, change the code to use ``nextDouble()`` instead of ``nextInt()`` and change the variables to type ``double`` to read in decimal numbers.

<div class="warn" markdown="block">

Notice that the ``nextInt()`` and ``nextDouble()`` methods read in a number, but leave any **space** or **newline** characters on the input stream. This can cause problems if you have input to read in multiple lines! 

Using ``nextLine()`` and the other ``Scanner`` methods together on the same input source sometimes requires code to _adjust_ for the methods’ different ways of handling **whitespace**. Java programmers will often add in an extra call to ``scan.nextLine();`` to read in the rest of the line after reading in a number.  

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

### Pokemon Activity

The following exercise reads in a data file about Pokemon and prints out the first 10 lines in the file. This file has the extension `.csv` which stands for **Comma Separated Values**. All spreadsheets can be saved as CSV text files, and spreadsheet software can easily open CSV files as spreadsheets.

<div class="task" markdown="block">

1. Add the `pokemon.csv` file (that I emailed to you) to your repository.
2. Complete the code in the main method below to read in the first 10 lines of the pokemon file using the Scanner class, save each line into the pokemonLines array, and print it out. Make sure you check that the line counter i is less than 10 in the condition of the loop. 

```java
       public static void main(String[] args) throws IOException
       {
           File myFile = new File("pokemon.csv");
           Scanner scan = new Scanner(myFile);
           String[] pokemonLines = new String[10];

           int i = 0;
           // 1. Add in the loop condition that checks if scan has another line of input
           //    and that i is less than 10.
           while (         )
           {
               // 2. Read in the next line of the file

               // 3. Assign the line to the ith element of the pokemonLines array

               // 4. Print out the line

               i++; // line count
            }
            scan.close();           
      }
```
</div>

#### Split Strings

If you take a look at the Pokemon CSV file, you'll notice that each line contains multiple data attributes separated by commas. These attributes include each Pokemon's name, type, speed, etc. on each row. Typically, the first line of a CSV file serves as the header, indicating the names of these attributes. 

```
   // The first line of the Pokemon CSV file
   Number, Pokemon, Type 1, Type 2, HP, Attack, Defense, Speed, PNG, Description
```

The Java ``String`` class provides a useful method called ``split(String delimeter)`` that allows us to split a string into an array of substrings based on a specified **delimiter** which is a character like a comma or a space that separates the units of data. This method returns a ``String`` array where each element in the array represents a field of data from the line.  

```java
    String sentence = "A quick brown fox jumps";
    // Split the sentence into words along spaces to create:
    //  words = {"A", "quick", "brown", "fox", "jumps"}
    String[] words = sentence.split(" ");
```

Here is an example of how to use the split method to split a line of data with commas separating the fields from the Pokemon csv file into identifiable chunks of data. The first line of headers in the file indicates that the 0th element of the data array is the Pokemon's number, element 1 is the name, etc. We only need to save the data that we want to use. In this case, we want to save the name, type1, speed, and imageFile. If we want to do math or comparisons with the speed, we can convert it to an int using the ``Integer.parseInt`` method that will be described in the next lesson.

```java
   // Split the line of data into an array of Strings
   String[] data = line.split(",");
   // Identify the data 
   // data: Number,Name,Type1,Type2,HP,Attack,Defense,Speed,PNG,Description 
   String name = data[1];
   String type1 = data[2];
   ...
   String speed = data[7];
   String imageFile = data[8];
```

Try the exercise below to display Pokemon images using the ``split`` method to extract names and urls saved in the file.

**PokeImages:** This program reads in some of the data from the pokemon file into a String array of lines. Complete the ``randomPokemon`` method to print out a random pokemon name and its image using the split method. Run the program multiple times to see different Pokemon names and images.

```
    import java.io.*;
    import java.util.*;

    public class PokeImages
    {
        private String filename = "pokemon.csv";
        private String[] pokemonLines = new String[152];

        /* This method reads in filename into the pokemonLines array */
        public int readFile() throws IOException
        {
            File myFile = new File(filename);
            Scanner scan = new Scanner(myFile);
            int i = 0;
            while (scan.hasNext())
            {
                pokemonLines[i] = scan.nextLine();
                i++; 
            }
            System.out.println("Read in " + i + " lines.");
            scan.close();
            return i;
        }

        /* Write a function randomPokemon that prints out a random Pokemon name and image */
        public void randomPokemon(int length)
        {
            // 1. pick a random number from 1 to length 
            //    (the 0th row is the headers)
      

            // 2. get the line at that random index from the array pokemonLines

            // 3. Use the split method to split the line into a String array data

            // 4. Print out the name using the correct index in the split data
            //   (Check above for the correct index for the name)

            // 5. Call the printHTMLimage method below
            //    with an element of the data array to print out the image.
            //    (Check above for the correct index for the image url)

        }

        public static void main(String[] args) throws IOException
        {
            PokeImages obj = new PokeImages();
            // call readFile() to read file into the array pokemonLines
            int length = obj.readFile();
            obj.randomPokemon(length);
        }

        // This method will just work on Runestone to print out images
        public static void printHTMLimage(String url)
        {
            System.out.print("<img src=" + url + " width=300px />");
        }
    }
```

#### Object-Oriented Design with CSV Files

To better organize and work with this data, we can create a ``Pokemon`` class that corresponds to these attributes using object-oriented design. A CSV data file can be saved into an array of ``Pokemon`` objects by splitting each line (except the header) into the attributes for one ``Pokemon`` object.

We can use the ``split`` method to extract the individual pieces of data from each line of the CSV file and save this data into a ``Pokemon`` object. We must first create a ``Pokemon`` class with instance variables that correspond to the data attributes, and a constructor that initializes these variables. Assuming that we have already written the ``Pokemon`` class and constructor, the following code creates a Pokemon object from the data using its constructor and saves it into an array of ``Pokemon`` objects.

```java

    // Create an array of Pokemon objects
    Pokemon[] pokemonArray = new Pokemon[152];

    int i = 0;
    while (scan.hasNext())
    {
        String line = scan.nextLine();
        // Split each line into its attributes name, type1, etc.
        String[] data = line.split(",");
        String name = data[1];
        String type1 = data[2];
        ...
        String speed = data[7];
        String imageFile = data[8];
           
        // Create a Pokemon object from the split data 
        Pokemon p = new Pokemon(name, type1, speed, imageFile);
        // Save p in the array 
        pokemonArray[i] = p;        
        
        i++;
    }
```

Note that sometimes you may need to skip the 0th row in the file if it is column headers. For this file, it will just get split into strings, but if your data file contains numbers that need to be processed, you could skip one like: ``if (i == 0) scan.nextLine();``.

Let's try the code to read into an array of Pokemon objects in the challenge exercise below.

#### Array of Pokemon from Input File

Let's end with a challenge that combines all the skills you have learned so far. You could work in pairs for this challenge. Create a class Pokemon that has at least 3 attributes that can be found in the Pokemon file, including its name, type1, and imagefile, and any other attributes from the file that you would like. Write a constructor and getters for these attributes. Then, read in the data from the pokemon file, split each line, and save the data in an array of Pokemon objects. Write a ``findType`` method that returns to the type of a Pokemon given its name as an argument. It should loop through the array to find the right Pokemon object using the ``getName`` and ``getType`` methods that you will write. It should also display the image for the Pokemon.

Design the class Pokemon that has at least 3 attributes that can be found in the Pokemon file, including its name, type1, and imagefile, and any other attributes from the file that you would like. Write a constructor and getters for these attributes. Then, read in the data from the pokemon file, split each line, and save the data in an array of Pokemon objects. Write a ``findType`` method that loops through the array to find the Pokemon with the given name as argument and print out and return its type and its image. 

```java
   import java.io.*;
   import java.util.*;

   class Pokemon
   {
       // 1. Add at least 3 String attributes of a Pokemon 
       //   including name, type1, and imagefile

       // 2. Add a constructor that initializes the attributes of a Pokemon
       //  to the values given as arguments

       // 3. Add getters for the attributes

   }

   public class PokemonArray
   {
       // An array of 152 Pokemon objects
       private Pokemon[] pokemonArray = new Pokemon[152];
       private String filename = "pokemon.csv";

       public PokemonArray() throws IOException
       {
            readFile(); // read in the data file into pokemonArray
       }

       // 4. Write a method to read in the data file (it may throw an exception).
       // Loop through each row to split it into attributes.
       //     Create a new Pokemon object from the attributes.
       //     and save it into the pokemonArray
       public void readFile() 
       {

       }

       // 5. Write a findType method that prints out the type of a Pokemon 
       // given its name as an argument.
       // It should loop through the array to find the Pokemon object with the correct name.
       // It should print and return the type and print the image. 
       // This method can call printHTMLimage(url) defined below.
       public String findType(String name)
       {
           // Loop through the array to find the Pokemon with the given name
           // Call the getType method to get the type of the Pokemon
           // Call the printHTMLimage method to print out the image
           // return the type
        
        
           return "Type";
       }
  
       // This method will just work on Runestone to print out images
       public static void printHTMLimage(String url)
       {
           System.out.print("<img src=" + url + " width=300px />");
       }

       public static void main(String[] args) throws IOException
       {
           PokemonArray obj = new PokemonArray();
           // Call your method to find the type of a Pokemon and display its image
           System.out.println("Pikachu's type is " + obj.findType("Pikachu"));

       }
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
