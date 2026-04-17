# Example Problem 2: String Slicing

Continuing our practical walkthroughs, let's explore **String Slicing**. 

When handling administrative civic data, it is very common to encounter structured ID codes. For example, a municipal zoning permit might contain the year, the region, and an internal tracking number all mashed into one string.

In this exercise, we will take a serialized municipality permit code and use string slicing to extract those individual pieces of information.

---

## Step 1: Receiving the Data Code

First, we define our variable. Let's assume we pulled this code directly from a provincial registry spreadsheet.

```python
# A hypothetical Zoning Permit code
permit_code = "ZON-2026-ON-00A9"
```

If we look at the structure of this code, it's highly predictable: 
- `ZON-` is the prefix (Indices 0 through 3)
- `2026` is the year (Indices 4 through 7)
- `-ON-` is the province surrounded by dashes (Indices 8 through 11)
- `00A9` is the unique internal ID (Indices 12 through 15)

## Step 2: Slicing the Year

String slicing in Python uses brackets and colons: `[start:stop]`. The `start` index is inclusive, but the `stop` index is exclusive. 

To grab the year, we want to start at index 4 and stop before index 8.

```python
# Grab the 4 characters that make up the year
year = permit_code[4:8]

print("Permit Year:", year)
# Output: 2026
```

## Step 3: Slicing the Province Code

Next, we want to extract the province (`ON`). It starts at index 9 and ends before index 11. 

```python
# Grab the 2 characters representing the province
province = permit_code[9:11]

print("Province:", province)
# Output: ON
```

## Step 4: Slicing the Unique ID (Negative Indexing)

For the final tracking ID, we could count the indices from the beginning (12 to 16). However, because we know this ID is always at the very end of the string, we can use **Negative Indexing**.

In Python, `-1` represents the last character of a string, `-2` the second to last, and so on. If we leave the `stop` argument blank, Python slices all the way to the end of the string!

```python
# Grab the last 4 characters of the string
tracking_id = permit_code[-4:]

print("Tracking ID:", tracking_id)
# Output: 00A9
```

---

## The Complete Script

Here is the complete workflow. String slicing is an incredibly fast, efficient way to parse predictable data structures like file names, tracking numbers, and civic ID codes!

```python
# The raw data string
permit_code = "ZON-2026-ON-00A9"

# Slicing the string into variables
year = permit_code[4:8]
province = permit_code[9:11]
tracking_id = permit_code[-4:]

# Printing our newly isolated variables
print(f"Year: {year}")
print(f"Province: {province}")
print(f"ID: {tracking_id}")
```

```{tip}
If you ever want to grab everything from the *start* of a string up to a specific index, you can leave the start blank! For example, `permit_code[:3]` will quickly yield `"ZON"`.
```
