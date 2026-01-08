---
layout: project
title: "💻 Unit 3 Project"
projectname: "Creature Class"
parent: "3️⃣ Class Creation"
nav_order: 11
---


### Overview & Setup

In this project, you will practice defining and working with Java classes by creating an interactive `Creature` class. You'll demonstrate understanding of:
* instance variables
* constructors
* getter and setter methods
* the toString method
* behavior methods

<html>
<details>
<summary>📥 <strong class="text-green-200">PROJECT SETUP & SUBMISSION INSTRUCTIONS</strong></summary>
  
<div class="setup" markdown="block">



</div>

</details>
</html>

---

### Part A: 

#### 1. Section
<div class="task" markdown="block">

1. Steps

</div> 


### Instructions & Requirements

<div class="task" markdown="block">

1. **Create the Class**
  - [ ] Create a new _file_ named `Creature.java`.
  - [ ] Define a `public` _class_ named `Creature`.
2. **Declare Instance Variables**
  - [ ] `private String species;` (_required_)
  - [ ] At least one other `String` variable
  - [ ] At least one `int` variable 
  - [ ] At least one `double` variable
  - [ ] At least one `boolean` variable
  > Make sure all instance variables are `private`!
3. **Write Two Constructors**
  - [ ] Write a _no-argument_ constructor that sets _default_ values for all instance variables.
  - [ ] Write a _parameterized_ constructor that initializes all instance variables based on _arguments_ passed to it.
  > Make sure to use the `this` keyword!
4. **Write Accessor/Getter Methods**
  - [ ] Write a `public` _get_ method for each instance variable to allow external access to their values.
  > Make sure your `return` type matches the instance variable!
5. **Write Mutator/Setter Methods**
  - [ ] Write a `public` _set_ method for each instance variable to allow external modification of their values.
  > Make sure your method accepts a _parameter_ of the same data type as the instance variable!
6. **Write a toString Method**
  - [ ] Override the `toString()` method to `return` a _String representation_ of the object that includes all instance variables.
7. **Write Behavior Methods**
  - [ ] Add at least TWO additional behavior methods that define _actions_ the creature can perform. These methods can use the instance variables and return results, perform tasks, or indirectly affect the state of instance variables.
  > _Examples:_
  > - `public void grow(int years)` - Increases the age of the creature by a given number of years.
  > - `public String speak()` - Returns a string like "The Dragon lets out a mighty roar!" based on the species.
8. **Write a Test Class**
  - [ ] Create a separate `Main.java` class with a `main()` method that demonstrates **all features** of your Creature class.
  > _In the main method:_
  > - Create at least two Creature **objects** using different constructors.
  > - Use the **getter** and **setter** methods to access and modify instance variables.
  > - Call the **behavior methods** and display their outputs.
  > - **Print** the objects using the toString method.

</div> 

### Extension

#### Make it Interactive!
After ensuring your test class works as intended, update it to allow for _user interaction_:
1. Import the `Scanner` class at the top of your program.
2. Set up a `Scanner` object instance in the `main` method.
3. Prompt the user to input values for each instance variable, store those values in variables, then pass those variables into your _parameterized constructor_.

Allow the user to run your behavior methods as they choose, demonstrating the _output_ or _effects_ in a way that makes sense:
```java
while (!userInput.equals("quit") {
  System.out.println("What would you like to do with your creature - speak or grow?");
  userInput = scan.nextLine();
  if (userInput.equals("speak")) {
    System.out.println(creature.speak());
  }
  else if (userInput.equals("grow")) {
    System.out.println("Enter a whole number: ");
    int years = scan.nextInt();
    creature.grow(years);
    System.out.println("Your creature is now " + creature.getAge() + " years old!");
  }
  else {
    System.out.println("That command is not recognized, try again.");
  }
}
```
> Different types of methods (`void` or _returns_ data, if it needs _input_ or not) will require different handling as seen in the example above.


{:.highlight}
You can also turn your text-based interactive version into a visual one with a **GUI** (Graphical User Interface)! See my `Java Swing` demo: [GitHub Swing GUI](https://github.com/katerinanavab/JavaGUI-Demo) and make sure to copy your completed `Creature.java` file in the repository too. 

<!--

For this problem, you will be creating a class and using the Main class to test your output.  Leave the Main class alone for now and create another class called CollegeStudent.  This class should go below the closing curly brace for the Main class.  Define this class as described below.  All variables should be declared as private and all methods as public.  

Class Name:	CollegeStudent (do not put public on the class line)

Static Variable:	costPerHour = 125 (this should be an int)

Instance Variables:	
name – String (in the format lastName, firstName – Example: Smith, John)
courseTitle – String
courseNumber – String
credits – int
courseFee – int

Instance Methods: 	
A default constructor
A constructor that accepts arguments for name, courseTitle, courseNumber, and credits (use the same variable name for the parameter as the instance variables).  Course fee should be set by multiplying the credits and the costPerHour.
accessor methods for each of the class fields
mutator methods for each of the class fields – the mutator for courseFee should use the credits as a parameter and calculate the fee using the costPerHour (use credits as the parameter variable)
toString() a method to display the fields of an instance of the class in an easy to read format (preferable on separate lines).  Use this when referencing the instance variables.

Complete the Main class to test your CollegeStudent class as follows:
Create a static method below the main method to get user inputs, this method should:
Have one parameter to pass in the scanner that will be created in the main method (Scanner scan).  This is necessary because this method will need to get user input, but the scanner will be out of scope from the main method unless you send it in through a parameter.
Create a CollegeStudent object using the default constructor.
Prompt the user for the inputs – First Name, Last Name (as one String), course title, course number, and number of credits.  It should not ask for the course fee.
Use the mutator methods to set those values for the object.  Remember that the mutator for the course fee needs the credits.
Return the CollegeStudent with the values given by the user.
The main method should use a while loop to accept input until the user indicates there are no more inputs.  Use a boolean flag to control the loop.
In the loop, call the method to get the input for the College Student and then display the CollegeStudent object nicely formatted.  Then prompt the user if they would like to input information for another student (Y for yes and N for no) and set the boolean flag for the loop accordingly.



