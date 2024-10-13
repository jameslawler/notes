# Algorithm

## Lambdas

Lambdas are small anonymous functions.

```python
x = lambda a : a + 10

print(x(5))
```

Lambdas can be returned.

```python
def myfunc(n):
  return lambda a : a * n

mydoubler = myfunc(2)

print(mydoubler(11))
```

## Decorators

A decorator is the implementation of a pattern that allows adding a behaviour to a function or class.

```python
def some_decorator(f):
    def wraps(*args):
        print(f"Calling function '{f.__name__}'")
        return f(args)
    return wraps

@some_decorator
def decorated_function(x):
    print(f"With argument '{x}'")
```

Other example

```python
def hello(func):
    def inner():
        print("Hello ")
        func()
    return inner

def name():
    print("Alice")

obj = hello(name)
obj()
```

## Iterators

Iterator is an object that contains countable number of values and can be looped.

Example of iterable class

```python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    return x

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```
