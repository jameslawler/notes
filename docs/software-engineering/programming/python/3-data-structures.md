# Data Structures

## List

Lists can contain duplicate values.

```python
colors = ['red', 'green', 'blue']
```

## Tuple

Tuples are immutable whereas lists can be changed.

```python
colors = ('red', 'green', 'blue')
```

## Set

Unordered mutable list and values in the set must be unique.

```python
A = {1, 2, 3, 4, 5}
B = {1, 2, 6, 7}

allValues = A.union(B) // equals {1, 2, 3, 4, 5, 6, 7}
```

### Set Operations

- union
- intersection (values that are in both A and B)
- difference (values that are in A but not in A and B, or vice versa)
- symmetric_difference (values that are in A or B but not in A and B)
- issuperset (checks if A contains everything also in B)
- issubset (checks the opposite, )

## Dictionary

Dictionaries are key value based.

```python
phonenumbers = {'alice': 128382929, 'bob': 8473618181}
phonenumbers['alice'] // outputs 128382929
```
