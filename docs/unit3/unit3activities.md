---
layout: notes
title: "🎯 Unit 3 Activities" 
parent: "3️⃣ Class Creation"
nav_order: 10
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
3. Specify the **repository name**: `CS2-Unit-3-Activity`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!

</div>

  </details>
</html>

---

## ACTIVITY #1: Class Pet 🐶🐱🐹🐰🐸

You've been hired to create a software system for the Awesome Animal Clinic! They would like to keep track of their animal patients. Your task is to write a complete `class` that defines a `Pet` object to keep track of pet records at the animal clinic. 

Here are some **attributes** (_data/fields/instance variables_) of the pets that they would like to track:

- `name`
- `age`
- `weight`
- `type` (dog, cat, lizard, etc.)
- `sterile` (tracks if the pet is neutered/spayed or not)

Your class must include all the key _object-defining class_ components covered so far: **instance variables**, **constructors**, **accessor/getter methods**, a **toString** **method**, and **mutator/setter methods**.

### PART A: Define the Class

<div class="task" markdown="block">

1. Navigate to your Codespace's **File Explorer** tab. Click the **Create New File** icon and name it `Pet.java`.
2. In `Pet.java`, write the class header and include a set of curly brackets to set up the file.
3. Declare what **instance variables** are needed in the `class` and their data types.
  > * Make sure you use ``int``, ``double``, `boolean`, and ``String`` data types.
  > * Make all the instance variables ``private``.
5. Write a **constructor** that initializes the instance variables. This constructor should accept many parameters such that the user can provide values for each of the instance variables. 
6. Write **accessor/getter** **methods**, one for each of the instance variables.
7. Write a ``toString`` **method** that returns a text string of the data in a ``Pet`` record.
8. Write **mutator/setter** **methods**, one for each of the instance variables.

</div>

#### Outline for `Pet.java`

```java
/**
 * Pet class
 * @author
 */
public class Pet {
    // 1. INSTANCE VARIABLES

    // 2. CONSTRUCTORS

    // 3. METHODS
}
```

### PART B: Test the Class

<div class="task" markdown="block">

1. Navigate back to `Main.java`, this "client" file is where you can **run/test** your `Pet` class code as a user.
2. Inside the ``main()`` method, **create** 2 new ``Pet`` objects with different values by calling the constructor and passing in arguments.
3. **Call** each of your accessor methods, mutator methods, and ``toString`` methods to demonstrate how they work.

</div>

#### Outline for `Main.java`

```java
public class Main {
    public static void main(String[] args) {
        // Create 2 Pet objects using the constructor

        // Test all of your methods (accessors, toString, mutators)

    }
}
```


---


