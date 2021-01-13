#### Hello, Python!

🎬 [**San**](https://sanspace.in)thosh Srinivasan

---

#### What?

  - Rapid Prototyping Language
  - Easy to learn, read and use
  - An interpreted language



#### Why?

  - Productivity and Readable Code
    - reads like "pseudo-code"
  - "Life's better without braces" (Bruce Eckel)
    - and semicolons (me!)



If you're still not convinced

[What makes Python Awesome?](https://youtu.be/NfngrdLv9ZQ)

By Raymond Hettinger ([@raymondh](https://twitter.com/raymondh))



#### Comparing to other Languages

> typically **3-5 times shorter than** equivalent **Java** programs.

> often **5-10 times shorter than** equivalent **C++** code!

> Python has an applicability well beyond Perl's niche



#### Properties

  - Open Source
  - Mature (Almost as old as me!)
  - Portable
  - Automatic Memory Management
  - No core dumps

---

#### Where is it used?

  - Web Development
  - Data Analytics and Data Science
  - Machine Learning
  - GUI Apps
  - and many more...



#### Who's using it?

  - Google
  - NASA
  - NYSE
  - Yahoo
  - Redhat
  - and many more...

---

#### Class Outline 📃

- interactive "shell"
- basic types: numbers, strings
- container types: lists, dictionaries, tuples
- variables
- control structures
- functions
- classes
- modules & packages
- exceptions
- files & standard library

---

#### Interactive Shell

Demo

  - Python Shell
  - IDLE

---

#### High-level data types

  - Numbers
  - Strings
  - Lists
  - Dictionaries
  - Tuples

---

#### Numbers

```python
>>> 2 + 2
4
>>> 50 - 5*6
20
>>> (50 - 5*6) / 4
5.0
>>> 8 / 5  # division always returns a floating point number
1.6
```



```python
>>> 17 / 3  # classic division returns a float
5.666666666666667
>>>
>>> 17 // 3  # floor division discards the fractional part
5
>>> 17 % 3  # the % operator returns the remainder of the division
2
>>> 5 * 3 + 2  # result * divisor + remainder
17
```

---

#### Strings

| code | output |
| --- | --- |
| `"hi" + " san!"` | `"hi san!"` |
| `"hello" * 3` | `"hellohellohello"` |
| `"hello"[0]` | `"h"` |
| `"hello"[-1]` | `"o"` |
| `"hello"[1:4]` | `"ell"` |
| `len("hello")` | `5` |



#### More Strings

| code | output |
| --- | --- |
| `"hello" < "jello"` | `True` |
| `"e" in "hello"` | `True` |
| `"x" not in "hello"` | `True` |
| `"python"` | `'python'` |
| `'python'` | `'python'` |
| `r'python'` | `'python'` |



#### Moore Strings

| code | output |
| --- | --- |
| `"python".upper()` | `PYTHON` |
| `"python".capitalize()` | `Python` |
| `"PYTHON".lower()` | `python` |
| `"hello".count("l")` | `2` |
| `"hello".find("l")` | `2` |
|`"hello".index("el")` | `1` |

---

#### Lists

Flexible Arrays

```python
a = [99, "bottles of beer", ["on", "the", "wall"]]
```

Same operators as strings

```python
a+b, a*3, a[0], a[-1], a[1:], len(a)
```

lists vs strings; strings are immutable



Item and Slice Assignment

```python
a = [99, "bottles of beer", ["on", "the", "wall"]]

a[0] = 98 # [98, "bottles of beer", ["on", "the", "wall"]]

a[1:2] = ["bottles", "of", "beer"]
    # [98, "bottles", "of", "beer", ["on", "the", "wall"]]

del a[-1]	# [98, "bottles", "of", "beer"]
```



More List Operations

```python
>>> a = list(range(5))  # [0, 1, 2, 3, 4]
>>> a.append(5)         # [0, 1, 2, 3, 4, 5]
>>> a.pop()             # [0, 1, 2, 3, 4]
5
>>> a.insert(0, 42)     # [42, 0, 1, 2, 3, 4]
>>> a.pop(0)            # [0, 1, 2, 3, 4]
42
>>> a.reverse()         # [4, 3, 2, 1, 0]
>>> a.sort()            # [0, 1, 2, 3, 4]
```



More List Operations

```python
>>> a
[0, 1, 2, 3, 4]
>>> min(a)
0
>>> max(a)
4
>>> sum(a)
10
>>> a.count(2)
1
```

---

#### Dictionaries

Hash tables, "associative arrays"

```python
d = {"make": "Honda", "model": "CR-V"}
```

Lookup:

```python
d["make"] # "Honda"
d["brand"] # raises KeyError exception
```

Delete, insert, overwrite:

```python
del d["model"]      # {"make": "Honda"}
d["make"] = "Toyota"   # {"make": "Toyota"}
d["model"] = "Corolla"  # {"make": "Toyota", "model": "Corolla"}
```



#### More Dict Ops

Keys, values, items:

```python
d.keys()   # dict_keys(['make', 'model'])
d.values() # dict_values(['Toyota', 'Corolla'])
d.items()  # dict_items([('make', 'Honda'), ('model', 'Corolla')])
```

Presence check:

```python
"Toyota" in d      # True
"Honda" not in d  # True
```

Values of any type; keys almost any

```python
{
    "name":"Guido",
    "age":43,
    ("hello","world"):1,
    42:"yes",
    "flag": ["red","white","blue"]
}
```



#### Dict Details

  - Keys must be immutable:
    - numbers, strings, tuples of immutables
      - these cannot be changed after creation
    - reason is hashing (fast lookup technique)
    - not lists or other dictionaries
      -these types of objects can be changed "in place"
    - no restrictions on values

---

#### Tuples

```python
key = (lastname, firstname)
point = x, y, z   # parentheses optional
x, y, z = point   # unpack
lastname = key[0]
singleton = (1,)  # trailing comma!!!
empty = ()        # parentheses!
```
tuples vs. lists; tuples immutable

---

#### Control Structures - If

```python
if condition:
  statements
[elif condition:
  statements]...
else:
  statements
```

```python
x = int(input("Please enter an integer: "))

if x < 0:
    x = 0
    print('Negative changed to zero')
elif x == 0:
    print('Zero')
elif x == 1:
    print('Single')
else:
    print('More')
```



#### Control Strucures - For

```python
for var in sequence:
    statements
```

```python
# Measure some strings:
words = ['cat', 'window', 'defenestrate']
for w in words:
    print(w, len(w))

# prints as below
# cat 3
# window 6
# defenestrate 12
```



#### Control Structures

```python
while condition:
    statements
```

```python
break
continue
```



#### Indentation

In C:

```C
for (i = 0; i < 20; i++) {
    if (i%3 == 0) {
        printf("%d\n", i);
        if (i%5 == 0) {
            printf("Bingo!\n");
        }
    }
    printf("---\n");
}
```

In Python:

```python
for i in range(20):
    if i%3 == 0:
        print(i)
        if i%5 == 0:
            print("Bingo!")
    print("---")
```



#### Looping ➰

```python
for c in "python": # over a string

for item in [1, 2, 3]: # over a list

for key in {"a": 1, "b": 2}: # over a dict

for item in (1, 2, 3): # over a tuple
```

---

#### Functions

```python
def name(arg1, arg2):
    """documentation""" # optional doc string

    statements
    return expression
```



#### Example Function

```python
def gcd(a, b):
    """greatest common divisor"""

    while a != 0:
        a, b = b%a, a    # parallel assignment
    return b

>>> gcd.__doc__
'greatest common divisor'
>>> gcd(12, 20)
4
```



#### Function with default arg

```python
def say_hello(name="there"):
    """prints hello with a given or a default name"""

    print(f"Hello, {name}!")

say_hello()         # Hello, there!
say_hello("San")    # Hello, San!
```



#### Function with keyword args

```python
def average(total, count):
    """returns average by dividing total by count"""

    return total/count

average(5, 2) # 2.5
average(total=5, count=2) # 2.5
average(count=2, total=5) # 2.5
```

---

#### Classes

```python
class name:
    """documentation"""

    statements
```
or
```python
class name(base1, base2, ...):
    ...
```
Most statements are method defnitions:
```python
    def name(self, arg1, arg2, ...):
        ...
```



Example Class:

```python
class Stack:
    """A well-known data structure…"""

    def __init__(self):		# constructor
        self.items = []

    def push(self, x):
        self.items.append(x)	# the sky is the limit

    def pop(self):
        x = self.items[-1]		# what happens if it’s empty?
        del self.items[-1]
        return x

    def empty(self):
        return len(self.items) == 0	# Boolean result
```



#### Using Classes:

To create an instance, simply call the class object:

```python
x = Stack()	# no 'new' operator!
```

To use methods, use dot notation:

```python
x.empty()   # -> True
x.push(1)   # [1]
x.empty()   # -> False
x.push("hello")   # [1, "hello"]
x.pop()     # -> "hello"	# [1]
```

To inspect instance variables, use dot notation:

```python
x.items     # -> [1]
```



Subclassing

```python
class FancyStack(Stack):
    """stack with added ability to inspect inferior stack items"""

    def peek(self, n):
        """peek(0) returns top; peek(-1) returns item below that; etc."""
        size = len(self.items)
        assert 0 <= n < size	# test precondition
        return self.items[size-1-n]
```



Subclassing (2)

```python
class LimitedStack(FancyStack):
    """fancy stack with limit on stack size"""

    def __init__(self, limit):
        self.limit = limit
        FancyStack.__init__(self)   # base class constructor

    def push(self, x):
        assert len(self.items) < self.limit
        FancyStack.push(self, x)    # "super" method call
```

---

#### Modules

  - Collection of stuff in foo.py file
    - functions
    - classes
    - variables



Importing modules:
```python
import re;
print(re.match("[a-z]+", s))

# or

from re import match;
print(match("[a-z]+", s))
```

Import with rename:
```python
import re as regex

# or

from re import match as m
```

---

#### Packages 📦

  - Collection of modules in directory
  - Must have `__init__.py` file
  - May contain subpackages



Import syntax:
```python
from P.Q.M import foo;
print(foo())

from P.Q import M;
print(M.foo())

import P.Q.M;
print(P.Q.M.foo())

import P.Q.M as M;
print(M.foo()) # new
```

---

#### Catching Exceptions

```python
def foo(x):
    return 1/x

def bar(x):
    try:
        print(foo(x))
    except ZeroDivisionError as err:
        print("Can't divide by zero:", err)

bar(0)
```



#### try-finally cleanup

```python
f = open(file)

try:
    process_file(f)
finally:
    f.close()   # always executed

print("OK") # executed on success only
```



#### Raising Exceptions

```python
raise IndexError  # shorthand for 'raise IndexError()'

raise IndexError("k out of range")

try:
    something
except:
    print("Oops!")
    raise # reraise
```

---

#### File Objects

```python
f = open(filename, mode)
```

  - mode can be `r`, `w`, `a` (like C stdio); default `r`
  - append `b` for text translation mode
  - append `+` for read/write open



#### Reading Files

```python
with open('file.txt') as f:
    for line in f:
        print(line)
```

---

#### Standard Library 🗃️

  - Operating System Interface (`import os`)
  - System (`import sys`)
  - RegEx (`import re`)
  - Testing (`import unittest`)



#### More standard library 🗃️

  - Pretty Print (`import pprint`)
  - Logging (`import logging`)
  - Collections (`import collections`)
  - itertools (`import itertools`)

---

### Beyond Basics 🎟️

  - Third Party Packages (`pip`, `PyPI`)
  - Comprehensions
  - Iterators
  - Generators
  - Magic Methods
  - Decorators

---

#### ❔

Questions?

---

#### Resources 🔖

  - [Official Docs](https://docs.python.org/3/)
  - [Beginner's Guide](https://wiki.python.org/moin/BeginnersGuide)
  - [Hitchhiker's Guide](https://docs.python-guide.org/)
  - [Dev Guide](https://devguide.python.org/)
  - [Raymond's Talks](https://py.checkio.org/blog/5-best-speeches-mr-raymond-hettinger/)

---

#### References 📚

  - Guido's Presentations
    - [Intro to Python](https://legacy.python.org/doc/essays/ppt/lwnyc2002/intro22.ppt)
    - [Python](https://legacy.python.org/doc/essays/ppt/fannie/fannie.ppt)
  - [Official Tutorial](https://docs.python.org/3/tutorial/)
  - [Essential Python for DS](https://towardsdatascience.com/essential-python-every-data-scientist-should-know-in-2021-65e571c20d19)

---

#### Feedback 🗣️

  - This deck is on [Github](https://github.com/sanspace/hello-python). Issues/PRs are appreciated!
  - Reach out to [me](https://sanspace.in).
