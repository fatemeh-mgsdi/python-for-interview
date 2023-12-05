## Introduction

Dictionaries and lists share the following characteristics:
Both are mutable.
Both are dynamic. They can grow and shrink as needed.
Both can be nested. A list can contain another list. A dictionary can contain another dictionary. A dictionary can also contain a list, and vice versa.

Dictionaries differ from lists primarily in how elements are accessed:

List elements are accessed by their position in the list, via indexing.
Dictionary elements are accessed via keys.


Dictionaries are Python’s implementation of a data structure that is more generally known as an associative array. A dictionary consists of a collection of key-value pairs. Each key-value pair maps the key to its associated value. 

The following defines a dictionary that maps a location to the name of its corresponding Major League Baseball team:

```
>>> MLB_team = {
...     'Colorado' : 'Rockies',
...     'Boston'   : 'Red Sox',
...     'Minnesota': 'Twins',
...     'Milwaukee': 'Brewers',
...     'Seattle'  : 'Mariners'
... }

```

![Screenshot from 2023-12-05 12-47-05](https://files.realpython.com/media/t.b3e3d8f2d100.png)



**Create a dict object from tuples**
```
>>> dict_tuples = dict([("a", 0), ("b", 1), ("c", 2)])

>>> dict_tuples

{'a': 0, 'b': 1, 'c': 2}
```

**Create a dict object from two iterables**
```
>>> dict_keys = ["a", "b", "c"]

>>> dict_values = [0, 1, 2]

>>> dict_zipped = dict(zip(dict_keys, dict_values))

>>> dict_zipped

{'a': 0, 'b': 1, 'c': 2}
```

**Create a dict object from key-value assignments**
```
>>> dict_assigned = dict(a=0, b=1, c=2)

>>> dict_assigned

{'a': 0, 'b': 1, 'c': 2}
```


**Use dictionary comprehension**
```
>>> squares = {x: x*x for x in range(5)}

>>> squares

{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

**Use the one-line if-else**
```
>>> name = student["name"] if "name" in student else "Unknown"

>>> name

'John'

>>> gender = student["gender"] if "gender" in student else "Unknown"

>>> gender

'Unknown'
```


**Merge dictionaries using update()**
```
>>> d0 = {"a": 0, "b": 1}

>>> d1 = {"b": 2, "c": 3}

>>> d0.update(d1)

>>> d0

{'a': 0, 'b': 2, 'c': 3}
```


**Merge dictionaries using unpacking**
```
>>> dict0 = {0: "a", 1: "b"}

>>> dict1 = {1: "z", 2: "c"}

>>> dict2 = {**dict0, **dict1}

>>> dict2

{0: 'a', 1: 'z', 2: 'c'}
```

**Merge dictionaries using dict()**
```
>>> d0 = {"a": 0, "b": 1}

>>> d1 = {"b": 2, "c": 3}

>>> d2 = dict(d0, **d1)

>>> d2

{'a': 0, 'b': 2, 'c': 3}
```

