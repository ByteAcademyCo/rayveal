# Introduction to Python

---

## Overview

* Hello World
* Data Types
* Control Flow
* Functions
* Complexity Theory

===

## Hello World
* Running Python
* Variables and Objects
* Input/Output

---

## Running Python
### Invoking the Interpreter
* Through command prompt
```
python hello-world.py
```

---

## Running Python
### Using an editor
* Definition window
* Interaction window

---

## Variables and Objects
### Name bindings (=)
```Python
x = 1337
```
* This creates a binding between a name ```x``` and a reference to an object ```1337```
  * How this ```name->reference to object``` binding happens will be discussed in the Python internals section
* The object consists of 3 parts
  * A value
  * An ID
  * A type

---

### Value
* To access the value of an object, simply type its' name
```Python
x = 1337
print(x)
```

---

### ID
* To access the ID of an object, use the ```id``` function
* Functions in Python are called very similar to how they are called in Math
```Python
x = 1337
id(x)
x = 1338
id(x)
```

---

### Type
* To access the type of an object, use the ```type``` function
* ```x = 1``` declares x to reference an ```int``` type
* There also exists the ```str``` (String) type to allow us to handle text
```Python
x = 1
type(x)
x = "Hello World"
type(x)
```

## Input/Output
### input, print
* Python provides a way for your program to take in information from the user and display information to the user
* Done through the ```input``` and ```print``` functions
```Python
x = "Please enter your name: "
y = input(x)
z = f"Hello {user_input}, nice to meet you!"
print(z)
```

---

### Styling your coded
* Python recommends following a specific [style guide](https://www.python.org/dev/peps/pep-0008/) for how code should "look"
* Includes naming convention for variables, spacing and indentation rules and much more
* Allows for Python code to be consistent and scallable throughout organizations
```Python
message = "Please enter your name: "
user_input = input(message)
user_output = f"Hello {user_input}, nice to meet you!"
print(user_output)
```

---

### Code Modularization
* We typically want to divide our code into separate parts, each conerned with independent tasks
* Code modularization can be as simple as a space between lines of code or as complex as dividing code into separate files
```Python
message = "Please enter your name: "
user_input = input(x)

user_output = f"Hello {user_input}, nice to meet you!"
print(user_output)
```
* The generated slide deck based on aggregation of the sections

===

# Data Types
* Number
* Boolean
* String
* List
* Tuple
* Dictionary
* Set

---

## Number (```int```, ```float```)
### Method - Initialization
```Python
x = 5
```

---

### Method - 6 Arithmetic Operators
```Python
3 + 2 # 5
3 - 2 # -1
3 * 2 # 6
3 / 2 # 1.5
3 ** 2 # 9
3 % 2 # 1
```

---

### Method - 6 Comparison Operators
```Python
2 == 1 # False
2 != 1 # True
2 < 1 # False
2 <= 1 # False
2 > 1 # True
2 >= 1 # True
```

---

### Method - 2 Type Casters
```Python
int(3 / 2) # 1
float(3 * 2) # 6.0
```

---

### Feature - Immutable
```Python
x = 1111
id(x)
x += 1
id(x)
y = 1112
id(y)
```

---

## Boolean (```bool```)
### Method - Initialization
```Python
x = True
y = False
z = 1 <= 2
```

---

### Method - Boolean Operators (3)
```Python
1 <= 2 and 2 >= 3 # False
1 <= 2 or 2 >= 3 # True
not(2 >= 3) # True
```

---

### Feature - Immutable
```Python
x = True
y = True
print(id(x))
print(id(y))
```

---

### Feature - Short Circuiting
```Python
True or False # True (without looking at False)
1 <= 2 or 1/0 # True (without looking at 1/0)
1 <= 2 and 1/0 # ZeroDivisionError
1 >= 2 and 1/0 # False (without looking at 1/0)
1 >= 2 or 1/0 # ZeroDivisionError
```

---

### Feature - Lazy Evaluation
```Python
1 or 0 # 1
1 and 0 # 0
1 or 1/0 # 1
1 and 1/0 # ZeroDivisionError
```

---

## String (```str```)
### Method - Initialization
```Python
x = "hello world"
```

---

### Method - ```len```
```Python
len("hello world") # 11
```

---

### Feature - Immutable
```Python
x = "hello world"
y = "hello world"
print(id(x))
print(id(y))
x = "hi"
id(x)
```

---

### Feature - Indexable
```Python
x = "hello world"
print(x[1]) # 'e'
x[1] = 'i' # TypeError
```

---

### Feature - Iteration
```Python
x = "hello world"
for i in x:
 print(i)
```

---

### Feature - Slicing
```Python
x = "hello world"
x[1:8]
x[1:8:2]
x[1:8:-1]
x[-1:-8:1]
```

---

## List (```list```)
### Method - Initialization
```Python
x = [1, 2, 3]
```

---

### Method - ```len```
```Python
len([1, 2, 3]) # 3
```

---

### Method - ```append```, ```remove```, ```+```
```Python
x = [1, 2, 3]
x.append(4)
print(x)
x.remove(3)
print(x)
y = x + [1, 2, 3]
```

---

### Method - ```index```, ```insert```, ```pop```
```Python
x = [1, 2, 3]
x.index(2)
x.index(20) # ValueError
x.insert(4, 2) 
print(x)
x.insert(10, 100)
print(x)
```

---

### Feature - Mutable
```Python
x = [1, 2, 3]
print(id(x))
x.append(4)
print(id(x))
```

---

### Feature - Iteration
```Python
x = [1, 2, 3]
for i in x:
 print(i)
```

---

### Feature - Slicing
```Python
x = [1, 2, 3]
x[1:3]
x[1:3:2]
x[-1:-8:-1]
```

---

## Tuple (```tuple```)
### Method - Initialization
```Python
x = (1, 2, 3)
y = (1, )
```

---

### Method - ```len```
```Python
len((1, 2, 3)) # 3
```

---

### Feature - Immutable
```Python
x = (1, 2, 3)
x[1] = 5 # TypeError
```

---

### Feature - Iteration
```Python
x = (1, 2, 3)
for i in x:
 print(i)
```

---

### Feature - Slicing
```Python
x = (1, 2, 3)
x[1:3]
x[1:3:2]
x[-1:-8-1]
```

---

## Dictionary (```dict```)
### Method - Initialization
```Python
x = {1:1, 2:2, 3:3}
```

---

### Method - ```len```
```Python
x = {1:1, 2:2, 3:3}
len(x) # 3
```

---

### Method - ```get```, ```set```
```Python
x = {1:1, 2:2, 3:3}
x[1] # "1"
x[3] = "Hello"
```

---

### Method - ```keys```, ```values```, ```items```
```Python
x = {1:"1", 2:"2", 3:"3"}
keys = x.keys()
values = x.values()
items = x.items()
for i in keys:
 print(i)
for i in values:
 print(i)
for i in items:
 print(i)
```

---

### Feature - Mutable Container
```Python
x = {1:1, 2:2, 3:3}
x[4] = "hi"
print(x)
```

---

### Feature - Immutable Keys
```Python
x = {1:1, 2:2, 3:3}
x[4] = "hi"
x["hi"] = 4
x[["hi"]] = 4 # TypeError
```

---

### Feature - Mutable Values
```Python
x = {1:1, 2:2, 3:3}
x[4] = ["hi"]
```

---

### Feature - Iteration
```Python
x = {1:1, 2:2, 3:3}
for i in x:
 print(i)
```

---

## Set (```set```)
### Method - Initialization
```Python
x = {1, 2, 3}
```

---

### Method - ```len```
```Python
x = {1, 2, 3}
len(x) # 3
```

---

### Method - ```&```, ```|```, ```/```
```Python
x = {1, 2, 3}
y = {2, 3, 4}
x & y # {2, 3}
x | y # {1, 2, 3, 4}
x / y # {1}
```

---

### Method - ```add```, ```remove```
```Python
x = {1, 2, 3}
x.add(5) # {1, 2, 3, 5}
x.remove(3) # {1, 2, 5}
```

---

### Feature - Mutable Container
```Python
x = {1, 2, 3}
x.add(5)
```

---

### Feature - Immutable Keys
```Python
x = {1, 2, 3}
x.add([1, 2]) # TypeError
```

---

### Feature - Iteration
```Python
x = {1, 2, 3}
for i in x:
 print(i)
```
