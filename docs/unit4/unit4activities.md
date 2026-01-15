---
layout: notes
title: "🎯 Unit 4 Activities" 
parent: "4️⃣ Data Collections"
nav_order: 18
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

<html>
  <details>
    <summary>💻 <strong class="text-green-200">ACTIVITY PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit4-Activity#`
    > Replace `#` with the specific _activity number_.
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!

</div>

  </details>
</html>

---

## 🔴 ACTIVITY #1: Pokemon Dataset

In this activity, you'll practice using **arrays** and working with **text files** with a dataset about [Pokemon](https://bulbapedia.bulbagarden.net/wiki/Main_Page).

### PART A: Create Array from the Data File

The following exercise reads in a data file about Pokemon and prints out the first 10 lines in the file. This file has the extension `.csv` which stands for **Comma Separated Values**. All spreadsheets can be saved as CSV text files, and spreadsheet software can easily open CSV files as spreadsheets.

<div class="task" markdown="block">

1. Add the `pokemon.csv` file (that I emailed to you) to your repository.
2. Complete the code in the main method below to read in the first 10 lines of the pokemon file using the Scanner class, save each line into the pokemonLines array, and print it out. Make sure you check that the line counter i is less than 10 in the condition of the loop. 

```java
public static void main(String[] args) throws IOException {
...
}
```

```java
File myFile = new File("pokemon.csv");
Scanner scan = new Scanner(myFile);
String[] pokemonLines = new String[10];
```

```java
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


#### Loop to Read in a File

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

#### Save File Data into an Array

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

### PART B: Display Names & Images

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

### PART C: Organize Data with Object-Oriented Design

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

Let's try the code to read into an array of Pokemon objects in the challenge exercise below. Create a class Pokemon that has at least 3 attributes that can be found in the Pokemon file, including its name, type1, and imagefile, and any other attributes from the file that you would like. Write a constructor and getters for these attributes. Then, read in the data from the pokemon file, split each line, and save the data in an array of Pokemon objects. Write a ``findType`` method that returns to the type of a Pokemon given its name as an argument. It should loop through the array to find the right Pokemon object using the ``getName`` and ``getType`` methods that you will write. It should also display the image for the Pokemon.

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


