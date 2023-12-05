## mutable VS immutable

Objects of built-in type that are **mutable** are:

- Lists
    
- Sets
    
- Dictionaries
    
- User-Defined Classes (It purely depends upon the user to define the characteristics)


Objects of built-in type that are **immutable** are:

- Numbers (Integer, Rational, Float, Decimal, Complex & Booleans)
    
- Range
    
- Strings
    
- Tuples
    
- Frozen Sets
    
- User-Defined Classes (It purely depends upon the user to define the characteristics)


Object mutability is one of the characteristics that makes Python a dynamically typed language.

### Where can you use mutable and immutable objects?

Mutable objects can be used where you want to allow for any updates. For example, you have a list of employee names in your organizations, and that needs to be updated every time a new member is hired. You can create a mutable list, and it can be updated easily.

Immutability offers a lot of useful applications to different sensitive tasks we do in a network centered environment where we allow for parallel processing. By creating immutable objects, you seal the values and ensure that no threads can invoke overwrite/update to your data. This is also useful in situations where you would like to write a piece of code that cannot be modified. For example, a debug code that attempts to find the value of an immutable object.

***Important***
Like all, there are exceptions in the immutability in python too. Not all immutable objects are really mutable. This will lead to a lot of doubts in your mind. Let us just take an example to understand this.

Consider below tuple:

```
tup = (‘GreatLearning’,[4,3,1,2])
```

We see that the tuple has elements of different data types. The first element here is a string which as we all know is immutable in nature. The second element is a list which we all know is mutable. Now, we all know that the tuple itself is an immutable data type. It cannot change its contents. But, the list inside it can change its contents. So, the value of the Immutable objects cannot be changed but its constituent objects can. 

```
tup = ('sayMyName', [1,2,3,4],)
tup[0] = 'hi'
```

Whe you run this, you hit this error:
_TyppeError: 'tuple' object does not support item assignment_

But we can change the values of the list:

```
tup[1][0] = 9
```
