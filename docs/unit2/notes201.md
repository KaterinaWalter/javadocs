---
layout: notes
title: "📓2.1: Selection & Repetition Algorithms" 
parent: "2️⃣ Selection & Iteration"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.1]() 

---

Every algorithm consists of a sequence of steps. Up until now, we have been writing code one line at a time in sequence which then gets executed by the computer in that sequential order by default. However, we can create more complex algorithms that do not follow the default sequential order. In this unit, we will learn to branch the code into different paths or repeat a block of code.

The building blocks of algorithms are **sequencing**, **selection**, and **repetition**. Algorithms can contain selection, through decision making, and repetition, via looping. In fact, it's been proven that all algorithms for problems that can be solved on a computer can be constructed by using just these three control structures: sequence, selection, and repetition as seen below.

![Sequence, Selection, and Repetition](Figures/algorithms.png)

## Selection

Selection is the process of making a choice based on a true or false decision. In programming, selection (also called branching) occurs when a choice of how the execution of an algorithm will proceed is based on a true or false decision. An algorithm may take different paths based on certain conditions, often using true/false logic.

<div class="task" markdown="block">

**Check Your Understanding**

Identify all the selection (decision or branching) phrases in the following algorithm:

Morning routine:
1. Wake up.
2. Snooze for 5 more minutes.
3. Check your phone and the weather.
4. **If** there is a text from your friend, answer it.
5. Brush teeth and shower.
6. **If** it’s cold, wear a sweater.
7. Check **if** you have homework due. If so, pack it in your bag.
8. Put on your sunglasses **if** it's sunny.
9. Leave for school or work.

Selections are made based on a true or false decision. Look for the word "if" to identify selections.

</div>

## Repetition

Repetition is when a process repeats itself until a desired outcome is reached. In programming, repetition is achieved through loops. A **loop** allows an algorithm to repeat certain actions until a specified condition is met. Another term commonly used for repetition is **iteration**.

<div class="task" markdown="block">

**Check Your Understanding**

Identify all the repetition phrases in the following algorithm:

Morning routine 2:
1. Wake up.
2. Snooze for 5 more minutes. **Keep** waking up and snoozing for the next 15 minutes.
3. If there is a text from your friend, answer it. Do this for **all** of your texts.
4. Brush teeth and shower.
5. If it’s cold, wear a sweater.
6. Check if you have homework due. If so, pack it in your bag.
7. **Repeat** packing items until your bag is ready.
8. Leave for school or work.

Repetition is when a process repeats itself until a desired outcome is reached. Look for the words "repeat," "all," or "keep" to identify repetition.

</div>

## Algorithms with Pseudocode and Flowcharts

For complex problems, it is important to plan your solution before writing code. **Pseudocode** is a simplified, informal way of describing the steps in an algorithm in a human language like English but following the sequence, selection, and repetition structure of a programming language. **Flowcharts** are diagrams that represent the steps in an algorithm. Selection is usually represented as a triangle in a flowchart, and arrows are used to show repetition. Both pseudocode and flowcharts are tools that help you plan your algorithm before writing code.

![Flowchart for Selection branching the code into two paths](Figures/Condition-two.png)

The order in which sequencing, selection, and repetition are used contributes to the outcome of the algorithm.

<div class="task" markdown="block">

**Check Your Understanding**

Put the steps of the algorithm below in order. Then decide what the outcome will be based on the order of the steps and the conditions.

Pseudocode: Buying a birthday gift for your friend

1. Initialize `total` amount of money.
2. Repeat while still money in `total`:
   - If `total` more than $25, buy a gift card and subtract 25 from `total`.
   - If `total` more than $10, buy a small cake and subtract 10 from `total`.
   - If `total` more than $5, buy some candy and subtract 5 from `total`.
   - If `total` more than $1, buy a card and subtract 1 from `total`.
   - Otherwise, give them the change.

</div>

<div class="task" markdown="block">

**Check Your Understanding**

Given the pseudocode above:

- If you have $16 to spend, what will be the outcome?
  - You will buy a gift card, a small cake, some candy, and a card.
  - You will buy a small cake and some candy.
  - ✅ You will buy a small cake, some candy, and a card.
  - You will buy 2 cakes and some candy.

- If you have $22 to spend, what will be the outcome?
  - You will give them a gift card, a small cake, some candy, and a card.
  - You will give them a small cake and some candy.
  - You will give them a small cake, some candy, and a card.
  - ✅ You will give them 2 cakes, a card, and $1.

</div>

## Coding Challenge: Algorithms

<div class="task" markdown="block">

In this group activity, create an algorithm for a common problem: **choosing a snack**! Write pseudocode that includes both selection and repetition.

For example:
- If there is no chocolate, keep searching for another snack.
- If you're thirsty, consider the drinks in the fridge.
- You may want to consider every item in the fridge or leftover Halloween candy before deciding.

Be creative!

</div>

## Summary

- The building blocks of algorithms include sequencing, selection, and repetition.
- Algorithms can contain selection, through decision making, and repetition, via looping.
- Selection occurs when a choice of how the execution of an algorithm will proceed is based on a true or false decision.
- Repetition is when a process repeats itself until a desired outcome is reached.
- The order in which sequencing, selection, and repetition are used contributes to the outcome of the algorithm.

---

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

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
