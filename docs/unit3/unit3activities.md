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

Here are some **attributes** (_data/fields/instance variables_) of the pets that the clinic wants to track:

- `name`
- `age`
- `weight`
- `type` (dog, cat, lizard, etc.)
- `sterile` (tracks if the pet is neutered/spayed or not)

Your class must include all the key _object-defining class_ components covered so far: **instance variables**, **constructors**, **accessor/getter methods**, a **toString** **method**, and **mutator/setter methods**.

### PART A: Set up Files

<div class="task" markdown="block">

1. Add some outline comments to `Main.java`:
    ```java
    public class Main {
        public static void main(String[] args) {
            // CREATE 2 Pet objects with different initial values
    
            // TEST all Pet methods (getters, toString, setters)
    
        }
    }
    ```
    > Because we don't have a `Pet` class defined, we can't actually work with any Pet objects in this file yet... we will come back to this file in Part C. 
2. Navigate to your Codespace's **📁 File Explorer** tab then **➕ Create** a new file named `Pet.java`.
3. In `Pet.java`, write the class header and include a set of curly brackets to set up the file structure.
    ```java
    public class Pet {
        // 1. Declare INSTANCE VARIABLES
    
        // 2. Define CONSTRUCTOR
    
        // 3. Define METHODS (getters, toString, setters)
    
    }
    ```
    
</div> 

### PART B: Define the Class

<div class="task" markdown="block">

1. Inside the `Pet` class, start by declaring the 5 **instance variables** with appropriate **data types**.
  > Remember to make all the instance variables ``private``!
2. Write a **constructor** with a **parameter list**. This constructor should accept an argument for each of the instance variables. 
  > _Link to notes section:_ [📓 3.4 Writing Constructors - Parameterized](https://coderina.dev/javadocs/docs/unit3/notes304.html#parameterized-constructors) 
3. Write **accessor/getter** **methods**, one for each of the instance variables.
  > _Link to notes section:_ [📓 3.5 Writing Methods - Getters](https://coderina.dev/javadocs/docs/unit3/notes305.html#how-to-define-a-getter) 
4. Write a ``toString`` **method** that returns a text string of the data in a ``Pet`` record.
  > _Link to notes section:_ [📓 3.5 Writing Methods - toString](https://coderina.dev/javadocs/docs/unit3/notes305.html#the-tostring-method) 
5. Write **mutator/setter** **methods**, one for each of the instance variables.
  > _Link to notes section:_ [📓 3.5 Writing Methods - Setters](https://coderina.dev/javadocs/docs/unit3/notes305.html#how-to-define-a-setter) 

</div>

### PART C: Test the Class

<div class="task" markdown="block">

1. Navigate back to `Main.java`, this "client" file is where you can **run/test** your `Pet` class code as a user.
2. Inside the ``main()`` method, **create** 2 new ``Pet`` objects with different values by calling the constructor and passing in arguments.
  > _Link to notes section:_ [📓 3.4 Writing Constructors - Creating Objects](https://coderina.dev/javadocs/docs/unit3/notes304.html#constructors-create-objects) 
3. **Call** each of your accessor methods, mutator methods, and ``toString`` methods to demonstrate how they work.

</div>

#### REVIEW: CALLING METHODS
{:.no_toc}

Remember that if you want to use an object's instance method in _another_ class, you must first **create an object instance** of that class, and then call its methods using the syntax pattern ``objectName.methodName()``. 

Here are some examples, assuming `turt` is an object of the `Turtle` class:

```java
// Calling a VOID method (no return)
turt.forward();

// Calling a NON-VOID method (store the return value)
int xPosition = turt.getXPos();
// OR just use it immediately (if you don't need it later)
System.out.println( turt.getXPos() );
```


