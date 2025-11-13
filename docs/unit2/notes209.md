---
layout: notes
title: "📓2.9: Selection + Iteration Algorithms" 
parent: "2️⃣ Selection & Iteration"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.9](https://runestone.academy/ns/books/published/csawesome2/topic-2-9-loop-algorithms.html) 

---

## Implementing Algorithms with Selection + Iteration

In this lesson, you will learn how to implement **algorithms** that use loops to solve problems. You will learn how to use the accumulator pattern to calculate sums and averages, how to find minimum and maximum values, how to determine if a number is evenly divisible by another number, and how to count the frequency of a specific criterion. 

There are standard algorithms that use both **loops** and **selection** to: 

- compute a sum or average of a set of values
- determine a minimum or maximum value 
- identify if an integer is or is not evenly divisible by another integer 
- identify the individual digits in an integer 
- determine the frequency with which a specific criterion is met

### Accumulator Pattern for Sum/Average

The **accumulator pattern** is an algorithm that iterates through a set of values using a loop and updates an accumulator variable with those values, for example to compute a sum or average of a set of values. The accumulator pattern has 4 steps:

1. Initialize the accumulator variable before the loop.
2. Loop through the values.
3. Update the accumulator variable inside the loop.
4. Print or use the accumulated value when the loop is done.

For example, this loop calculates the sum of 1 through 100. The ``sum`` variable is the accumulator variable.

```java
    int sum = 0;
    for (int i = 1; i <= 100; i++)
    {
        sum += i;
    }
    System.out.println("The sum of 1 through 100 is " + sum);
```

The accumulator pattern can also be used to calculate the average of a set of values by adding them together and then dividing by the number of values. For example, this loop calculates the average of 10 random numbers.

```java
    int sum = 0;
    for (int i = 0; i < 10; i++)
    {
        int num = (int)(Math.random() * 100);
        sum += num;
    }
    double average = (double)sum / 10;
    System.out.println("The average of 10 random numbers is " + average);
```

### Input-Controlled Loop

Here's an example of an **input-controlled loop** that calculates the average of positive numbers using the accumulator pattern with a ``while`` loop. The number -1 is used as the **sentinel value**. The ``while`` loop will run while the user does not input -1. What would happen if you forgot step 3 (update the loop variable - get a new input)? Remember that skipping step 3 will often lead to an infinite loop! 

```java

    // 1. initialize the loop variable (get the first number)
    System.out.print("Please enter a number to average in or -1 to stop: ");
    number = scan.nextInt();

    // 2. test the loop variable (against sentinel value)
    while (number != -1) 
    {
      sum += number; // add number to sum
      count++; // count the number
      // 3. Update the loop variable (get a new number)
      System.out.print("Please enter a number to average in or -1 to stop: ");
      number = scan.nextInt();
    }
    System.out.println(count);
    // calculate average
    average = (double) sum/count;
    System.out.println("The average is " + average);
```

### Loop with if and Minimum/Maximum

A common variation of the accumulator pattern is to have an ``if`` statement inside the loop that tests each value being considered in the loop. 
> This is a very common pattern in the AP exam for FRQ #1. 

To determine the minimum or maximum value in a sequence of numbers, use a variable to store the current minimum or maximum value. Use a loop to go through the sequence of numbers and update the minimum or maximum value if you find a number that is lower or higher than the current minimum or maximum. For example, this loop chooses 10 random numbers and finds the minimum value among them.

```java

    int min = Integer.MAX_VALUE;
    for (int i = 0; i < 10; i++)
    {
        int num = (int)(Math.random() * 100);
        System.out.println(num);
        if (num < min)
        {
            min = num;
        }
    }
    System.out.println("The minimum value is " + min);
```

### Divisibility

To determine if an integer is evenly divisible by another integer, you can use the remainder operator ``%``. If you divide two numbers and there is no remainder, then the first number is evenly divisible by the second number. The remainder operator is often used to check if a number is even or odd: if ``num % 2 == 0`` is true, then ``num`` is even. But it can be used to check if any number is divisible by another. For example, 10 is evenly divisible by 5 because 10 divided by 5 is 2 with no (0) remainder. 

```java
    int num1 = 10;
    int num2 = 5;
    if (num1 % num2 == 0)
    {
        System.out.println(num1 + " is evenly divisible by " + num2);
    }
    else
    {
        System.out.println(num1 + " is not evenly divisible by " + num2);
    }
```

The selection statement above can be put in a loop to determine if a number is divisible by a range of numbers. For example, you can determine if a number is prime by checking if it is divisible by any number between 2 and n-1 (or even the square root of the number since multiples of numbers repeat after the square root). Remember that a prime number is a number that is only divisible by 1 and itself, so if you find any other divisor, the number is not prime.

### Finding Digits with / and %

We can also use division (``/``) and remainder (``%``) to find the digits of a number by dividing by 10. For example, 1234 divided by 10 is 123 with a remainder of 4. Remember that in integer
division the result truncates (cuts off) everything to the right of the decimal point, so we get the number without the last digit when we divide by 10. The remainder is the last digit of the number. You could use this algorithm to add the digits of a number, reverse the digits of a number, or check if a digit is equal to a certain number, etc.


Complete the checkDigit method below to determine if a positive number has a given single-digit number as one of its digits. 


```java
          // checkDigit checks whether a number has a given digit in it
          public static boolean checkDigit(int number, int digit) 
          {
              // 1. Use a while loop: while number is greater than 0

                 // 2. Get the last digit of number with % 10
                 // 3. if it equals the argument digit, return true
                 // 4. remove the last digit of number with / 10
            
            // if loop finishes, return false
            return false; // Digit not found
        }
        
```

The **remainder** operator has been used quite a bit on the AP CSA exam. Keep it in mind for the following uses:

- Use remainder to check for odd or even numbers. If ``num % 2 != 0`` is true, ``num``
  is odd and if ``num % 2 == 0`` is true then ``num`` is even.

- Use remainder to check if any number is evenly divisible by any
  other: If ``num1 % num2 == 0`` is true then ``num1`` is evenly divisible by
  ``num2``.

- Use it to get the last digit from an integer number: ``num % 10`` gives us the
  rightmost digit of ``num``.

- Use it to get the number of minutes left when you convert a total number of minutes to hours and minutes:

    ```java
     int totalMinutes = 345;
     int hours = totalMinutes / 60;   // Number of whole hours, i.e. 5
     int minutes = totalMinutes % 60; // Number of minutes left over, i.e. 45
    ```
- Use it whenever you have limit in the value, and you need to wrap around to
  zero if the value goes over the limit: the value of ``num % limit`` will
  always be in the range from 0 (inclusive) to ``limit`` (exclusive) as long as
  ``num`` and ``limit`` are both positive.

### Math.random() in if Statements
 
The ``Math.random()`` method returns a random number between 0.0 and 1.0.  You can use this method with ``if`` statements to simulate a coin flip or an event occuring a certain percentage of the time. For example, if you want to simulate a coin flip, you can check if the random number is less than 0.5 (halfway between 0 and 1) to simulate a 50% chance of heads or tails. (Thank you to Kate McDonnell from Cherry Creek Schools for the ideas in this section).

```java

    if (Math.random() < 0.5)
    {
        System.out.println("Heads");
    }
    else
    {
        System.out.println("Tails");
    }
```

If you want to simulate an event occuring 90% of the time, you can check the random number to see if it is less than 0.9 (90% of the way between 0 and 1):

```java

    if (Math.random() < 0.9)
    {
        // 90% of the time
        System.out.println("Event happened");
    }
    else 
    {
        // 10% of the time
        System.out.println("Event did not happen");
    }
```

### Frequency

You can use a counter variable inside a loop to determine the frequency with which a specific criteria is met.  For example, you can count the number of even numbers in a sequence of numbers. You can use a loop and increment the counter each time an even number is found like below:

```java

    int count = 0;
    for (int i = 0; i < 100; i++)
    {
        if (i % 2 == 0)
        {
            count++;
        }
    }
    System.out.println("There are " + count + " even numbers from 1 to 100.");
```
The AP exam often gives a boolean method for students to use to determine some criteria in a set of values. For example, in the following challenge, you can count the number of prime numbers from 1 to 100 given a boolean method to use ``isPrime(n)`` which returns true or false. 


#### 💻 Coding Practice
{:.no_toc}

Coding Challenge : Prime Number Finder


---

## Summary

- (AP 2.9.1) There are standard algorithms that use **loops** and **selection** to: 
    - compute a sum or average of a set of values
    - determine a minimum or maximum value 
    - identify if an integer is or is not evenly divisible by another integer 
    - identify the individual digits in an integer 
    - determine the frequency with which a specific criterion is met.

- The **accumulator** pattern is an algorithm that involves storing and updating an accumulator value within a loop, for example to compute a sum or average of a set of values.

- A common algorithm pattern is an `if` statement within a loop to test each value against a criterion, such as finding the minimum or maximum value in a sequence of numbers.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
