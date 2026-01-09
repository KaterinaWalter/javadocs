---
layout: project
title: "💻 Unit 3 Project"
projectname: "Travel Booking System"
parent: "3️⃣ Class Creation"
nav_order: 11
---


### Overview & Setup

✈️ You are a software engineer for a high-end travel agency, *"Wanderlust Solutions."* Your task is to create a system that tracks custom travel bookings, using **object-oriented class design**. 

While the theme is travel, you have the creative freedom to decide what *kind* of travel item you are modeling, for example:
* All-Inclusive Vacation Packages 🏖️
* Luxury Cruise 🚢
* Backpacking Adventure 🎒
* Disney Trip 👑
* Teen Tour 🧳
* Space Tourism Ticket 🚀

<html>
<details>
<summary>📥 <strong class="text-green-200">PROJECT PROGRAM SETUP INSTRUCTIONS</strong></summary>
  
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Travel-Booking-System`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Write code in this Codespace during class.

</div>

</details>
</html>

---

### PART A: Define the Travel Class

<div class="task" markdown="block">

Leave the Main class alone for now and create another class to represent a **travel booking object**. Define this class as described below. All variables should be declared as `private` and all methods as `public`. 

#### CLASS NAME: 
{:.no_toc}
* Choose a name that fits your specific trip theme (e.g., `VacationPackage`, `TeenTour`, etc.)

#### STATIC VARIABLE:
{:.no_toc}
* `processingFeePerDay` = 45 (this represents a flat daily fee for the travel agency, feel free to adjust the value to reflect a higher or lower standard of service).

#### INSTANCE VARIABLES:
{:.no_toc}
Declare at least **six** private instance variables.

  1. `travelerName` (String)
  2. `destination` (String)
  3. `durationInDays` (int)
  4. Your choice of **boolean** (e.g., `isInternational`)
  5. Your choice of **double** (e.g., `starRating`, `luggageWeight`)
  6. `totalPackageCost` (int) → *this will be a calculated field*

#### INSTANCE METHODS:
{:.no_toc}

  1. **Default Constructor:** Sets generic default values for all fields (_instance variables_).
  2. **Parameterized Constructor:** Accepts arguments for the first four variables (use the same variable names for the parameters as the instance variables).
    * **Calculation:** The `totalPackageCost` should be set by multiplying the `durationInDays` by the static `processingFeePerDay`.
  3. **Accessor Methods:** "Getters" for every field.
  4. **Mutator Methods:** "Setters" for every field.
    * **The Cost Mutator:** The mutator for `totalPackageCost` must accept `durationInDays` as a parameter and recalculate the cost using the static `processingFeePerDay`.
  5. **toString():** Returns a formatted, multi-line string that represents the object's state. Use creative labels like `--- TRIP ITINERARY FOR [Name] ---`.

</div> 

#### Example String Representation:
{:.no_toc}

```java
public String toString() {
  String itinerary = "--------------------------------------------\n" +
           "         ✨⛺️ GLAMPING ITINERARY ⛺️✨        \n" +
           "--------------------------------------------\n" +
           "GUEST NAME:       " + travelerName + "\n" +
           "DESTINATION:      " + destination + "\n" +
           "STAY DURATION:    " + durationInDays + " Nights\n" +
           "LUXURY RATING:    " + tentLuxuryRating + " / 5.0 Stars\n" +
           "--------------------------------------------\n" +
           "TOTAL BOOKING:    $" + totalPackageCost + ".00\n" +
           "--------------------------------------------\n" +
           "  Thank you for choosing Wanderlust Solutions! \n";
  return itinerary;  
}
```

--- 

### PART B: Test the System

<div class="task" markdown="block">

Complete the `Main` class to test your travel object:

1. **Static Method for Creating Objects:**
Write a `static` method below the `main` method (but inside the `Main` class) to create objects.
  * **Method Name:** `bookTrip`
  * **Return Type:** An object whose "data type" is the name of the custom class you wrote in Part A (e.g., `VacationPackage`, `TeenTour`, etc.)
  * **Parameter:** It must accept a `Scanner` object from the main method.
  * **Method Body:**
    1. **Object Creation:** Start by creating a blank travel object using the **default constructor**.
    2. Ask the user for all the details (Name, Destination, Duration, and your custom variables).
       > _Do **NOT** ask for the total package cost, since this is a calculated value._
    4. Call all of your **mutator methods** to _update_ the object’s values based on what the user typed.
    5. _Return_ the completed **travel object** back to the `main` method.

2. **Main Interaction Loop:**
In the `main` method, set up the user interface:

  * Create a `Scanner` object called `input`.
  * Use a `while` loop controlled by a `boolean` flag variable called `bookTrip`.

🔁 _Inside the loop:_
  1. Call your static `bookTravel()` method to create a new travel object.
  2. Display the object's details using the `toString()` method.
  3. Ask the user: `"Would you like to log another trip? (Y/N)"`.
  4. Use a `Scanner` method to accept user input, and store their response in a variable called `response`. 
  5. Use an `if-else` conditional block to test their response, and set the `boolean` flag to either run the loop again, or exit.

</div> 

---

#### Creative Requirements Checklist:

* [ ] Does my class use a unique travel-related name?
* [ ] Did I include a `double` and a `boolean` as instance variables?
* [ ] Does my `toString()` look like an actual travel receipt or itinerary?
* [ ] Did I remember to use `this.variableName` in my parameterized constructor?

{:.highlight}
You can also turn your text-based interactive version into a visual one with a **GUI** (Graphical User Interface)! See my `Java Swing` demo: [GitHub Swing GUI](https://github.com/katerinanavab/JavaGUI-Demo) and make sure to copy your completed class file in the repository too. 

<!--

## OLD PROJECT: Creature Class

### Overview 

In this project, you will practice defining and working with Java classes by creating an interactive `Creature` class. You'll demonstrate understanding of:
* instance variables
* constructors
* getter and setter methods
* the toString method
* behavior methods

### Instructions 

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

-->
