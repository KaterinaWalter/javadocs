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

---

## Wrapper Classes: Integer and Double

For every primitive type in Java, there is a built-in object type called a wrapper class. The wrapper class for int is called Integer, and for double it is called Double.   Sometimes you may need to create a wrapped object for a primitive type so that you can give it to a method that is expecting an object. To wrap a value, call the constructor for the wrapper class in earlier versions of Java. In Java 9 on, this is **deprecated** which means it's not the best way to do this anymore, and you should instead just set it equal to a value. The AP CSA Exam covers Java 7 which does allow using the constructor.

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


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
