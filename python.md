# Python 


![Python](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/219px-Python-logo-notext.svg.png)

---

## What is Python?

A high-level, general-purpose programming language designed by Guido von Rossum, first released on 1991.

Its design philosophy emphasizes code readability with the use of significant indentation.

---

## REPL

The `Read-Eval-Print-Loop` otherwise known as the interactive console.

```bash
Python 3.9.0 (default, Jul 16 2023, 00:45:39)
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> "Hello, World!"
'Hello, World!'
>>>
```

---

## Hello, World!

```python
# Create a file named hello_world.py with the following contents
print("Hello, World!")
```

Run the program via the command line with:

`python hello_world.py`

Use `python3` if you're running MacOS.

---

## Built-in Types

| Type  | Description                                                   |
| ----- | ------------------------------------------------------------- |
| int   | Integers  - whole numbers                                     |
| float | Floating point numbers - decimal values or fractional numbers |
| str   | Strings - textual data e.g. sequence of characters            |
| bool  | Boolean - represents truth value i.e. `True` or `False`       |

---

### Numeric values

```python
# Math is what you would expect
1 + 1   # => 2
8 - 1   # => 7
10 * 2  # => 20
35 / 5  # => 7.0
```

---

### Strings

```python
# Strings are created with " or '
"This is a string."
'This is also a string.'

# Strings can be added too
"Hello " + "world!"  # => "Hello world!"
```

---

### `f-strings` or Formatted String Literals

```python
band = "blink-182"
f"Pop-punk band from SoCal: {band}"
# => "Pop-punk band from SoCal: blink-182"

# Any valid expression inside the curly braces is returned 
# to the string.
```

---

### Booleans

```python
True   # => True
False  # => False

# Generally used for comparisons
1 == 1  # => True
2 == 1  # => False
1 != 1  # => False
2 != 1  # => True
```

---
### The `None` type

```python
# None is an object
# Used to denote the absence of a value
# Generally used for comparisons
None  # => None

# Use "is" when performing comparisons
"etc" is None  # => False
None is None   # => True
```

---

## Variables

```python
# Convention in naming variables is the snake_case style.
some_var = 5
some_var  # => 5

# The `=` is the assignment operator.
# The left-hand side is where the variable name is defined.
# The right-hand side is the value being assigned to the variable.
```

---

## User Input

```python
fave_music_genre = input("Favorite music genre? ")
print(fave_music_genre) # prints out user provided input

# The `input` function returns a string.
```

---

## Error Handling

```python
# Handle exceptions with a try/except block
user_input_raw = input("Please enter a number: ")
try:
	user_input_number = float(user_input_raw)
	print(user_input_number)
except ValueError:
	print(f"You entered an invalid number {user_input_raw}")
```

---
## Getting type information

```python
print(type(1)) # => <class 'int'>
print(type(1) == int) # => True

print(isinstance(1, int)) # True
```

---
## Functions

In programming, a **function** is a self-contained block of code that encapsulates a specific task or related group of tasks.

---

### Syntax

```python
# Use "def" to create new functions
def add(x, y):
    print(f"x is {x} and y is {y}")
    return x + y  # Return values with a return statement

# Calling functions with parameters
add(5, 6)  # => prints out "x is 5 and y is 6" and returns 11

# Another way to call functions is with keyword arguments
add(y=6, x=5)  # Keyword arguments can arrive in any order.
```

---

### Positional Arguments

The most straightforward way to pass arguments to a Python function is with **positional arguments** (also called **required arguments**).

```python
def format_item_price(qty, item, price):
	print(f"{qty} {item} cost ${price:.2f}")
```

---

### Keyword Arguments

Functions can also be called by specifying arguments in the form of `<keyword>=<value>`.

```python
format_item_price(qty=6, item="bananas", price=1.74)
# 6 bananas cost $1.74
```

---

### Scope

```python
# global scope
x = 5

def set_x(num):
    # local scope begins here
    # local var x not the same as global var x
    x = num    # => 43
    print(x)   # => 43
```

---
## Conditionals

---

### Boolean (or Logical) Operators

```python
# Note "and" and "or" are case-sensitive
True and False  # => False
False or True   # => True

# negate with not
not True   # => False
not False  # => True
```

---

### `and` Truth Table

| X     | Y     | X and Y |
| ----- | ----- | ------- |
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

---

### `or` Truth Table

| X     | Y     | X or Y |
| ----- | ----- | ------ |
| True  | True  | True   |
| True  | False | True   |
| False | True  | True   |
| False | False | False  |

---

### `not` Truth Table

| X     | not(X) |
| ----- | ------ |
| True  | False  |
| False | False  |

---

### Comparison Operators

```python
# Equality is ==
1 == 1  # => True
2 == 1  # => False

# Inequality is !=
1 != 1  # => False
2 != 1  # => True

# More comparisons
1 < 10  # => True
1 > 10  # => False
2 <= 2  # => True
2 >= 2  # => True
```

---

### Control Flow

```python
some_var = 5

# Here is an if statement. Indentation is significant in Python!
# This prints "some_var is smaller than 10"
if some_var > 10:
    print("some_var is totally bigger than 10.")
elif some_var < 10:    # This elif clause is optional.
    print("some_var is smaller than 10.")
else:                  # This is optional too.
    print("some_var is indeed 10.")
```

---

### Truthiness and Falsiness

What values are considered _falsy_? (Check with the `bool` function.)

- Zero values of any numeric type e.g. `0`, `0.0`
- Empty strings `""`
- Empty collections e.g. `list`, `set`, `tuple`, `dict`
- `None`
- `False`

---

## Type Hints

```python
# Support for type hints added in version 3.5.

# The function `surface_area_of_cube` takes an argument
# expected to be an instance of `float`.
# The function is expected to return an instance
# of `str`, as indicated by the `-> str` hint.
def surface_area_of_cube(edge_length: float) -> str:
    return f"The surface area is {6 * edge_length ** 2}."
```

---

## Lists

A list is an ordered collection of arbitrary objects. Lists are defined in Python by enclosing a comma-separated sequence of objects in square brackets (`[]`).

---

### Lists can contain arbitrary objects

```python
# The elements of a list can all be the same type:
a = [2, 4, 6, 8]
print(a) # [2, 4, 6, 8]

# Or the elements can be of varying types:
b = [21.42, 'foobar', 3, 4, 'bark', False, 3.14159]
print(b)
# [21.42, 'foobar', 3, 4, 'bark', False, 3.14159]
```

---

### List items can be accessed by index

```python
# Individual elements in a list can be accessed using an index in square brackets. 
# List indexing is zero-based.

a = ['foo', 'bar', 'baz', 'qux', 'quux', 'corge']
print(a[0]) # => 'foo'
print(a[2]) # => 'baz'
print(a[5]) # => 'corge'

# Looking out of bounds is an IndexError
print(a[6])  # Raises an IndexError
```

---

### Lists can be nested

```python
li = [
	1,
    [1, 2, 3]
    5,
]

print(li[1][2]) # => 3
```

---

### Lists are mutable

```python
a = ['foo', 'bar', 'baz', 'qux', 'quux', 'corge']

a[2] = 10
a[-1] = 20
print(a)
# ['foo', 'bar', 10, 'qux', 'quux', 20]
```

---

### Slices

```python
# You can look at ranges with slice syntax.
# The start index is included, the end index is not
# (It's a closed/open range for you mathy types.)
li = [1, 2, 3, 4]

# Use any combination of these to make advanced slices
# li[start : end : step]
li[1:3]  # index 1 to 3 => [2, 3]
li[2:]   # start from index 2 => [3, 4]
li[:3]   # from start until index 3  => [1, 2, 3]
li[::2]  # step size of 2 => [1, 3]
li[::-1] # reverse order => [4, 3, 2, 1]
```

---

### List Operations

```python
li = []

# Add stuff to the end of a list with append
li.append(1)    # li is now [1]
li.append(2)    # li is now [1, 2]

# Add multiple items with extend
li.extend([3, 4]) # li is now [1, 2, 3, 4]

# Remove from the end with pop
li.pop()        # => 4 and li is now [1, 2, 3]
# Or remove a specific element by providing an index 
li.pop(1)       # => 2 and li is now [1, 3]
```

---

### List Operations (cont. 1)

```python
a = ['foo', 'bar', 'baz', 'qux', 'quux', 'corge']

# Check for "membership" i.e. is item in or not in the list
print("qux" in a)      # => True
print("thud" not in a) # => True

# Returns the size of the list
print(len(a)) # 6
```

---
## Loops

---

### `while` loop

```python
"""
While loops go until a condition is no longer met.
prints:
    0
    1
    2
    3
"""
x = 0
while x < 4:
    print(x)
    x += 1  # Shorthand for x = x + 1
```

---

### `for` loop

```python
"""
For loops iterate over lists
prints:
    dog is a mammal
    cat is a mammal
    mouse is a mammal
"""
for animal in ["dog", "cat", "mouse"]:
    print(f"{animal} is a mammal")
```

---

### `for` loop (cont. 1)

```python
# updating a list "in-line"
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for index in range(len(nums)):
    nums[index] = nums[index] ** 2
print(squares)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

---

### `for` loop (cont. 2)

```python
# creating a new list
orig_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
squares = []
for number in orig_list:
    squares.append(number ** 2)
print(squares)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

---

### `range` function

```python
"""
"range(number)" returns an iterable of numbers
from zero up to (but excluding) the given number
prints:
    0
    1
    2
    3
"""
for i in range(4):
    print(i)
```

---

### `range` (cont. 1)

```python
"""
"range(lower, upper)" returns an iterable of numbers
from the lower number to the upper number
prints:
    4
    5
    6
    7
"""
for i in range(4, 8):
    print(i)
```

---

### `range` (cont. 2)

```python
"""
"range(lower, upper, step)" returns an iterable of numbers
from the lower number to the upper number, while incrementing
by step. If step is not indicated, the default value is 1.
prints:
    4
    6
"""
for i in range(4, 8, 2):
    print(i)
```

---

### `enumerate` function

```python
"""
Loop over a list to retrieve both the index 
and the value of each list item:
    0 dog
    1 cat
    2 mouse
"""
animals = ["dog", "cat", "mouse"]
for i, value in enumerate(animals):
    print(i, value)
```

```python
# updating a list "in-line"
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for index, value in enumerate(nums):
    nums[index] = value ** 2
print(squares)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

---

### Nested Loops

```python
spreadsheet = [
	[1, 2, 3],
	[4, 5, 6],
]

for row in spreadsheet:
	# the inner loop goes through all its items
	# then hands control back to the outer loop
    for cell in row:
        print(cell)

# 1
# 2
# 3
# 4
# 5
# 6
```

---

### List Comprehensions

```python

# syntax
# new_list = [expression for member in iterable]

orig_list = [1, 2, 3, 4]
squares = [num ** 2 for num in orig_list]
print(squares) # [1, 4, 9, 16]

# This is equivalent to this for loop
# orig_list = [1, 2, 3, 4]
# squares = []
# for item in orig_list:
	# squares = item ** 2
```

---

## Dictionaries, Tuples, and Sets

---

### Dictionaries

```python
# Dictionaries store mappings from keys to values
empty = {}
# Here is a prefilled dictionary
filled = {"one": 1, "two": 2, "three": 3}
```

---

### Dictionary Keys and Values

```python
# Note keys for dictionaries have to be immutable types.
# Immutable types include ints, floats, strings, tuples.
invalid = {[1,2,3]: "123"}  # => Yield a TypeError
valid = {"123": [1,2,3]}   # Values can be of any type
```

---

### Looking up values

```python
filled = {"one": 1, "two": 2, "three": 3}

# Look up values with []
print(filled["one"])  # => 1

# Check for existence of keys in a dictionary with "in"
print("one" in filled)  # => True
print(1 in filled)      # => False

# Looking up a non-existing key is a KeyError
try:
	filled["four"]  # KeyError
except KeyError:
	print("Key does not exist in dictionary.")
```

---

### Looking up values (cont. 1)

```python
filled = {"one": 1, "two": 2, "three": 3}

# Use "get()" method to avoid the KeyError
print(filled.get("one"))      # => 1
print(filled.get("four"))     # => None

# The get method supports a default argument
# when the value is missing
print(filled.get("one", 4))   # => 1
print(filled.get("four", 4))  # => 4
```

---

### Adding values

```python
filled = {"one": 1, "two": 2, "three": 3}

# this overrides existing values if the key is already present
filled.update({"four":4}) 
# {"one": 1, "two": 2, "three": 3, "four": 4}
filled["four"] = 4 # another way to add to dict

# "setdefault()" inserts into a dictionary only if the
# given key isn't present
filled.setdefault("five", 5)  # filled_dict["five"] is set to 5
filled.setdefault("five", 6)  # filled_dict["five"] is still 5

# inspect the dictionary contents
print(filled)
```

---

## Looping through keys and values

```python
gold_medal_count = {"USA": 40, "Australia": 18}

# print all keys
for key in gold_medals_dict.keys():
	print(key)

# print all values
for value in gold_medals_dict.values():
	print(value)

# print all key, value pairs
for key, value in gold_medals_dict.items():
	print(f"{key} - {value}")
```

---

### Removing items

```python
filled = {"one": 1, "two": 2, "three": 3}

# Remove keys from a dictionary with del
del filled["one"]
```

---

## I/O (Input/Output)

---

### CSV (Comma-separated values)

```csv
name,department,birthday_month
John Smith,Accounting,November
Erica Meyers,IT,March
```

---

### Reading CSV Files with `csv.reader()`

```python
import csv

with open("employee_birthday.csv") as csv_file:
    csv_reader = csv.reader(csv_file)
	next(csv_reader) # skip headers (first row)

	for row in csv_reader:
		if row:
			employee_name = row[0]
			department_name = row[1]
			birthday_month = row[2]
		    print(f"Name: {employee_name}")
			print(f"Department: {department_name}")
			print(f"Birth month: {birthday_month}")
```

---

### Using `csv.DictReader`

```python
import csv

with open("employee_birthday.csv") as csv_file:
    csv_dictreader = csv.DictReader(csv_file)
	for row in csv_dictreader:
		if row:
		    print(f"Name: {row["name"]}")
			print(f"Department: {row["department"]}")
			print(f"Birth month: {row["birthday_month"]}")
```

---

## OOP (Object-Oriented Programming)

---

### Classes

```python
# dog.py

class Dog:
	# Class attribute
    species = "Canis familiaris"

	# Constructor containing instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age

	# Instance method
    def speak(self, sound):
        return f"{self.name} says {sound}"
```

---

### Instances

```python
# instances.py

# Instance attributes are unique to each instance of an object
miles = Dog("Miles", 4)
print(miles.speak("Woof"))

buddy = Dog("Buddy", 9)
print(buddy.say("Bow wow"))

# Class attributes are the same for all instances
print(miles.species)
print(buddy.species)
```

---

## `__str__` and other *dunder methods*

```python
# instances.py

miles = Dog("Miles", 4)
print(miles)
# <__main__.Dog object at 0x00aeff70>
```

Now add the following code to `dog.py`, then try running `instances.py` again.

```python
    def __str__(self):
        return f"{self.name} is {self.age} years old"
```

---