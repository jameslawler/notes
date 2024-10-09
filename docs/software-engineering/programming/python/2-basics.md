# Basics

## Variable declarations

Assignment is done using the `=` operator.

## Data types

Data types are set to variables on the first value that is assigned.

Text

- str

Numeric

- int
- float
- complex

Sequence

- list
- tuple
- range

Mapping

- dict

Set

- set
- frozenset

Boolean

- bool

Binary

- bytes
- bytearray
- memoryview

None

- NoneType

Examples:

```python
x = "Hello World"
x = 20
x = 20.5
```

Specific data types can be set

```python
x = str("Hello World")
x = int(20)
x = float(20.5)
```

## Functions

Functions are defined using the `def` keyword and indentation is used to show code blocks.

```python
def my_function():
  print("Hello World")

my_function()
```

Parameters are passed as like in any other language.

```python
def my_function(name):
  print("Hello " + name)

my_function("Bob")
```

Arbitary number of arguments.

```python
def my_function(*names):
  print("The fisrt names is: " + names[0])

my_function("Alice", "Bob", "Catherine")
```

## Conditionals

### If statement

A simple way to run code if a condition is met

```python
if <expression>:
  <statement>
```

### Else and elif

Else is used to run statements if the first condition is false

```python
if <expression>:
  <statement_if_true>
else
  <statement_if_false>
```

Elif is used to combine if statements

```python
if <expression>:
  <statement_if_true>
elif <expression_two>
  <statement_if_two>
else
  <statement_if_false>
```

## Loops

### While loop

Run statements while a condition is true.

```python
while <expression>:
  <statement>
```

### For loop

For loops run for a set number of iterations.

```python
for <iterator_var> in <sequence>:
  <statement>
```

Example.

```python
n = 4
for i in range(0, n):
  print(i)
```

`continue` can be used to go to the next iteration in the for loop.
`break` can be used to exit the for loop.
`pass` is a statement that does nothing in each loop iteration.
