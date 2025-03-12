---
layout: notes
title: "📓9.6: Polymorphism" 
parent: "9️⃣ Inheritance"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.6](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-6-polymorphism.html) 

---

## Polymorphism

**Polymorphism** is a big word that you can break down into "_poly_" which means _many_ and "_morphism_" which means _form_. So, it just means many forms. In Java it means that the method that gets called at **run-time** (when the code is run) depends on the *type* of the object at run-time.

This is similar to the See N-Say toddler toy that has pictures of animals and when a handle is pulled an arrow spins.  When the arrow stops the toy plays the sound associated with that animal:

![image-small](Figures/SeeNSay.jpg)

If you were simulating this toy in software you could create an ``Animal`` class that had a ``makeNoise`` method. Each subclass of ``Animal`` would override the ``makeNoise`` method to make the correct noise for that type.  This type of polymorphism is called **inheritance-based polymorphism**.  You have a common parent class, but the _behavior_ is specified in the child class.

{:.highlight}
In Java an object variable has both a **declared (compile-time) type** and an **actual (run-time) type**.  The *declared (compile-time) type*  of a variable is the type that is used in the declaration.  The *actual (run-time) type* is the class that actually creates the object using new.

The variable ``nameList`` declared below has a **declared type** of ``List`` and an **actual** or **run-time type** of ``ArrayList``.  
> * The **compiler** will check if the declared type has the methods or inherits the methods being used in the code, and give an error if it doesn't find the method(s).
> * At **run-time** the execution environment will first look for the ``add`` method in the ``ArrayList`` class since that is the actual or run-time type. If it doesn't find it there it will look in the parent class and keep looking up the inheritance tree until it finds the method. It may go up all the way to the Object class. The method will be found, since otherwise the code would not have compiled.

```java
ArrayList<String> nameList = new ArrayList<String>();
nameList.add("Hi");
```

<div class="warn" markdown="block">
  
The variable ``message`` declared below has a **declared type** of ``Object`` and an **actual** or **run-time type** of ``String``. Since the declared type of ``message`` is ``Object`` the code ``message.indexOf("h");`` will cause a _compiler error_ since the ``Object`` class does not have an ``indexOf`` method.

```java
Object message = new String("hi");
message.indexOf("h"); // ERROR!! Objects don't have indexOf!
```
</div>

At _compile time_, the compiler uses the **declared type** to check that the methods you are trying to use are available to an object of that type.  The code won't compile if the methods don't exist in that class or some parent class of that class. At _run-time_, the actual method that is called depends on the **actual type** of the object. 

In the last lesson on inheritance hierarchies, we were actually seeing **polymorphic behavior** at _run-time_ in the following ways:

1. Polymorphic assignment statements such as ``Shape s = new Rectangle();``
2. Polymorphic parameters such as ``print(Shape)`` being called with different subclass types.
3. Polymorphic array and ``ArrayList`` types such as ``Shape[] shapeArray = { new Rectangle(), new Square() };``

In all of these cases, there are no errors at compile-time because the compiler checks that the "subclass is-a superclass" relationship is true. But at run-time, the Java interpreter will use the object's actual subclass type and call the subclass methods for any overridden methods. This is why they are polymorphic -- the same code can have different results depending on the object's actual type at run-time.

#### 💻 In-Class Activity: Shopping Cart 2
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-6-polymorphism.html"><button type="button" name="button" class="btn">CSAwesome Topic 9.6</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Shopping Cart 2** activity in pairs.

</div>

---

## ⭐️ Summary

- At _compile time_, methods in or inherited by the **declared type** determine the correctness of a non-static method call.

- At _run-time_, the method in the **actual object type** is executed for a non-static method call. This is called **POLYMORPHISM**.

- For `static` methods, *only* the declared type is used to determine what method to execute.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
