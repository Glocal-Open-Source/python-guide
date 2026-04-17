# Python Master Cheat Sheet

This extensive reference sheet covers Python's core concepts, syntax, built-in functions, operators, and data structures. Use the search bar to find specific functions, keywords, or topics.

---

## 1. Basics & Syntax

### Variables & Core Types
```python
x = 5               # int
y = 3.14            # float
name = "Alice"      # str
is_active = True    # bool
nothing = None      # NoneType
```

### Comments
```python
# This is a single-line comment

"""
This is a 
multi-line string,
often used as a docstring.
"""
```

---

## 2. Operators

### Arithmetic Operators
| Operator | Name | Example | Description |
| :---: | :--- | :--- | :--- |
| `+` | Addition | `x + y` | Sum of x and y |
| `-` | Subtraction | `x - y` | Difference of x and y |
| `*` | Multiplication | `x * y` | Product of x and y |
| `/` | Division | `x / y` | Quotient of x and y |
| `//` | Floor Division| `x // y` | Quotient rounded down |
| `%` | Modulus | `x % y` | Remainder of division |
| `**`| Exponentiation| `x ** y` | x to the power of y |

### Comparison Operators
| Operator | Name | Example | Description |
| :---: | :--- | :--- | :--- |
| `==` | Equal | `x == y` | True if x equals y |
| `!=` | Not equal | `x != y` | True if x is not equal to y |
| `>` | Greater than | `x > y` | True if x is strictly greater |
| `<` | Less than | `x < y` | True if x is strictly less |
| `>=` | Greater/Equal | `x >= y` | True if x is greater or equal |
| `<=` | Less/Equal | `x <= y` | True if x is less or equal |

### Logical Operators
| Operator | Description | Example |
| :---: | :--- | :--- |
| `and` | True if both statements are true | `x < 5 and  x < 10` |
| `or`  | True if one of the statements is true | `x < 5 or x < 4` |
| `not` | Reverse the result | `not(x < 5)` |

### Identity & Membership Operators
| Operator | Description | Example |
| :---: | :--- | :--- |
| `is` | True if both variables point to the same object | `x is y` |
| `is not`| True if variables point to different objects | `x is not y` |
| `in` | True if a sequence with the specified value is present in the object | `x in y` |
| `not in`| True if a sequence with the specified value is not present | `x not in y` |

---

## 3. Data Structures

### Lists (Ordered, Mutable)
```python
# Creation
fruits = ["apple", "banana", "cherry"]
empty = []
mixed = [1, "two", 3.0, True]

# Indexing & Slicing
fruits[0]       # 'apple'
fruits[-1]      # 'cherry'
fruits[0:2]     # ['apple', 'banana']
fruits[::-1]    # ['cherry', 'banana', 'apple'] (reversed)

# Methods
fruits.append("orange")         # Adds to end
fruits.insert(1, "kiwi")        # Inserts at index 1
fruits.remove("banana")         # Removes first occurrence
item = fruits.pop()             # Removes and returns last item
fruits.clear()                  # Empties the list
fruits.extend(["grape", "fig"]) # Appends multiple items
fruits.index("apple")           # Returns index of 'apple'
fruits.count("apple")           # Returns count of occurrences
fruits.sort()                   # Sorts in-place
fruits.reverse()                # Reverses in-place
```

### Tuples (Ordered, Immutable)
```python
# Creation
coords = (10, 20)
single = (1,)           # Comma is required for single item
empty = ()

# Unpacking
x, y = coords

# Methods
coords.count(10)        # Returns 1
coords.index(20)        # Returns 1
```

### Dictionaries (Key-Value, Mutable)
```python
# Creation
person = {"name": "Alice", "age": 25}
empty = {}

# Access & Modify
person["name"]          # 'Alice'
person.get("age", 0)    # 25 (returns default 0 if missing)
person["city"] = "NY"   # Adds new key-value pair

# Methods
person.keys()           # dict_keys(['name', 'age', 'city'])
person.values()         # dict_values(['Alice', 25, 'NY'])
person.items()          # dict_items([('name', 'Alice'), ...])
person.pop("age")       # Removes 'age' and returns 25
person.update({"id": 1})# Merges dictionary
```

### Sets (Unordered, Unique, Mutable)
```python
# Creation
colors = {"red", "green", "blue"}
empty_set = set()       # {} creates a dictionary, not a set

# Methods
colors.add("yellow")
colors.remove("red")    # Erros if 'red' is not found
colors.discard("red")   # Does not error if missing
colors.clear()

# Set Operations
a = {1, 2, 3}
b = {3, 4, 5}
a.union(b)              # {1, 2, 3, 4, 5}  (or a | b)
a.intersection(b)       # {3}              (or a & b)
a.difference(b)         # {1, 2}           (or a - b)
a.symmetric_difference(b) # {1, 2, 4, 5}   (or a ^ b)
```

---

## 4. Control Flow

### If, Elif, Else
```python
if x > 10:
    print("Greater than 10")
elif x == 10:
    print("Exactly 10")
else:
    print("Less than 10")

# Ternary Operator
status = "Adult" if age >= 18 else "Minor"
```

### For Loops
```python
for item in ["a", "b", "c"]:
    print(item)

# Range
for i in range(5):          # [0, 1, 2, 3, 4]
    print(i)
    
for i in range(1, 10, 2):   # Start, Stop, Step
    print(i)

# Enumerate
for index, value in enumerate(["a", "b"]):
    print(f"{index}: {value}")
```

### While Loops
```python
x = 0
while x < 5:
    print(x)
    x += 1
```

### Loop Control
```python
break       # Exits the loop entirely
continue    # Skips to the next iteration
pass        # Does nothing (placeholder)
```

---

## 5. Functions

### Definition & Arguments
```python
def greet(name, msg="Hello"):
    return f"{msg}, {name}!"

greet("Alice")              # 'Hello, Alice!'
greet("Bob", msg="Hi")      # 'Hi, Bob!'

# Variable Arguments
def sum_all(*args):
    return sum(args)        # args is a tuple

def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}") # kwargs is a dict
```

### Lambda Functions (Anonymous)
```python
# lambda arguments : expression
square = lambda x: x * x
square(5) # 25
```

### Generators & Yield
```python
def count_up_to(max):
    count = 1
    while count <= max:
        yield count
        count += 1
```

---

## 6. Comprehensions

```python
# List Comprehension
# [expression for item in iterable if condition]
squares = [x**2 for x in range(10)]
evens = [x for x in range(10) if x % 2 == 0]

# Dictionary Comprehension
squares_dict = {x: x**2 for x in range(5)}

# Set Comprehension
unique_chars = {char for char in "hello"}
```

---

## 7. Exception Handling

```python
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Cannot divide by zero: {e}")
except TypeError:
    print("Type misalignment")
except Exception as e:
    print(f"Generic error fallback: {e}")
else:
    print("Executes only if no exception occurred")
finally:
    print("Always executes, regardless of errors")
    
# Triggering Exceptions
if x < 0:
    raise ValueError("x cannot be negative")
```

---

## 8. Classes & Object-Oriented Programming

```python
class Animal:
    # Class attribute
    planet = "Earth"

    # Constructor
    def __init__(self, name):
        self.name = name    # Instance attribute

    # Instance Method
    def speak(self):
        return "Generic animal sound"

class Dog(Animal): # Inheritance
    def speak(self): # Method Overriding
        return "Woof!"

    # Magic (Dunder) Methods
    def __str__(self):
        return f"A dog named {self.name}"
        
dog = Dog("Rex")
print(dog.speak())  # Woof!
```

---

## 9. File Handling

```python
# Read a file
with open("data.txt", "r") as file:
    content = file.read()       # Read all
    lines = file.readlines()    # Read into list

# Write to a file
with open("data.txt", "w") as file:
    file.write("Hello World!\n")

# Append to a file
with open("data.txt", "a") as file:
    file.write("More text.\n")
```

---

## 10. String Manipulation

```python
s = "  Hello, Python!  "

s.strip()           # 'Hello, Python!'
s.lower()           # '  hello, python!  '
s.upper()           # '  HELLO, PYTHON!  '
s.replace("o", "a") # '  Hella, Pythan!  '
s.split(",")        # ['  Hello', ' Python!  ']
"-".join(["a", "b"])# 'a-b'
s.startswith(" ")   # True
s.endswith("!")     # False

# F-Strings (Python 3.6+)
name = "Alice"
age = 30
f"{name} is {age} years old."
```

---

## 11. Built-in Functions Master List

| Function | Description |
| :--- | :--- |
| `abs(x)` | Absolute value |
| `all(iterable)` | True if all elements are true |
| `any(iterable)` | True if any element is true |
| `bin(int)` | Convert to binary string |
| `bool(x)` | Convert to boolean |
| `chr(i)` | Convert unicode integer to string character |
| `dir(obj)` | Return list of valid attributes of object |
| `enumerate(iter)` | Returns enumerate object containing pairs of index/value |
| `filter(func, iter)`| Construct iterator from elements where func is true |
| `float(x)` | Convert a string or number to a floating point number |
| `help([obj])` | Invoke built-in help system |
| `hex(x)` | Convert integer to hexadecimal string |
| `id(obj)` | Return the unique identifier (memory address) of an object |
| `input([prompt])` | Read a string from standard input |
| `int(x)` | Convert a number or string to an integer |
| `isinstance(obj, class)` | Check if an object is an instance of a class |
| `len(s)` | Length (number of items) of an object |
| `list([iter])` | Creates a list|
| `map(func, iter)` | Apply function to every item of iterable |
| `max(iter)` | Return largest item |
| `min(iter)` | Return smallest item |
| `pow(x, y)` | x to the power of y |
| `print(*objs)` | Print objects to the text stream |
| `range(start, stop)`| Generate sequence of numbers |
| `round(x, [ndigits])`| Round number to desired precision |
| `set([iter])` | Create a new set object |
| `sorted(iter)` | Return a new sorted list from items in iterable |
| `str(x)` | Return string version of object |
| `sum(iter)` | Sums items of an iterable |
| `tuple([iter])` | Creates a tuple |
| `type(obj)` | Returns the type of an object |
| `zip(*iters)` | Iterate over several iterables in parallel |

---

## 12. Important Standard Libraries (Quick Reference)

```python
import math
math.sqrt(16)   # 4.0
math.pi         # 3.14159...

import random
random.randint(1, 10)       # Random integer between 1 and 10
random.choice(['a', 'b'])   # Random element from sequence

import datetime
now = datetime.datetime.now()

import os
os.path.exists("file.txt")  # Check if file exists
os.listdir(".")             # List files in current directory

import json
json_str = json.dumps({"a": 1}) # Python to JSON string
data = json.loads(json_str)     # JSON string to Python dict

import re # Regular Expressions
re.search(r'\d+', 'item 42')    # Matches '42'
```
