# Control Flow & Logic

To write programs that actually make decisions, you need control flow strings (like `if` statements) and the logic to back them up (like operators). This is how your code branches out to handle different scenarios automatically.

## Basic Python Operators and Logic Table

Comparisons and logical operators are critical for `if / else` flows and loop breaks.

### Arithmetic
| Operator | Name | Example |
| :---: | :--- | :--- |
| `+` | Addition | `5 + 2  # 7` |
| `-` | Subtraction | `5 - 2  # 3` |
| `*` | Multiplication | `5 * 2  # 10` |
| `/` | Division (float result) | `5 / 2  # 2.5` |
| `//` | Floor Division (rounds down) | `5 // 2  # 2` |
| `%` | Modulus (remainder) | `5 % 2  # 1` |
| `**`| Exponentiation | `2 ** 3 # 8` |

### Comparison
| Operator | Name | Example |
| :---: | :--- | :--- |
| `==` | Equal to | `5 == 5  # True` |
| `!=` | Not equal to | `5 != 3  # True` |
| `>` | Greater than | `5 > 3   # True` |
| `<` | Less than | `5 < 3   # False` |
| `>=` | Greater than or equal | `5 >= 5  # True` |
| `<=` | Less than or equal | `3 <= 5  # True` |

### Logical
| Operator | Name | Example |
| :---: | :--- | :--- |
| `and` | True if both are True | `True and False  # False` |
| `or` | True if at least one is True| `True or False   # True` |
| `not` | Inverts the Boolean value | `not True        # False` |

### Membership
| Operator | Name | Example |
| :---: | :--- | :--- |
| `in` | True if value is in collection | `'a' in 'cat'     # True` |
| `not in`| True if value not in collection| `'z' not in 'cat' # True` |

### Identity
```{note}
The `is` and `is not` operators check if variables point to the exact same object in memory, not necessarily if they have the same value.
```
```python
>>> a = 5
>>> b = 3
>>> a is b
False

>>> a is not b
True
```

```{tip}
- Comparison and logical operators are the backbone of **`if`** statements and **`while`** loops.
- Use parentheses `()` to explicitly control the order of evaluation in complex expressions!
```
