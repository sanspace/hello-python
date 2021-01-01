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

  - Numbers, Strings (immutable)
  - Lists, Dictionaries and Tuples

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
| `"python"` | `'python'` |
| `'python'` | `'python'` |
| `r'python'` | `'python'` |

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
>>> a = range(5)    # [0,1,2,3,4]
>>> a.append(5)     # [0,1,2,3,4,5]
>>> a.pop()         # [0,1,2,3,4]
5
>>> a.insert(0, 42) # [42,0,1,2,3,4]
>>> a.pop(0)        # [0,1,2,3,4]
5.5
>>> a.reverse()     # [4,3,2,1,0]
>>> a.sort()        # [0,1,2,3,4]
```

---

#### Dictionaries

Hash tables, "associative arrays"

```python
d = {"duck": "eend", "water": "water"}
```

Lookup:

```python
d["duck"] # "eend"
d["back"] # raises KeyError exception
```

Delete, insert, overwrite:

```python
del d["water"]      # {"duck": "eend", "back": "rug"}
d["back"] = "rug"   # {"duck": "eend", "back": "rug"}
d["duck"] = "duik"  # {"duck": "duik", "back": "rug"}
```



#### More Dict Ops

Keys, values, items:

```python
d.keys()   # ["duck", "back"]
d.values() # ["duik", "rug"]
d.items()  # dict_items([('duck', 'duik'), ('back', 'rug')])
```

Presence check:

```python
"duck" in d # True
"spam" in d # False
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

#### Control Structures

```python
if condition:
  statements
[elif condition:
  statements]...
else:
  statements
```



#### Control Structures

```python
while condition:
    statements
```

```python
for var in sequence:
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

To use methods of the instance, call using dot notation:

```python
x.empty()	# -> True
x.push(1)	# [1]
x.empty()	# -> False
x.push("hello")   # [1, "hello"]
x.pop()		# -> "hello"	# [1]
```

To inspect instance variables, use dot notation:

```python
x.items		# -> [1]
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
  - [Official Tutorial](https://docs.python.org/3/tutorial/)
  - [Beginner's Guide](https://wiki.python.org/moin/BeginnersGuide)
  - [Hitchhiker's Guide](https://docs.python-guide.org/)
  - [Dev Guide](https://devguide.python.org/)
  - [Raymond's Talks](https://py.checkio.org/blog/5-best-speeches-mr-raymond-hettinger/)

---

#### References 📚

  - Guido's Presentations
    - [Intro to Python](https://legacy.python.org/doc/essays/ppt/lwnyc2002/intro22.ppt)
    - [Python](https://legacy.python.org/doc/essays/ppt/fannie/fannie.ppt)

---

#### Feedback 🗣️

  - This deck is on [Github](https://github.com/sanspace/hello-python). Issues/PRs are appreciated!
  - Reach out to [me](https://sanspace.in).
