---
layout: notes
title: "📓3.6: Methods that Pass or Return Objects" 
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

## Writing Methods

Up until this unit, you wrote all your code in the main method, but now we are using lots of methods. Why have multiple methods instead of just one? 

{:.highlight}
**Procedural Abstraction** allows us to name a block of code as a **method** and call it whenever we need it, _abstracting_ away the details of how it works. 
> This serves to _organize_ our code by function and _reduce repetition_ of code. In addition, it helps with debugging and maintenance since changes to that block of code only need to happen in one place!

Here are some of the main reasons to use multiple methods in your programs:

- **Organization and Reducing Complexity:** organize your program into small sections of code by function to reduce its complexity. Divide a problem into subproblems to solve it a piece at a time.
- **Reusing Code:** avoid repetition of code. Reuse code by putting it in a method and calling it whenever needed.
- **Maintainability and Debugging:** smaller methods are easier to debug and understand than searching through a large main method.

### How to Write a Method

<div class="imp" markdown="block">

There are three steps to creating and calling a custom **method**:

3. **Method Definition**: Write the method's **header/signature** and **body** code _inside the class_ that defines the object.
```java
// Step 1: Define the method in the class
// Method HEADER/SIGNATURE
public void methodName() {
    // Method BODY for the repeatable code
}
```
2. **Object Instance**: Declare an object of your class type in the main method or _from outside the class._
```java
// Step 2: Declare an object
ClassName objectName = new ClassName();
```
3. **Method Call**: Whenever you want to use the method, call it on the object by using the dot `.` operator
```java
// Step 3: Call the object's method
objectName.methodName(); 
```
> * 📥 If the method requires any *INPUT* to work, provide those values in the parenthesis. These are known as **arguments**, or **actual parameters**.
> * 📤 If the method provides any _OUTPUT_, meaning it has a **return** value, store it in a variable of the appropriate type (see below for more details on using methods that return values).

</div>

🎶 Let's look at an example with lots of repetition of code and create methods to reduce the repetition of code. You can sing along here: [This Old Man Song](https://www.youtube.com/watch?v=Di23O5cN4ZU&ab_channel=Rock%27NLearn).

You may have noticed that the chorus is repeated _"With a knick knack paddy whack, give a dog a bone. This old man came rolling home."_ When you see **repeated code**, that is a signal for you to make a new method!

For example, here is a `chorus()` method definition that we could write for the "This Old Man Song":

```java
public void chorus() {
    System.out.println("With a knick knack paddy whack, give a dog a bone.");
    System.out.println("This old man came rolling home.");
}
```
> Run the tester code in the [Java visualizer](http://www.pythontutor.com/visualize.html#code=public%20class%20Song%20%0A%20%20%7B%20%0A%20%20%20%20//%20The%20chorus%20method%0A%20%20%20%20public%20void%20chorus%28%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20System.out.println%28%22With%20a%20knick%20knack%20paddy%20whack,%20give%20a%20dog%20a%20bone.%22%29%3B%0A%20%20%20%20%20%20%20System.out.println%28%22This%20old%20man%20came%20rolling%20home.%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20public%20static%20void%20main%28String%20args%5B%5D%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20Song%20mySong%20%3D%20new%20Song%28%29%3B%0A%20%20%20%20%20%20System.out.println%28%22This%20old%20man,%20he%20played%20one.%22%29%3B%0A%20%20%20%20%20%20System.out.println%28%22He%20played%20knick%20knack%20on%20my%20thumb.%20%22%29%3B%0A%20%20%20%20%20%20mySong.chorus%28%29%3B%0A%0A%20%20%20%20%20%20System.out.println%28%22This%20old%20man,%20he%20played%20two.%22%29%3B%0A%20%20%20%20%20%20System.out.println%28%22He%20played%20knick%20knack%20on%20my%20shoe.%20%22%29%3B%0A%20%20%20%20%20%20mySong.chorus%28%29%3B%0A%20%20%20%20%7D%0A%20%20%7D&cumulative=false&curInstr=22&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0) to see the song This Old Man print out. Can you replace the last two lines in the second verse in the main method with a call the `chorus()` method instead?

### Method Input: Formal Parameters

You may have noticed even more repetition in the song above. What about the lines of each _verse_? Notice that every word is repeated except the last ones that include a number and a rhyme such as one/thumb and two/shoe.

```java
    System.out.println("This old man, he played one.");
    System.out.println("He played knick knack on my thumb.");
    ...
    System.out.println("This old man, he played two.");
    System.out.println("He played knick knack on my shoe.");
```

We can make methods even more powerful and more abstract by giving them **parameters** for data that they need to do their job - think of it like taking _INPUT_ before the process. We can make a method called verse that takes the number and the rhyme to print out any verse!

```java
public void verse(String number, String rhyme) {
       System.out.println("This old man, he played " + number);
       System.out.println("He played knick knack on my " + rhyme);
}
```
> Run the tester code in the [Java visualizer](http://www.pythontutor.com/visualize.html#code=public%20class%20Song%20%0A%20%20%7B%20%0A%20%20%20%20%0A%20%20%20%20/**%20Verse%0A%20%20%20%20%20*%20%40param%20number%20-%20a%20String%20like%20%22one%22,%20%22two%22,%20etc.%0A%20%20%20%20%20*%20%40param%20rhyme%20-%20a%20String%20like%20%22thumb%22,%20%22shoe%22,%20etc.%0A%20%20%20%20%20*/%0A%20%20%20%20%20public%20void%20verse%28String%20number,%20String%20rhyme%29%0A%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20System.out.println%28%22This%20old%20man,%20he%20played%20%22%20%2B%20number%29%3B%0A%20%20%20%20%20%20%20System.out.println%28%22He%20played%20knick%20knack%20on%20my%20%22%20%2B%20rhyme%29%3B%0A%20%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20//%20The%20chorus%20method%0A%20%20%20%20public%20void%20chorus%28%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20System.out.println%28%22With%20a%20knick%20knack%20paddy%20whack,%20give%20a%20dog%20a%20bone.%22%29%3B%0A%20%20%20%20%20%20%20System.out.println%28%22This%20old%20man%20came%20rolling%20home.%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20public%20static%20void%20main%28String%20args%5B%5D%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20Song%20mySong%20%3D%20new%20Song%28%29%3B%0A%20%20%20%20%20%20mySong.verse%28%22one%22,%20%22thumb%22%29%3B%0A%20%20%20%20%20%20mySong.chorus%28%29%3B%0A%20%20%20%20%20%20mySong.verse%28%22two%22,%20%22shoe%22%29%3B%0A%20%20%20%20%20%20mySong.chorus%28%29%3B%0A%20%20%20%20%7D%0A%20%20%7D&cumulative=false&curInstr=24&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0) to see the song This Old Man print out using the `verse` and `chorus` methods. Can you add verse three with the rhyme "knee"? Can you add verse four with the rhyme "door"? How many verses do you know?

<div class="imp" markdown="block">

🤵‍♀️🤵🤵‍♂️ When you **define** your own method, the variables you specify for it in the method header are called **formal parameters**. 

📣 When you **call** the method to do its job, you give or pass in **arguments** or **actual parameters** to it that are then saved in these local parameter variables.

</div>

When a method is called, the right method definition is found by checking the **method signature** or **header** at the top of the method definition to *match* the following:

1. The method **name**
2. The **number** of arguments
3. The **data types** for the arguments
4. The `return` type (either `void` or a data type like `int`, `String`, etc.)

For example, imagine we are calling the methods for the This Old Man song:
```java
Song mySong = new Song();
mySong.verse("one", "thumb");
mySong.chorus();
mySong.verse("two", "shoe");
mySong.chorus();
```

Here's what that looks like with the 2 method calls above. Notice how the parameter variables get new values with every method call.

![image](Figures/args2params.png)

{:.warning}
Java uses **Call by Value** when it passes arguments to methods. This means that a _copy_ of the value in the argument is saved in the parameter variable. If the parameter variable changes its value inside the method, the original value outside the method is not changed.

If you pass in an argument that holds a **reference** to an **object**, like a `String` or `Person` or `Turtle` object, a _copy_ of this reference is passed in and saved in the parameter variable. The formal parameter and the actual parameter (argument) are then **aliases**, both refering to the same object. 
> Java was designed this way to avoid copying large objects from method to method. Remember when we discussed **reference aliases** with `Turtle` objects who are set equal to one another.

![image](Figures/turtleEquality.png)

### Method Output: Return Values

📤  Methods can also **return** values of any type back to the calling method, which can be considered _OUTPUT_. Recall that **non-void** methods, like we saw when writing **getter/accessor** methods, `return` a value of a specific data type. 

{:.highlight}
If a certain method returns a value, the calling method should then _do something_ with this `return` value, like printing it out or assigning it to a variable (of the same type).

```java
// Printing a value returned from a method call
System.out.print("The student's name is " + student.getName() );
// Storing a return value in a new variable
String studentName = student.getName();
```

#### 💻 In-Class Activity: Song with Parameters
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-6-writing-methods.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.6</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Song with Parameters** activity in pairs.

</div>

---

## ⭐️ Summary

- **Procedural Abstraction** (creating methods) reduces the complexity and repetition of code. We can name a block of code as a _method_ and call it whenever we need it, abstracting away the details of how it works.
    - A programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem.

- To write methods, write a **method definition** with a **method signature** like `public void chorus()` and a **method body** in `{ }` and make method calls using an `object.methodName()` and arguments whenever you need it to do its job.

- To call an object's method, you must use the object name and the dot (`.`) operator followed by the method name, for example `object.method();`

- When you call a method, you can give or pass in **arguments** or **actual parameters** to it inside the parentheses **object.method(arguments)**. The arguments are saved in local **formal parameter** variables that are declared in the method header, for example: `public void method(type param1, type param2) { ... }`.
    - Values provided in the arguments in a method call need to correspond to the order and type of the parameters in the method signature.
    - When an actual parameter is a primitive value, the formal parameter is initialized with a copy of that value. Changes to the formal parameter have no effect on the corresponding actual parameter.
    - When an actual parameter is a reference to an object, the formal parameter is initialized with a copy of that reference, not a copy of the object. The formal parameter and the actual parameter are then aliases, both refering to the same object.
    -  When an actual parameter is a reference to an object, the method or constructor could use this reference to alter the state of the original object. However, it is good programming practice to not modify mutable objects that are passed as parameters unless required in the specification.
  


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
