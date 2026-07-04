# CST 338 - Week 1 Notes

## Introduction

This week's material focused on the foundations of Java and Object-Oriented Programming (OOP). The main topics included Java syntax, classes and objects, encapsulation, access modifiers, methods, constructors, UML diagrams, and writing clean code using Google's Java Style Guide.

---

# Classes

## What it is

A class is a blueprint for creating objects. It defines what data an object stores (fields) and what actions it can perform (methods).

## What it does

A class groups related variables and methods together into one reusable structure.

## Why it's useful

- Organizes code.
- Allows objects to share the same design.
- Makes programs easier to maintain.
- Supports Object-Oriented Programming.

### Example

```java
public class Student {

    private String name;
    private int age;

}
```

---

# Objects

## What it is

An object is an instance of a class.

Think of a class as the blueprint for a house.

An object is an actual house built from that blueprint.

## What it does

Stores its own values while sharing the methods defined in the class.

## Why it's useful

- Represents real-world things.
- Allows multiple copies of the same class.
- Each object can contain different data.

### Example

```java
Student studentOne = new Student();
Student studentTwo = new Student();
```

Both objects are Students, but each stores different information.

---

# Class Members

## What it is

Everything inside a class is called a class member.

There are two main types:

- Fields (member variables)
- Methods

## What it does

Fields store information.

Methods perform actions.

## Why it's useful

Keeping related data and behavior together makes code easier to understand.

---

# Fields (Member Variables)

## What it is

A field is a variable that belongs to a class.

## What it does

Stores information about an object.

## Why it's useful

Every object gets its own copy of the fields.

### Example

```java
private String name;
private int age;
private double gpa;
```

Every Student object has its own name, age, and GPA.

---

# Methods

## What it is

A method is a function that belongs to a class.

## What it does

Performs an action or returns information.

## Why it's useful

- Reuses code.
- Breaks large problems into smaller pieces.
- Makes programs easier to read.

### Example

```java
public void study() {
    System.out.println("Studying...");
}
```

---

# Functions vs Methods

## What it is

A function is reusable code.

A method is a function that belongs to an object.

## What it does

Methods allow objects to perform actions.

## Why it's useful

Understanding this difference helps explain Object-Oriented Programming.

Example:

```java
student.study();
```

The object is calling one of its own methods.

---

# Dot Notation

## What it is

The period (`.`) used to access an object's methods and variables.

## What it does

Allows one object to interact with another.

## Why it's useful

Without dot notation, objects couldn't communicate.

### Example

```java
student.getName();

student.setAge(21);

student.study();
```

---

# Java Data Types

Java is **statically typed**.

This means every variable must declare its type before it can store data.

Example:

```java
int age = 21;

double gpa = 3.85;

String name = "Sawyer";
```

---

# Primitive Data Types

## What it is

Primitive data types are Java's simplest built-in data types.

## What it does

Stores simple values.

## Why it's useful

- Uses less memory.
- Faster than objects.
- Easy to work with.

Common primitive types

| Type | Example |
|------|---------|
| byte | 10 |
| short | 25 |
| int | 42 |
| long | 1000000L |
| float | 3.14f |
| double | 3.14159 |
| boolean | true |
| char | 'A' |

---

# Reference Types

## What it is

Reference types are objects.

Instead of storing the actual data, they store a reference (address) to the object.

## What it does

Allows Java to create more complex data structures.

## Why it's useful

Reference types have:

- Methods
- Variables
- State

Examples

```java
String

Scanner

ArrayList

Student
```

---

# Primitive vs Reference Types

## Primitive Types

- Store actual values.
- Faster.
- Fixed size.
- Cannot call methods.

Example

```java
int number = 10;
```

---

## Reference Types

- Store object references.
- Can call methods.
- Can hold multiple variables.
- Can contain other objects.

Example

```java
String name = "Sawyer";

System.out.println(name.length());
```

Notice that Strings have methods because they are objects.

---

# Constructors

## What it is

A constructor is a special method that creates an object.

It has the same name as the class.

## What it does

Initializes an object's fields.

## Why it's useful

Allows objects to start with useful values.

### Example

```java
public Student(String name, int age) {

    this.name = name;
    this.age = age;

}
```

Creating an object

```java
Student s1 = new Student("Sawyer", 23);
```

---

# The `this` Keyword

## What it is

`this` refers to the current object.

## What it does

Distinguishes instance variables from constructor parameters.

## Why it's useful

Without `this`, Java may not know which variable you're referring to.

Example

```java
public Student(String name){

    this.name = name;

}
```

The first `name` is the field.

The second `name` is the constructor parameter.

---

# Encapsulation

## What it is

Encapsulation is one of the four main principles of Object-Oriented Programming.

It means hiding an object's data and controlling access through methods.

## What it does

Protects an object's internal state.

Instead of letting other classes change data directly, they must use getters and setters.

## Why it's useful

- Prevents invalid data.
- Protects objects.
- Makes debugging easier.
- Makes programs more reliable.

Example

```java
private String name;
```

Instead of

```java
student.name = "Sawyer";
```

You use

```java
student.setName("Sawyer");
```

---

# Getters

## What it is

A getter returns the value of a private field.

## What it does

Allows other classes to read data safely.

## Why it's useful

Keeps fields private while still allowing access.

Example

```java
public String getName(){

    return name;

}
```

---

# Setters

## What it is

A setter changes the value of a private field.

## What it does

Allows objects to update their own data.

## Why it's useful

Allows validation before changing data.

Example

```java
public void setAge(int age){

    if(age >= 0){

        this.age = age;

    }

}
```

Notice that the setter prevents negative ages.

---

# Access Modifiers

## What it is

Keywords that determine who can access fields and methods.

## What it does

Controls visibility.

## Why it's useful

Protects data and controls how classes interact.

### `private`

Only the same class can access it.

Example

```java
private String password;
```

---

### `public`

Accessible from anywhere.

Example

```java
public void printInfo(){
}
```

---

### `protected`

Accessible within the same package and subclasses.

---

### Package-Private

No keyword.

Only classes in the same package can access it.

Example

```java
int count;
```

---

# Why Encapsulation Uses `private`

If every field were public, anyone could change an object's data.

Example

```java
student.setAge(-500);
```

A good setter prevents invalid values.

```java
public void setAge(int age){

    if(age >= 0){

        this.age = age;

    }

}
```

This is one of the biggest reasons encapsulation exists.

---

# UML (Unified Modeling Language)

## What it is

A UML Class Diagram is a visual blueprint of a Java class.

It shows:

- Fields
- Constructors
- Methods
- Relationships between classes

## What it does

Helps developers design classes before writing code.

## Why it's useful

- Makes planning easier.
- Helps teams communicate.
- Reduces mistakes before coding.

### Example

```text
-----------------------------
|         Student           |
-----------------------------
- name : String
- age : int
-----------------------------
+ Student(String, int)
+ getName() : String
+ setName(String) : void
-----------------------------
```

### UML Symbols

| Symbol | Meaning |
|--------|---------|
| + | public |
| - | private |
| # | protected |
| ~ | package-private |

---

# Java Style Guide

## What it is

A collection of rules that make Java code consistent and easy to read.

The course follows Google's Java Style Guide.

## What it does

Provides standards for naming, formatting, spacing, and comments.

## Why it's useful

- Makes code easier to read.
- Makes teamwork easier.
- Keeps projects organized.

### Basic Rules

- Class names use **PascalCase**.
- Method names use **camelCase**.
- Variable names use **camelCase**.
- Constants use **ALL_CAPS**.
- Every statement gets braces.
- Opening braces stay on the same line.
- Use meaningful comments.

Example

```java
if(score > 90){
    System.out.println("A");
}
```

---

# Javadoc

## What it is

Javadoc is Java's built-in documentation system.

## What it does

Creates documentation directly from specially formatted comments.

## Why it's useful

- Explains code.
- Helps other programmers.
- Generates professional documentation automatically.

Example

```java
/**
 * Returns the student's name.
 *
 * @return student's name
 */
public String getName(){
    return name;
}
```

Common Tags

- `@author`
- `@param`
- `@return`
- `@throws`

---

# Exceptions

## What it is

An exception is an error that occurs while a program is running.

## What it does

Stops normal execution until Java handles the error.

## Why it's useful

- Prevents crashes.
- Makes programs more reliable.
- Helps programmers identify bugs.

Examples

- Divide by zero
- Array index out of bounds
- Invalid input
- File not found

---

# try

## What it is

A block containing code that may cause an exception.

## What it does

Allows Java to watch for errors while executing code.

## Why it's useful

Lets you safely execute risky code.

Example

```java
try{

    int answer = 10 / 0;

}
```

---

# catch

## What it is

A block that handles exceptions.

## What it does

Runs if an error occurs inside the try block.

## Why it's useful

Allows the program to recover instead of crashing.

Example

```java
catch(Exception e){

    System.out.println("Something went wrong.");

}
```

---

# finally

## What it is

A block that always executes.

## What it does

Runs whether an exception occurs or not.

## Why it's useful

Useful for cleanup tasks.

Example

```java
finally{

    System.out.println("Finished.");

}
```

---

# throw

## What it is

A keyword used to create your own exception.

## What it does

Forces Java to generate an error.

## Why it's useful

Lets programmers stop invalid situations immediately.

Example

```java
throw new IllegalArgumentException("Age cannot be negative.");
```

---

# Debugging

## What it is

The process of finding and fixing problems in code.

## What it does

Helps identify why programs don't behave correctly.

## Why it's useful

- Improves code quality.
- Makes development faster.
- Builds problem-solving skills.

Good debugging habits

- Read error messages carefully.
- Print variable values.
- Test one thing at a time.
- Use IntelliJ's debugger.

---

# Git

## What it is

Git is a version control system.

## What it does

Tracks every change made to a project.

## Why it's useful

- Allows undoing mistakes.
- Makes collaboration easier.
- Keeps project history.

---

# GitHub

## What it is

GitHub is a website that stores Git repositories online.

## What it does

Backs up projects and allows collaboration.

## Why it's useful

- Access projects anywhere.
- Share code.
- Submit assignments.

---

# Common Git Commands

## git clone

Copies a repository from GitHub.

```bash
git clone repository-url
```

---

## git status

Shows the current status of your repository.

```bash
git status
```

---

## git add

Stages files for a commit.

```bash
git add .
```

---

## git commit

Saves a snapshot of staged changes.

```bash
git commit -m "Describe your changes"
```

---

## git push

Uploads commits to GitHub.

```bash
git push
```

---

## git pull

Downloads changes from GitHub.

```bash
git pull
```

---

## git checkout -b

Creates and switches to a new branch.

```bash
git checkout -b feature-name
```

---

# Branching

## What it is

A branch is an independent version of your project.

## What it does

Allows developers to work on new features without affecting the main code.

## Why it's useful

- Safe experimentation.
- Easier teamwork.
- Prevents breaking working code.

---

# JUnit

## What it is

JUnit is Java's testing framework.

## What it does

Runs automated tests to verify code works correctly.

## Why it's useful

- Finds bugs early.
- Makes code easier to maintain.
- Prevents future changes from breaking existing code.

---

# Unit Testing

## What it is

Testing one small piece of code at a time.

## What it does

Checks whether a single method behaves correctly.

## Why it's useful

Makes debugging much easier.

---

# Common Assertions

## assertEquals()

Checks whether two values are equal.

Example

```java
assertEquals(5, calculator.add(2,3));
```

---

## assertNotEquals()

Checks that two values are different.

---

## assertTrue()

Checks that a condition is true.

---

## assertFalse()

Checks that a condition is false.

---

## assertNull()

Checks that an object is null.

---

## assertNotNull()

Checks that an object exists.

---

# Common JUnit Annotations

## @Test

Marks a method as a test.

```java
@Test
public void testAddition(){

}
```

---

## @BeforeEach

Runs before every test.

Useful for creating objects that multiple tests use.

---

## @AfterEach

Runs after every test.

Useful for cleanup.

---

## @BeforeAll

Runs once before every test in the class.

---

## @AfterAll

Runs once after all tests finish.

---

# Coding Best Practices

- Use meaningful variable names.
- Write one method for one job.
- Keep methods short.
- Comment complicated logic.
- Follow the Java Style Guide.
- Test your code often.
- Read compiler errors carefully.
- Don't ignore warnings.

---

# Key Takeaways

- Classes are blueprints; objects are instances.
- Encapsulation protects object data.
- Getters and setters control access.
- Access modifiers determine visibility.
- UML diagrams help plan code before writing it.
- Javadoc documents your methods.
- Git tracks changes to your project.
- GitHub stores your repositories online.
- JUnit helps verify that your code works correctly.
- Clean, readable code is easier to debug and maintain.