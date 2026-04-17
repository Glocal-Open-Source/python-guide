# Data Types & Structures

## Basic Python: Variables and Types

Python is dynamically typed. You can assign any value to a variable without explicitly declaring its type:

```python
# string
url = "https://example.gov/data"

# integer
retry_limit = 3 

# dictionary with key:value pairs (allows for mixed types inside)
bob = {"name": "bob", "age": 50, "height_cm": 200.5}

# dictionary types can also be written like this to make it easier to read:
bob = {
    "name": "bob",
    "age": 50,
    "height": 200.5,
    # you can even embed a dict within a dict!
    "favorites": {
        "food": "pizza", 
        "color": "red"
    }
}
# within one dict, we have 4 values - one with 2 additional subvalues
```

### Common Built-in Types You’ll Use:

- **Strings (`str`)**: sequences of characters
- **Integers (`int`)**: a whole number, for example `3`
- **Floating Point (`float`)**: a floating decimal/point - for example, `3.5`
- **Booleans (`bool`)**: `True` or `False`
- **Lists (`list`)**: ordered sequences
- **Tuples (`tuple`)**: immutable sequences
- **Dictionaries (`dict`)**: key–value mappings

Python automatically sets a data type when you assign a variable. For example:

```python
>>> x = 1 # int
>>> y = 1.5 # float

>>> x + y # python interprets 1 as 1.0 || 1.0 + 1.5
2.5
```

If you try to perform a type-restricted operation on the wrong type, you will receive a `TypeError`:

```python
>>> x = "1" # string
>>> y = 1 # int
>>> x + y # the character "1" + the number 1
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
```

### Type Casting (Converting Types)

When you are scraping raw data from a website, it will ALWAYS be collected as a `str`. If, for example, you scrape a number that will be used in a calculation (i.e. scraping population data from a table), you can specify the typing using constructors:

```python
x = "1"
x = x * 5 # "11111"

x = int(x)
x = x * 5 # 5
```

Here are numerous examples of converting variables from one type to another:

```python
s1 = "GLOCAL"
s2 = "1234"
i = 1
f = 2.5
lst = ["GLOCAL", "Foundation", "of", "Canada"]
dictionary = {"Name": "Daniel", "Location": "Mars"}
sentence = "This is the first time that Daniel has written a book"

# Convert string to integer
int_s2 = int(s2)  # 1234

# Convert integer to float
float_i = float(i)  # 1.0

# Convert float to integer (truncates decimal)
int_f = int(f)  # 2

# Convert integer to string
str_i = str(i)  # "1"

# Convert list to string (joined with space)
joined_list = " ".join(lst)  # "GLOCAL Foundation of Canada"

# Convert string to list (of characters)
list_s1 = list(s1)  # ['G', 'L', 'O', 'C', 'A', 'L']

# Convert dictionary keys or values to a list
dict_keys = list(dictionary.keys())      # ['Name', 'Location']
dict_values = list(dictionary.values())  # ['Daniel', 'Mars']

# Convert list of tuples to dictionary
tuples = [("a", 1), ("b", 2)]
tuple_to_dict = dict(tuples)  # {'a': 1, 'b': 2}

# Safely convert unknown type to string by creating a new variable
safe_str = str(dictionary)  # "{'Name': 'Daniel', 'Location': 'Mars'}"

# Convert string to list of words
split_sentence = sentence.split()  
# ['This', 'is', 'the', 'first', 'time', 'that', 'Daniel', 'has', 'written', 'a', 'book']
```

---

## Working with Strings

Data comes in all shapes and configurations on the web - you will inevitably run into cases where text isn't displayed in a format that matches the receiving database. Python’s string methods make this easy:

```python
text = "   Hello, World!  \n"

clean = text.strip()                   # "Hello, World!"
lower = clean.lower()                  # "hello, world!"
parts = clean.split(",")               # ["Hello", " World!"]
joined = "-".join([p.strip() for p in parts]) # "Hello-World!"    
snippet = clean[7:12]                  # "World"
```

---

## Structuring Data

You’ll often gather multiple items of data. Lists and dictionaries let you organize them:

```python
urls = [f"https://example.gov/page/{i}" for i in range(1, 6)]
results = []  # list of dicts

for url in urls:
    record = {"url": url, "status": None}
    results.append(record)
```

A single page’s parsed data can live in a dict:

```python
park = {
    "name": "Riverside Park",
    "address": "123 River Rd.",
    "hours": "6 AM–10 PM"
}
```

This is especially helpful when scraping large amounts of similar data. For example, the process for scraping federal election candidates effectively utilizes key/value assignment before appending each entry to a CSV. Scraped values are collected, cleaned, and assigned a variable before being aggregated into a dictionary block:

```python
candidate_record = {
    "name": full_name,
    "constituency": riding,
    "role": role,
    "affiliation": sel["affiliation"],
    "image_file": photo_url,
    "bio": bio_text,
    # Dumping sub-objects as stringified json for easy flat CSV storage
    "socials": json.dumps(socials, ensure_ascii=False),
    "sources": json.dumps(sources, ensure_ascii=False)
}
```
