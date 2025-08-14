---
layout: notes
title: "📓4.9: ArrayList Traversals" 
parent: "4️⃣ Data Collections"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.9](https://runestone.academy/ns/books/published/csawesome2/topic-4-9-arraylist-traversal.html) 

---

# ArrayList Traversal

Traversing an `ArrayList` means visiting each element in the list, often to perform some action or computation on it.

## Traversal Methods

You can traverse an `ArrayList` in several ways:

1. **Enhanced for loop (for-each)**  
   Useful when you need to look at every element without changing the list.

   ```java
   for (String name : nameList) {
       System.out.println(name);
   }
   ```

2. **Regular for loop (with index)**
   Useful when you need to know the index of the element or change elements.

   ```java
   for (int i = 0; i < nameList.size(); i++) {
       System.out.println(nameList.get(i));
   }
   ```

3. **While loop with index**
   Gives you more control, especially if you need to adjust the index.

   ```java
   int i = 0;
   while (i < nameList.size()) {
       System.out.println(nameList.get(i));
       i++;
   }
   ```

**Note:** Do not change the size of an `ArrayList` while using an enhanced `for` loop, as this can cause a `ConcurrentModificationException`.

---

## Removing Elements While Traversing

When removing elements while traversing an `ArrayList`, you need special care to avoid skipping elements. If you remove an element at index `i`, the element after it will shift into index `i`. If you increment `i` in the same iteration, you'll skip that new element.

Example:

```java
int k = 0;
Integer zero = 0;
while (k < nums.size()) {
    if (nums.get(k).equals(zero)) {
        nums.remove(k);
    } else {
        k++;
    }
}
```

---

## Check Your Understanding

<div class="task" markdown="block">

**Question:**
Assume `nums` initially contains `[0, 0, 4, 2, 5, 0, 3, 0]`.
What will it contain after running `numQuest()` below?

```java
public void numQuest() {
    int k = 0;
    Integer zero = 0;
    while (k < nums.size()) {
        if (nums.get(k).equals(zero))
            nums.remove(k);
        k++;
    }
}
```

Choices:
a. `[0, 4, 2, 5, 3]` ✅
b. `[3, 5, 2, 4, 0, 0, 0, 0]`
c. `[0, 0, 0, 0, 4, 2, 5, 3]`
d. `[4, 2, 5, 3]`

**Answer:** a — Incrementing `k` every time skips elements when there are two zeros in a row.

</div>

---

## Reading Files with `java.nio.file`

The `java.nio.file` package (added in Java 7) has a `Files.readAllLines` method to read an entire file into a `List<String>`.

```java
import java.nio.file.*;
...
List<String> lines = Files.readAllLines(Paths.get("data.txt"));
```

Advantages:

* Automatically stores lines in a resizable `ArrayList`.
* No need to know how many lines in advance.

---

## Coding Exercise: Read Pokémon File

<div class="task" markdown="block">

Open a Codespace and create a file `ReadData.java`:

1. Import `java.nio.file.*` and `java.util.*`.
2. In `main`, read `"pokemon.csv"` into a `List<String> lines` using `Files.readAllLines`.
3. Loop through and print the first 10 Pokémon.

```java
import java.io.*;
import java.nio.file.*;
import java.util.*;

public class ReadData {
    public static void main(String[] args) throws IOException {
        List<String> lines = Files.readAllLines(Paths.get("pokemon.csv"));
        for (int i = 0; i < 10; i++) {
            System.out.println(lines.get(i));
        }
    }
}
```

</div>

---

## ArrayList of Custom Objects

You can store any type of object in an `ArrayList`.

```java
ArrayList<Student> roster = new ArrayList<>();
roster.add(new Student("Skyler", "skyler@sky.com", 123456));
roster.add(new Student("Ayanna", "ayanna@gmail.com", 789012));

for (Student s : roster) {
    System.out.println(s);
}
```

```java
class Student {
    private String name, email;
    private int id;

    public Student(String name, String email, int id) {
        this.name = name;
        this.email = email;
        this.id = id;
    }

    public String toString() {
        return id + ": " + name + ", " + email;
    }
}
```

---

## Groupwork Challenge: FRQ Word Pairs

<div class="task" markdown="block">

Create an `ArrayList<WordPair>` from a given `String[] words` so that each word is paired with all following words.

1. Initialize `allPairs` as an empty `ArrayList<WordPair>`.
2. Nested loop: outer loop for `i` from `0` to `length-1`, inner loop for `j` from `i+1` to `length`.
3. Add each `new WordPair(words[i], words[j])` to `allPairs`.

```java
public class WordPairsList {
    private ArrayList<WordPair> allPairs;

    public WordPairsList(String[] words) {
        allPairs = new ArrayList<>();
        for (int i = 0; i < words.length; i++) {
            for (int j = i + 1; j < words.length; j++) {
                allPairs.add(new WordPair(words[i], words[j]));
            }
        }
    }

    public int numMatches() {
        int count = 0;
        for (WordPair wp : allPairs) {
            if (wp.getFirst().equals(wp.getSecond())) {
                count++;
            }
        }
        return count;
    }

    public String toString() {
        return allPairs.toString();
    }
}
```

```java
class WordPair {
    private String word1, word2;
    public WordPair(String w1, String w2) { word1 = w1; word2 = w2; }
    public String getFirst() { return word1; }
    public String getSecond() { return word2; }
    public String toString() { return "(" + word1 + ", " + word2 + ")"; }
}
```

</div>

---

## Summary

* **(AP 4.9.A.1)** Traversing an `ArrayList` means visiting each element, usually with a loop.
* Can use enhanced `for`, regular `for` with index, or `while` loops.
* **(AP 4.9.A.2)** When removing during traversal, adjust the index to avoid skipping elements.
* **(AP 4.9.A.3)** Accessing an out-of-bounds index throws `IndexOutOfBoundsException`.
* **(AP 4.9.A.4)** Do not add/remove elements during an enhanced `for` loop — can cause `ConcurrentModificationException`.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
