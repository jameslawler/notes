# Modules

Modules are a way to split up. Function can be imported between files.

```python
# Fibonacci numbers module

def fib(n):    # write Fibonacci series up to n
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
    print()

def fib2(n):   # return Fibonacci series up to n
    result = []
    a, b = 0, 1
    while a < n:
        result.append(a)
        a, b = b, a+b
    return result
```

In another file

```python
import fibo

fibo.fib(1000)
```

You can import by named approach too

```python
from fibo import fib, fib2

fib(1000)
```
