# 1. Data Types — Exercises

> Syllabus topic: Data Types (AQA 3.2.1 / OCR 2.1)
> Open Thonny and create a new file for each exercise.

---

## Quick Reference

| Data Type      | Python Type | Example              |
|----------------|-------------|----------------------|
| Integer        | `int`       | `42`, `-7`, `0`      |
| Real/Float     | `float`     | `3.14`, `-0.5`       |
| Boolean        | `bool`      | `True`, `False`      |
| Character      | `str`       | `"A"`, `"7"`         |
| String         | `str`       | `"Hello world"`      |

Use `type()` in the Thonny Shell to check any value: `type(42)` → `<class 'int'>`

---

## Exercises

### A. Identify the type

For each value, write down the data type **before** checking in Thonny.

```
1.  42
2.  "42"
3.  3.14
4.  True
5.  "Hello"
6.  0
7.  -7.5
8.  "A"
9.  False
10. ""
11. "3.14"
12. 0.0
```

**Check your answers** — type each into the Thonny Shell:
```python
>>> type(42)
>>> type("42")
>>> type(3.14)
```
...and so on.

---

### B. What's the output?

Predict the output of each line, then run it in Thonny to check.

```python
# 1
print(type(10))

# 2
print(type(10.0))

# 3
print(type("10"))

# 4
print(type(True))

# 5
print(type("True"))

# 6
print(type(""))
```

---

### C. Same value, different types

Open a new file. Create three variables that all represent the number five, each as a different data type.

```python
a = ___
b = ___
c = ___

print(a, type(a))
print(b, type(b))
print(c, type(c))
```

Expected output:
```
5 <class 'int'>
5.0 <class 'float'>
5 <class 'str'>
```

---

### D. Why does it matter?

Predict the output of each pair, then run them in Thonny.

```python
# Pair 1
print(3 + 4)
print("3" + "4")

# Pair 2
print(10 / 3)
print(10 // 3)

# Pair 3
print(1 + 2.0)
print(type(1 + 2.0))
```

Write a comment next to each explaining **why** the output is what it is.

---

### E. Fix the bugs

Each snippet has a data type problem. Find and fix it.

**1.**
```python
age = "15"
next_year = age + 1
print(next_year)
```

**2.**
```python
price = 9.99
message = "The price is " + price
print(message)
```

**3.**
```python
answer = input("Enter a number: ")
double = answer * 2
print(double)
```
(Hint: if you type `5`, what does `"5" * 2` give you?)

---

### F. Classify the variables

Write a program that creates one variable of each data type, then prints its value and type.

```python
my_integer = ___
my_float = ___
my_boolean = ___
my_character = ___
my_string = ___

print(my_integer, type(my_integer))
print(my_float, type(my_float))
print(my_boolean, type(my_boolean))
print(my_character, type(my_character))
print(my_string, type(my_string))
```

---

### G. True or False quiz

Answer True or False for each statement. Check your answers in the Thonny Shell.

```
1. type(7) is int
2. type(7.0) is int
3. type("7") is str
4. type(True) is str
5. type("False") is bool
6. "hello" and "Hello" are the same
7. 5 and 5.0 are the same type
8. "" is a valid string
```

---

### H. Exam-style questions

**Q1.** State the most appropriate data type for each of the following:

```
a) A person's first name
b) The number of students in a class
c) The price of an item in a shop
d) Whether a light switch is on or off
e) A single letter grade (A, B, C, D)
f) A phone number like "07700123456"
g) The number of lives remaining in a game
h) A student's average test score
```

**Q2.** A programmer writes this code:

```python
x = "25"
y = 10
z = x + y
```

Explain why this code will produce an error. State the type of error and how to fix it.

**Q3.** Give two reasons why choosing the correct data type matters when writing a program.

**Q4.** A variable stores the value `"100"`. Explain why this is a string and not an integer. How would you store it as an integer instead?

---

### I. Repeated practice — quick fire

Open the Thonny Shell and predict each result before pressing Enter.

```python
>>> type(99)
>>> type(-3.5)
>>> type("True")
>>> type(False)
>>> type("X")
>>> type(0)
>>> type(0.0)
>>> type("")
>>> "5" + "5"
>>> 5 + 5
>>> 5 + 5.0
>>> "5" * 3
>>> type("5" * 3)
```

---

## Answers

<details>
<summary>Click to reveal answers</summary>

### A. Identify the type

1. `int` 2. `str` 3. `float` 4. `bool` 5. `str` 6. `int` 7. `float` 8. `str` 9. `bool` 10. `str` 11. `str` 12. `float`

### B. What's the output?

1. `<class 'int'>` 2. `<class 'float'>` 3. `<class 'str'>` 4. `<class 'bool'>` 5. `<class 'str'>` (it's in quotes, so it's a string) 6. `<class 'str'>` (empty string is still a string)

### C. Same value, different types

```python
a = 5
b = 5.0
c = "5"
```

### D. Why does it matter?

- `3 + 4` → `7` (integer addition)
- `"3" + "4"` → `"34"` (string concatenation)
- `10 / 3` → `3.333...` (real division always gives float)
- `10 // 3` → `3` (integer division)
- `1 + 2.0` → `3.0` (mixing int and float gives float)
- `type(1 + 2.0)` → `<class 'float'>`

### E. Fix the bugs

1. `age = 15` (remove the quotes)
2. `message = "The price is " + str(price)`
3. `answer = int(input("Enter a number: "))`

### G. True or False quiz

1. True 2. False (it's float) 3. True 4. False (it's bool) 5. False (it's str — it's in quotes) 6. False (case-sensitive) 7. False (int vs float) 8. True

### H. Exam-style questions

**Q1.** a) String b) Integer c) Float/Real d) Boolean e) Character (or String) f) String (leading zero would be lost as integer) g) Integer h) Float/Real

**Q2.** `x` is a string and `y` is an integer. You cannot use `+` between a string and an integer — Python raises a `TypeError`. Fix: change `x = "25"` to `x = 25`, or change line 3 to `z = int(x) + y`.

**Q3.** Any two of: determines which operations can be performed; affects memory usage; prevents errors from mixing incompatible types; ensures data is stored and compared correctly.

**Q4.** It is a string because the value is enclosed in quotation marks. Python treats anything in quotes as text, regardless of the characters inside. Store as integer: `x = 100` (no quotes).

### I. Quick fire

`int`, `float`, `str`, `bool`, `str`, `int`, `float`, `str`, `"55"`, `10`, `10.0`, `"555"`, `str`

</details>

---

*Next: [02 — Variables and Constants](02_variables_and_constants.md)*
