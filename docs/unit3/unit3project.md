---
layout: project
title: "💻 Unit 3 Project"
projectname: "Interactive Pet"
parent: "3️⃣ Class Creation"
nav_order: 11
---


### Overview

<html>
<details>
<summary>📥 <strong class="text-green-200">PROJECT SETUP & SUBMISSION INSTRUCTIONS</strong></summary>
  
<div class="setup" markdown="block">

1. Go to the `CS2 Unit 3 Project` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, **submit the link to your repository** in the `CS2 Unit 3 Project` assignment on Blackbaud.

</div>

</details>
</html>

In this project, you will practice defining and working with Java classes by creating an interactive `Pet` class. You'll demonstrate their understanding of instance variables, constructors, getter and setter methods, the toString method, and behavior methods.

---

### Part A: 

#### 1. Section
<div class="task" markdown="block">

1. Steps

</div> 

<!--
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


-->
