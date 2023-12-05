## Memory Views
The built-in memoryview class is a shared-memory sequence type that lets you handle slices of arrays without copying bytes. It was inspired by the NumPy library. 

 When should a memoryview be used? like this:
A memoryview is essentially a generalized NumPy array structure in Python itself (without the math). It allows you to share memory between data-structures (things like PIL images, SQLlite databases, NumPy arrays..)


## Choosing Between == and is
The == operator compares the values of objects (the data they hold), while is compares their identities.
We often care about values and not identities, so == appears more frequently than is in Python code.

However, if you are comparing a variable to a singleton, then it makes sense to use is.
By far, the most common case is checking whether a variable is bound to None. This is the recommended way to do it:
x is None
And the proper way to write its negation is:
x is not None

The is operator is faster than ==, because it cannot be overloaded, so Python does not have to find and invoke special methods to evaluate it, and computing is as simple as comparing two integer IDs.

## Python Lambda
A lambda function is a small anonymous function.
A lambda function can take any number of arguments, but can only have one expression.
lambda arguments : expression
x = lambda a : a + 10
print(x(5)) => 15


##Python MRO (Method Resolution Order)
When we search for an attribute in a class that is involved in python multiple inheritance, an order is followed.
First, it is searched in the current class. If not found, the search moves to parent classes. This is left-to-right, depth-first.
