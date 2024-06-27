---
cssclasses:
  - pen-green
---

---

**Chapter 2: Basic Python Syntax**

---

**Section 1: Variables and Data Types**

---

In Python, variables are used to store data. You can think of a variable as a container that holds a value. Python is dynamically typed, meaning you don't need to specify the data type of a variable explicitly. Here's how you declare and use variables in Python:

```python
# Example of variable declaration and assignment
x = 10
y = "Hello, Python!"

# Printing the values of variables
print(x)  # Output: 10
print(y)  # Output: Hello, Python!
```

---

Python supports various data types, including integers, floats, strings, booleans, lists, tuples, and dictionaries. You can check the data type of a variable using the `type()` function:

```python
# Examples of different data types
a = 10
b = 3.14
c = "Python"
d = True
e = [1, 2, 3]
f = (4, 5, 6)
g = {"name": "John", "age": 30}

# Checking data types
print(type(a))  # Output: <class 'int'>
print(type(b))  # Output: <class 'float'>
print(type(c))  # Output: <class 'str'>
print(type(d))  # Output: <class 'bool'>
print(type(e))  # Output: <class 'list'>
print(type(f))  # Output: <class 'tuple'>
print(type(g))  # Output: <class 'dict'>
```


- more on strings here: [[String Methods In Python|String Methods]]
---

**Section 2: Operators**

Operators are used to perform operations on variables and values. Python supports various types of operators, including arithmetic, comparison, logical, assignment, and more. Here are some examples:

```python
# Arithmetic operators
x = 10
y = 5

print(x + y)  # Addition: 15
print(x - y)  # Subtraction: 5
print(x * y)  # Multiplication: 50
print(x / y)  # Division: 2.0
print(x % y)  # Modulus: 0
print(x ** y) # Exponentiation: 100000
print(x // y) # Floor Division: 2
```

```python
# Comparison operators
a = 10
b = 20

print(a == b)  # Equal to: False
print(a != b)  # Not equal to: True
print(a > b)   # Greater than: False
print(a < b)   # Less than: True
print(a >= b)  # Greater than or equal to: False
print(a <= b)  # Less than or equal to: True
```

```python
# Logical operators
x = True
y = False

print(x and y)  # Logical AND: False
print(x or y)   # Logical OR: True
print(not x)    # Logical NOT: False
```

---

**Section 3: Control Flow Statements (if, elif, else)**

---

Control flow statements allow you to control the flow of execution in your program. The `if`, `elif` (short for else if), and `else` statements are used for decision-making. Here's how they work:

```python
# Example of if-elif-else statement
x = 10

if x > 10:
    print("x is greater than 10")
elif x == 10:
    print("x is equal to 10")
else:
    print("x is less than 10")
```

---

**Section 4: Loops (for and while)**

---

Loops are used to repeat a block of code multiple times. Python supports two main types of loops: `for` loops and `while` loops. Here's how they're used:

```python
# Example of a for loop
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

```python
# Example of a while loop
i = 1

while i <= 5:
    print(i)
    i += 1
```

---

**Section 5: Lists, Tuples, and Dictionaries**

---

Lists, tuples, and dictionaries are data structures used to store collections of data.

- Lists are ordered and mutable (modifiable).
- Tuples are ordered and immutable (unchangeable).
- Dictionaries are unordered and mutable, consisting of key-value pairs.

---

Here's how you can work with these data structures:

```python
# Lists
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Accessing elements by index

# Tuples
colors = ("red", "green", "blue")
print(colors[1])  # Accessing elements by index

# Dictionaries
person = {"name": "John", "age": 30}
print(person["name"])  # Accessing values by key
```

---

**Section 6: Functions**

---

Functions are blocks of reusable code that perform a specific task. They allow you to break down your program into smaller, manageable pieces. Here's how you define and use functions in Python:

```python
# Example of a function
def greet(name):
    print("Hello, " + name + "!")

# Calling the function
greet("Alice")  # Output: Hello, Alice!
```

---

**Section 7: Working with Files**

---

Python provides built-in functions for working with files. You can open, read, write, and close files using these functions. Here's a basic example:

```python
# Example of working with files
# Writing to a file
with open("example.txt", "w") as file:
    file.write("Hello, Python!")

# Reading from a file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)  # Output: Hello, Python!
```

---
