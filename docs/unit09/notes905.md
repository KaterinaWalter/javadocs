---
layout: notes
title: "📓9.5: Hierarchies" 
parent: "9️⃣ Inheritance"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.5](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-5-hierarchies.html) 

---

## Inheritance Hierarchies

If you have multiple subclasses that inherit from a superclass, you can form an **inheritance hierarchy**. Every **subclass** _is-a_ or is a kind of the **superclass**, and the hierarchy can reach many levels.  

For example, here is an inheritance hierarchy of shapes: 

![image](Figures/shapes.png)
> `Square` _is-a_ `Rectangle` and a **subclass** of Rectangle. `Rectangle` _is-a_ `Shape` and a **subclass** of Shape. In Java, the class `Object` is always at the **top** of any hierarchy. Every class in Java inherits from Object and is-an Object.

One of the main reasons to use an inheritance hierarchy is that all the classes in the hierarchy _can be treated as instances of the top type_ in the hierarchy. This is called **polymorphism** and we'll discuss it in more detail in the next section.

Inheritance can also _reduce code duplication_ since **common behaviors** can be defined in methods in a **superclass** and _inherited_ by all their subclasses. 
> But you should never use inheritance just to reuse code if there isn't a true **“is-a” relationship** between the subclass and the superclass!

<div class="task" markdown="block">
    
💬 **DISCUSS:** 
* What **variables** and **methods** might be inherited from the superclass `Shape` in the inheritance hierarchy above?
* Can you make a 3-level inheritance hierarchy for **living things** on Earth?

</div>


### Superclass References

A superclass **reference variable** can hold an object of that superclass or of any of its subclasses. 

For example, a `Shape` **reference variable** can hold a `Rectangle` or `Square` object: 
```java
// The variables declared of type Shape can hold objects of its subclasses
Shape s1 = new Shape();
Shape s2 = new Rectangle();
Shape s3 = new Square();
```

{:.warning}
Notice that the opposite is not true! You cannot _declare_ a variable of the **subclass** but then _construct_ a **superclass** object. 

For example, a `Square` reference cannot hold a `Shape` object because _not all Shapes are Squares_:

```java
// A subclass variable cannot hold the superclass object!
// A Square is-a Shape, but not all Shapes are Squares.
Square q = new Shape(); // ERROR!!
```
> The code above will give an "Incompatible types: Shape cannot be converted to Square" error.

Why is using a superclass reference for subclass objects useful? Because now, we can write **methods** with _parameters_ of type `Shape`, or have **arrays** of type `Shape`, and use them with any of its subclasses as seen in the next sections.

### Superclass Method Parameters

Another advantage of an inheritance hierarchy is that we can write methods with _parameters_ of the superclass type, but then _pass in_ subclass objects to them. 

For example, the `print(Shape)` method below could be called with many different Shape **subclasses** and work for `Rectangles`, `Squares`, etc.

```java
// This will work with all Shape subclasses (Squares, Rectangles, etc.) too
public void print(Shape s) {
    ...
}
```

Notice that in the following code, the print method has a parameter of type ``Person``, but it can be called with ``Student`` or ``Person`` objects in the ``main`` method. How do we know which ``toString`` method is called? It depends on whether a ``Person`` or ``Student`` is _passed in_ at runtime. 

```java
public class Tester {
    public static void main(String[] args) {
        Person p = new Person("Sila");
        Student s = new Student("Tully", 1001);
        System.out.println(p); // call print with a Person
        System.out.println(s); // call print with a Student
    }
}
```
```java            
public class Person {
    private String name;

    public Person(String name) {
        this.name = name;
    }

    public String toString() {
        return name;
    }
}
```
```java
public class Student extends Person {
    private int id;

    public Student(String name, int id) {
        super(name);
        this.id = id;
    }

    public String toString() {
        return super.toString() + " " + id;
    }
}
```
> 💬 **DISCUSS:** Which `toString()` method is called? What would happen if you commented out the ``toString`` method in ``Student``? Which one would be called now?

### Superclass Arrays and ArrayLists

Using inheritance hierarchies, we can create arrays and ``ArrayLists`` using the superclass type and put in values that are of the subclass types. This can be very useful! 

For example, here is some code that creates a ``Shape[]`` array and an ``ArrayList<Shape>``, both of which can hold any objects of ``Shape`` AND any of its subclasses:

```java
// This shape array can hold the subclass objects too
Shape[] shapeArray = { new Rectangle(), new Square(), new Shape() };

// The shape ArrayList can add subclass objects too
ArrayList<Shape> shapeList = new ArrayList<Shape>();
shapeList.add(new Shape());
shapeList.add(new Rectangle());
shapeList.add(new Square());
```
    
#### 💻 In-Class Activity: Shopping Cart
{:.no_toc}

<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-5-hierarchies.html"><button type="button" name="button" class="btn">CSAwesome Topic 9.5</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Shopping Cart** activity in pairs.

</div>

---

## ⭐️ Summary

- An **inheritance hierarchy** of subclasses _inheriting from_ superclasses can be formed with `Object` being the **top** of the hierarchy.

- When a class S "is-a" class T, T is referred to as a **superclass**, and S is referred to as a **subclass**.

- If S is a subclass of T, then a reference of type T can be used to refer to an object of type T or S. This is called **polymorphism**, defined more in the next lesson.

- Declaring **references of superclass type** T, when S is a subclass of T, is useful in the declaring of:
    - Formal **method parameters** of type T
    - **Arrays** of type T
    - **ArrayList** of type T

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
