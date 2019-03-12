## Python3 cheatsheet

### Set up:
```python
$ brew install python3

$ mkdir project_env

# initialise environment
$ python3 -m venv ./project

# activate environment
$ source project_env/bin/activate

# your prompt will now read:
'(project_env)  ~/Development/projects'

# close environment
$ deactivate

# install packages:
# note pip3 is aliased to 'pip' in venv envs
$ pip install package_name
```
note `/projects` houses the environment, this is not where you should build your app. It just isolates the packages you install to your project.

envs to projects should have a 1-1 relationship.

### Variables:
```python
use_snake_case = 'for variables'

# print to stdout
print(use_snake_case)
```

### Most common primitives:
```python
# bool
this_is_true = True

# int / long
cats = 12
people = 7000000000

# float
pi = 3.14

# str
a_string = 'string'

# None - like nil (ruby) , or null (js)
nothing_here = None
```

### Truthy / Falsy:
```python
# all values are truthy other than:
None
False
0
0.0
0j
Decimal(0)
Fraction(0, 1)

# empty:
[]    # list
{}    # dict
()    # tuple
''    # str
b''   # bytes
set()
range(0)

# objects for which
obj.__bool__() # returns False
obj.__len__() # returns 0

```

### Booleans:
```python
True and False # -> False

True or False  # -> true

# negation
True and not False # -> True
```

### Comparison operators:
```python
2 == 2  # -> True
2 != 2  # -> False
1 < 10  # -> True
1 > 10  # -> False
2 <= 2  # -> True
2 >= 2  # -> True
```

### Strings
```python
# concatenation
string3 = string1 + string2

# string length
len(string)

# print out certain chars from string
string = "This is a string"
print(string[0:4])
# >>> This
print(string[:4])
# >>> This

# print last 5
print(string[-5:])

# up to last 5
print(string[:-5])

# Capitalise
string.caplitalize()

# Find value in string and return index
index = string.find("i")
print(index)
# >>> 2

# True if all letters
hi = "hello1"
hi.isalpha()
# >>> False

# True if all numbers
nums = "1235"
nums.isalnum()

# replace a word
string.replace('This', 'That')

# strip whitespace
string.strip()

# split into list
string.split()

```

**Formatting strings:**
```python
# % - deprecated
name = "Eric"
age = 74
"Hello, %s. You are %s." % (name, age)

# format() - deprecated
"Hello, {}. You are {}.".format(name, age)

# modern way - user f strings:
name = "Eric"
age = 74
f"Hello, {name}. You are {age}."
```

### Control flow:
```python
# if-then-else
if True:
    print("true")
elif False:
    print("false")
else:
    print("not true or false")

# for loops - iterate over lists
people = ["dave", "tom", "anne"]:
for person in people:
    print(person)

# use range to return an interable of numbers
for i in range(4):
    print(i)

for x in range(0, 10):
    # end="" - remove newlines
    print(x, ' ', end="")

>>> 0 1 2 3 4 5 6 7 8 9

# cycle through nested lists.
num_list = [[1, 2, 3],[10, 20, 30],[100, 200, 300]]
for x in range(0,3):
    for y in range(0,3):
        print(num_list[x, y])

# list comprehensions - short hand syntax for iteration
# basic sytax: [ expression for item in list if conditional ]

squares = []
# traditional loop
for x in range(10):
    squares.append(x**2)

# list comprehension syntax
squares = [x**2 for x in range(10)]

# >>> [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# while loops
x = 0
while x <= 20:
    if(x % 2 == 0):
         print(i)
    elif(i == 9):
        break
    else:
        x += 1
        continue
    x += 1
```

### User input from stdin:
```python
while 1: # infinite loop
    # or import sys and use
    # name = sys.stdin.readline()
    name = input("Name: ")
    if name == "":
        print("Ops! Retry")
    else:
        print("Hello", name)
        break  # this will break the loop
```

### Functions / methods:
- functions are first class obejects in python.
- variables declared in functions are scoped to them.

```python
# use explicit returns
def add(x, y):
    return x + y

# functions with out returns return None
def say(name):
    print(name)

a = say("ben")

print(a) # -> None

# anonymous functions are 'lambdas'
# and are only one line.
add = lambda x, y : x + y
add(2, 5) # -> 7
```

### Inbuilt compound types:

**List**
- An ordered collection (similar to an array in ruby).
```python
# definition
list = ['a', 'b', 'c']

# get it's length
len(list) # -> 3

# index access
list[1] # -> 'b'
list[-1] # -> 'c'
list[0:2] # -> ['a', 'b']

# add value to end
list.append('d')

# delete list items
del list[2] # -> ['a', 'b']

# remove specific item
list.remove("a")

# insert
list.insert(1, 'd')

# sort / reverse sort
list.sort()
list.reverse()

# delete item in list
del list[2]

# length
len(list)

# max min values
max(list)
min(list)

# concatenation
list3 = list1 + list2
```

**Tuple**
- An immutable ordered collection
- have same length and access methods as lists
- work with `min()`, `max()`, `len()` like lists.

```python
# definition
tuple = (1, 2, 3)
tuple = 1, 2, 3 # no bracket syntax

# commonly used to return multiple values:
def something(num1, num2):
    return (num1, num2)

one, two = something(one, two)

# cast to list
new_list = list(tuple)

# case list to tuple:
new_tuple = tuple(list)

```
**Dict (dictionary)**
- Unordered (key, value) mapped pairs (similar to a hash in ruby).
- can't be concatenated with `+`.
```python
# definition
numbers = {'one':1, 'two':2, 'three':3}

# Access a value via the key
numbers['two'] # -> 2

# Set a new key:value pair
numbers['ninety'] = 90

# delete entry
del numbers['one']

# length
len(numbers)

# add a key/value
numbers['four'] = 4

# retrieve a value
numbers.get('two')

# get list of keys/values
numbers.keys()
numbers.values()


```

**Set**
- Unordered collection of unique values
```python
# definition
primes = {2, 3, 5, 7}

# union: items appearing in either
primes | odds      # with an operator
primes.union(odds) # equivalently with a method

# intersection: items appearing in both
primes & odds             # with an operator
primes.intersection(odds) # equivalently with a method

# difference: items in primes but not in odds
primes - odds           # with an operator
primes.difference(odds) # equivalently with a method

# symmetric difference: items appearing in only one set
primes ^ odds                     # with an operator
primes.symmetric_difference(odds) # equivalently with a method
```

### Randomness
- for secure random numbers use the [secrets](https://docs.python.org/3/library/secrets.html#module-secrets) module.
- for pseudorandom use random:
```python
import random

# num in random range:
random.randint(a, b)
random.randrange(1,9)

# random val from list
random.choice(list)
```

### Reading / writing files

```python
# 'r' -  reading
# 'w' -  writing
# 'x' - creating and writing a new file
# 'a' - appending to a file
# 'r+' - reading and writing to the same file

file = open(path_to_file, 'r')

# all contents in single string
file.read()

# individual line
file.readline()

# array with string for each line
file.readlines()

# writing
file = open(new_path,'w')

# takes a string - you must specify newlines
file.write(content)

# close
file.close()

# delete a file
os.remove("your_file.txt")

```

### Error handling
```python
try:
    x = float(input("Your number: "))
    inverse = 1.0 / x
except ValueError:
    print("You should have given either an int or a float")
except ZeroDivisionError:
    print("Infinity")
finally:
    print("There may or may not have been an exception.")
```

- An else clause will be executed if the try clause doesn't raise an exception.

```python
try:
    fh = open(file_name, 'r')
except IOError:
    print('cannot open', file_name)
else:
    text = fh.readlines()
    fh.close()
```

### Classes and Objects:

```python
class Animal
    # __name means private - use get/setters to access
    __name = ""
    __height = 0
    __weight = 0

    # constructor function called @ Class(args)
    def __init__(self, name, height, weight, sound):
        self.__name = name
        self.__height = height
        self.__weight = weight
        self.__sound = sound

    # self needs to be explicitly passed
    # it refers to the instance.
    def set_name(self, name):
        self.__name = name

    def get_name(self):
        return self.name

    # etc. other getters and setters

    def get_type(self):
        return "animal"

    def to_string(self)
        return f"My name is {self.__name}"

```

**Instantiation**

```python
dog = Animal("fido", 20, 25, "woof")
```

**Inheritance**

```python
class Dog(Animal)
    __owner = ""

    def __init__(self, name, height, weight, sound = "Woof!", owner):
        self.__owner = owner

        # calling super class constructor
        super(Dog, self).__init__(name, height, weight, sound)

    def set_owner(self, owner):
       self.__owner = owner

    def get_owner(self)
        return self.__owner

    # etc. other getters and setters ...

    def get_type(self):
        return "dog"

    def woof
        return self.sound

    # method overriding
    def to_string(self)
        return f"My name is {self.__name} and my owner is {self.__owner}"

    # default arguments
    def woofer(self, number_of_woofs = None):
        if number_of_woofs is None:
            print(self.woof())
        else:
            print(self.woof() * number_of_woofs)

```

