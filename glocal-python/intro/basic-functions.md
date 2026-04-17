# Introduction to Functions

By now, you've learned how to store data in variables, evaluate conditions with `if` statements, and loop over data. But what happens when you need to perform the exact same logic over and over again in different parts of your script?

If you copy and paste your code 10 times, and then discover a bug, you have to find and fix that bug in 10 different places. This is where **Functions** come in.

Functions allow you to isolate a block of code, give it a name, and run it whenever you want just by calling that name. 

## Defining a Function
In Python, we create functions using the `def` keyword, short for "define."

```python
# Defining the function
def greet_user():
    print("Welcome to the municipal database!")

# Calling the function
greet_user()
# Output: Welcome to the municipal database!
```

## Passing Information to Functions (Arguments)
A function isn't very useful if it can only do one static thing. We can configure our functions to accept variables when we call them. We call these variables **Arguments** (or parameters).

```python
# This function requires a 'username' argument
def greet_user(username):
    print(f"Welcome back, {username}!")

# We pass 'Alice' into the function
greet_user("Alice") 
# Output: Welcome back, Alice!

# We can call it again with different data!
greet_user("Bob")   
# Output: Welcome back, Bob!
```

## Multiple Arguments and Defaults
You can require as many arguments as you need, separated by commas. You can also provide **Default Values** so that if the user forgets to provide data, the function won't crash.

```python
# 'department' defaults to 'General Staff' if nothing is provided
def create_profile(name, age, department="General Staff"):
    print(f"Profile Created: {name}, {age} ({department})")

# Passing all arguments
create_profile("Alice", 28, "Public Works") 
# Output: Profile Created: Alice, 28 (Public Works)

# Relying on the default argument
create_profile("Bob", 45)                   
# Output: Profile Created: Bob, 45 (General Staff)
```

## Returning Data
So far, our functions have just printed text to the screen. In the real world, functions usually process data and hand the finished product back to the main script. We do this using the `return` keyword.

When a function hits a `return` statement, it instantly ends and spits out the requested data.

```python
def calculate_tax(amount):
    tax_rate = 0.13
    total = amount + (amount * tax_rate)
    
    # Hand the final number back!
    return total

# We catch the returned data inside a new variable
final_bill = calculate_tax(100)

print(f"Your final bill is: ${final_bill}")
# Output: Your final bill is: $113.0
```

```{warning}
Remember: `print` just shows information to the human reading the screen. `return` actually passes the data back to the computer so you can use it in other calculations!
```
