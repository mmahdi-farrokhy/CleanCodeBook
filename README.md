# What Is Clean Code?

Robert C. Martin states:

* Writing dirty code will lead to failure in our project.
* Writing clean code may look difficult and time consuming, but it actually speeds up the development and debugging.
* To clean a dirty code and rewrite it, requires additional effort, but it is worth it. Because it creates value.

Spending time for cleaning the code is not only cost-effective, but also the condition of professional survival.

Disturbances quickly lead to slowness and deadline violations. The only way to move quickly and meet the deadline is to keep the code clean at its highest level and at all times. So the importance of clean code can not be denied.

In this document, we learn more about the concept of clean code and try to consider its several different definitions.

## Why should my code be clean?
### Martin Fowler(British Software Engineer): Any fool can write a code that a computer understands. Good programmers write a code that humans can understand.
So the code has to be clean in order to be easy-to-understand by a humans. Which can be the author of the code or someone else.

## Is it worth to consume time to keep my code clean?
Considering the time and energy consumed for debugging a dirty code, we find it absolutely effective to clean our code.


## What happens if my code is not clean?
There is a state in software development where modifying the code leads to more dysfunctionality of the software. The code is so unrecognized that in some point it will be impossible to change it. This phase is called wading.

## What do the pioneers of software industry say about clean code?
### Bjarne Strostrup - Creator of C++
I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide.

### Grady Boosh
Clean code is simple and direct. Clean code is read like a well-written prose. Clean code never obscures the designer's intent but rather is full of crisp abstractions and straightforward lines of control.

### Dove Thomas
Clean code can be read, and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. It provides one way rather than many ways to do one task. It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone.

### Michael Feathers
Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you are led back to where you are, sitting in appreciation of the code someone left for you. Code written by someone who cared deeply about the craft.

## In brief clean code has these features:
- It's minimal.
- It has comprehensive tests.
- It is efficient and easy to maintain.
- It can be read like a newspaper.
- Every module is made for one and only one purpose.
---

# Meaningful Names
Name of the classes, methods and variables must have some characteristics to make it easier to understand the code. In this chapter we will learn a few of them.

1. **The name should be intension-revealing.**
    - What is the purposebehind this element of code? (method, object, variable, ...)
    - What was the author of the code thinking about and what was he looking for?
    - What is this module supposed to do?

The name should be chosen in such way that no comments or documents are required to answer these questions. Name of the element should answer all the big questions. If a name needs comment, it doesn’t reveal its intent.

```
    // BAD CODE
    private void changeColorOfText()
```
```
    // BAD CODE
    private void changeColorOfTextOnMouseClick()
```

2. **The name should not give dis-information.** Using names that may mislead the reader, will take more time to understand the code. Or even take his mind towards another concept with a similar name, or hidethe meaning of the code. Some possible situations:
    - Using the name hp as the acronym of hypotenuse.
    - Using the name accountList while its type is not List. Instead we can use accountGroup, bunchOfAccountsor even accounts.
    - Using long similar names like XYZControllerForEfficientHandlingOfStrings and XYZControllerForEfficientStorageOfStrings.
    - Using the letters O and l along side with the numbers 0 and 1.

3. **The name should make meaningful distinctions.** We should pick a name for code elements in such way to differthem easily, no matter how much they are alike. Some examples:
    - The names in a scope, or method arguments should not be singularletterand similar, like they are only to satisfy the compiler. The reader should not be forced to read the algorithm to understand the intention of the variable.
    - Three classes named Product, ProductInfoand ProductData. What is the intention behind each one?
    - Using words like variable, methodor classfor naming.

4. **The name should be pronounceable.**
    Maybe using bthymdh as a variable name look like a good decision as the acronym of birthdayYearMonthDayHour in the first look. But every time you want to read this part of code you will be forced to wait for a few seconds so you could understand and read this variable.

5. **The name should be searchable.** Using singular letter variables or constant numbers will make it difficult to find them in code with the eye quickly.
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

10. **Use one word for one concept.** If you once used insert as a keyword for adding a new element to a collection, use *insert* for any situation you add a new element to a collection. If you once used getas a keyword for getting an existing element in a collection, use *get* for any situation you get an existing element in a collection.

11. **Use solution domain names.** It is better to use computer science terms, design patterns and algorithms names instead of using the problem domain names all the time. Using problem domain names requires the presence of a domain expert.

12. **But if you have access to the domain expert, choosing problem domain names can be a good decision.**

13. **Add meaningful context.** Some names may be ambiguous by themselves. Adding a meaningful context can clear the naming.

14. **Don’t add gratuitous context.**
Some prefixes or postfixes only add more complexity. Imagine adding per at the beginning of every property name in class Person. By writing per the IDE suggests too many different objects and it confuses us.

## In brief meaningful name has these features:
- The name is not dis-informative.
- The name doesn’t remind the reader of another concept.
- The name doesn’t need comments to be understood.
- The name reveals the author’s intentions.
- The names of the classes, objects and variables are nouns or noun phrases.
- The names of the methods are verbs or verb phrases.
- The names of the enums are adjectives.
- The names of the packages are nouns or noun phrases.
- There is a semantic continuity between name of the class with its methods and properties.
- There is no similar and duplicated names.
- The more the distance of a variable’s declaration and usage, the longer its name.
- The more publica method, the more general its task and the shorter its name.
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
Each method should implement one and only one task. While the implementation itself may involve calling multiple methods that execute a solitary job. If a method takes the responsibility of more than one task, it does the task either wrong or dirty. One way to know if the method does more than one job is to name the method as it reflects the sequence of events within it. If the method name contains or, and or then it does multiple tasks. Each proposition between these words is to be implemented as a separate method.

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
There is a saying about this rule: **Extract till you drop.** We break a method down to smaller ones to reduce complexity and code duplication. This aligns with rule #1.

### *Rule #3: The Fewer The Arguments, The Cleaner The Method*
Having too many arguments for a method confuses the reader and makes it more difficult to understand the method’s behavior. It also complicates writing coverable tests. Best kind of method has no arguments. Although we can have method arguments, but it's not recommended to have more than with 3 arguments. One way to decrease the number of arguments is to gather similar ones in a single object.

```
    // BAD CODE
    private Circle createCircle(double x, double y, double radius)
```

```
    // GOOD CODE
    private Circle createCircle(Point center, double radius)
```

### *Rule #4: No Boolean/Null/Enum Arguments*
Introducing boolean/nullable/enum arguments introduces branching logic, leading to multiple distinct paths depending on argument's value. So it violates rule #1. Because more than one task is being implemented in one method. We should check its value before calling the method and implement different methods for its different values.

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
---
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
If a section of code is unclear, don't comment it, Refactor it.

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
If the method is part of an standard library and can not be refactored by the programmer, it’s a good idea to make it clear.

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
    public void testWithReallyBigFile() {
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
---
# Objects And Data Structures
True abstraction hides data types and applies operations on them as public methods. 

```
    // BAD CODE: Reveals details of private fields
    public interface Vehicle {
        double getFuelTankCapacityInGallons();
        double getGallonsOfGasoline();
    }
```

```
    // GOOD CODE: Uses private fields for a public behavior
    public interface Vehicle {
        double getPercentFuelRemaining();
    }
```

**Anemic Classes:** *Data structures* that contain data, but no methods. They're used only to move data between classes and layers. That's why we call them *Data Transfer Object(DTO)*.

**Domain Classes:** Hide data through abstraction, offering methods that implement *Business logics* and define software behavior.

In the code below, there are three anemic classes and a client class that uses them. Adding a new business logic or new data structures affects only the client.
```
    // PROCEDURAL CODE
    public class Square {
        public Point topLeft;
        public double side;
    }

    public class Rectangle {
        public Point topLeft;
        public double height;
        public double width;
    }

    public class Circle {
        public Point center;
        public double radius;
    }

    public class Geometry {
        public final double PI = 3.141592653589793;

        public double area(Shape shape) throws NoSuchShapeException {
            if (shape instanceof Square) {
                Square s = (Square) shape;
                return s.side * s.side;
            } else if (shape instanceof Rectangle) {
                Rectangle r = (Rectangle) shape;
                return r.height * r.width;
            } else if (shape instanceof Circle) {
                Circle c = (Circle) shape;
                return PI * c.radius * c.radius;
            }

            throw new NoSuchShapeException();
        }
    }
```

Here is an Object-Oriented code with *interface*s that define *business rule*s. Adding a new business logic means defining a new abstract method in the interface and implementing it in concrete classes. So, adding new business logic affects all of them. Adding a new concrete class affects the client class.
```
    // OBJECT ORIENTED CODE
    public interface Shape {
        public double area();
    }

    public class Square implements Shape {
        public Point topLeft;
        public double side;

        @Override
        public double area() {
            return side * side;
        }
    }

    public class Rectangle implements Shape {
        public Point topLeft;
        public double height;
        public double width;

        @Override
        public double area() {
            return height * width;
        }
    }

    public class Circle implements Shape {
        public final double PI = 3.141592653589793;
        public Point center;
        public double radius;

        @Override
        public double area() {
            return PI * radius * radius;
        }
    }

    ///////////////////////////////

    public class ShapeService {
        Shape shape;

        public ShapeService(Shape shape) {
            this.shape = shape;
        }

        public static double calculateArea() {
            return shape.area();
        }
    }

    public class ClientClass {
        private ShapeType shapeType;
        private ShapeService shapeService;

        public ClientClass(ShapeType shapeType) {
            this.shapeType = shapeType;
            this.shapeService = ShapeServiceFactory.createShapeService(shapeType);
        }

        public double calculateArea() {
            return shapeService.calculateArea();
        }
    }

    public class ShapeServiceFactory {
        private ShapeServiceFactory() {
        }

        public static ShapeService createShapeService(ShapeType shapeType) {
            Shape shape;

            switch (shapeType) {
                case ShapeType.Square:
                    shape = new Square();
                    break;

                case ShapeType.Rectangle:
                    shape = new Rectangle();
                    break;

                case ShapeType.Circle:
                    shape = new Circle();
                    break;
            }

            return new ShapeService(shape);
        }
    }

    public enum ShapeType {
        Rectangle,
        Circle,
        Square
    }
```

## Procedural Form vs. Object-Oriented Form
- Procedural code:
   - Adding new data structures requires modification of all methods in client class.
   - Suitable for systems likely to see more future behaviors and business logics.

- Object-Oriented Code:
   - Adding new methods(business rules) demands modification of all concrete classes.
   - Suitable for systems likely to introduce new data structures.

## The Law Of Demeter
This law is stated in different words:
- A unit should have limited knowledge about others.
- Only units next to the current unit should be familiar with its details.
- Each unit should only talk to its neighbors.
- Don't talk to strangers.

Simply put, *Law of Demeter* states that method **m()** in class **C** should only be able to call methods from:
- Class **C**
- An object from return type of method **m()**
- Parameters of method **m()**
- A field object of class **C**

This implies that sequential getter methods violate this principle.

```
    // BAD CODE
    public class Airport {
        private AirportCode code;
        private Coordinate coordinate;
        private Location location;
        private String name;

        public AirportCode getCode() {
            return code;
        }

        public Coordinate getCoordinate() {
            return coordinate;
        }

        public Location getLocation() {
            return location;
        }

        public String getName() {
            return name;
        }
    }
    ///////////////////////////
    public class Flight {
        private Airport originAirport;
        private Airport destinationAirport;

        public Airport getOriginAirport() {
            return originAirport;
        }

        public Airport getDestinationAirport() {
            return destinationAirport;
        }
    }
    ///////////////////////////
    public class Order {
        private Flight flight;

        public Flight getFlight() {
            return flight;
        }
    }
    ///////////////////////////
    public class Client {
        private void operation() {
            Order order = new Order();
            String originAirportName = order.getFlight().getOriginAirport().getName();
        }
    }
```

```
    // GOOD CODE
    public class Airport {
        private AirportCode code;
        private Coordinate coordinate;
        private Location location;
        private String name;

        public AirportCode getCode() {
            return code;
        }

        public Coordinate getCoordinate() {
            return coordinate;
        }

        public Location getLocation() {
            return location;
        }

        public String getName() {
            return name;
        }
    }
    ///////////////////////////
    public class Flight {
        private Airport originAirport;
        private Airport destinationAirport;

        public Airport getOriginAirport() {
            return originAirport;
        }

        public Airport getDestinationAirport() {
            return destinationAirport;
        }

        public String getOriginAirportName() {
            return originAirport.getName();
        }
    }
    ///////////////////////////
    public class Order {
        private Flight flight;

        public Flight getFlight() {
            return flight;
        }

        public String getOriginAirportName() {
            return flight.getOriginAirportName();
        }
    }
    ///////////////////////////
    public class Client {
        private void operation() {
            Order order = new Order();
            String originAirportName = order.getOriginAirportName();
        }
    }
```

## Data Transfer Object - DTO
Data structures are defined as classes with private variables and no methods. These structures facilitate the transfer of data between different system layers. For instance, we extract data from a database, place it into a DTO, and transmit it to other layers such as domain or application. Consider simulating a flight with two classes: Flight, contains logic methods and FlightDTO that only moves data. Our goal is to distinctly separate business classes from data classes.

## In brief we could say:
When we refer to data structures, we mean anemic classes with only getters and setters. These classes store and move data, and are also recognized as DTOs. On the other side, domain classes execute business logic and lack setter methods. We can only access their data without changing it.
---
# Boundaries
Third Party Code is a code that we use, but did not write. Like calling an API. This could lead to multiple issues:
1. We must learn to work with the API.
      - **Solution - Learning Tests:** When dealing with third-party code, it's important to understand it. However, this can be a challenging task. There are a few ways to go about it.
          - Reading the API's documentation, which can be time-consuming.
          - Search online, especially if we're using a well-known library or framework.
          - The most effective method: Create learning tests. This approach is quick, cost-effective, and secure.

2. We might depend too heavily on APIs in our program. If the API's main functionality changes, we'll be forced to change our code to adapt with the new version; and this violates *Open-Close Pronciple* from *S.O.L.I.D*.
3. This API might offer more functions than we actually require.

      - **Solution To Problems #2 And #3: Wrapper Module:** Once we've got familiar with the third-party code, we can start incorporating it into our program. There are two approaches for that:
          - The less effective approach: Using the third-party code directly all over our program, which can lead to problems when we update API's version. We'd be forced to modify anywhere we used the API.
          - The better approach: Creating a wrapper class that interacts as an interface between the API and our codebase. This approach separates the API from the rest of the software. Any issues or conflicts resulting from different API versions will be isolated in the wrapper class.

### *Benefits Of Using A Wrapper Class*
- **Controlled API Usage:** We can restrict the API's functions to necessary.
- **Reduced Dependency:** By relying on the wrapper class, we decrease dependency to the API.
- **Easy Adaptation:** Changing the API or library becomes simpler since modifications are only limited to the wrapper class.
- **Enhanced Testing:** While we can't directly test the API itself, we can test the wrapper class effectively.
- **Forward Planning:** Imagine a scenario where the API isn't available yet. We could create other modules of our program, test and use them without problems. This is because our dependency on the API is limited to just one class. This grants us and the API development team more flexibility and time for development.
---
# Unit Tests
### *Test Driven Development*: It's really important to write effective unit tests to ensure code quality, reliability, and maintainability. They provide us early detection of bugs during development. It's also so imortant to keep test code as clean as production code. Clean tests satisfy the need for documentation, as they describe the logical flow of a class or even the entire software.

## The Three Laws of TDD
Test Driven Development (TDD) is a practice where tests are written before the actual code. TDD is guided by three laws:
1. Begin by writing a failing test that cannot be compiled.
2. Write just enough production code to make the failing test compile and pass logically.
3. Develop the production code only to pass the test, without exceeding the requirements.

Here we consider some points about TDD.

### *Test Driven Development*
- Tests Must Be Clean.
    - As the product evolves, tests evolve too.
    - Dirty tests lead to challenges during modification.
    - An unclear test requires additional time and effort to cover new product code.
    - Test code holds equal importance as product code.
    - Test code is not a second class citizen; it demands careful thought, design and attention.

- Tests Give You Power.
    - Unit tests empower your code by enhancing its flexibility, maintainability, and reusability.
    - When you have tests in place, you gain the confidence to modify your code without fear.
    - In the absence of tests, any modification becomes a potential bug.
    - Regardless of your architecture's flexibility or the elegance of your design, the absence of tests leads to hesitation in making changes.

- One Test – One Assertion: This rule might look a little much too strict, but it has a great benefit. Tests with only one assertion are fast and easy to understand. But we can be more flexible and change the rule into another:
    - One Test - The Minimum Number Of Assertions Possible.

- One Test – One Concept
    - Best practice is to test a single concept inside each test method.
    - Avoid lengthy test methods that test multiple subjects consecutively.
    - This principle aligns with the earlier guideline and results to  minimal assertions in test methods.

- Tests Should Be F.I.R.S.T: Clean tests also follow five other guidelines:
    - Fast: Test should run quickly.
    - Independent: Test should not depend on other tests.
    - Repeatable: Test should produce the same result every time.
    - Self-Validating: Test should have a boolean output.
    - Timely: Test should be written before production code, not after it.
---
# Class Organization
Each language has its own standard structure for the classes. In Java (and similar languages), we write a class in this order:
1. Public static final variables
2. Public static variables
3. Public variables
4. Private static variables
5. Private fields
6. Public methods
7. Private methods which are called by public methods

## Encapsulation
Tests dominate the code. If a test inside the package needs to call a method or access a field, that method or field should be declared as protectedor to be accessible all over the package. Yet, decreasing the encapsulation level should be the last thing to consider.

## Minimal Classes
The first rule for classes is that they should be small as possible. Just like the methods, being minimal is the primary principle for designing the classes.

## Class Name
- Name of a class should clearly reflect its responsibilities and purpose.
- The chosen name can even serve as a prior indicator of its potential size. If we couldn’t find a proper short name for the class, it is most likely going to be large.
- An ambiguous class name informs us that this class has multiple responsibilities. For instance, a class containing Processor, Manager.

## Single Responsibility Principle (SRP): A class should have one and only one reason to change.
This is one of the most important principles of object oriented design and S.O.L.I.D principles. One way to comply with this principle is to write too many small classes, instead of a few large classes. Every small class isolates a single responsibility.

### Signs of violating SRP
- Too many instance variables in a class
- Too many public methods with implicit interface
- Methods using different instances
- Private methods that do extra work.

### Solution
Use collaborator class that handles minor tasks that are done in the main class.

## Class Cohesion
There should be a conceptual relation between fileds and methods of a class with its purpose. There are some rules to acheive this:
- Classes should have the minimum number of instance variables (fields).
- Break large methods into smaller ones.
- Move the methods that share a mutual logic to another class.

## Organization For Modification
Every change in software triggers a chain reaction, influencing subsequent changes. Since change is inevitable in software development, it's essential to design a structure for the system that minimizes the change. In an ideal system, adding a new feature means expanding the existing system, not modifying the current codebase. This approach streamlines development and helps maintain software stability. To isolate the changes, we should use *Dependency Inversion Principle (DIP)* from *S.O.L.I.D*.

## Dependency Inversion Principle (DIP)
Dependency should be defined on abstraction, not concretion. We should not be aware of implementation details, and this lack of awareness can help us in replacement stage. Client class does not determine the required type, it only determines the required rule and system will provide the specific type.

### *Signs of violating DIP*
- High level class depends on low level class.
- Vendor Lock-In: A package is developed using a framework and can not be used with other technologies.

### *Solution*
Adapter design pattern.

## Summary
- There is conceptual continuity between fields and methods in a clean class.
- If a method is too large, it should be divided into multiple small methods, each one implementing one task.
- Some of these small methods interact with some objects from a specific class. They should be moved to that class.
- It is very usual to add new features or fix bugs in a software. The legacy code has to change. It comes with a risk. The change on one module would disrupt the functionality of others. To avoid this issue, we use interfaces or abstract classes, and place the new codes inside a new class that extends the parent class or interface.
---
# Systems
A software system is composed of distinct sub-systems and layers, each handling specific tasks. Crucially, these sub-systems must be isolated from one another. The client method constructs the required objects for the system and hands them over to the application layer, which utilizes them.

## Dependency Injection and Inversion of Control (IoC)
A potent technique to segregate creation from application logic is dependency injection. This involves employing inversion of control (IoC) in dependencies management. With dependency inversion, we can delegate secondary responsibilities from one object to others that are specifically designed for it, leading to compliance of *SRP*. In the dependency handling concept, an object should not bear the responsibility of instantiating its own dependencies. Instead, this task must be entrusted to a different, influential mechanism that inverts the control. Typically, this powerful mechanism is either the main routine or a single purpose container, considering the setup as a global concern.


```
    public interface MessageSender {
        public void sendMessage(String recipient, String message);
    }
```

```
    public class EmailSender implements MessageSender {
        @Override
        public void sendMessage(String recipient, String message) {
            System.out.println("Sending email to " + recipient + ": " + message);
        }
    }
```

```
    public class SMSSender implements MessageSender{
        @Override
        public void sendMessage(String recipient, String message) {
            System.out.println("Sending SMS to " + recipient + ": " + message);
        }
    }
```

```
    public class User {
        private String contactInfo;

        public User(String contactInfo) {
            this.contactInfo = contactInfo;
        }

        public String getContactInfo() {
            return contactInfo;
        }
    }
```

```
    // BAD CODE
    public class UserController {
        private String communicationMethod;
        private EmailSender emailSender = new EmailSender();
        private SMSSender smsSender = new SMSSender();

        public UserController(String communicationMethod) {
            this.communicationMethod = communicationMethod;
            emailSender = new EmailSender();
            smsSender = new SMSSender();
        }

        public void registerUser(User user) {
            if (communicationMethod.equals("Email")) {
                emailSender.sendMessage(user.getContactInfo(),
                    "Welcome to our platform!");
            }
            else if (communicationMethod.equals("SMS")) {
                smsSender.sendMessage(user.getContactInfo(),
                    "Welcome to our platform!");
            }            
        }
    }
```

```
    // GOOD CODE
    public class UserController {
        private MessageSender messageSender;

        public UserController(MessageSender messageSender) {
            this.messageSender = messageSender;
        }

        public void registerUser(User user) {
            messageSender.sendMessage(user.getContactInfo(),
                    "Welcome to our platform!");
        }
    }
```

```
    public class Client {
        public static void main(String[] args) {
            UserController userController = new UserController(new EmailSender());
            User user = new User("user@email.com");
            userController.registerUser(user);
        }
    }
```

## Domain-Specific Languages (DSL)
DSLs are customized languages tailored to a particular domain, enabling concise and precise communication between developers and stakeholders. DSLs allow for the expression of complex business rules and concepts in such way that is easily understood by non-technical experts. Creating a DSL, creates a software development environment more aligned with the problem space. Incorporating DSLs in the development process enhances collaboration and reduces the gap between technical and non-technical team members. It enables domain experts to actively participate in shaping the software's behavior, resulting in more accurate implementations. DSLs should be expressive, focused on the domain's core concepts, and designed to provide clarity and maintainability. Utilizing DSLs empowers teams to build systems that are closely aligned with the domain's intricacies and requirements.

## Conclusion
Systems must also be clean. An aggressive architecture obscures domain logic and affects agility. When the domain’s logic becomes ambiguous, the quality will suffer, because it will be easier for the bugs to hide and it will be more difficult to implement the customer's requirements.
If agility is compromised, productivity will suffer and the benefits of TDD will be lost. At all levels of abstraction, the goal must be clear. Regardless of whether you are designing a system or individual modules, never forget to use the simplest things that work for your needs.

---

# Clarity
An important point for having clean code is to have clarity in the design. Based on Beck’s opinion, design is simple if it,
1. passes all tests.
2. has no duplication.
3. is expressive.
4. has minimal classes and methods.

## Passes all tests.
We start by designing a system that works as expected. However, even if a system functions well theoretically, it's all in vain if we can't easily verify it. A testable system should be thoroughly tested and consistently pass those tests. 
Increasing the number of tests gets us closer to testable components, leading to the required confidence for building better system design. It also opens up the opportunity to apply principles like S.O.L.I.D and design patterns to our code.

### Refactoring
To change code's structure, without changing its logic. Afterward, we run all the tests again to ensure our modification did not disrupt the logic.

## No Duplication
Duplication means additional effort, additional risk and unnecessary complexity. Different forms of code duplication are:
- Lines with exact same code
- Lines with similar codes, but different parameters

```
    // BAD CODE
    public void client() {
        JButton button1 = new JButton("1");
        button1.setBounds( 0 , 0 , 50 , 60 );
        button1.setBackground(Color. _white_ );
        button1.setBorder((BorderFactory. _createLineBorder_ (Color. _white_ )));

        JButton button2 = new JButton("2");
        button2.setBounds( 100 , 100 , 50 , 60 );
        button2.setBackground(Color. white );
        button2.setBorder((BorderFactory. createLineBorder (Color. white )));

        JButton button3 = new JButton("3");
        button3.setBounds( 200 , 200 , 50 , 60 );
        button3.setBackground(Color. _white_ );
        button3.setBorder((BorderFactory. _createLineBorder_ (Color. _white_ )));
    }
```

```
    // GOOD CODE
    private static final int BUTTON_WIDTH = 50;
    private static final int BUTTON_HEIGHT = 60;
    private static final Color BORDER_COLOR = Color.white;
    private static final Color BACK_COLOR = Color.white;

    public static void client() {
        JButton button1 = createButton("1", 0, 0);
        JButton button2 = createButton("2", 100, 100);
        JButton button3 = createButton("3", 200, 200);
    }

    private static JButton createButton(String text, int x, int y) {
        JButton button = new JButton(text);
        button.setBounds(x, y, BUTTON_WIDTH, BUTTON_HEIGHT);
        button.setBackground(BACK_COLOR);
        button.setBorder(BorderFactory.createLineBorder(BORDER_COLOR));
        return button;
    }
```

## Expressive
The major cost of a software project is attributed to its long-term maintenance. To minimize the cost and potential modifications issues, we have to understand system’s behavior and functionality. The code should clearly reflect the author's intentions. A well-written code can be easily understood, leadihng to significant reductioin of onboarding time and maintenance cost.

## Minimal Classes And Methods
The goal is to keep the system compact at its highest level. So we need minimum number of small classes and methods.
