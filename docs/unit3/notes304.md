---
layout: notes
title: "📓3.4: Writing Constructors" 
parent: "3️⃣ Class Creation"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.4](https://runestone.academy/ns/books/published/csawesome2/topic-3-4-constructors.html) 

---

## Writing Constructors

In Unit 2, we learned how to create objects by calling **constructors**. 

<div class="imp" markdown="block">
    
📣 To review, a _call_ to a **constructor** consists of the word ``new`` followed by the
name of the `class` being constructed, and then an **argument list** in parentheses:

```java
// To create a new object, write:
// ClassName variableName = new ConstructorName(arguments);
World world = new World();
Turtle t = new Turtle(world);
Person p = new Person("Pat", "pat@gmail.com", "123-456-7890");
```
> This is how we create specific ``World``, ``Turtle``, and ``Person``
objects as _instances_ of their classes.

</div>

Now it's time to learn to write our own constructors.

### Constructor Signature

In the source code for a class, constructors are usually written after the
instance variables and before any methods.

➰🖋️ The **signature** of a constructor is similar to the signature of a method except
there is **no return type**, not even ``void``, and instead of a method name, the
name of the constructor is the **same as the name of the class**. 
> _Other details:_ The constructors you write will almost always be marked ``public``. Like methods, constructors also have a **parameter list** specified in parenthesis that declare the variables that will be used to hold the arguments passed when the constructor is called.

```java
public class ClassName
{
    /* Instance variable declarations go here, before constructors */

    /* Constructor - same name as Class, no return type */
    public ClassName()
    {
        /* Implementation not shown */
    }

    /* Method definitions go here, after constructors */
}
```

{:.highlight}
⚠️ Constructors must have the **same name** as the `class`! Constructors have **no return type**!

### The Job of a Constructor

The job of a constructor is to **set the initial values** for the object’s instance
variables to "useful" values. But what does “useful” mean? 
> Sometimes we describe the values of all an object's instance variables at a given time as the object's **state**. And we say an object is in a **valid state** when all its instance variables have values that _let us use the object_ by invoking its public methods.

🏗️🧱 So another way to describe the job of a constructor is to set up a specific object’s instance values so it’s in a **valid state** – essentially, using the blueprint (class) to crate a **usable object with data**. 

{:.highlight}
Classes can have zero or more constructors but they should all produce an object
in a **valid, usable state**.

#### Default no-argument constructor
The easiest way to write a constructor is to *not* write one. If you do not
write a constructor, your class will **automatically** get what is called the
**default no-argument constructor**. This constructor will initialize all your
instance variables to the _default value_ for their data type: 
* 0 for ``int`` and ``double``
* ``false`` for ``boolean``
* ``null`` for all reference (object) types like `String`.

In the (rare) case where those default values are sufficient to put your object into a valid state, you may not need to write a constructor at all.

#### Constructors that take arguments

Usually, however, if you are writing a class that has instance variables, you
need to initialize your instance values to **some specific values**. In that case you
probably need to write a constructor that **takes arguments and uses them** to
initialize your instance variables.

Consider the constructor from the ``Person`` class from the last section. This constructor ensures that all three of the **instance variables** (``name``, ``email``, and ``phoneNumber``) in ``Person`` are **initialized** to the values provided by whatever code called the constructor:

```java
public Person(String initName, String initEmail, String initPhone)
{
    name = initName;
    email = initEmail;
    phoneNumber = initPhone;
}
```
> For example, in the constructor call ``new Person("Pat", "pat@gmail.com", "123-456-7890")``, the argument "Pat" is passed into the parameter variable ``initName``, which the constructor then assigns to the instance variable ``name``.  

{:.warning}
_One important note:_ if you DO write a constructor, Java will NOT generate the **default** constructor automatically for you. This is a good thing because it lets you make sure that instances of your class are always properly initialized. 

> With this constructor in place, for instance, there’s no way to construct a ``Person`` object without providing the three required ``String`` values.

#### Overloading constructors

Sometimes you will want to write _more than one constructor_ so there are
different ways of making an instance of your class. 

{:.highlight}
Writing **multiple methods** that the same _NAME_ but accept different _ARGUMENTS_ is called **overloading**. One reason to **overload constructors** is to make it convenient to create instances from different kinds/combinations of arguments. 

> We discussed **overloading** in Chapter 2 from the perspective of calling methods with the same name, but providing different amounts of information: like `String.substring(int from)` and `String.substring(int from, int to)`.

For instance, suppose we were writing a program that had another class
``AddressBookEntry`` which had getters for name, email, and phone number. In
that program it might be useful to write another ``Person`` constructor like
this:

```java
public Person(AddressBookEntry address) {
{
    name = address.getName();
    email = address.getEmail();
    phoneNumber = address.getPhoneNumber();
}
```

Most of the time, you might still even want to provide a **no-argument constructor**. If
there’s a valid object that you can create without any arguments, you could
write a no-argument constructor for ``Person`` like:

```java
public Person()
{
    name = "Anonymous";
    email = "unknown";
    phoneNumber = "unknown";
}
```
> It’s up to you to decide if this is actually a useful value to have or if it would be better to force the users of the ``Person`` class to choose the values themselves.

#### 💻 In-Class Activity: Student Class
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-2-writing-constructors.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.2</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Student Class** activity in pairs.

</div>

<!--

## Constructors

A **constructor** is a special method used to initialize new objects. It sets the starting state of an object’s attributes when it is created.

---

## Key Features

- **Same name as the class**
- **No return type** (not even `void`)
- Can take parameters to set initial values
- Called automatically when `new` is used

---

## Example

```java
public class Dog {
    private String name;
    private int age;

    // Constructor
    public Dog(String dogName, int dogAge) {
        name = dogName;
        age = dogAge;
    }
}
````

Usage:

```java
Dog myDog = new Dog("Buddy", 3);
```

---

## Default Constructors

* If you do not write any constructor, Java provides a **default constructor** with no parameters.
* If you write **any** constructor, Java does **not** create the default one automatically.

Example of default constructor:

```java
public class Dog {
    private String name;
    private int age;

    // Default constructor
    public Dog() {
        name = "Unknown";
        age = 0;
    }
}
```

---

## Multiple Constructors

A class can have multiple constructors with different parameter lists (**constructor overloading**).

```java
public class Dog {
    private String name;
    private int age;

    public Dog() {
        name = "Unknown";
        age = 0;
    }

    public Dog(String dogName) {
        name = dogName;
        age = 0;
    }

    public Dog(String dogName, int dogAge) {
        name = dogName;
        age = dogAge;
    }
}
```

---

## Summary

* Constructors set the **initial state** of an object.
* They have the **same name** as the class and no return type.
* Overloading allows multiple ways to create an object.

---

## AP Practice

<details>
<summary><strong>Question</strong></summary>

What happens if you write a constructor that takes parameters but do not include a no-argument constructor?

* A. Java creates a no-argument constructor automatically.
* B. You cannot create objects without passing arguments. ✅
* C. The class will not compile.
* D. The default constructor will still be available.

</details>
-->

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
