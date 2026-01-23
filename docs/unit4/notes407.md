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
📖 This page is a condensed version of [CSAwesome Topic 4.7](https://runestone.academy/ns/books/published/csawesome2/topic-4-7-wrapper-classes.html) 

<div style="text-align: center;">
<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong><br>Create a blank Java program to take your class notes in for the next few lessons.<br><em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>
</div>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit4PartB-Notes`
4. For the **description**, write: `ArrayList data collections, Integer & Double wrapper classes`
5. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
6. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
7. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
8. 📝 Take notes in this Codespace during class, writing **code** & **comments** along with the instructor.

</div>

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! **Codespaces** are TEMPORARY editing environments, so you need to COMMIT changes properly in order to update the main **repository** for your program. 

_There are multiple steps to saving in GitHub Codespaces:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

</details>

</html>

---

## Wrapper Classes: Integer and Double

For every primitive type in Java, there is a built-in object type called a **wrapper class**. The wrapper class for `int` is called `Integer`, and for `double` it is called `Double`. _Why do this?_ Sometimes you may need to create a **wrapped OBJECT** version of a **primitive type**, so that you can give it to a method that is expecting an object. 

![image-small](https://external-preview.redd.it/G_XR_y2ep9Sl4c45tXhLfwwATWZ-6RHlLQ2KKbbw05s.jpg?width=640&crop=smart&auto=webp&s=0409a7c9298ec38d6bb6e91dc884b23bd0761114)

🎁 To **wrap** a value, call the _constructor_ for the wrapper class in earlier versions of Java. In Java 9 on, this is **deprecated** which means it's not the best way to do this anymore, and you should instead just set it equal to a value. The AP CSA Exam covers Java 7 which does allow using the constructor.

```java
   // in older versions of Java (and on the AP exam)
   Integer i = new Integer(2); // create an object with 2 in it
   Double d = new Double(3.5); // create an object with 3.5 in it

   // in newer versions of Java (9+)
   Integer i = 2;
   Double d = 3.5;
```

These wrapper classes (defined in the `java.lang` included **package**) are also useful because they have some special values (like the minimum and maximum values for the type) and methods that you can use.

When would you ever use `Integer.MIN_VALUE` or `Integer.MAX_VALUE`?  They are handy if you want to initialize a variable to the smallest possible value and then search a sequence of values for a larger value.

### Autoboxing and Unboxing 

**Autoboxing** is the automatic conversion that the Java compiler makes between primitive types and their corresponding object wrapper classes. This includes converting an `int` to an `Integer` and a `double` to a `Double`. The Java compiler applies autoboxing when a primitive value is passed as a parameter to a method that expects an object of the corresponding wrapper class or assigned to a variable of the corresponding wrapper class. Here's an example of autoboxing.

```java
   Integer i = 2;
   Double d = 3.5;
```

**Unboxing** is the automatic conversion that the Java compiler makes from the wrapper class to the primitive type. This includes converting an Integer to an int and a Double to a double. The Java compiler applies unboxing when a wrapper class object is passed as a parameter to a method that expects a value of the corresponding primitive type or assigned to a variable of the corresponding primitive type. Here's an example of unboxing:

```java
   Integer i = 2;  // autoboxing - wrap 2
   int number = i; // unboxing - back to primitive type
```

---

## ⭐️ Summary

- The ``Integer`` class and ``Double`` class are **wrapper classes** that create objects from primitive types.

- (AP 4.7.A.1) The ``Integer`` class and ``Double`` class are part of the ``java.lang`` package. 

- (AP 4.7.A.1) An ``Integer`` object is immutable, meaning once an ``Integer`` object is created, its attributes cannot be changed. A ``Double`` object is immutable, meaning once a ``Double`` object is created, its attributes cannot be changed.

- (AP 4.7.A.2) **Autoboxing** is the automatic conversion that the Java compiler makes between primitive types and their corresponding object wrapper classes. This includes converting an ``int`` to an ``Integer`` and a ``double`` to a ``Double``. The Java compiler applies autoboxing when a primitive value is:

    - passed as a parameter to a method that expects an object of the corresponding wrapper class
    - assigned to a variable of the corresponding wrapper class

- (AP 4.7.A.3) **Unboxing** is the automatic conversion that the Java compiler makes from the wrapper class to the primitive type. This includes converting an ``Integer`` to an ``int`` and a ``Double`` to a ``double``. The Java compiler applies unboxing when a wrapper class object is:

    - passed as a parameter to a method that expects a value of the corresponding primitive type
    - assigned to a variable of the corresponding primitive type

- (AP 4.7.A.4) The following class ``Integer`` method—including what it does and when it is used—is part of the Java Quick Reference: ``static int parseInt(String s)`` returns the ``String`` argument as a signed ``int``.
- (AP 4.7.A.5) The following class ``Double`` method—including what it does and when it is used—is part of the Java Quick Reference: ``static double parseDouble(String s)`` returns the ``String`` argument as a signed ``double``.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
