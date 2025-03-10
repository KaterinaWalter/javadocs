---
layout: notes
title: "📓10.1: Recursion" 
parent: "🔟 Recursion"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 10.1](https://runestone.academy/ns/books/published/csawesome/Unit10-Recursion/topic-10-1-recursion.html?mode=browsing) 

<html>
<details>
<summary>📓<strong>DEMO PROGRAM SETUP INSTRUCTIONS</strong></summary>

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-10-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>
</details>
</html>

---

## What is Recursion?

**Recursion** is when a _method calls itself_. Recursion is another strategy for *repeating code*.

![image]()

The method below will print out "This is the method that never ends!" and then _call itself_, which will print out the message again, and then call itself, and so on.

```java
public static void neverEnd() {
    System.out.println("This is the method that never ends!");
    neverEnd();
}
```
> ♾️ This is called **infinite recursion**, which is a recursion that never ends. Of course, this particular method is not very useful. (Actually, in practice it *will* end, crashing with a ``StackOverFlowError`` because there is a limit on how many times you can recurse.)

{:.highlight} The AP CSA exam usually has about **4-6 recursion problems** in the MCQ section. You only need to know how to _trace recursive methods_, as in, figure out what they _return_ or _print_.
> You will NOT be asked to _write_ a recursive method on the exam.


#### Why Use Recursion?
{:.no_toc}

Recursion is most useful for solving problems where the structure of the problem
allows it to be broken into smaller, but similar problems, whose solutions can
be combined into the solution to the original problem.

For example, suppose you wanted to find out how much space a folder on your
computer uses? Well, if you knew how much space each of the files and
sub-folders in that folder used, you could add them up and get the answer.
Getting the size of a regular file is usually easy, but figuring out how much
space each sub-folder takes up is the same problem we stared with, just with a
different folder.

But that’s actually great news because we can use the same procedure to solve
this smaller problem: find the size of all the files and sub-folders in *it* and
add them up. Eventually, as we try to get the size more deeply nested folders,
eventually we'll get to folders that only contain plain files whose sizes we can
add up and return and eventually we work our way back up to give the answer to
our question about the original top-most folder.

Recursion can also be used to create **fractals**. A simple example is Sierpinski's
triangle in which you subdivide a triangle into 4 new triangles as shown below.
You can then do the some procedure with each new triangle except the center one.

![image](Figures/triangleSub.png)

Recursion can also be used to **traverse** ``String``s, arrays, and ``ArrayList``s just like a loop. In fact, any loop—also known as *iterative* code—can be
re-written using recursion. 
> However in most languages, including Java, there are limitations on how deeply code can recurse, which rules out using recursion for infinite or even very long loops.

On the other hand, recursion is more **powerful** than simple loops, especially when dealing with _branching structures_ like the file folder example. Computer scientists call such structures “**trees**” and they incredibly common in computer programs.

Recursive procedures that operate on trees often cannot be easily translated into simple loops, at least not without using some extra data structures to keep
track where you are in the tree. Thus one way to think about recursion is as “loops for trees”. If you need to loop over a simple linear structure like a ``String`` or an array, by all mean use a ``for`` loop. And if you want to navigate a 2D array a pair of nested ``for`` loops is the way to go. But if you need to traverse a tree structure, recursion should be your go to.

### Factorial Method

### Base Case

## Tracing Recursive Methods


#### 💻 In-Class Activity
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit10-Recursion/topic-10-1-recursion.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 10.1</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge** activity in pairs.

</div>

---

## ⭐️ Summary



<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Type a brief **commit message** in the box, for example: `updated Main.java`
3. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
4. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
5. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
