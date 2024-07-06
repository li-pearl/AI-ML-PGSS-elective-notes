# Introduction to Python

This lesson will cover the basics of Python programming, including what Python is, why we use it, and fundamental concepts such as variables, functions, operators, and basic math operations.

## What is Python?

Python is a high-level, interpreted programming language created by Guido van Rossum and first released in 1991. It emphasizes code readability and simplicity, making it an excellent choice for beginners and experienced programmers alike. Python supports multiple programming paradigms, including procedural, object-oriented, and functional programming.

## Why Use Python?

Python is popular for several reasons:
- **Easy to Read and Write**: Python's syntax is clear and concise.
- **Versatile**: Used in web development, data analysis, artificial intelligence, scientific computing, and more.
- **Large Community and Libraries**: Extensive standard libraries and a supportive community.
- **Interpreted Language**: Allows for interactive testing and debugging.

## Variables

Variables are used to store data values. In Python, you don't need to declare the type of a variable; it's dynamically typed.

```python
# Example of variables
x = 10         # Integer
y = 3.14       # Float
name = "Python" # String

print(x)
print(y)
print(name)
```

## Functions
Functions are reusable blocks of code that perform a specific task. You define a function using the `def` keyword.

```python
# Example of a function
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

## Operators
Operators are used to perform operations on variables and values. Python supports various types of operators:

### Arithmetic Operators
```
 + : Addition
- : Subtraction
* : Multiplication
/ : Division
% : Modulus
** : Exponentiation
// : Floor Division
```

## Comparison Operators

```
== : Equal to
!= : Not equal to
> : Greater than
< : Less than
>= : Greater than or equal to
<= : Less than or equal to
```

``` python
# Example of comparison operators
a = 10
b = 3

print(a == b)  # Equal to
print(a != b)  # Not equal to
print(a > b)   # Greater than
print(a < b)   # Less than
print(a >= b)  # Greater than or equal to
print(a <= b)  # Less than or equal to

```

## Logical Operators

```
and : Returns True if both statements are true
or : Returns True if one of the statements is true
not : Reverses the result
```

```python
# Example of logical operators
a = True
b = False

print(a and b)  # Logical AND
print(a or b)   # Logical OR
print(not a)    # Logical NOT

```

## Math Operations
Python provides a variety of mathematical functions through the math module.

```python
import math

# Example of math functions
print(math.sqrt(16))     # Square root
print(math.factorial(5)) # Factorial
print(math.pow(2, 3))    # Power

# Trigonometric functions
print(math.sin(math.pi / 2)) # Sine
print(math.cos(math.pi))     # Cosine

```

## Project - Calculator:

Instructions
1) Define Functions: Create functions for addition, subtraction, multiplication, and division.
2) Take User Input: Write a function to take input from the user.
3) Perform Calculation: Write a function to perform the calculation based on the user input.
4) Display Result: Write a function to display the result of the calculation.
5) Run the Program: Combine all functions and run the program.

### Helpful tips for the project (Includes some solutions so beware if you want to try on your own):

Getting input:

```python
def get_input():
    num1 = float(input("Enter the first number: "))
    num2 = float(input("Enter the second number: "))
    operation = input("Enter the operation (+, -, *, /): ")
    return num1, num2, operation
```