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

# Using Text Files

Files are used to store data in software that we use every day. For example, when you play a game on your computer, your game progress is saved in a file. The next time you play that game, your game progress is loaded in from that file so you can continue where you left off. In this lesson, you will learn how to read in data from a file in Java.

A **file** is storage for data that *persists* when the program is not running. The data in a file can be retrieved during program execution. For example, in a previous lesson, you created a `SpellChecker` class that reads in a dictionary file into an array of words, and a `spellcheck` method that uses this array to verify if a word is spelled correctly. Input files like the dictionary enable us to handle large amounts of data efficiently. Instead of manually entering data into our program every time it runs, we can store the data in a file and read it as needed. Another benefit of using files is the ability to separate the data from the code, allowing for more modular and flexible software design.

---

## Java `File`, `Scanner`, and `IOException` Classes

A file can be connected to the program using the `File` and `Scanner` classes. These classes must be imported from libraries:

- The `Scanner` class is in the `java.util` package.
- The `File` class is in the `java.io` package (`io` stands for **input/output**).

A file can be opened by creating a `File` object, using the name of the file or the complete path to the file as the argument of the constructor. For example:

```java
import java.io.*;

File myFile = new File("data.txt");
````

After opening a file, you can connect it to a `Scanner` object to read data from it.

```java
import java.io.*;
import java.util.*;

File myFile = new File("data.txt");
Scanner inputFile = new Scanner(myFile);
```

Because reading from a file might cause an **input/output exception** (`IOException`), you either need to handle it with a `try-catch` block or add `throws IOException` to the method header.

---

## Example: Reading Words from a File

<div class="task" markdown="block">

**Steps:**

1. Create a text file `data.txt` with a list of words, one per line.
2. Use `File` and `Scanner` to read them.
3. Print each word as it’s read.

```java
import java.io.*;
import java.util.*;

public class ReadFileExample
{
    public static void main(String[] args) throws IOException
    {
        File file = new File("data.txt");
        Scanner input = new Scanner(file);

        while (input.hasNext()) {
            String word = input.next();
            System.out.println(word);
        }

        input.close();
    }
}
```

</div>

---

## Example: Reading Numbers from a File

You can read numbers using `nextInt()`, `nextDouble()`, etc.

```java
File file = new File("numbers.txt");
Scanner input = new Scanner(file);

while (input.hasNextInt()) {
    int num = input.nextInt();
    System.out.println(num);
}

input.close();
```

---

## Splitting Data from a CSV File

A CSV (Comma-Separated Values) file stores data in rows and columns, with commas separating each value. The `String.split(",")` method can be used to break a line into an array of Strings.

```java
// Split the line of data into an array of Strings
String[] data = line.split(",");

// Example indices for a Pokemon CSV:
// data: Number,Name,Type1,Type2,HP,Attack,Defense,Speed,Image,Description
String name = data[1];
String type1 = data[2];
String speed = data[7];
String imageFile = data[8];
```

---

## Coding Exercise: Display Pokemon Images

<div class="task" markdown="block">

**Goal:** Read from `pokemon.csv` into an array of Strings, and print a random Pokemon's name and image.

```java
import java.io.*;
import java.util.*;

public class PokeImages
{
    private String filename = "pokemon.csv";
    private String[] pokemonLines = new String[152];

    public int readFile() throws IOException
    {
        File myFile = new File(filename);
        Scanner scan = new Scanner(myFile);
        int i = 0;
        while (scan.hasNext()) {
            pokemonLines[i] = scan.nextLine();
            i++;
        }
        System.out.println("Read in " + i + " lines.");
        scan.close();
        return i;
    }

    public void randomPokemon(int length)
    {
        // TODO: Implement steps:
        // 1. Pick a random index (skip index 0, which is the header).
        // 2. Get the line at that index.
        // 3. Split it into data[].
        // 4. Print the name.
        // 5. Call printHTMLimage() with the image URL.
    }

    public static void printHTMLimage(String url)
    {
        System.out.print("<img src=" + url + " width=300px />");
    }

    public static void main(String[] args) throws IOException
    {
        PokeImages obj = new PokeImages();
        int length = obj.readFile();
        obj.randomPokemon(length);
    }
}
```

</div>

---

## Object-Oriented Design with CSV Files

Instead of working directly with arrays of Strings, we can create a `Pokemon` class with attributes and store each Pokemon as an object.

```java
Pokemon[] pokemonArray = new Pokemon[152];
int i = 0;
while (scan.hasNext()) {
    String[] data = scan.nextLine().split(",");
    String name = data[1];
    String type1 = data[2];
    String speed = data[7];
    String imageFile = data[8];

    Pokemon p = new Pokemon(name, type1, speed, imageFile);
    pokemonArray[i] = p;
    i++;
}
```

---

## Groupwork Challenge: Array of Pokemon from Input File

<div class="task" markdown="block">

**Your Task:**

1. Create a `Pokemon` class with at least 3 attributes from the CSV (`name`, `type1`, `imagefile`).
2. Write a constructor and getters.
3. Read `pokemon.csv` into an array of `Pokemon` objects.
4. Write `findType(name)` to return and print the type, plus display the image.

```java
import java.io.*;
import java.util.*;

class Pokemon
{
    // TODO: attributes, constructor, getters
}

public class PokemonArray
{
    private Pokemon[] pokemonArray = new Pokemon[152];
    private String filename = "pokemon.csv";

    public PokemonArray() throws IOException
    {
        readFile();
    }

    public void readFile()
    {
        // TODO: read file, split each row, create Pokemon objects
    }

    public String findType(String name)
    {
        // TODO: loop through array, find name, print type and image
        return "Type";
    }

    public static void printHTMLimage(String url)
    {
        System.out.print("<img src=" + url + " width=300px />");
    }

    public static void main(String[] args) throws IOException
    {
        PokemonArray obj = new PokemonArray();
        System.out.println("Pikachu's type is " + obj.findType("Pikachu"));
    }
}
```

</div>

---

## Optional Challenge: Your Own Dataset

<div class="task" markdown="block">

1. Choose a CSV dataset (provided or your own).
2. Create a class with at least 3 attributes from the file.
3. Read the file into an array of your objects.
4. Perform an operation (e.g., find max/min, filter by attribute).

```java
import java.io.*;
import java.util.*;

class OneItem
{
    // TODO: attributes, constructor, getters, toString
}

public class Data
{
    // TODO: array of OneItem, readFile(), analysis method

    public static void main(String[] args) throws IOException
    {
        Data obj = new Data();
        // obj.readFile();
        // obj.doSomething();
    }
}
```

</div>

---

## Summary

* **Files** store data that persists when the program isn’t running.
* Use `File` and `Scanner` to read from files.
* `throws IOException` may be required when working with files.
* `String.split(delimiter)` is useful for parsing CSV data.
* Use loops with `hasNext()` to process all lines in a file.
* Object-oriented design lets you store file data as structured objects.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
