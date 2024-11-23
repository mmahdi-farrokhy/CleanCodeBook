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
