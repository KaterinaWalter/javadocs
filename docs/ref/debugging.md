---
layout: default
title: "🐞 Debugging Help" 
parent: References
nav_order: 2
---

# 🐞 Debugging Help
{:.no_toc}

{: .highlight } 
Code not working? Follow the steps in the **debugging process** below _before_ asking a peer or your teacher! Fixing your own errors, no matter how small, is one of the _best_ ways to become a better coder. 

### ☕ Java Debugging Process

1. **Read the Error Message**

   * Focus on the **first error**, not the dozens that follow — one small bug can cause many.
   * Look at the **line number** and the type of error (e.g., `SyntaxError`, `NullPointerException`).

2. **Check for Missing Symbols**

   * Every line (except the last in a block) needs a **semicolon (`;`)**.
   * Make sure **parentheses `()`**, **braces `{}`**, and **brackets `[]`** are all paired.
   * Method headers must have parentheses: `public void sayHi()`

3. **Check Braces and Indentation**

   * Every `{` must have a matching `}`.
   * Indent code inside `{}` to match visually.
   * Don’t forget to close classes and methods!

4. **Check Capitalization**

   * Java is **case-sensitive**: `System` ≠ `system`, `main` ≠ `Main`
   * Classes must start with **capital letters** (`MyClass`), but variables/methods use lowercase (`myVariable`)

5. **Check Spelling and Naming**

   * Watch for typos like `Systm.out.print` instead of `System.out.print`
   * Match variable names exactly; Java won’t correct you

6. **Check Data Types and Declarations**

   * Make sure all variables are declared with a type (`int`, `String`, `double`, etc.)
   * Strings must be capitalized: `String name = "Alice";`

7. **Print for Clarity**

   * Use `System.out.println()` to check variable values
   * Print before and after key lines to isolate bugs

8. **Compile (Press RUN) Often**

   * Don't write 50 lines without compiling. Compile **frequently** so you catch errors early.

9. **Ask Yourself Questions**

   * Is this variable _initialized_?
   * Am I using the correct _data type_ for this operation?
   * Should this be inside the `main` method?

10. **If All Else Fails…**

    * Comment out blocks to isolate the issue
    * Create a minimal version of your code that still shows the bug


