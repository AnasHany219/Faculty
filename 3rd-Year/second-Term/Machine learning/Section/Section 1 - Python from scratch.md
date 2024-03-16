## **Python Basics** 🐍

### 1. **Variables and Data Types**:

```python
# Variables
note_title = "Python Basics 📝"
word_count = 500
is_published = True

# Data Types
title_type = type(note_title)  # <class 'str'>
count_type = type(word_count)  # <class 'int'>
pub_type = type(is_published)   # <class 'bool'>
```
### 2. **Lists and Dictionaries**:

```python
# Lists
tags = ["Python", "Obsidian", "Automation"]
notes = ["Basics", "Advanced", "Tips"]

# Dictionaries
note_info = {"title": "Python Basics", "word_count": 500, "published": True}
```
### 3. **Control Flow and Loops**:

```python
# If-else statement
if word_count > 1000:
    print("This is a lengthy note! 📚")
else:
    print("This note is concise. ✏️")

# For loop
for tag in tags:
    print(tag)

# While loop
note_count = 0
while note_count < 3:
    print("Note", note_count)
    note_count += 1
```
### 4. **Functions**:

```python
# Function definition
def greet_user(username):
    """Greet the user."""
    print(f"Hello, {username}! 👋")

# Function call
greet_user("Obsidian User")
```
### 5. **File Handling**:

```python
# Writing to a file
with open("notes.txt", "w") as file:
    file.write("Python Basics\n")
    file.write("Python is awesome! 🚀")

# Reading from a file
with open("notes.txt", "r") as file:
    content = file.read()
    print(content)
```
### 6. **Modules and Packages**:

```python
# Importing modules
import math
print(math.pi)  # 3.141592653589793

# Installing and using packages
# !pip install pandas
import pandas as pd
```

- For more resources, check out [this GitHub repository](https://github.com/AnasHany219/Python) 📚
