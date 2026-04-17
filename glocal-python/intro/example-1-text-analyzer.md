# Example Problem 1: The Text Analyzer

Now that we understand basic data types, string manipulation, and control flow, let's put it all together into a practical workflow! We are going to build a simple **Text Analyzer**. 

Often when you scrape public records or dataset descriptions from civic domains (like city council minutes), the text you retrieve is messy. It has random capitalizations, leading spaces, and line breaks. In this exercise, we will take a piece of messy update text, clean it up, count the number of words, and use basic logic to evaluate it.

---

## Step 1: Receiving the Messy Data

First, we need to assign our raw data to a variable. In Python, multi-line strings are created using triple quotes `"""`.

```python
# Our raw, scraped text from a city council meeting summary
raw_text = """
    CITY COUNCIL UPDATE: New transit funding approved for the downtown district! It is 
highly Anticipated and   Ready to begin.   
"""
```

## Step 2: Cleaning the String

If we analyze the string right now, the spaces and weird capitalization will throw off our analysis. Let's use **string manipulation** to fix it.

- `.strip()` removes the extra spaces and line breaks at the very beginning and very end.
- `.lower()` makes the entire string lowercase so it's uniform.

```python
# 1. Remove outer whitespace
clean_text = raw_text.strip()

# 2. Convert to lowercase
clean_text = clean_text.lower()

print("Cleaned text:", clean_text)
# Output: city council update: new transit funding approved for the downtown district! it is highly anticipated and   ready to begin.
```

## Step 3: Analyzing the Data (Structures & Methods)

We want to know how many words are in this update. To do that, we can use the `.split()` method on our string, which cuts the string wherever there is a space and returns a **List** of those isolated words.

```python
# Split the string into a List of words
words_list = clean_text.split()

# Use the len() function to count the number of items in that list
word_count = len(words_list)

print("Total words:", word_count)
```

## Step 4: Applying Logic (Control Flow & Operators)

Finally, let's evaluate the text using an `if / elif / else` block and some **logical operators**. We want to classify the update based on its length and check if a specific keyword ("funding") was officially mentioned.

```python
# Check if a keyword exists using the 'in' membership operator
mentions_funding = "funding" in clean_text

if word_count > 20:
    category = "Long Update"
elif word_count >= 10:
    category = "Short Update"
else:
    category = "Brief Snippet"

print("Category:", category)
print("Mentions Funding?", mentions_funding)
```

---

## The Complete Script

Here is the entire program from start to finish! This is a typical, foundational Python workflow: gathering raw data, cleaning it structurally, analyzing its properties, and using logic to make a decision about it.

```python
# 1. The Data
raw_text = """
    CITY COUNCIL UPDATE: New transit funding approved for the downtown district! It is 
highly Anticipated and   Ready to begin.   
"""

# 2. The Cleanup
clean_text = raw_text.strip().lower() # You can chain methods!

# 3. The Extraction
words_list = clean_text.split()
word_count = len(words_list)

# 4. The Logic
mentions_funding = "funding" in clean_text

if word_count > 20:
    category = "Long Update"
elif word_count >= 10:
    category = "Short Update"
else:
    category = "Brief Snippet"

# 5. The Output
print(f"Text Category: {category}")
print(f"Word Count: {word_count}")
print(f"Discusses Funding: {mentions_funding}")
```

```{tip}
Notice how we chained string methods in the final script: `raw_text.strip().lower()`. Python evaluates from left-to-right, so it strips the text first, and then immediately lowercases the stripped result!
```
