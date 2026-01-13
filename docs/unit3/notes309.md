---
layout: notes
title: "📓3.9: THIS Keyword" 
parent: "3️⃣ Class Creation"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.9](https://runestone.academy/ns/books/published/csawesome2/topic-3-9-this.html) 

---

## The `this` Keyword

{:.highlight}
The keyword ``this`` can be used in a class to refer to the **current calling object**.

Within a class' instance method or a constructor, the keyword ``this`` acts as a special variable that holds a **reference to the current object** — the specific object whose method or constructor is being _called_.

{:.warning}
The ``this`` variable can only be used in instance methods and constructors. **Static methods** cannot refer to `this` or instance variables because they are called with the _classname_, not an object, so there is no `this` object.

### `this.instanceVariable`

The keyword `this` is sometimes used by programmers to _distinguish between variables_. Programmers can give the parameter variables the same names as the instance variables and this can distinguish them and avoid a naming conflict. 

For example, both the **instance variable** and the **parameter variable** are called `name` in the `Person` class below:

```java
// instance variables
private String name;

// constructor
public Person(String name) {
    // Set this object's instance variable name to the parameter variable name
    this.name = name;
}
```
> Here, ``this.variable`` is a way to indicate that we are referring to the **instance variables** of this object instead of **a local variable**.

### `this` as an Argument

The ``this`` variable can be used anywhere you would use an object variable! You can even _pass it to another method_ as an **argument**. 

**💬 DISCUSS:** Consider the classes below, ``Pay`` and ``Overtime``. What does this code print out? Trace through the code. Notice how the `this` `Pay` object is passed to the `Overtime` class constructor.

```java
public class Pay {
       private double pay;

       public Pay(double p) {
           pay = p;
       }

       public double getPay() {
           return pay;
       }

       public void calculatePayWithOvertime() {
           // this Pay object is passed to the Overtime constructor
           Overtime ot = new Overtime(this);
           pay = ot.getOvertimePay();
       }

       public static void main(String[] args) {
           Pay myPay = new Pay(100.0);
           myPay.calculatePayWithOvertime();
           System.out.println(myPay.getPay());
       }
}
```
```java
public class Overtime {
       private double payWithOvertime;

       public Overtime(Pay p) {
           payWithOvertime = p.getPay() * 1.5;
       }

       public double getOvertimePay() {
           return payWithOvertime;
       }
}
```
> The ``Pay`` class declares an ``Overtime`` object and passes in ``this`` (the current ``Pay`` object) to its constructor which computes the overtime with respect to that ``Pay`` object.

Here is an image that shows how ``this``, ``myPay`` and ``p`` all refer to the **same object in memory**:

![image](Figures/thisTrace.png)

#### 💻 Coding Activity: Bank Account
{:.no_toc}

Many people keep their money in a bank account. The bank may keep track of the account holder's name, the acount balance which is the amount of money in the account, and assign an account number to each account. At the bank or an ATM (automatic teller machine) or on a phone app, the account holder can deposit (add) or withdraw (subtract) an amount from their account. 

🏧 Here's a ATM video that breaks down _the steps to use an ATM_ to withdraw money from a bank acount. Phone apps like Venmo and Paypal connect to your bank account or credit card to send and get money from businesses or friends.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YpD1tJK9vIA?si=OP_UCtUtsBmsp2-f" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome2/topic-3-9-this.html"><button type="button" name="button" class="btn">CSAwesome Topic 3.9</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Coding Challenge: Bank Account** activity in pairs.

</div>

---

## ⭐️ Summary

- (AP 3.9.A.1) Within an instance method or a constructor, the keyword ``this`` acts as a special variable that holds a reference to the current object—the object whose method or constructor is being called.

- ``this.instanceVariable`` can be used to distinguish between this object's instance variables and local parameter variables that may have the same variable names.

- (AP 3.9.A.2) The keyword ``this`` can be used to pass the current object as an argument in a method call.

- (AP 3.9.A.3) Class methods do not have a ``this`` reference.



---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
