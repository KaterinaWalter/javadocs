---
layout: project
title: "💻 Unit 2 Project"
projectname: "Choose-Your-Own Adventure Game"
parent: "2️⃣ Selection & Iteration"
nav_order: 14
---


### Overview

<html>
<details>
<summary>📥 <strong class="text-green-200">PROJECT PROGRAM SETUP INSTRUCTIONS</strong></summary>
  
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Adventure-Game`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Write code in this Codespace during class.

</div>

</details>
</html>

One of the first games coded for early computers in the 1970s was called [Colossal Cave Adventure](https://en.wikipedia.org/wiki/Colossal_Cave_Adventure). It was a **text-based interactive fiction game** where you had to make your way through an elaborate cave. The program only understood one word or phrase commands like north, south, enter, take, etc. 

You can try [playing adventure](http://www.web-adventures.org/cgi-bin/webfrotz?s=Adventure) recreated online following some of the commands in this [walkthrough](https://adventuregamers.com/walkthrough/full/colossal-cave). Part of the challenge is finding the commands that the code will understand.

In a game like Adventure, `if`, `else if`, and `else` statements can be used to respond to commands from the user like `n`, `e`, `s`, `w`.

![image-small](Figures/adventure.jpg)

---

### Instructions

#### PART A: Planning

<div class="task" markdown="block">

1. 🧠 Come up with a **unique location** for your adventure.
  > Your adventure could be set anywhere... a place you are _familiar_ with (like BWL or Manhattan), a place you'd _like to visit_, or even a _fantasy/fictional_ world.
2. 📝 **PLAN & DRAW OUT YOUR MAP** on paper before coding!!! Alternatively, make a **FLOWCHART**. 

</div> 

#### PART B: Starter Code

<div class="task" markdown="block">

1. Replace the content in your `Main.java` file with the following starter code:
    ```java
    import java.util.Scanner;
    public class Main 
    {
       public static void main(String []args) 
       {
          System.out.println("Starting a new adventure...\n");
          String command = ""; // stores the user's choices
          
       } // END OF MAIN METHOD
    
       /** Method to prompt & process input for the next command
         * @param prompt to display to user, asks for specific input
         * @return user's input command as a lowercase String
       */
       public static String getCommand(String prompt) 
       {
          System.out.println("\n▶︎▶︎▶︎ " + prompt);
          Scanner scan = new Scanner(System.in);
          String command = scan.nextLine().toLowerCase();
          scan.close();
          return command;
       } // END OF METHOD
    } // END OF CLASS
    ```
2. Incorporate this starter scenario _inside_ your `main` method, after the existing statements:
    ```java
      // STEP #1: Describe the scenario scene
      System.out.println("You are at a crossroads.");
      // STEP #2: Get user command (prompt & take input)
      command = getCommand("Do you take the path on the LEFT (l) or RIGHT (r)?");
      // STEP #3: Process user command (choose a path)
      if (command.equals("l")) 
      {
         System.out.println("You turned left and continued walking.");
      }
      else if (command.equals("r")) 
      {
         System.out.println("You turned right and continued walking.");
      }
      else 
      {
         System.out.println("Bad input. Press RUN to restart!");
      }
    ```

</div> 

#### PART C: Write your own Branches

<div class="task" markdown="block">

🔀 Add more _branches_ to expand the gameplay by **nesting** conditional blocks.
> * Review [📓 2.4: Multiway Selection](https://coderina.dev/javadocs/docs/unit2/notes204.html#multiway-selection-nested-if-statements) notes on _Nested if Statements_.
> * Follow your **map/flowchart** carefully as you write code for the branches you designed.

##### EXAMPLE:
```java
if (command.equals("l")) 
{
  System.out.println("You turned left and continued walking.");
  // NEXT BRANCH...
  command = getCommand("Do you pick the pretty flower 🌺 on the path? (y/n)");
  if (command.equals("y"))
  {
    System.out.println("The flower explodes! 💣💥");
  }
  else if (command.equals("n"))
  {
    System.out.println("You keep walking down the path.");
  }
}
```

</div> 

#### 💡 TIPS:

* Don't forget to get the user's input (the **command**) before opening the next conditional block!
  ```java
  command = getCommand("prompt");
  ```
* You do not need to keep the command options as `l` and `r` every time. You can even have _more than two choices_ ( like`n`,`e`,`s`,`w`) by providing more `else if` statements for that block. 
  * Just make sure you tell the user what the options are in the **prompt**!


---

### Extensions

{:.highlight}
Turn your **text-based** adventure into a visual one with a **GUI** (Graphical User Interface)! See my `Java Swing` demo: [GitHub Swing GUI](https://github.com/katerinanavab/JavaGUI-Demo)

