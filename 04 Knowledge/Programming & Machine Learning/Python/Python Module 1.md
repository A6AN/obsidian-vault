---
tags: [machine-learning, programming, python]
---


# **Module 1: Introduction & Python Fundamentals**

## **1.1 Welcome to Python for AI** 🎉

### **Why Learn Python?**

Python is one of the most popular programming languages for AI and machine learning. It is:

- Easy to learn and read.
- Packed with powerful libraries for AI and data science (NumPy, Pandas, TensorFlow, PyTorch).
- Used by top companies like Google, Tesla, and OpenAI.

This module will give you a **strong foundation in Python**, so you're ready to tackle AI in later modules.

---

## **1.2 Setting Up Your Environment** 🖥️

We’ll be using **Google Colab** because it’s free, requires no installation, and supports AI-related libraries out of the box.

🔹 **Getting Started with Colab:**

1. Go to [Google Colab](https://colab.research.google.com/)
2. Click **New Notebook**
3. Start coding in Python!

Alternatively, you can use **Replit**, **Jupyter Notebook**, or install Python locally.

---

## **1.3 Python Basics** 🔤

### **Printing & Comments**

Python's `print()` function lets you display text:

```python
print("Hello, AI world!")  # This is a comment
```

Comments (using `#`) help explain code but don’t affect execution.

### **Variables & Data Types**

Variables store information. Python has several data types:

```python
name = "Alice"      # String
age = 20           # Integer
height = 5.6       # Float
is_student = True  # Boolean
```

You can check the type of any variable using `type()`:

```python
print(type(age))  # Output: <class 'int'>
```

---

## **1.4 User Input & Basic Operations** 🔢

### **Taking User Input**

```python
name = input("What is your name? ")
print("Hello, " + name + "!")
```

Input is always stored as a string, so convert if needed:

```python
age = int(input("Enter your age: "))
print("In 5 years, you will be", age + 5)
```

### **Operators in Python**

Python supports:

- **Arithmetic:** `+`, `-`, `*`, `/`, `//` (floor division), `%` (modulus)
- **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Logical:** `and`, `or`, `not`

```python
print(5 + 3)  # Output: 8
print(10 // 3) # Output: 3 (floor division)
print(4 > 2 and 3 < 5)  # Output: True
```

---

## **1.5 Control Structures: If, Loops, and More** 🔄

### **Conditional Statements (If-Else)**

```python
age = int(input("Enter your age: "))
if age >= 18:
    print("You can vote!")
else:
    print("You are too young to vote.")
```

### **Loops (For & While)**

#### **For Loop**

```python
for i in range(5):
    print("Iteration:", i)
```

#### **While Loop**

```python
count = 1
while count <= 3:
    print("Count is:", count)
    count += 1
```

---

## **1.6 Lists and Functions** 📋

### **Lists: Storing Multiple Values**

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Output: apple
fruits.append("orange")  # Add an item
print(len(fruits))  # Get list length
```

### **Functions: Reusable Code Blocks**

```python
def greet(name):
    return "Hello, " + name + "!"

print(greet("Alice"))
```

---

## **1.7 Hands-On Challenges 🏆**

Try these exercises:

1. Write a Python program that asks for two numbers and prints their sum.
2. Create a loop that prints all even numbers from 1 to 20.
3. Write a function that takes a number as input and returns its square.

---

