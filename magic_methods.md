### Magic or Dunder Methods

Magic methods are not meant to be invoked directly by you, but the invocation happens internally from the class on a certain action.

These are commonly used for operator overloading.

-  Built-in methods are faster than dunder ones

- If you only implement one of these special methods, choose __repr__, because when no custom __str__ is available, Python will call __repr__ as a fallback.

-The default implementation is useless (it’s hard to think of one which wouldn’t be, but yeah)

- __repr__ goal is to be unambiguous (usually debugging)
    
- __str__ goal is to be readable (The goal is to represent it in a way that a user, not a programmer, would want to read it)
    
- Container’s __str__ uses contained objects’ __repr__
    

Magic methods in Python are the special methods that start and end with the double underscores. They are also called dunder methods. Magic methods are not meant to be invoked directly by you, but the invocation happens internally from the class on a certain action. For example, when you add two numbers using the + operator, internally, the __add__() method will be called.

Built-in classes in Python define many magic methods. Use the dir() function to see the number of magic methods inherited by a class

```
>>> num=12

>>> str(num)

'12'

>>> #This is equivalent to

>>> int.__str__(num)

'12'
```

Basically, bool(x) calls x.__bool__() and uses the result. If __bool__ is not implemented, Python tries to invoke x.__len__() , and if that returns zero, bool returns False . Otherwise bool returns True