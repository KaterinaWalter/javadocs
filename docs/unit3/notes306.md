---
layout: notes
title: "📓3.6: Passing & Returning Objects" 
parent: "3️⃣ Class Creation"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.6](https://runestone.academy/ns/books/published/csawesome2/topic-3-6-methods-references.html) 

---

## Passing & Returning References of an Object

Programs often consist of many classes that interact with each other in various ways: 
* Objects of one class can be _declared as instance variables_ of another class.
* Objects can be _passed_ as arguments to methods.
* Objects can be _returned_ from methods.

This is a powerful feature of object-oriented programming that allows for complex interactions between objects. 

### Objects as Instance Variables

Classes can have complex instance variables that use other classes. For example, a ``Person`` class could have an instance variable for the address which can be an object with its own instance variables of street, city, state, and zipcode. 

{:.highlight}
This is a `has-a` relationship, where a "Person **has an** Address". 

```java
    class Address
    {
        // instance variables
        private String street;
        private String city;
        private String state;
        private String zipcode;
    }
    
    class Person
    {
        // instance variables
        private String name;
        private Address addr;  // instance variable of type Address
    }
```

### Objects as Arguments

Java uses **Call by Value** when it passes arguments to methods and constructors. This means that a **copy** of the value in the _argument_ is saved in the _parameter_ variable. 
> If the parameter variable changes its value _inside_ the method, the **original value** outside the method is _not_ changed!

{:.highlight}
There is an important difference between passing **primitive** data (_copies of values_) and **objects** (_copies of references_) in Java methods. Passing an object as a **parameter** gives the method a _reference to the object_ - like the directions to the data container. 

With primitive types like `int` and `double`, the argument value is copied into the parameter variable as expected. However, if you pass in an argument that holds a reference to an **object**, like a `String` or `Person` or `Address` or `Turtle` objects, the _reference_ is copied, not the whole object. 
> Java was designed this way to avoid copying large objects from method to method.  

<div class="task" markdown="block">
  
💬 **DISCUSS:** If you lend your friend your only copy of a book, and they write in it, what happens to your book when you get it back?

> **Passing object references** in Java is like _lending_ out your book - not giving them a new copy. Any changes they make affect your original book.

</div>

When a copy of a reference is passed in and saved in the parameter variable, the parameter and the argument are then **aliases**, both refering to the same object. Remember when we discussed reference aliases with turtle objects who are set equal to one another:

![image](Figures/turtleEquality.png)

* There can be unexpected results if the parameter refers to a _mutable_ object; the method or constructor can use this reference to alter the state of the original object. 

* Some classes like ``String`` are _immutable_, so they cannot be changed by any method; for example, when ``s.toUpperCase()`` is called, it returns a new String object with the uppercase letters, but the original String object is not changed.

### Returning Objects

Methods can also **return** objects. Remember that methods can only return the _value_ of a variable. If the return value is of a primitive type like int or double, only a copy of the value is returned; the original variable cannot be changed. 

But when the return expression evaluates to an object reference, the reference is returned, not a reference to a new copy of the object. This means that there can be multiple references to the same object. If the object is mutable, then any changes made to the object through one reference will be seen through any other references to the object.

For example, the ``Person`` class can have a ``getAddress`` method that returns the ``Address`` instance variable which is an object. Since ``Address`` has set methods which make it mutable, the caller can change the Address object through the reference returned by the method.

```java
    public class Person
    {
        // instance variables
        private String name;
        private Address addr;  // instance variable of type Address       

        public Address getAddress()
        {
            return addr;
        }

        public static void main(String[] args)
        {
            Person p1 = new Person("Skyler", new Address("123 Main St", "Anytown", "Anystate", "12345"));
            System.out.println(p1);
            Address a = p1.getAddress();
            a.setCity("Othertown");
            System.out.println(p1);
        }
    }
```

---

#### 💻 Coding Challenge: Friends & Birthdays
{:.no_toc}

In this activity, you will create a class `Friend` which keeps track of your friends’ names and birthdays using another class called `Date`. 

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/bwl_apcs_25-26/topic-3-6-methods-references.html"><button type="button" name="button" class="btn">CSAwesome Topic 3.6</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Coding Challenge: Friends and Birthdays** activity in pairs.

</div>

---

## ⭐️ Summary

- (AP 3.4.A.3) When a mutable object is a constructor parameter, the instance variable should be initialized with a copy of the referenced object. In this way, the instance variable does not hold a reference to the original object, and methods are prevented from modifying the state of the original object.

- (AP 3.6.A.1) When an argument is an object reference, the parameter is initialized with a copy of that reference; it does not create a new independent copy of the object. If the parameter refers to a mutable object, the method or constructor can use this reference to alter the state of the object. It is good programming practice to not modify mutable objects that are passed as parameters unless required in the specification.
- (AP 3.6.A.2) When the return expression evaluates to an object reference, the reference is returned, not a reference to a new copy of the object.
- (AP 3.6.A.3) Methods cannot access the private data and methods of a parameter that holds a reference to an object unless the parameter is the same type as the method’s enclosing class.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
