---
layout: notes
title: "📓3.5: Writing Methods" 
parent: "3️⃣ Class Creation"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.5](https://runestone.academy/ns/books/published/csawesome2/topic-3-5-methods.html) 

---

## Writing Methods in Object Classes

In object-oriented programming, the three main parts of a `class` are:

- the **instance variables** which hold data/attributes/values associated with each object, 
- the **constructors** whose job is to initialize the instance variables, 
- and the **methods** which contain the code for the behaviors of an object and which can use the instance variables defined in the class.

In Unit 1, we used ``Turtle`` objects and called methods like ``forward`` which changed the ``x`` and ``y`` coordinates (instance variables) of the turtle. We also defined static methods that did not work with objects.  In this unit, we will learn how to _write our own methods_ in our own classes.

### Defining Methods

---

## Accessor Methods (_Getters_)

Since the instance variables in a class are usually marked as ``private`` to the
class, if you want code outside the class to be able to access the value of an
instance variable, you need to write what is formally called an **accessor
methods** but which everyone actually just calls a **getter**. 

### How to Define a Getter

<div class="imp" markdown="block"> 
  
👉 A **getter** is a ``public`` method that _takes no arguments_ and _returns the value_ of the
``private`` instance variable. 

```java
class ExampleTemplate
{
  // Instance variable declaration
  private typeOfVar varName;

  // Accessor (getter) method template
  public typeOfVar getVarName()
  {
    return varName;
  }
}
```
> Notice that the getter’s return type is the **same as the type of the instance
variable** and all the body of the getter does is return the value of the variable
using a ``return`` statement.

</div>

Here's an example of an accessor method called ``getName`` for the ``Student``
class which also demonstrates how to call ``getName`` using a ``Student``
object:

```java
public class Student
{
  //Instance variable name
  private String name;

  /** getName() example
  *  @return name */
  public String getName()
  {
    return name;
  }

  public static void main(String[] args)
  {
    // To call a get method, use objectName.getVarName()
    Student s = new Student();
    System.out.println("Name: " + s.getName() );
  }
}
```

> Note that getters only return the **value** of the variable. In other words, the
code that called the getter and which receives that value has _no ability to
change the object's instance variable_ - they just get a **copy** of the value. 

However if the instance variable is a **reference (object) type** like ``String`` or``Person`` the value that is copied is the value of the reference. That means the caller receives a new copy of the reference that points to the same object as is stored in the instance variable. 
> In the next section, when we talk about **mutation**, you'll see how that means that the caller might be able to change the object even though it can't change the reference.

<div class="warn" markdown="block">
  
Some common errors when _writing_ and _using_ getters are:

- Forgetting a **return type** like ``int`` before the method name.
- Forgetting to use the ``return`` **keyword** to return a value at the end of the method.
- Forgetting to **do something** with the value returned from a method, like assigning it to a variable or printing it out.

</div>

### The ``toString`` Method

📜 While not strictly speaking a getter, another important method that returns a
value is the ``toString`` method. This method is called automatically by Java in
a number of situations when it needs to convert an object to a ``String``. 

{:.highlight} 
Most notably the methods ``System.out.print`` and ``System.out.println`` use an object's `toString` method to convert a object argument into a ``String`` to be printed.

Here is the ``Student`` class again, but this time with a ``toString`` method:

```java
  public class Student {
      private String name;
      private String email;
      private int id;

      public Student(String initName, String initEmail, int initId) {
          name = initName;
          email = initEmail;
          id = initId;
      }

      // toString() method
      public String toString() {
          return id + ": " + name + ", " + email;
      }
  }
```

Note that when we call ``System.out.println(s1)`` in the tester class below, it will automatically call the
``toString`` method within the `Student` class to get a ``String`` representation of the ``Student``
object:
```java
  public class TesterClass {
      // main method for testing
      public static void main(String[] args) {
          Student s1 = new Student("Skyler", "skyler@sky.com", 123456);
          System.out.println(s1);
      }
  }
```
> The ``toString`` method will return a ``String`` that is then printed out.

---

## Mutator Methods (_Setters_)

As we saw in the last section, since we typically make instance variables
``private``, we have to define getters if we want to allow code outside the
class to access the value of particular instance variables.

{:.highlight} 
By the same token, if we want to allow code outside the class to `change` the value of an instance variable we have to provide what is formally called a
**mutator method** but which everyone actually calls a **setter**. A setter is a `void` method with a name that starts with ``set`` and that takes a single
argument of the same type as the instance variable to be set. 
> The **effect** of a setter, as you would probably expect, is to assign the provided value to the instance variable.

Just as you shouldn't reflexively write a getter for every instance variable,
you should think even harder about whether you want to write a setter. Not all
instance variables are meant to be **manipulated directly** by code outside the
class.
> For example, consider the ``Turtle`` class. It provides getters ``getXPos`` and
``getYPos`` but it _does not provide corresponding setters_. There are, however,
methods that change a ``Turtle``\ ’s position like ``forward`` and ``moveTo``.
But they do more than just changing the values of instance variables; they also
take care of drawing lines on the screen if the pen is down. 

### How to Define a Setter

<div class="imp" markdown="block">

🪄 A setter is a `void` method with a name that starts with ``set`` and that takes a **single
argument** of the same type as the instance variable to be set.

```java
public class ExampleTemplate
{
     // Instance variable declaration
     private typeOfVar varName;

     // Setter method template
     public void setVarName(typeOfVar newValue)
     {
          varName = newValue;
     }
}
```
> The effect of a setter is to *assign the new provided value* to the object's **instance variable**. 

</div>

Here's an example of the ``Student`` class with a setter for the ``name`` variable:

```java
public class Student
{
     // Instance variable name
     private String name;

     /**
     * setName sets name to newName
     * @param newName
     */
     public void setName(String newName)
     {
          name = newName;
     }

     public static void main(String[] args)
     {
          // To call a set method, use objectName.setVar(newValue)
          Student s = new Student();
          s.setName("Ayanna");
     }
}
```

Compare the **difference** between setters and getters in the following figure:

![image](Figures/get-set-comparison.png)

* Getters `return` an instance variable's **current value**, have the _same return type_ as this variable, and accept **NO parameters**. 
* Setters have a `void` return type and **accept a new value as a parameter** to change the value of the instance variable.

#### 💻 In-Class Activity: Class Pet
{:.no_toc}

You've been hired to create a software system for the Awesome Animal Clinic! They would like to keep track of their animal patients. Here are some **attributes** (_data/fields/instance variables_) of the pets that they would like to track:

- `name`
- `age`
- `weight`
- `type` (dog, cat, lizard, etc.)
- `breed`

🐶🐱🐹🐰🐸 Your task is to create a `class` that defines a `Pet` object to keep track of pet records at the animal clinic. Your class should include all the key _object-defining class_ components covered so far: **instance variables**, **constructors**, **accessor/getter methods**, a **toString** **method**, and **mutator/setter methods**.

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-3-5-methods.html"><button type="button" name="button" class="btn">CSAwesome Topic 3.5</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Class Pet** activity in pairs.

#### CLASS CHECKLIST:
{: .no_toc }

- [ ] First declare what **instance variables** are needed in the `class` and their data types.
  > Make sure you use ``int``, ``double``, and ``String`` data types. Make the instance variables ``private``.

- [ ] Write a **constructor** with many parameters to initialize values for all the instance variables.

- [ ] Write **accessor/getter** **methods** for each of the instance variables.

- [ ] Write a ``toString`` **method** that returns a text string of the data in a ``Pet`` record.

- [ ] Write **mutator/setter** **methods** for each of the instance variables.

- [ ] In the ``main`` method, **test** your object class: create 2 new ``Pet`` objects with different values
   and call the constructor, accessor methods, mutator methods, and ``toString`` methods to test all your code.

</div>

---

## ⭐️ Summary

- (AP 3.5.A.1) A ``void`` method does not return a value. Its header contains the keyword ``void`` before the method name.
- (AP 3.5.A.2)	A **non-void method** returns a single value. Its header includes the return type in place of the keyword ``void``.

- (AP 3.5.A.3) In non-void methods, a return expression compatible with the return type is evaluated, and the value is returned. This is referred to as **return by value**.
- (AP 3.5.A.4) The ``return`` keyword is used to return the flow of control to the point where the method or constructor was called. Any code that is sequentially after a return statement will never be executed. Executing a return statement inside a selection or iteration statement will halt the statement and exit the method or constructor.
- (AP 3.5.A.5) An **accessor method** (getter) allows objects of other classes to obtain a copy of the value of instance variables or class variables. An accessor method is a non-void method.
- (AP 3.5.A.6) A **mutator (modifier) method** (setter) is a method that changes the values of the instance variables or class variables. A mutator method is often a void method.
- Comparison of accessor/getters and mutator/setters syntax:

![image](Figures/get-set-comparison.png)
  
- (AP 3.5.A.7) Methods with **parameters** receive values through those parameters and use those values in accomplishing the method's task.
- (AP 3.5.A.8)	When an argument is a primitive value, the parameter is initialized with a copy of that value. Changes to the parameter have no effect on the corresponding argument.

- The ``toString`` method is an overridden method that is included in classes to
  provide a text description of a specific object. It generally includes what values
  are stored in the instance data of the object. If ``System.out.print`` or ``System.out.println`` is passed an object, that
  object’s ``toString`` method is called, and the returned ``String`` is
  printed. An object’s ``toString`` method is also used to get the ``String``
  representation when concatenating the object to a ``String`` with the
  ``+`` operator.
  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
