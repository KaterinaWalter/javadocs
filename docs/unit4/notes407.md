---
layout: notes
title: "📓4.7: Wrapper Classes (Integer & Double)" 
parent: "4️⃣ Data Collections"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.7]() 

---

# Wrapper Classes - Integer and Double

A **wrapper class** is a class that wraps (encloses) around a primitive data type and gives it an object appearance. The wrapper classes are part of the `java.lang` package, which is imported by default into all Java programs. The `Integer` class and `Double` class are **wrapper classes** that create objects from primitive types of `int` and `double` respectively.

You might need to create a wrapped object for a primitive type so that you can:
- Pass it to a method that is expecting an object
- Store it in a collection like an `ArrayList` (seen in the next lesson)
- Convert between strings and primitive data types, especially with `Scanner` input.

---

## Creating `Integer` and `Double` Objects

In Java 7, you could use a constructor like `new Integer(2)` to create an object with the value 2 in it. In Java 9 and later, you can just use:

```java
Integer i = 2;
Double d = 3.5;
````

`Integer` and `Double` objects are immutable — once created, their values cannot be changed.

```java
// in older versions of Java
Integer i = new Integer(2);
Double d = new Double(3.5);

// in newer versions of Java (9+)
Integer i = 2;
Double d = 3.5;
```

---

## Minimum and Maximum Values

These wrapper classes have special constants (like the minimum and maximum values for the type) and useful methods.

<div class="task" markdown="block">

**Codespaces Task:**
Type the following in your Codespace, run it, and observe the output.

```java
public class Test1
{
    public static void main(String[] args)
    {
        System.out.println(Integer.MIN_VALUE);
        System.out.println(Integer.MAX_VALUE);
        System.out.println(Integer.MIN_VALUE - 1);
        System.out.println(Integer.MAX_VALUE + 1);
    }
}
```

</div>

**Note:**
The `int` type in Java can represent any whole number from `-2147483648` to `2147483647`. Integers in Java are stored in **two’s complement** using 32 bits.

* Going below `MIN_VALUE` wraps to `MAX_VALUE` (**underflow**)
* Going above `MAX_VALUE` wraps to `MIN_VALUE` (**overflow**)

---

## Autoboxing and Unboxing

**Autoboxing**: Automatic conversion from a primitive type to its wrapper object.

```java
Integer i = 2;  // int → Integer
Double d = 3.5; // double → Double
```

**Unboxing**: Automatic conversion from a wrapper object to its primitive type.

```java
Integer i = 2;  // autoboxing
int number = i; // unboxing
```

---

## Check Your Understanding

<div class="task" markdown="block">

Match the term with its definition:

* Autoboxing → automatic conversion from primitive to wrapper object
* Unboxing → automatic conversion from wrapper object to primitive
* `Integer` → wrapper class
* `int` → primitive type
* `Integer.MAX_VALUE + 1` → overflow
* `Integer.MIN_VALUE - 1` → underflow

</div>

---

## Parsing Strings to Numbers

The `Integer` and `Double` classes have methods to convert strings to numbers:

* `static int parseInt(String s)` → returns the string as a signed int
* `static double parseDouble(String s)` → returns the string as a signed double

Example:

<div class="task" markdown="block">

```java
public class Test2
{
    public static void main(String[] args)
    {
        Integer i = 2;
        Double d = 3.5;
        System.out.println(i.intValue());
        System.out.println(d.doubleValue());

        String ageStr = "16";
        System.out.println("Age " + ageStr + " in 10 years is " + (Integer.parseInt(ageStr) + 10));
    }
}
```

</div>

---

## Debugging Challenge

<div class="task" markdown="block">

Fix the following code so it uses correct `Integer`/`Double` syntax and methods:

```java
public class Debug
{
    public static void main(String[] args)
    {
        integer i = 2.3;
        Double d = 5;
        System.out.println( i.intValue );
        System.out.println( doubleValue() );
        System.out.println(Integer.min_value);
        System.out.println( int.MAX_VALUE() );
        String numStr = "2.5";
        System.out.println( Int.parseInt(numStr) * 2 );
    }
}
```

</div>

---

## Groupwork Coding Challenge: Pokémon Speed

We’ll read a Pokémon CSV file, calculate the **average speed**, and find the Pokémon with the **highest speed**. Speed is in the 8th column (index `7` after splitting).

<div class="task" markdown="block">

```java
import java.io.*;
import java.util.*;

public class PokeSpeed
{
    private String filename = "pokemon.csv";
    private String[] pokemonLines = new String[152];

    public PokeSpeed() throws IOException
    {
        readFile();
    }

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

    public int findMaxSpeed()
    {
        int maxSpeed = 0;
        String maxPokemonName = "";

        // TODO: loop, split, parse speed, update maxSpeed and name
        return maxSpeed;
    }

    public double findAverageSpeed()
    {
        double averageSpeed = 0;
        double totalSpeed = 0;

        // TODO: loop, split, parse, sum speeds
        return averageSpeed;
    }

    public static void main(String[] args) throws IOException
    {
        PokeSpeed p = new PokeSpeed();
        System.out.println("Max speed: " + p.findMaxSpeed());
        System.out.println("Average speed: " + p.findAverageSpeed());
    }
}
```

</div>

---

## Summary

* `Integer` and `Double` are **wrapper classes** from `java.lang` for `int` and `double`.
* They are **immutable**.
* **Autoboxing**: primitive → wrapper
* **Unboxing**: wrapper → primitive
* Use `Integer.parseInt(String)` and `Double.parseDouble(String)` to convert strings to numbers.
* `Integer.MIN_VALUE` and `Integer.MAX_VALUE` are useful constants for comparisons.
* Overflow/underflow wrap around to the opposite extreme.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
