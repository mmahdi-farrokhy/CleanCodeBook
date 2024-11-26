# What Is Clean Code?

Robert C. Martin states:

* Writing dirty codewill lead to failurein our project.
* Writing clean code may look difficult and time consuming, but it actually speeds upthe development and debugging.
* To clean a dirty code and rewrite it, requires additional effort, but it is worth it. Because it creates value.

Spending time for cleaning the code is not only cost-effective, but also the condition of professional survival.

Disturbances quickly lead to slowness and deadline violations. The only way to move quickly and meet the deadline is to keep the code clean at its highest level and at all times. So the importance of clean code can not be denied.

In this document, we learn more about the concept of clean code and try to consider its
several different definitions.

## Why should my code be clean?
### Martin Fowler(British Software Engineer): Any fool can write a code that a computer understands. Good programmers write a code that humans can understand.
So the code has to be clean in order to be easy-to-understand by a humans. Which can be the author of the code or someone else.

## Is it worth to consume time to keep my code clean?
Considering the time and energy consumed for debugging a dirty code, we find it absolutely effective to clean our code.


## What happens if my code is not clean?
There is a state in software development where modifying the code leads to more dysfunctionality of the software. The code is so unrecognized that in some point it will be impossible to change it. This phase is called _wading_.

## What do the pioneers of Software Industry say about clean code?
### Bjarne Strostrup - Creator of C++
I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide.

### Grady Boosh
Clean code is simple and direct.Clean code is read like a well-written prose. Clean code never obscures the designer's intent but rather is full of crisp abstractions and straightforward lines of control.

## Dove Thomas
Clean code can be read, and enhancedby a developer other than its original author. It has unitand acceptancetests. It has meaningfulnames. It provides onewayrather than many ways for doing onething. It has minimaldependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literatesince depending on the language, not all necessary information can be expressed clearly in code alone.

## Michael Feathers
Clean code always looks like it was written by someone who cares.There isnothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you are led back to where you are, sitting in appreciation of the code someone left for you—code written by someone who careddeeply about the craft.

## In brief clean code has these features:
- It is short and minimal.
- It has comprehensive tests.
- It is efficient and easy to maintain and develop.
- Reading it is like reading a newspaper.
- Naming is the way that the reader understands the intent of the author by
    reading the name of modules(class, method, variable, ...).
- Every module is made for one and only one purpose.
---

# Meaningful Names
Name of the classes, methods and variables must have some characteristics to make it easier to understand the code. In this chapter we will learn a few of them.

1. **The name should be intension-revealing.**
    - What is the purposebehind this element of code? (method, object, variable, ...)
    - What was the author of the code thinking about and what was he looking for?
    - What is this module supposed to do?

The name should be chosen in a way that no comments or documents are required to answer these questions. Name of the element should answer all the big questions. If a name needs comment, it doesn’t reveal its intent.

```
private void changeColorOfText()
```
```
private void changeColorOfTextOnMouseClick()
```

2. **The name should not give dis-information.** Using names that may mislead the reader, will take more time to understand the code. Or even take his mind towards another concept with a similar name, or hidethe meaning of the code. Some possible situations:
    - Using the name hpas the acronym of hypotenuse.
    - Using the name accountListwhile its type is not List. Instead we can use accountGroup, bunchOfAccountsor even accounts.
    - Using long similar names like XYZControllerForEfficientHandlingOfStrings and XYZControllerForEfficientStorageOfStrings.
    - Using the letters Oand lalong side with the numbers 0 and 1.

3. **The name should make meaningful distinctions.** We should pick a name for code elements in a way to differthem easily, no matter how much they are alike. Some examples:
    - The names in a scope, or method arguments should not be singularletterand similar, like they are only to satisfy the compiler. The reader should not be forced to read the algorithm to understand the intention of the variable.
    - Three classes named Product, ProductInfoand ProductData. What is the intention behind each one?
    - Using words like variable, methodor classfor naming.

4. **The name should be pronounceable.**
    Maybe using bthymdhas a variable name look like a good decision as the acronym of birthdayYearMonthDayHourin the first look. But every time you want to read this part of code you will be forced to wait for a few seconds so you could understand and read this variable.

5. **The name should be searchable.** Using singular letter variables or constant numbers in the code will make it difficult to find them in code with the eye quickly.
    - Variable names should be more than 3 characters long.
    - Constant numbers should be stored in a finalvariable and use the variable where needed.

6. **The name should avoid encoding.** The code is complex by itself. So we don’t need extra complexity caused by encoded names. Suh as:
    - Names with member prefix: m_is a sign of class members used in old IDEs. Today this kind of names are obsolete.
    - Hungarian notation: It was used in the old IDEs where there was a distance between object declaration and its usage; and the programmer wanted to remember the object type.

7. **The name of interfacesand their implementor classes.** Don’t use *I* at the beginning of an interfacename. Instead write a *C* at the beginning or *Impl* at the end of its implementor classes.

8. **The name of classes:**
    - It should be noun or noun phrase like Customer, Account and AddressParser.
    - It should not contain general words like Manager, Processor,Data or Infothat indicate a big variety of tasks and do not reveal the true functionality of the class.

9. **The name of methods:**
    - It should be verb or verb phrase like deletePage, calculateDistance and postPayment.
    - Settermethods should start with set.
    - Gettermethods should start with get.
    - Booleanmethodsshould start with is.

10. **Use one word for one concept.** If you once used insertas a keyword for adding a new element to a collection, use *insert* for any situation you add a new element to a collection. If you once used getas a keyword for getting an existing element in a collection, use *get* for any situation you get an existing element in a collection.

11. **Use solution domain names.** It is better to use computer science terms, design patterns and algorithms names instead of using the problem domain names all the time. Using problem domain names requires the presence of a domain expert.

12. **But if you have access to the domain expert, choosing problem domain names can be a good decision.**

13. **Add meaningful context.** Some names may be ambiguous by themselves. Adding a meaningful context can clear the naming.

14. **Don’t add gratuitous context.**
    Some prefixes or postfixes only add more complexity. Imagine adding perat the beginning of every property name in class Person. By writing perthe IDE suggests too many different objects and it confuses us.

## In brief meaningful name has these features:
- The name is not dis-informative.
- The name doesn’t remind the reader of anotherconcept.
- The name doesn’t need commentsto be understood.
- The name reveals the author’s intentions.
- The names of the classes, objects and variables are nounsor nounphrases.
- The names of the methods are verbsor verbphrases.
- The names of the enums are adjectives.
- The names of the packages are nounsor nounphrases.
- There is a semanticcontinuitybetween name of the class with its methods and properties.
- There is no similarand duplicatednames.
- The more the distanceof a variable’s declaration and usage, the longerits name.
- The more publica method, the more generalits task and the shorterits name.
---
# Methods
Methods play an important role in code; they define a class's behavior. You might have encountered methods
- with more than 100 lines
- managing multiple of tasks
- dealing with excessive arguments
- returning values calculated from mathematical operations.

Such methods are listed as dirty code. However, there are some points to consider that makes methods way too clean.

## Rules of clean methods:
### *Rule #1: One Method – One Task*
Each method should implement one and only one task. While the implementation itself may involve calling multiple methods that execute a solitary job. If a method takes the responsibility of more than one task, it does the task either wrong or dirty. One way to know if the method does more than one job is to name the method as it reflects the sequence of events within it. If the method name contains or, andor thenit does multiple tasks. Each proposition between these words is to be implemented as a separate method.

```
    // BAD CODE
    public void getUserInputAndSaveInDatabase() {
        // Code To Get User Input
        // Code To Save In Database
    }
```

```
    // GOOD CODE
    public void SaveInDatabase() {
        SaveUserInputInDataBase(getUserInput());
    }

    public UserInput getUserInput() {
        // Code To Get And Return User Input
    }

    public void SaveUserInputInDataBase(UserInput userInput) {
        // Code To Save User Input In Database
    }
```

### *Rule #2: Method Is Small As Possible.*
There is a saying about this rule: **Extract till you drop.** We break a method down to smaller methods to reduce complexity and code duplication. This aligns with rule #1.

### *Rule #3: The Fewer The Arguments, The Cleaner The Method*
Having too many arguments for a method confuses the reader and makes it more difficult to understand the method’s behavior. It also complicates writing coverable tests. Best kind of method has no arguments. Although we can have method arguments, but it's not recommended to havw more than with 3 arguments. One way to decrease the number of arguments is to gather similar ones in a single object.

```
    // BAD CODE
    private Circle createCircle(double x, double y, double radius)
```

```
    // GOOD CODE
    private Circle createCircle(Point center, double radius)
```

### *Rule #4: No Boolean/Null/Enum Arguments*
Introducing boolean/nullable/enum arguments introduces branching logic, leading to multiple distinct paths depending on argument's value. So it violates rule #1. Because more than one task is being implemented in one method. We should check its value before calling the method and implement differene methods for its differene values.

```
    // BAD CODE
    private void mainMethod() {
        someMethod(someCondition);
    }

    private void someMethod(boolean condition) {
        if (condition)
            doThis();
        else
            doThat();
    }
```

```
    // GOOD CODE
    private void mainMethod() {
        if (someCondition)
            doSomething();
        else
            doSomethingElse();
    }

    private void doSomething() {
    }

    private void doSomethingElse() {
    }
```

### *Rule #5: Argument Should Not Be Changed In The Method Body.*
Changing the argument's value makes it unpredictable and difficult for us to trace the code in debugging.

### *Rule #6: No switch-case To Decide What To Do Or How To Do It.*
In many situations we check the value of an object in a switch statement and decide what operation to perform in different cases. This is doing multiple tasks and violates rule #1. Instead, we create an abstract class with abstract methods and some concrete classes that extend it. Each child class is related to one case. Then we create an object of the abstract class and initialize it in cases by concrete classes and call the abstract method on the object.

```
    // BAD CODE
    public Shape createShape(ShapeType shapeType) {
        switch(shapeType)
        {
            case "chapter06.Rectangle":
                return side * side;
            case "chapter06.Circle":
                return 3.14 * radius * radius;
            case "Triangle":
                return (base * height) / 2;
        }
    }
```

```
    // GOOD CODE
    public interface Shape {
        public double area();
    }

    public class Rectangle implements Shape {
        private double side;

        @Override
        public double area() {
            return side * side;
        }
    }

    public class Circle implements Shape {
        private double radius;

        @Override
        public double area() {
            return radius * radius * 3.14;
        }
    }

    public class Triangle implements Shape {
        private double base;
        private double height;

        @Override
        public double area() {
            return base * height / 2;
        }
    }

    ////////////////////////////////////////////////////

    public Shape createShape(ShapeType shapeType) {
        switch (shapeType) {
            case "Rectangle":
                return new Rectangle();
            case "Circle":
                return new Circle();
            case "Triangle":
                return new Triangle();
        }
    }

    public double calculateShapeAre() {
        Shape shape = createShape(shapeType);
        return shape.area();
    }
```

### *Rule #7: Separate Commands From Queries.*
Imagine a method that sends a request or executes a command. But at the same time it executes query and returns data. It is both *setter* and *getter*.

```
    // BAD CODE
    public boolean saveInDatabase(Data data) {
        // Code To Save Data In Database
        // Code To Check If The Data Was Successfully Saved In Database And Return The Result
    }
```

```
    // GOOD CODE
    public void saveInDatabase(Data data) {
        // Code To Save Data In Database
    }

    public boolean isDataSaved(Data data) {
        // Code To Check If The Data Was Successfully Saved In Database And Return The Result
    }
```

### *Rule #8: Avoid Returning Null.*
Sometimes we return null if an operation couldn’t be done or a variable has unexpected value. It increases the risk of NullPointerException which is a difficult exception to handle. The first alternative approach is to return an object with default values. The best one is to define customized exceptions and throw them instead of returning null.

```
    // BAD CODE
    public User createNewUser() {
        User newUser;

        if (isPasswordConfirmed)
            newUser = new User();
        else
            newUser = null;

        return newUser;
    }
```

```
    // GOOD CODE
    public User createNewUser() {
        User newUser;

        if (isPasswordConfirmed)
            newUser = new User();
        else
            throw new PasswordNotConfirmedException();

        return newUser;
    }
```

### *Rule #9: One Entry – One Exit*
Using return or break statements in the middle of method makes it dirty. The best practice is to have only one return in the method.

```
    // BAD CODE
    public Value getSomeValue() {
        if (condition)
            return value1;
        else
            return value2;
    }
```

```
    // GOOD CODE
    public Value getSomeValue() {
        Value result;
        if (condition)
            result = value1;
        else
            result = value2;

        return result;
    }
```

### *Rule #10: Blocking & Indentation*
The depth of blocks should not pass three levels.

```
    // BAD CODE
    public void doSomething() {
        if (condition) {
            for (int i = 0; i < n; i++) {
                for (int j = 0; j < m; j++) {
                    // Commands
                }
            }
        }
    }
```

```
    // GOOD CODE
    public void doSomething() {
        if (condition) {
            for (int i = 0; i < n; i++) {
                executeCommands();
            }
        }
    }
```

### *Rule #11: try-catch Extraction*
If try-catch is required, it should be isolated as the implementation of a method. The method begins with try and ends with catch or finally. In the try scope we call a method that might throw a certain exception.

```
    // BAD CODE
    private String openDocumentButtonPushed() {
        // Codes That Open And Read The Document
        try {
            // Code With Possibility Of An Exception
        } catch (SomeException exception) {
            showMessageBox(“An error occurred while opening the document”);
        }

        // Code To Process Data Read From The Document
    }
```

```
    // GOOD CODE
    private void openDocumentButtonPushed() {
        try {
            openDocument();
        } catch (NullPointerException | IOException e) {
            showMessageBox(“An error occurred while opening the file”);
        }
    }

    public void openDocument(String filePath) throws IOException, NullPointerException {
        // Implementation
    }
```
# Comments
### Are comments really that bad?
- Comments are often unrecognized components of code that can confuse readers and lead to misunderstanding.
- Comments are used to cover for bad code, instead of fixing it.
- If code requires comments, it means, it can not express the author's intention clearly.
- Comments are often not updated along with the code.
- Codes get refactored, but comments don’t.
- Comments might become detached from the code they explain.

Although I'd like to say _“don’t use comments”_ , it's not always practical. Because sometimes they can lead to value. So we should consider some points about them.

### *Point 1: Comments Don’t Repay For Bad Code.*
If a section of code is unclear, don't comment it. Refactor it.

### *Point 2: Express Yourself In Code.*
Code is the most effective way to transfer the author's message to fellow developers.

```
    // BAD CODE
    // Check to see if the employee is eligible for full benefits
    if((employees.flags && HOURLY_FLAG) && (employees.age >65))
```

```
    // GOOD CODE
    if(employees.isEligibleForFullBenefits())
```

### *Point 3: Legal Comments Are Acceptable.*
Copyright comments could be used.

```
    // ACCEPTABLE
    // Copyright (C) 2003, 2004, 2005 by Object Mentor, Inc. All Rights reserved.
    // Release under the terms of the GNU General Public License 2 or later
```

### *Point 4: Informative Comments For Abstractions Are Acceptable.*
It’s helpful to use a comment for abstract methods or classes.

```
    // ACCEPTABLE
    // Returns an instance of the Responder being tested
    protected abstract Responder responderInstance();
```

### *Point 5: Explanation Of An Ambiguous Code By Comment Is Valuable.*
Explaining the reason behind a particular code decision.

```
    // ACCEPTABLE
    // This is our best attempt to get a race condition
    // by creating large number of threads.
    for(int i = 0; i< 25000;i++)
    {
        WidgetBuilderThread widgetBuilderThread = new WidgetBuilderThread(widgetBuilder, text, parent, failFlag);
        Thread thread = new Thread(widgetBuilderThread);
        thread.start();
    }
```

### *Point 6: Clarification Of An Ambiguous Code By Comment Is Valuable.*
If the method is part of an standard library and can not be refactored by the programmer, it’s a good idea to make it clerar.

```
    // ACCEPTABLE
    assertTrue(a.compareTo(b) != 0); // a != b
    assertTrue(ab.compareTo(ba) == 0); // ab == ba
```

### *Point 7: Offering Warnings Through Comments Is Useful.*
Notify others if certain code sections might be time-consuming to run.

```
    // ACCEPTABLE
    // Don't run unless you have time to kill
    public void _testWithReallyBigFile() {
        writeLinesToFile(10000000);
        response.setBody(testFile);
        response.readyToSend(this);
        String responseString = output.toString();
        assertSubString("Content-Length: 10000000", responseString);
        assertTrue(bytesSent > 10000000);
    }
```

### *Point 8: TODO Comments Are Beneficial.*
They serve as reminders for future tasks.

```
    // ACCEPTABLE
    //TODO: These method should be deleted
    protected VersionInfo makeVersion() throws Exception {
        return null;
    }
```

### *Point 9: Marker Comments Are Problematic.*
While they might seem helpful in the first look, they can become misplaced during code changes and cause confusion.

```
    // NOT ACCEPTABLE
    private void doSomething(){
        method1();
        method2();

        // Getting The Result
        method3();
        method4();

        // Sorting The Result
        method5();
        method6();
    }
```

### *Point 10: Redundant Comments Are Bad.*
A comment for a simple method is redundant and needs to be deleted.

### *Point 11: Misleading Comments Are Bad.*
Sometimes we use words and phrases in our comments that do not send the correct message to the reader. It may lead to misunderstanding of the code’s intention.

### *Point 12: Obsessive Comments Are Bad.*
Like commenting every argument in a method.

### *Point 13: Journal Comments Are Outdated.*
Recording every code change with dates in comments is outdated, as source control software now handles this.

### *Point 14: Author’s Name Is Not Acceptable*
IDEs and version control systems provide information on code changes. Commenting the author's name is redundant.

### *Point 15: Commented Codes*
It’s one of the dirtiest codes to write. A commented code confuses the reader.
- If this code is redundant why is it commented and not deleted?
- Is this code going to be used later? If so, why is there no TODO comments around it?
- What happens if I delete this code?
