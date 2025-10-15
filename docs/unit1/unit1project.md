---
layout: project
title: "💻 Unit 1 Project"
projectname: "Digital Receipt"
parent: "1️⃣ Objects & Methods"
nav_order: 18
---


### Overview & Setup

🛍️ Whenever we shop or dine out, we often spend money and receive a **receipt** in return. This receipt serves as proof of our purchase. The business’s register uses specialized software that prints the receipt in a _specific format_, containing certain predetermined details.

<html>
<details>
<summary>📥 <strong class="text-green-200">PROJECT SETUP & SUBMISSION INSTRUCTIONS</strong></summary>
  
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Digital-Receipt`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Write code in this Codespace during class.

</div>

</details>
</html>

--- 


### PART A: Basic Receipt

You will start with a basic receipt that you might get after making a purchase from the high school snack bar. In a later activity you will create a more complex version that includes asking the user for information (input) about items purchased so that a custom receipt can be produced for that purchase.  

<div class="task" markdown="block">

1. Copy and paste (or retype) the following starter code into your `Main.java` file:
  ```java
  public class Main {
     public static void main(String [] args) {
        // RECEIPT PRINTOUT SECTION
        System.out.println("**************************************");
        System.out.println("*                                    *");
        System.out.println("*     High School Snack Bar          *");
        System.out.println("*                                    *");
        System.out.println("*     Drink ..........$1.50          *");                      
        System.out.println("*     Candy ..........$1.25          *");     
        System.out.println("*     Hot Dog ........$2.75          *");     
        System.out.println("*     Hamburger ......$3.50          *");     
        System.out.println("*                                    *");    
        System.out.println("**************************************");
     }
  }
  ```
2. Run the program.
3. If any **errors** occur, fix them so the program compiles and runs successfully.

</div>

<br>

<html>
<details class="highlight-block">
<summary><strong>💡 HINTS: </strong></summary>

<div markdown="block">

* A **syntax error** is a mistake in the program where the rules of the programming language are not followed. These errors are detected by the compiler. 

* A **logic error** is a mistake in the algorithm or program that causes it to behave incorrectly or unexpectedly. These errors are detected by testing the program with specific data to see if it produces the expected outcome. 

* A **run-time error** is a mistake in the program that occurs during the execution of a program and typically causes the program to terminate abnormally. 

* An **exception** is a type of run-time error that occurs as a result of an unexpected error that was not detected by the compiler. It interrupts the normal flow of the program’s execution.  

</div>
</details>
</html>

<hr>

### PART B: Enhanced Receipt

The receipt that was generated in Part A prints **String literal** values (contained in quotes) for each of the items, but that is not always the best practice. In this activity you will modify the code from before to include **variables** that will store your high school’s name and the prices of the items available at the snack bar. 

<div class="task" markdown="block">

1. Move the starter code (print statements) **down** several lines.
4. _Above_ the starter code, but still inside the `main()` method, create a **variable** to store your `highSchoolName`.
5. Initialize separate variables to store the `price` of each snack bar item.
  > Choose the most appropriate **data type** for each variable!
7. Replace the _literal_ values in `System.out.println` with **string concatenation** using your new _variables_.
  > Run the program and debug if needed. Make sure the receipt displays correctly with your variables before moving on!

</div>

<br>

<html>
<details class="highlight-block">
<summary><strong>💡 HINTS: </strong></summary>

<div markdown="block">

* The variable for high school name should be of type `String` because it will contain letters, and the variables for the cost of a drink, candy, hot dog, and hamburger should be of type `double` because each of them will contain a real number value. 

* The syntax for **declaring** a variable is `dataType variableName =  initialValue ;`.

* To correctly **concatenate** the variable name `highSchoolName` with the literal “Snack Bar” in the print statement, the syntax should be `highSchoolNameSystem.out.printIn("*     " + highSchoolName + " Snack Bar     *");`

* To correctly **concatenate** a variable name `itemName` with a real number `itemCost` in the print statement, the syntax should be `System.out.printIn("*     " + itemName + ".............$" + itemCost +"     *");`

</div>
</details>
</html>

<hr>

### PART C: Adding Randomness

In this part we are going to add some arithmetic to the program to **calculate** the subtotal, tax, and total for the purchase based on ordering multiples of each of the items. To determine the number ordered of each item, your program should generate a **random** number between 0 and 2, inclusive, which represents the number ordered of each item. Your code should also generate an order number, which is a random number between 1 and 100, inclusive. 

<div class="task" markdown="block">

4. Declare more **variables** (_before the printout section_):
   * Order number
   * Number of drinks ordered
   * Number of candies ordered
   * Number of hot dogs ordered
   * Number of hamburgers ordered
   * Tax rate
   * Subtotal
   * Total tax
   * Total
5. Use `Math.random()` to generate values for the following:
   * Assign each item a quantity **between 0 and 2** (inclusive).
   * Assign an order number **between 1 and 100** (inclusive).
6. Update the **receipt printout** to use the variables for:
   * Order number
   * Quantity, name, and cost for each item
   * Total cost for the order
7. Run and debug the program.

</div>

<br>

<html>
<details class="highlight-block">
<summary><strong>💡 HINTS: </strong></summary>

<div markdown="block">

* The variables for tax rate, subtotal, total tax, and total should be of type `double` because each will contain a real number value. The variables for order number and the number of drinks, candies, hot dogs, and hamburgers should be of type `int` because each will contain a whole number.

* To generate the order number, which should be a random number between 1 and 100, inclusive, the `Math.random()` method should be used. The general form of generating a random number between low and high is `(int)(Math.random() * (high - low + 1) + low)`. For the order number example, the code should be `(int)(Math.random() * 100 + 1)`

* If the variable `numDrinks` contains the value that is randomly generated and the variable `drinkCost` contains the value of the cost per drink, then to calculate the total cost for the drinks, you would use the expression `numDrinks * drinkCost`.

* The subtotal can be found by _adding_ each of the item totals. The value for the tax can be found by _multiplying_ the subtotal and tax rate. The order total can be found by _adding_ the subtotal and the tax. 

* The **escape sequence** for adding a new line to an output is `"\n"`. The escape sequence for adding a tab to an output is `"\t"`.
 
</div>
</details>
</html>

<hr>

### PART D: Interactive Receipt

In the previous part we created variables and assigned their values directly. This is a good practice when initially designing a program, but a more robust program includes **getting data values from a user** or another source. In this activity we will use methods from the `Scanner` class to receive input from the user.

<div class="task" markdown="block">

4. Import the `Scanner` library at the top of the file:
   ```java
   import java.util.Scanner;
   ```
6. Construct a `Scanner` object to handle keyboard input:
   ```java
   Scanner input = new Scanner(System.in);
   ```
8. Ask the user to enter:
   * Number of drinks
   * Number of candies
   * Number of hot dogs
   * Number of hamburgers
9. Store these values in the appropriate **variables** using `input.nextLine()`
10. Prompt the user to enter the **full high school name**.
11. Use `String` class methods to create initials from the first letters of each word (e.g., “Birch Wathen Lenox” → “BWL”).
12. Replace the high school name on the receipt with the generated initials.
13. Calculate the order’s total cost using the user’s input values.
14. Print the updated receipt.
15. Run and debug the program.

</div>

<br>

<html>
<details class="highlight-block">
<summary><strong>💡 HINTS: </strong></summary>

<div markdown="block">

* The placement of the statement `import java.util.Scanner;` must be before the `public class Main` header.

* The placement of the statement `Scanner input = new Scanner(System.in);` should be after the header `public static void main(String[] args)`.

* If the variable `nameOfSchool` contains the four-word name of the high school, the String method substring can be used to extract the first letter. This would yield the statement `firstLetter = nameOfSchool.substring(0, 1);`.

* To find the position of the first space in the high school’s name, the String method `indexOf `can be used. This would yield the statement `int position = nameOfSchool.indexOf(" ");`.

* Once the position of the space is located, the String method `substring` can be used to get the remaining words. This would yield the statement `remainingWords = nameOfSchool.substring(position+1);`.

</div>
</details>
</html>
<hr>

### BONUS: Design a Receipt

If you complete Parts A-D, start a blank Java program and try this bonus activity!

<div class="task" markdown="block">

1. Choose a business type for your custom receipt (e.g., store, café, personal business).
2. Write down details about the business:
   * What it sells
   * Information shown on the receipt (store name, location, date, item descriptions, prices, quantities, etc.)
3. Decide how many items your receipt will include.
4. Draw your receipt on paper to plan the layout.
5. Identify all the variables needed to store your data.
6. Assign data to the variables:
   * Some set with literal values
   * Some set from user input
7. Add creativity by including extra features:
   * Generate a receipt number using part of the business name plus a random number.
   * Apply a random “surprise” discount (1%–10%).
   * Use `String` and `Math` class methods from the Java Quick Reference.
9. Test the program to ensure it displays correctly and works as intended.

</div>

<br>

<html>
<details class="highlight-block">
<summary><strong>💡 HINTS: </strong></summary>

<div markdown="block">

* Because of the way decimal numbers are stored, the values of a `double` variable value will print many decimal places. One way to display **only two decimal places** would be to use the statement:
```java
double value = ((int)(value * 100)/100.0);
```

</div>
</details>
</html>

<br>

<!--


### PART A: Basic Receipt

You will start with a basic receipt that you might get after making a purchase from the high school snack bar. In a later activity you will create a more complex version that includes asking the user for information (input) about items purchased so that a custom receipt can be produced for that purchase.  

The program shown is `Receipt1.java`. It is an example of how a list of items that are available at the snack bar and their prices can be printed on a receipt.  

Create a new file in your integrated development environment (IDE) called `Receipt1.java`. Copy and paste the given code (or retype it) into your IDE and run it. **Correct any errors** that might occur with your program before proceeding to the next activity. You will use the code in this activity as a starting point for the code in the next activity, so be sure to save it for reuse later. 

### PART B: Enhanced Receipt

The receipt that was generated in Activity 1 prints literal values for each of the items, but that is not always the best practice. In this activity you will modify the code from Activity 1 to include variables that will store your high school’s name and the prices of the items available at the snack bar. 

In your IDE, create a new file called Receipt2.java. Open the code from Activity 1, Receipt1.java (or use the code provided below) and copy and paste it into your new file. Be sure to rename the class Receipt2 so it matches the file name.  

Modify the code to include a variable for the high school’s name and variables for the prices of each item that is available on the snack bar menu. Be sure to use the most appropriate data types to store the values. Once the variables are declared and given initial values, use string concatenation to replace the statements that print the literal values that were given in Receipt1.java with the variables declared in this part. You will need to change the parameter in System.out.println. For example, instead of printing “Drink ...... $1.50”, you should print “Drink ......” followed by the value of the variable that stores the price of the drink. You might need to abbreviate the name of your high school so it fits on one line, or use a second line to accommodate the longer high school name. Run (and debug if needed) the program to be sure it prints the information in the correct format.
 
### PART C: Adding Random

In this activity we are going to add some arithmetic to the program to calculate the subtotal, tax, and total for the purchase based on ordering multiples of each of the items. To determine the number ordered of each item, your program should generate a random number between 0 and 2, inclusive, which represents the number ordered of each item. Your code should also generate an order number, which is a random number between 1 and 100, inclusive. 

Create a new file called Receipt3.java. Open the code from Activity 2, Receipt2.java (or use the code provided below) and copy and paste it into your new file. Be sure to rename the class Receipt3 so it matches the file name.  

Add variables to your code for order number, number of drinks ordered, number of candies ordered, number of hot dogs ordered, number of hamburgers ordered, tax rate, subtotal, total tax, and total for the order.  

When the receipt is printed, be sure to include the order number and the quantity, name, and cost of each item ordered as well as the total for the order. 

### PART D: Interactive Receipt

In the previous activity we created variables and assigned their values directly. This is a good practice when initially designing a program, but a more robust program includes getting data values from a user or another source. In this activity we will use methods from the Scanner class to receive input from the user. Your teacher might use other ways to get input from a user, so refer to your teacher for directions. 

The Java API library (https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Scanner.html#method-summary) shows all constructors and methods that are available for the Scanner class. We will use one constructor and two methods from this library. 

To access the Scanner library, it must be imported into the program before the class header. The line of code to do that is import java.util.Scanner;.  

To construct an object of this class, we refer to the syntax of the constructor given in the API. 

Scanner (File source) - constructs a new Scanner that produces values scanned from the specified file. 

Using this information, we can instantiate an object from the Scanner class as follows: 

Scanner input = new Scanner(System.in);

In this line, input is the name of the object that is created from the Scanner class. The parameter System.in indicates that the source of input will be from the keyboard. 

Next, let’s look at the method signature for reading in an integer value. 

int nextInt()  - scans the next token of the input as an int. 

This method signature indicates that the name of the method is nextInt, it has an empty parameter list, and it returns an integer value. 

To use this method, we can write a prompt asking the user to enter an integer value, then the program will read that value from the keyboard, and store it into a variable called value. 

System.out.print("Enter an integer value: ");
int value = input.nextInt(); 

Let’s look at the method signature for reading in a string. 

String nextLine()  - Advances this scanner past the current line and returns the input that was skipped. 

This method signature indicates that the name of the method is nextLine, it has an empty parameter list, and it returns the string that is typed. 

To use this method, we can write a prompt asking the user to enter a name, read that value from the keyboard, and store it into a variable called name. 

System.out.print("Enter a name: ");
String name = input.nextLine(); 

Create a new file called Receipt4.java. Open the code from Activity 3, Receipt3.java (or use the code provided below) and copy and paste it into your new file. Be sure to rename the class Receipt4 so it matches the file name.  

Modify your Receipt3.java program so that instead of randomly obtaining values for the number of drinks, candies, hot dogs, and hamburgers ordered it prompts the user to enter those values and then calculates the cost of the purchase based on the inputted values.  

Also ask the user to enter the full high school name. Once that is entered, have your code create initials for the high school based on the first letters of its name. For example, if the user entered “Trevor Packer High School”, your program would create the initials “TPHS” and use that value for the high school name on the receipt. Use the appropriate String methods on the Java Quick Reference sheet to create the high school initials. For consistency, enter a four-word name for the high school (e.g., “Trevor Packer High School” instead of “Packer High School”)

### PART E: Design a Receipt

In this last activity you will use the ideas and examples from prior activities and what you have learned in this class so far to design and create your own receipt. Your Java file should be named Receipt5.java. 

Begin by identifying the type of business for which you would like to create a receipt. Do you have a small business? Do you know someone who owns a business? Talk to a family member or a friend who owns a business or look at examples from when you or someone you know went shopping. 

* Write down what you know about the business. What does it sell? What items appear on the receipt (e.g., store name and location, date, item description, price, quantity)? 

* Decide how many items you will print on your receipt. In this unit we worked with a fixed number of items, but you should make a receipt design that is more flexible.

* Draw your receipt on paper to plan the output design first. 

* Identify the variables you need to store the data for the receipt. 

* Assign data to the variables. You should have a mix of assignment statements; some variables may be set with literal values, and some should be set from user input. 

Be creative! Incorporate other concepts from this unit, especially the methods of the String and Math classes. For example: 

* Print a receipt number by combining the first 3 letters from the business name, a hyphen, and a number (e.g., Har-813 could be a receipt number for a “Hardware Store” business). 

* Use a random value to apply a “surprise” discount (e.g., a random value discount between 1% and 10%).

--> 

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [CollegeBoard](https://apclassroom.collegeboard.org/8/home).
{: .fs-2 }


