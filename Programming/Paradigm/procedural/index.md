# Procedural Programming

Imagine this: You're at your favorite coffee shop, waiting in line for your order. While you wait, you decide to call your friend who works at a bank to transfer some money to a rather shady contact in Russia. At the same time, you're texting your wife, updating her about your day.

In this scenario, each action happens in a specific sequence — one after the other. You're performing multiple tasks, each with its own purpose, but all working together to complete the overall goal of your day.

Congratulations! You've just learned the essence of procedural programming through this story.

## Introduction

When most of us start programming, we often begin with the **procedural programming** paradigm. Procedural programming is built around the idea that programs are sequences of instructions executed in order. We call these instructions procedures, functions, or subroutines. Each can call the other, just like in the story: waiting for your coffee is one procedure, calling your friend is a function call, and so on.

Historically, some of the earliest procedural programming languages were **Fortran** and **ALGOL**. Even today, procedural programming is widely used, especially by beginners and in simple applications.

## Key Features

### 1. **Predefined Functions**

Predefined functions are instructions identified by a name and provided by the programming language or a library. These functions are ready to use and simplify development. For example, `charAt()` in JavaScript retrieves the character at a specific position in a string.

### 2. **Local Variables**

A local variable is declared inside a function and only accessible within that function. If you try to access it outside of the function, the program will throw an error.

### 3. **Global Variables**

Global variables are declared outside of all functions and are accessible from anywhere in the program. This can be convenient but poses potential risks in terms of security and maintenance.

### 4. **Modularity**

Modularity refers to breaking a large task into smaller, self-contained functions or procedures. These procedures work independently to achieve the overall task, improving code readability and maintainability.

### 5. **Parameter Passing**

Parameter passing allows you to send values or references to a function. This can be done in several ways:

- **Pass by value**: Sends a copy of the variable.
- **Pass by reference**: Sends a reference, so changes affect the original variable.
- **Pass by result**, **pass by value-result**, and **pass by name** are other less common methods.

## Pros and Cons

### Advantages

- **Great for general-purpose programming**: Procedural programming works well for many types of applications, especially where simplicity is key.
- **Simplicity**: It is often easier to write and understand for beginners.
- **Abundant learning resources**: There are plenty of tutorials, books, and tested algorithms that make learning procedural programming easier.
- **Portability**: Procedural programs are often portable, allowing the same code to run on different platforms.
- **Code reuse**: Procedures and functions can be reused throughout the program.
- **Optimized memory usage**: This approach can help reduce memory requirements.
- **Easily traceable program flow**: The step-by-step nature of procedural programming makes it easy to follow the execution of the code.

### Disadvantages

- **Scalability issues**: As programs grow in size, procedural code can become harder to manage.
- **Limited reusability across projects**: While you can reuse functions within a single program, sharing them between applications is more complex.
- **Hard to model real-world entities**: Procedural programming focuses more on actions than data, making it less intuitive for modeling real-world objects.
- **Data exposure**: Since global variables are accessible everywhere, data can easily be exposed, leading to potential security risks.
