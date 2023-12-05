# Introduction

List items are ordered, changeable, and allow duplicate values.
List items are indexed, the first item has index [0], the second item has index [1] etc.
When we say that lists are ordered, it means that the items have a defined order, and that order will not change.
If you add new items to a list, the new items will be placed at the end of the listWhen we say that lists are ordered, it means that the items have a defined order, and that order will not change.
If you add new items to a list, the new items will be placed at the end of the list.
The list is changeable, meaning that we can change, add, and remove items in a list after it has been created.


**Reverse list**

```
>>>Students = ['Harsh', 'Andrew', 'Danny']

>>>Students.reverse()

>>>Students

[‘Danny’, ‘Andrew’, ‘Harsh’]
```

**Find index of element**
```
>>>Students=['Harsh','Andrew','Danny','Ritesh','Meena']

>>>Students.index('Danny')

2
```


**Copy list**
```
>>>my_foods = ['pizza', 'falafel', 'carrot cake']

>>>friend_foods = my_foods[:]

>>>my_foods

>>>friend_foods

 [‘pizza’, ‘falafel’, ‘carrot cake’]

 [‘pizza’, ‘falafel’, ‘carrot cake’]

P.S = > The point to two different locations
```

**Concatenating a list of strings to form a string**
```
>>>my_foods = ['pizza', 'falafel', 'carrot cake']

>>>my_foods_csv=",".join(my_foods)

>>>my_foods_csv

pizza,falafel,carrot cake
```

**Removing duplicates**
```
My_list =[‘a’, ’b’, ’c’, ’b’, ’a’]

Mylist = list(dict.fromkeys(My_List))
```


**Filtering a list**
```
def my_filter(n):

    if n > 20:

        return n

My_list = list(filter(filter_function , my_list))
```


**Modifying list**
```
def squaring(n):

    return n**2

My_list = list(map(function,iterable))
```




## len vs __len__()
(a) For some operations, prefix notation just reads better than postfix — prefix (and infix!) operations have a long tradition in mathematics which likes notations where the visuals help the mathematician thinking about a problem. Compare the easy with which we rewrite a formula like x*(a+b) into x*a + x*b to the clumsiness of doing the same thing using a raw OO notation.
(b) When I read code that says len(x) I know that it is asking for the length of something. This tells me two things: the result is an integer, and the argument is some kind of container. To the contrary, when I read x.len(), I have to already know that x is some kind of container implementing an interface or inheriting from a class that has a standard len(). 
In other words, len is not called as a method because it gets special treatment as part of the Python data model, just like abs . But thanks to the special method __len__ , you can also make len work with your own custom objects.


## Listcomps No Longer Leak Their Variables
In Python 2.x, variables assigned in the for clauses in list comprehensions were set in the surrounding scope, sometimes with tragic consequences. See the following Python.

![Screenshot from 2023-12-05 12-45-51](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/a7b9d319-1bbe-4f24-9ba7-9e30550586ab)


As you can see, the initial value of x was clobbered. This no longer happens in Python3.
List comprehensions, generator expressions, and their siblings set and dict comprehensions now have their own local scope, like functions. Variables assigned within the expression are local, but variables in the surrounding scope can still be referenced. Even better, the local variables do not mask the variables from the surrounding scope.

![Screenshot from 2023-12-05 12-47-05](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/e32b8970-d47f-418a-a897-32b1eaa59166)



## Listcomps Versus map and filter
Listcomps do everything the map and filter functions do, without the contortions of the functionally challenged Python lambda.

![Screenshot from 2023-12-05 12-47-59](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/1dbbcaad-05e9-4b2f-976f-07fcc9a3d8ac)


list comprehension vs filter : When we are using a list with a small number of elements, then the list comprehension and filter method have almost the same execution speed. But when the list size is huge, then list comprehension is slightly faster than a filter. This is because list comprehension directly generates a list, whereas filter function returns an iterable object, which is then converted to a list. However, if we don't convert the object to a list, then the execution 
time is almost negligible.

## Map vs List Comprehension:
Without lambda: Map is faster than List Comprehension when function is already defined in case of map function
With lambda in map: List comprehension is better than map function when we don't define the function beforehand and use lambda expression inside map.


## map vs. for loop python speed 

Map and For Loop can produce the same output, but they work differently. Inside "for loop", we iterate a variable fed to an expression within an Iterable. Whereas "Map" is used to map a function to all the elements of the given Iterable. It is a one-lined code configuration of "for loop". So, in map vs for loop python speed, map wins.
In theory, if we had a compiler/interpreter that was smart enough to make use of multiple CPUs/processors, then the map could be implemented faster as the different operations on each item could be done in parallel. I don't think this is the case at present, however.


## List VS Arrays
The list type is flexible and easy to use, but depending on specific requirements, there are better options. For example, if you need to store 10 million floating-point values, an array is much more efficient, because an array does not actually hold full-fledged float objects, but only the packed bytes representing their machine values—just like an array
in the C language. On the other hand, if you are constantly adding and removing items from the ends of a list as a FIFO or LIFO data structure, a deque (double-ended queue) works faster.

An array is also a data structure that stores a collection of items. Like lists, arrays are ordered, mutable, enclosed in square brackets, and able to store non-unique items.
But when it comes to the array's ability to store different data types, the answer is not as straightforward. It depends on the kind of array used.
To use arrays in Python, you need to import either an array module or a NumPy package

The Python array module requires all array elements to be of the **same type**

![Screenshot from 2023-12-05 12-49-38](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/eb01eff0-f622-495a-b4fe-3b177e931637)


## Differences between lists and arrays in Python:

Arrays need to be declared. Lists don't, since they are built into Python. In the examples above, you saw that lists are created by simply enclosing a sequence of elements into square brackets. Creating an array, on the other hand, requires a specific function from either the array module (i.e., array.array()) or NumPy package (i.e., numpy.array()). Because of this, lists are used more often than arrays.
Arrays can store data very compactly and are more efficient for storing large amounts of data.
Arrays are great for numerical operations; lists cannot directly handle math operations. For example, you can divide each element of an array by the same number with just one line of code. If you try the same with a list, you'll get an error.

![Screenshot from 2023-12-05 12-50-35](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/dac75f69-4d39-4223-83b3-e8e5054b5192)


So, when should you use a list and when should you use an array?

If you need to store a relatively short sequence of items and you don't plan to do any mathematical operations with it, a list is the preferred choice. This data structure will allow you to store an ordered, mutable, and indexed sequence of items without importing any additional modules or packages.
If you have a very long sequence of items, consider using an array. This structure offers more efficient data storage.
If you plan to do any numerical operations with your combination of items, use an array. Data analytics and data science rely heavily on (mostly NumPy) arrays.







