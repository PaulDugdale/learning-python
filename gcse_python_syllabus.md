---
layout: default
title: Syllabus
nav_order: 2
---

# GCSE Python Programming Syllabus

> A complete guide to every Python programming topic you need for GCSE Computer Science.
> Covers **AQA (8525)** and **OCR (J277)** — the two most common exam boards.
> All code examples are written for **Thonny** and **Python 3**.

---

## Table of Contents

1. [Data Types](#1-data-types)
2. [Variables and Constants](#2-variables-and-constants)
3. [Casting (Type Conversion)](#3-casting-type-conversion)
4. [Input and Output](#4-input-and-output)
5. [Arithmetic Operators](#5-arithmetic-operators)
6. [Relational (Comparison) Operators](#6-relational-comparison-operators)
7. [Boolean (Logic) Operators](#7-boolean-logic-operators)
8. [Selection (If Statements)](#8-selection-if-statements)
9. [Iteration (Loops)](#9-iteration-loops)
10. [String Handling](#10-string-handling)
11. [Arrays and Lists](#11-arrays-and-lists)
12. [Two-Dimensional Arrays](#12-two-dimensional-arrays)
13. [Records and Dictionaries](#13-records-and-dictionaries)
14. [Subroutines — Functions and Procedures](#14-subroutines--functions-and-procedures)
15. [Scope — Local and Global Variables](#15-scope--local-and-global-variables)
16. [File Handling](#16-file-handling)
17. [Random Number Generation](#17-random-number-generation)
18. [SQL (Structured Query Language)](#18-sql-structured-query-language)
19. [Robust and Secure Programming](#19-robust-and-secure-programming)
20. [Searching Algorithms](#20-searching-algorithms)
21. [Sorting Algorithms](#21-sorting-algorithms)
22. [Trace Tables](#22-trace-tables)
23. [Errors and Testing](#23-errors-and-testing)
24. [Good Programming Practices](#24-good-programming-practices)

---

## 1. Data Types

You must know these five core data types and when to use each one.

| Data Type   | What it is                         | Python Type | Example          |
|-------------|------------------------------------|-------------|------------------|
| **Integer** | A whole number (no decimal point)  | `int`       | `42`, `-7`, `0`  |
| **Real/Float** | A number with a decimal point   | `float`     | `3.14`, `-0.5`   |
| **Boolean** | True or False — only two values    | `bool`      | `True`, `False`  |
| **Character** | A single letter, digit or symbol | `str`       | `"A"`, `"7"`     |
| **String**  | A sequence of characters (text)    | `str`       | `"Hello world"`  |

> **Note:** Python doesn't have a separate `char` type — a character is just a string of length 1.

### Why does the data type matter?

- It determines what operations you can perform (`3 + 4` = `7`, but `"3" + "4"` = `"34"`)
- It affects how much memory is used
- It determines how data is stored and compared

---

## 2. Variables and Constants

### Variables

A **variable** is a named container that stores a value. The value can change while the program runs.

```python
score = 0           # integer variable
name = "Alice"      # string variable
score = score + 10  # value changed to 10
```

### Constants

A **constant** is a value that should NOT change during the program. Python doesn't enforce constants, but by convention we write them in UPPER_CASE to signal "don't change this".

```python
MAX_LIVES = 3
TAX_RATE = 0.2
PI = 3.14159
```

### Rules for naming variables

- Must start with a letter or underscore (`_`)
- Can contain letters, numbers and underscores
- Cannot contain spaces or special characters
- Cannot be a Python keyword (like `if`, `for`, `while`)
- Are **case-sensitive** — `Score` and `score` are different variables
- Should be **meaningful** — `player_name` is better than `x`

---

## 3. Casting (Type Conversion)

**Casting** means converting a value from one data type to another.

```python
# String to integer
age = int("16")             # age is now the integer 16

# String to float
price = float("9.99")      # price is now the float 9.99

# Integer to string
message = str(100)          # message is now the string "100"

# Float to integer (truncates — chops off the decimal)
whole = int(3.7)            # whole is now 3 (NOT rounded — just chopped)

# Integer to float
decimal = float(5)          # decimal is now 5.0
```

### Why you need casting

When you use `input()`, Python **always** gives you a string. If you want to do maths with it, you must cast it first:

```python
age = input("Enter your age: ")        # age is a STRING like "16"
age = int(input("Enter your age: "))   # age is now an INTEGER like 16
```

> **Thonny tip:** If you're not sure what type a variable is, use the Variables view (View > Variables) to see the type next to each value.

---

## 4. Input and Output

### Getting input from the user

```python
name = input("What is your name? ")
age = int(input("How old are you? "))
height = float(input("Enter your height in metres: "))
```

- `input()` always returns a **string**
- Wrap in `int()` or `float()` if you need a number

### Displaying output

```python
print("Hello, world!")
print(name)
print("Your score is", score)
print("Your score is " + str(score))       # concatenation (joining strings)
print(f"Your score is {score}")             # f-string (the modern way)
```

### f-strings (formatted string literals)

f-strings are the cleanest way to mix text and variables:

```python
name = "Alice"
score = 95
print(f"{name} scored {score} out of 100")
# Output: Alice scored 95 out of 100
```

---

## 5. Arithmetic Operators

These let you do maths with numbers.

| Operator | Name                  | Example     | Result |
|----------|-----------------------|-------------|--------|
| `+`      | Addition              | `7 + 3`     | `10`   |
| `-`      | Subtraction           | `7 - 3`     | `4`    |
| `*`      | Multiplication        | `7 * 3`     | `21`   |
| `/`      | Division (real/float) | `7 / 3`     | `2.333...` |
| `//`     | Integer division (DIV)| `7 // 3`    | `2`    |
| `%`      | Modulus/remainder (MOD)| `7 % 3`    | `1`    |
| `**`     | Exponentiation (power)| `2 ** 3`    | `8`    |

### DIV and MOD — the ones students forget

- **DIV (`//`)** — divides and throws away the remainder. `17 // 5` = `3`
- **MOD (`%`)** — gives you just the remainder. `17 % 5` = `2`

Common uses of MOD:
- Check if a number is even: `number % 2 == 0`
- Get the last digit: `number % 10`
- Wrap around (e.g. clock): `hour % 12`

---

## 6. Relational (Comparison) Operators

These compare two values and return `True` or `False`.

| Operator | Meaning                  | Example    | Result  |
|----------|--------------------------|------------|---------|
| `==`     | Equal to                 | `5 == 5`   | `True`  |
| `!=`     | Not equal to             | `5 != 3`   | `True`  |
| `<`      | Less than                | `3 < 5`    | `True`  |
| `>`      | Greater than             | `3 > 5`    | `False` |
| `<=`     | Less than or equal to    | `5 <= 5`   | `True`  |
| `>=`     | Greater than or equal to | `3 >= 5`   | `False` |

> **Common mistake:** Using `=` (assignment) instead of `==` (comparison). `x = 5` sets x to 5. `x == 5` checks if x equals 5.

---

## 7. Boolean (Logic) Operators

Combine conditions using `and`, `or`, `not`.

| Operator | What it does                      | Example                        | Result  |
|----------|-----------------------------------|--------------------------------|---------|
| `and`    | True only if BOTH are true        | `True and False`               | `False` |
| `or`     | True if AT LEAST ONE is true      | `True or False`                | `True`  |
| `not`    | Flips True to False and vice versa| `not True`                     | `False` |

### Truth tables (you need to know these)

**AND**
| A     | B     | A and B |
|-------|-------|---------|
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

**OR**
| A     | B     | A or B |
|-------|-------|--------|
| True  | True  | True   |
| True  | False | True   |
| False | True  | True   |
| False | False | False  |

**NOT**
| A     | not A |
|-------|-------|
| True  | False |
| False | True  |

### Combining in code

```python
age = 16
has_ticket = True

if age >= 12 and has_ticket:
    print("You can enter")

if age < 5 or age > 65:
    print("Free entry")

if not has_ticket:
    print("Buy a ticket first")
```

---

## 8. Selection (If Statements)

Selection lets your program make **decisions** — run different code depending on a condition.

### Simple if

```python
if temperature > 30:
    print("It's hot!")
```

### if-else

```python
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### if-elif-else

```python
if score >= 90:
    print("Grade A")
elif score >= 70:
    print("Grade B")
elif score >= 50:
    print("Grade C")
else:
    print("Fail")
```

### Nested selection (if inside an if)

```python
if age >= 18:
    if has_id:
        print("Entry allowed")
    else:
        print("Show your ID")
else:
    print("Too young")
```

> **Exam tip:** Indentation matters in Python. Everything inside an `if` block must be indented by the same amount (usually 4 spaces). Thonny handles this automatically when you press Enter after a colon.

---

## 9. Iteration (Loops)

Iteration means **repeating** a block of code.

### for loop — definite iteration (you know how many times)

```python
# Print numbers 0 to 4
for i in range(5):
    print(i)

# Print numbers 1 to 10
for i in range(1, 11):
    print(i)

# Count in steps of 2: 0, 2, 4, 6, 8
for i in range(0, 10, 2):
    print(i)

# Loop through a list
colours = ["red", "green", "blue"]
for colour in colours:
    print(colour)
```

### while loop — indefinite iteration (you don't know how many times)

```python
# Keep asking until they guess correctly
password = ""
while password != "secret":
    password = input("Enter password: ")
print("Access granted")
```

```python
# Count up to 5
count = 1
while count <= 5:
    print(count)
    count = count + 1
```

### Nested loops (a loop inside a loop)

```python
# Times table grid
for row in range(1, 6):
    for col in range(1, 6):
        print(f"{row * col:4}", end="")
    print()  # new line after each row
```

### When to use which loop

| Use a `for` loop when...           | Use a `while` loop when...              |
|------------------------------------|-----------------------------------------|
| You know how many times to repeat  | You don't know how many times           |
| Looping through a list/range       | Waiting for a condition to be met       |
| Counting a specific number of times| User input validation (keep asking)     |

---

## 10. String Handling

Strings are sequences of characters. You need to know how to manipulate them.

### Length

```python
word = "Hello"
print(len(word))    # 5
```

### Indexing (accessing individual characters)

```python
word = "Python"
# Index:  0 1 2 3 4 5

print(word[0])      # "P" (first character)
print(word[5])      # "n" (last character)
print(word[-1])     # "n" (last character using negative index)
```

### Slicing (extracting substrings)

```python
word = "Python"

print(word[0:3])    # "Pyt" (index 0, 1, 2 — NOT 3)
print(word[2:5])    # "tho"
print(word[:3])     # "Pyt" (from the start)
print(word[3:])     # "hon" (to the end)
```

### Concatenation (joining strings)

```python
first = "Hello"
second = "World"
result = first + " " + second   # "Hello World"
```

### Case conversion

```python
text = "Hello World"
print(text.upper())     # "HELLO WORLD"
print(text.lower())     # "hello world"
```

### Finding the position of a character or substring

```python
word = "Python"
print(word.find("th"))  # 2 (index where "th" starts)
```

### Character codes (ASCII)

Converting between characters and their numeric ASCII codes:

```python
print(ord("A"))     # 65 (character to ASCII code)
print(chr(65))      # "A" (ASCII code to character)
print(ord("a"))     # 97
```

### String conversion (casting)

```python
# String to integer / float (covered in Section 3)
number = int("42")
decimal = float("3.14")

# Integer / float to string
text = str(42)
text = str(3.14)
```

### Looping through a string

```python
for letter in "Python":
    print(letter)
```

---

## 11. Arrays and Lists

An **array** (called a **list** in Python) stores multiple values in a single variable.

### Creating lists

```python
fruits = ["apple", "banana", "cherry"]
scores = [85, 92, 78, 95, 88]
empty = []
```

### Accessing elements (0-indexed)

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])    # "apple"
print(fruits[1])    # "banana"
print(fruits[-1])   # "cherry" (last element)
```

### Modifying lists

```python
fruits = ["apple", "banana", "cherry"]

fruits[1] = "blueberry"        # change element at index 1
fruits.append("date")          # add to the end
```

### Getting the length

```python
numbers = [3, 1, 4, 1, 5, 9]
print(len(numbers))            # 6
```

### Looping through a list

```python
# By value
for fruit in fruits:
    print(fruit)

# By index
for i in range(len(fruits)):
    print(f"Index {i}: {fruits[i]}")
```

---

## 12. Two-Dimensional Arrays

A **2D array** is a list of lists — think of it as a table with rows and columns.

```python
# A 3x3 grid (3 rows, 3 columns)
grid = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Access: grid[row][column]
print(grid[0][0])    # 1 (first row, first column)
print(grid[1][2])    # 6 (second row, third column)
print(grid[2][1])    # 8 (third row, second column)
```

### Looping through a 2D array

```python
grid = [
    ["A", "B", "C"],
    ["D", "E", "F"],
    ["G", "H", "I"]
]

for row in grid:
    for item in row:
        print(item, end=" ")
    print()  # new line after each row

# Output:
# A B C
# D E F
# G H I
```

### Practical example — class register

```python
# Each row: [name, age, grade]
students = [
    ["Alice", 15, "A"],
    ["Bob", 16, "B"],
    ["Charlie", 15, "A"]
]

# Print all names
for student in students:
    print(student[0])

# Find a specific student
for student in students:
    if student[0] == "Bob":
        print(f"Bob is {student[1]} and got grade {student[2]}")
```

---

## 13. Records and Dictionaries

A **record** groups together related pieces of data with named fields. In Python, we use **dictionaries** for this.

### Creating dictionaries

```python
student = {
    "name": "Alice",
    "age": 15,
    "grade": "A"
}
```

### Accessing and modifying values

```python
print(student["name"])          # "Alice"
print(student["age"])           # 15

student["age"] = 16             # update a value
student["school"] = "Oak High"  # add a new field
```

### A list of records

```python
students = [
    {"name": "Alice", "age": 15, "grade": "A"},
    {"name": "Bob", "age": 16, "grade": "B"},
    {"name": "Charlie", "age": 15, "grade": "C"}
]

# Find all students aged 15
for student in students:
    if student["age"] == 15:
        print(student["name"])
```

---

## 14. Subroutines — Functions and Procedures

A **subroutine** is a named block of code that performs a specific task. It helps you avoid repeating code and makes programs easier to read and debug.

### Procedures (do something, return nothing)

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")      # Hello, Alice!
greet("Bob")        # Hello, Bob!
```

### Functions (do something AND return a value)

```python
def add(a, b):
    return a + b

result = add(3, 4)
print(result)       # 7
```

### Parameters and arguments

- **Parameter** = the variable name in the function definition
- **Argument** = the actual value you pass in when calling it

```python
def calculate_area(length, width):    # length and width are PARAMETERS
    return length * width

area = calculate_area(5, 3)           # 5 and 3 are ARGUMENTS
```

### Why use subroutines?

- **Reusability** — write once, use many times
- **Readability** — `calculate_tax(price)` is clearer than 10 lines of maths
- **Debugging** — fix a bug in one place instead of everywhere
- **Decomposition** — break a big problem into smaller, manageable pieces
- **Teamwork** — different people can work on different subroutines

---

## 15. Scope — Local and Global Variables

### Local variables

A variable created **inside** a function only exists inside that function.

```python
def my_function():
    x = 10          # local variable — only exists inside my_function
    print(x)

my_function()       # prints 10
# print(x)          # ERROR — x doesn't exist out here
```

### Global variables

A variable created **outside** all functions. It can be read anywhere, but to change it inside a function you need the `global` keyword.

```python
score = 0           # global variable

def add_points(points):
    global score
    score = score + points

add_points(10)
print(score)        # 10
```

### Why local variables are better

- They don't accidentally interfere with other parts of your program
- They only use memory while the function is running
- They make functions self-contained and reusable

> **Exam tip:** Avoid using `global` where possible. It's better to pass values as **parameters** and use **return** values.

---

## 16. File Handling

You need to read from and write to **text files**.

### Writing to a file

```python
# "w" = write mode (creates file or OVERWRITES existing content)
file = open("data.txt", "w")
file.write("Hello\n")
file.write("World\n")
file.close()
```

### Appending to a file

```python
# "a" = append mode (adds to the END of the file)
file = open("data.txt", "a")
file.write("New line\n")
file.close()
```

### Reading from a file

```python
# Read the entire file as one string
file = open("data.txt", "r")
content = file.read()
print(content)
file.close()

# Read line by line
file = open("data.txt", "r")
for line in file:
    print(line.strip())     # .strip() removes the trailing newline
file.close()

# Read all lines into a list
file = open("data.txt", "r")
lines = file.readlines()
file.close()
```

### Working with CSV-style data

```python
# Writing records
file = open("students.txt", "w")
file.write("Alice,15,A\n")
file.write("Bob,16,B\n")
file.close()

# Reading and splitting records
file = open("students.txt", "r")
for line in file:
    parts = line.strip().split(",")
    name = parts[0]
    age = int(parts[1])
    grade = parts[2]
    print(f"{name} is {age} and got grade {grade}")
file.close()
```

> **Thonny tip:** When working with files, make sure you save your Python script first. The file will be created in the same folder as your script. You can see the current folder at the top of the Thonny window.

### File modes summary

| Mode | Meaning                                       |
|------|-----------------------------------------------|
| `"r"`| Read — file must exist                        |
| `"w"`| Write — creates new or **overwrites** existing|
| `"a"`| Append — creates new or adds to the end       |

---

## 17. Random Number Generation

```python
import random

# Random integer between 1 and 6 (inclusive)
dice = random.randint(1, 6)

print(f"You rolled a {dice}")
```

> **Note:** These are **pseudo-random** numbers — generated by an algorithm, not truly random, but good enough for GCSE-level programs.

> **Exam tip:** Always put `import random` at the **top** of your program, before any other code that uses it.

---

## 18. SQL (Structured Query Language)

You need to understand basic SQL for querying databases. You won't run SQL in Python for the exam — but you must be able to read and write SQL statements.

### SELECT — retrieving data

```sql
-- Get all columns from a table
SELECT * FROM students

-- Get specific columns
SELECT name, age FROM students

-- With a condition
SELECT name, age FROM students WHERE age > 15

-- Multiple conditions
SELECT name FROM students WHERE age >= 15 AND grade = "A"

-- Sorted results
SELECT * FROM students ORDER BY name ASC    -- ascending (A-Z, 0-9)
SELECT * FROM students ORDER BY age DESC    -- descending (9-0, Z-A)
```

### Wildcards

```sql
-- Names starting with "A"
SELECT * FROM students WHERE name LIKE "A%"

-- Names ending with "n"
SELECT * FROM students WHERE name LIKE "%n"

-- Names containing "li"
SELECT * FROM students WHERE name LIKE "%li%"
```

### Key SQL keywords to know

| Keyword    | Purpose                            |
|------------|------------------------------------|
| `SELECT`   | Which columns to retrieve          |
| `FROM`     | Which table to query               |
| `WHERE`    | Filter rows by a condition         |
| `AND`/`OR` | Combine conditions                 |
| `ORDER BY` | Sort results (ASC or DESC)         |
| `LIKE`     | Pattern matching with wildcards    |
| `*`        | All columns                        |

---

## 19. Robust and Secure Programming

### Input validation

Making sure the user enters sensible data.

```python
# Range check
age = int(input("Enter your age: "))
while age < 0 or age > 120:
    print("Invalid. Age must be between 0 and 120.")
    age = int(input("Enter your age: "))

# Length check
password = input("Enter a password: ")
while len(password) < 8:
    print("Password must be at least 8 characters.")
    password = input("Enter a password: ")

# Presence check (not empty)
name = input("Enter your name: ")
while name == "":
    print("Name cannot be blank.")
    name = input("Enter your name: ")

# Type check using try/except
while True:
    try:
        age = int(input("Enter your age: "))
        break
    except ValueError:
        print("Please enter a whole number.")
```

### Types of validation

| Check           | What it does                              | Example                  |
|-----------------|-------------------------------------------|--------------------------|
| **Range check** | Value is within allowed limits            | Age between 0 and 120    |
| **Length check** | Input is the right length                | Password at least 8 chars|
| **Presence check** | Input is not empty/blank              | Name is not blank        |
| **Type check**  | Input is the correct data type            | Age is a number          |
| **Format check**| Input matches a required pattern          | Email contains `@`       |

### Authentication (username/password)

```python
stored_username = "admin"
stored_password = "pass123"
attempts = 0
max_attempts = 3

while attempts < max_attempts:
    username = input("Username: ")
    password = input("Password: ")

    if username == stored_username and password == stored_password:
        print("Login successful!")
        break
    else:
        attempts += 1
        remaining = max_attempts - attempts
        print(f"Incorrect. {remaining} attempts remaining.")

if attempts == max_attempts:
    print("Account locked.")
```

### Exception handling (try/except)

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number
    print(f"Result: {result}")
except ValueError:
    print("That wasn't a valid number.")
except ZeroDivisionError:
    print("You can't divide by zero.")
```

---

## 20. Searching Algorithms

### Linear search

Checks every element **one by one** from the start. Works on **any** list (sorted or unsorted).

```python
def linear_search(data, target):
    for i in range(len(data)):
        if data[i] == target:
            return i            # found — return the index
    return -1                   # not found

names = ["Alice", "Bob", "Charlie", "Diana"]
result = linear_search(names, "Charlie")
print(result)   # 2
```

| Pros                         | Cons                                    |
|------------------------------|-----------------------------------------|
| Simple to code               | Slow for large lists                    |
| Works on unsorted data       | Has to check every item in worst case   |
| Works on any data structure  | Average: checks half the items          |

### Binary search

Repeatedly **halves** the search area. Only works on **sorted** data.

```python
def binary_search(data, target):
    low = 0
    high = len(data) - 1

    while low <= high:
        mid = (low + high) // 2

        if data[mid] == target:
            return mid          # found
        elif data[mid] < target:
            low = mid + 1       # target is in the right half
        else:
            high = mid - 1      # target is in the left half

    return -1                   # not found

numbers = [2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
result = binary_search(numbers, 23)
print(result)   # 5
```

| Pros                         | Cons                                    |
|------------------------------|-----------------------------------------|
| Very fast for large lists    | Data MUST be sorted first               |
| Max ~10 checks for 1000 items| More complex to code                   |
| Halves the data each time    | Doesn't work on linked lists            |

---

## 21. Sorting Algorithms

### Bubble sort

Compares **adjacent pairs** and swaps them if they're in the wrong order. Repeats until no swaps are needed.

```python
def bubble_sort(data):
    n = len(data)
    for i in range(n - 1):
        swapped = False
        for j in range(n - 1 - i):
            if data[j] > data[j + 1]:
                data[j], data[j + 1] = data[j + 1], data[j]
                swapped = True
        if not swapped:
            break               # already sorted — stop early
    return data

numbers = [64, 34, 25, 12, 22, 11, 90]
print(bubble_sort(numbers))
# [11, 12, 22, 25, 34, 64, 90]
```

| Pros                              | Cons                              |
|-----------------------------------|-----------------------------------|
| Simple to understand and code     | Very slow for large lists         |
| Can detect if already sorted      | Lots of comparisons and swaps     |
| Doesn't need extra memory         | One of the slowest sorting methods|

### Insertion sort

Takes each item and **inserts** it into the correct position in the sorted portion of the list.

```python
def insertion_sort(data):
    for i in range(1, len(data)):
        key = data[i]
        j = i - 1
        while j >= 0 and data[j] > key:
            data[j + 1] = data[j]
            j -= 1
        data[j + 1] = key
    return data

numbers = [64, 34, 25, 12, 22, 11, 90]
print(insertion_sort(numbers))
# [11, 12, 22, 25, 34, 64, 90]
```

| Pros                              | Cons                              |
|-----------------------------------|-----------------------------------|
| Good for small or nearly-sorted data | Slow for large lists           |
| Simple to code                    | Still has to shift many items     |
| Sorts in place (no extra memory)  | Worse than merge sort for big data|

### Merge sort

**Divides** the list in half repeatedly, then **merges** the halves back together in order.

```python
def merge_sort(data):
    if len(data) <= 1:
        return data

    mid = len(data) // 2
    left = merge_sort(data[:mid])
    right = merge_sort(data[mid:])

    return merge(left, right)

def merge(left, right):
    result = []
    i = 0
    j = 0

    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])
    return result

numbers = [64, 34, 25, 12, 22, 11, 90]
print(merge_sort(numbers))
# [11, 12, 22, 25, 34, 64, 90]
```

| Pros                              | Cons                              |
|-----------------------------------|-----------------------------------|
| Fast even for large lists         | Uses extra memory for merging     |
| Consistent performance            | More complex to code              |
| Good for very large datasets      | Overkill for small lists          |

> **Thonny tip:** Use the debugger (click the bug icon or press Ctrl+F5) to step through sorting algorithms line by line. Watch the Variables panel to see how the list changes at each step — this is much better than just reading the code.

---

## 22. Trace Tables

A **trace table** tracks the values of variables as a program runs — step by step.

### Example program

```python
x = 5
y = 3
z = 0

while x > 0:
    z = z + y
    x = x - 1
```

### Trace table

| Step | x | y | z  | `x > 0` |
|------|---|---|----|----------|
| Init | 5 | 3 | 0  | True     |
| 1    | 4 | 3 | 3  | True     |
| 2    | 3 | 3 | 6  | True     |
| 3    | 2 | 3 | 9  | True     |
| 4    | 1 | 3 | 12 | True     |
| 5    | 0 | 3 | 15 | False    |

**Final values:** x = 0, y = 3, z = 15

> **Exam tip:** Trace tables are common exam questions. Work through each line carefully and update one variable at a time. Don't skip steps.

> **Thonny tip:** You can verify your trace tables by using the debugger. Step through the code and compare the Variables panel to your handwritten trace table.

---

## 23. Errors and Testing

### Types of errors

| Error Type    | What it means                          | Example                          |
|---------------|----------------------------------------|----------------------------------|
| **Syntax error** | Code breaks Python's grammar rules | `print("hello"` — missing `)`  |
| **Logic error**  | Code runs but gives wrong results  | Using `+` instead of `-`        |
| **Runtime error** | Code crashes while running         | Dividing by zero, missing file  |

### Types of test data

| Test Data Type   | Purpose                              | Example (for age 0-120)     |
|------------------|--------------------------------------|-----------------------------|
| **Normal**       | Typical, valid input                 | `25`, `50`, `80`            |
| **Boundary**     | Values at the edge of valid ranges   | `0`, `1`, `119`, `120`     |
| **Erroneous**    | Invalid input that should be rejected| `-5`, `200`, `"abc"`        |

### Why test at boundaries?

**Boundary testing** checks the exact edges where valid meets invalid. For a range of 0–120:
- `0` and `120` should be **accepted** (they're on the boundary)
- `-1` and `121` should be **rejected** (just outside the boundary)

This is where bugs most commonly hide — an `>` instead of `>=` would fail at the boundary.

---

## 24. Good Programming Practices

These aren't just nice-to-haves — you can **lose marks** for ignoring them.

### Meaningful variable names

```python
# Bad
x = 100
y = x * 0.2

# Good
price = 100
tax = price * 0.2
```

### Comments

```python
# Calculate the total including VAT
total = price + (price * VAT_RATE)
```

### Indentation

Python **requires** correct indentation — it defines the structure of your code.

```python
# Correct
if score > 50:
    print("Pass")
    print("Well done")

# Wrong — will cause an error
if score > 50:
print("Pass")
```

### Constants for fixed values

```python
# Bad — what does 0.2 mean?
tax = price * 0.2

# Good — clear and easy to change later
TAX_RATE = 0.2
tax = price * TAX_RATE
```

### Decomposition

Break large programs into smaller subroutines, each doing one job:

```python
def get_scores():
    # handles input

def calculate_average(scores):
    # handles the maths

def display_results(average):
    # handles output

# Main program — clear and readable
scores = get_scores()
average = calculate_average(scores)
display_results(average)
```

---

## Quick Reference — Python Syntax Cheat Sheet

```python
# Variables and assignment
name = "Alice"
age = 15

# Input/Output
name = input("Enter name: ")
age = int(input("Enter age: "))
print(f"Hello {name}, you are {age}")

# Selection
if condition:
    ...
elif other_condition:
    ...
else:
    ...

# For loop
for i in range(10):
    ...

# While loop
while condition:
    ...

# Function
def function_name(param1, param2):
    return result

# List
my_list = [1, 2, 3]
my_list.append(4)
my_list[0]

# Dictionary
my_dict = {"key": "value"}
my_dict["key"]

# File handling
file = open("file.txt", "r")
content = file.read()
file.close()

# Random
import random
random.randint(1, 10)

# String methods
len("hello")
"hello".upper()
"hello".lower()
"hello"[0:3]
"hello".find("ll")
ord("A")
chr(65)

# Casting
int("5")
str(5)
float("3.14")

# Exception handling
try:
    ...
except ValueError:
    ...
```

---

## Exam Board Coverage Map

| Topic                          | AQA (8525) Section | OCR (J277) Section |
|--------------------------------|--------------------|--------------------|
| Data types                     | 3.2.1              | 2.1                |
| Programming concepts           | 3.2.2              | 2.1                |
| Arithmetic operators           | 3.2.3              | 2.1                |
| Relational operators           | 3.2.4              | 2.1                |
| Boolean operators              | 3.2.5              | 2.1                |
| Data structures (arrays)       | 3.2.6              | 2.2                |
| Input/Output                   | 3.2.7              | 2.1                |
| String handling                | 3.2.8              | 2.2                |
| Random numbers                 | 3.2.9              | 2.2                |
| Subroutines and scope          | 3.2.10             | 2.2                |
| Robust programming & testing   | 3.2.11             | 2.3                |
| File handling                  | 3.2.11             | 2.2                |
| SQL                            | 3.2.12             | 2.3                |
| Searching algorithms           | 3.1                | 1.3                |
| Sorting algorithms             | 3.1                | 1.3                |

---

*Built from the AQA 8525 and OCR J277 GCSE Computer Science specifications.*
*All code examples use Python 3, run in Thonny, and only cover syllabus content.*
