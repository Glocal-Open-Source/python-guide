# Example Problem 3: Refactoring with Functions

As your scripts become more advanced, you will likely encounter situations where you need to process data exactly the same way multiple times. If you don't use functions, your code will quickly become a bloated, unreadable mess. 

This process of redesigning your code to be cleaner and more efficient without changing its actual output is called **Refactoring**.

In this example, we assume we are pulling raw text entries from three different municipal zoning databases. We need to clean each text string, extract the first word, and capitalize it.

---

## 🚫 The Unpythonic Way (Without Functions)
If we tackle this problem procedurally without using functions, we end up copying and pasting the same four lines of logic repeatedly.

```python
# Our dirty data sources
zoning_a = "   residential - Approved  "
zoning_b = "COMMERCIAL - Denied"
zoning_c = "  inDUSTrial - Pending review "

print("--- Processing Data ---")

# Processing Source A
clean_a = zoning_a.strip().lower()
words_a = clean_a.split()
final_a = words_a[0].capitalize()
print(f"Zone A Record: {final_a}")

# Processing Source B
clean_b = zoning_b.strip().lower()
words_b = clean_b.split()
final_b = words_b[0].capitalize()
print(f"Zone B Record: {final_b}")

# Processing Source C
clean_c = zoning_c.strip().lower()
words_c = clean_c.split()
final_c = words_c[0].capitalize()
print(f"Zone C Record: {final_c}")
```

### The Problem
If your boss suddenly asks you to extract the *last* word instead of the first word, you will have to manually find and update the code block 3 different times. If you had 500 zoning entries, you'd have to edit 500 blocks of code! 

---

## ✅ The Pythonic Way (Refactored with Functions)
Let's refactor this. By isolating the logic inside a single `def` block, we only write the complex instructions *once*.

```python
# Our dirty data sources
zoning_a = "   residential - Approved  "
zoning_b = "COMMERCIAL - Denied"
zoning_c = "  inDUSTrial - Pending review "

# 1. Define the logic ONCE!
def extract_zoning_type(raw_text):
    """Cleans a messy string and returns the capitalized first word."""
    clean_text = raw_text.strip().lower()
    words_list = clean_text.split()
    return words_list[0].capitalize()

print("--- Processing Data ---")

# 2. Call the function cleanly whenever we need it!
print(f"Zone A Record: {extract_zoning_type(zoning_a)}")
print(f"Zone B Record: {extract_zoning_type(zoning_b)}")
print(f"Zone C Record: {extract_zoning_type(zoning_c)}")
```

### The Benefit
The output is identical, but the code is half as long. If we suddenly need to change the logic, we only edit the `extract_zoning_type` function itself. The entire rest of the script automatically updates to use the new logic. 

```{tip}
Whenever you find yourself copying and pasting an explicit block of code to use somewhere else in your file... **stop**. You almost certainly need to write a function instead!
```

```{note}
Did you just work through this practice problem? That counts as volunteer training! Head to [volunteer.youcount.ca](https://volunteer.youcount.ca) and log your hours so your learning is officially recognized!
```
