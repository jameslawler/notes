# Object Oriented Programming

Object oriented programming in Python is accomplished through the use of classes, inheritance, and encapsulating data.

## Classes

Classes can be created with the `class` keyword.

```python
class Employee:
    def __init__(self, name, age):
        self.name =  name
        self.age = age

alice = Employee("Alice", 30)
bob = Employee("Bob", 32)
```

`__init__` is used as a constructor.

### Instance methods

Instance methods in python are basically public functions which can be called on the instance of the class to manipulate the class state.

```python
class Employee:
    def __init__(self, name, age):
        self.name =  name
        self.age = age

    # Instance method
    def description(self):
        return f"{self.name} is {self.age} years old"
```

Self is similar to `this` is JavaScript. It is a reference to the instance of the class.

### Static methods

Static methods are functions that are bound to the class definition and not an instance of the class. They can be created in two ways.

1. Defining the method within a class and then using the staticmethod function to make it a static method.

```python
class Calculator:

    def addNumbers(x, y):
        return x + y

# create addNumbers static method
Calculator.addNumbers = staticmethod(Calculator.addNumbers)

print('Product:', Calculator.addNumbers(15, 110))
```

2. Using the attribute @staticmethod during the initial function definition. This way is cleaner and easy to maintain.

```python
class Calculator:

    # create addNumbers static method
    @staticmethod
    def addNumbers(x, y):
        return x + y

print('Product:', Calculator.addNumbers(15, 110))
```

## Inheritance

Inheritance allows once class to take variable and function definitions from another class. The new class is the `child` class that inherits from the `parent` class.

```python
class Parent:
    hair_color = "brown"

class Child(Parent):
    hair_color = "purple"
```

In this example, the Child instance inherits from Parent, but overrides the shared variable called `hair_color` and sets it to `purple`.
