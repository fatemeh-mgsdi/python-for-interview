# Introduction

Tuples are used to store multiple items in a single variable.
Tuple is one of 4 built-in data types in Python used to store collections of data, the other 3 are List, Set, and Dictionary, all with different qualities and usage.

A tuple is a collection which is ordered and unchangeable
Tuple items are ordered, unchangeable, and allow duplicate values.

Tuple items are indexed, the first item has index [0], the second item has index [1] etc.
When we say that tuples are ordered, it means that the items have a defined order, and that order will not change.
Tuples are unchangeable, meaning that we cannot change, add or remove items after the tuple has been created.
Since tuples are indexed, they can have items with the same value:


**Define type without parentheses**

```
>>> t = 1, 2, 3, 'c'

>>> type(t)

<class 'tuple'>

>>> t = 1,

>>> type(t)

<class 'tuple'>
```


```
>>> # Note about this!

>>> t = (1)

>>> type(t)

Guess what?

<class 'int'> // be aware of putting “,” so that you can have a tuple
```

**Concatenate tuples**
```
>>> ('blue', 'red') + ('yellow', 'green')

('blue', 'red', 'yellow', 'green')
```


**Unpacking tuples**
```
>>> t = ('a', 'b', 'c')

>>> x, y, z = t

>>> x

'A'

>>> y

'B'

>>> z

'c'
```

