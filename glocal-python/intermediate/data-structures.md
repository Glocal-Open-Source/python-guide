# Advanced Data Structures

As programs grow in complexity, the efficiency of data retrieval, storage, and mutation becomes increasingly paramount. While foundational Python introductions cover the semantic usage of Lists, Dictionaries, Sets, and Tuples, intermediate mastery requires an understanding of their underlying mechanics and architectural implications.

## Mutability and State
At the core of Python’s data management is the concept of mutability. Mutable objects (such as Lists and Dictionaries) can be altered after their creation, meaning their memory payload can expand or contract at runtime. Immutable objects (such as Tuples and Strings), conversely, require the allocation of entirely new memory spaces upon modification.

```python
# Strings are immutable
name = "Civic"
name += " Data" 
# Python doesn't stretch the original string; it creates an entirely new string in memory!

# Lists are mutable
records = [1, 2, 3]
records.append(4)
# The same list in memory is dynamically expanded.
```

When passing mutable objects into functions, changes made inside the function directly affect the original object because the memory reference is passed, not a copy.

```python
def clear_records(data_list):
    data_list.clear() # Mutates the referenced list!

active_users = ["Alice", "Bob"]
clear_records(active_users)

print(active_users) 
# Output: [] (The original list was destroyed)
```

## Algorithmic Complexity and Hash Maps
Dictionaries and Sets in Python are implemented dynamically as **Hash Tables**. Unlike Lists, which compute retrieval linearly by iterating through indices—a process scaling linearly with time `O(n)`—Hash Tables generate deterministic mathematical values (hashes) from keys. This structural paradigm permits associative arrays to achieve amortized constant-time `O(1)` lookups. 

If you are checking if a specific administrative badge ID exists in a registry of 10 million employees, doing so in a List will take massive computing power. Doing so in a Set is near instantaneous.

```python
import time

# A massive list and a massive set
large_list = list(range(10_000_000))
large_set = set(range(10_000_000))

# Looking up a value in a list (Slow!)
start = time.time()
exists = 9_999_999 in large_list
print("List lookup took:", time.time() - start) 
# Might take ~0.15 seconds

# Looking up a value in a set (Lightning Fast!)
start = time.time()
exists = 9_999_999 in large_set
print("Set lookup took:", time.time() - start)
# Will take ~0.000001 seconds (Virtually instantaneous)
```

## Conceptualizing Tuples as Records
While frequently introduced as mere "immutable lists," Tuples structurally represent fixed records of heterogeneous data. Where a List implies a sequence of conceptually identical items subject to iteration, a Tuple is best conceptualized as a single holistic entity. 

By adopting Tuples to pass invariant coordinate data, configuration blocks, or database row returns, developers enforce strict immutability, preventing unintended side effects across module boundaries.

```python
# A list suggests iteration of uniform items
visitor_ages = [22, 34, 45, 19]

# A tuple acts as an immutable structure or "data row"
administrative_record = ("Alice Smith", "Director", "ID-90210")

# You can securely unpack Tuples knowing they cannot be structurally altered
name, title, admin_id = administrative_record

print(f"{name} operates as {title}.")
```

### NamedTuples (Advanced)
If standard tuples become too cryptic when scaling, the `collections` module provides **NamedTuples**, mapping properties natively to immutable structures.

```python
from collections import namedtuple

# Establishing the Blueprint
Permit = namedtuple('Permit', ['id', 'zone', 'status'])

# Instantiating the immutable record
new_permit = Permit(id='ZON-99', zone='Residential', status='Active')

# Access via dot notation!
print(new_permit.zone)  # Output: 'Residential'

# Inherently Immutable:
# new_permit.status = 'Revoked'  <-- THIS WILL THROW AN ERROR
```
