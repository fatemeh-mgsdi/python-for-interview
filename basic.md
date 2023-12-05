
## What is the Python Interpreter?

Python executes the code line by line i.e., Python is an interpreter language. As we know the computer can’t understand our language, it can only understand the machine language i.e., binary language. So, the Python interpreter converts the code written in python language by the user to the language which computer hardware or system can understand. It does all the time whenever you run your python script

  

## Is everything an object in Python?

What is an object?
Different programming languages define “object” in different ways. In some, it means that all objects must have attributes and methods; in others, it means that all objects are subclassable. 
In Python, the definition is looser; some objects have neither attributes nor methods, and not all objects are subclassable. But everything is an object in the sense that __it can be assigned to a variable or passed as an argument to a function__

## Python Variables Are Pointers

In many programming languages, variables are best thought of as containers or buckets into which you put data. So in C, for example, when you write

`// C code
`int x = 4;

you are essentially defining a "memory bucket" named x, and putting the value 4 into it. In Python, by contrast, variables are best thought of not as containers but as pointers. So in Python, when you write
`int x = 4;

you are essentially defining a pointer named x that points to some other bucket containing the value 4. Note one consequence of this: because Python variables just point to various objects, there is no need to "declare" the variable, or even require the variable to always point to information of the same type! This is the sense in which people say Python is **dynamically-typed**: variable names can point to objects of any type.

There is a consequence of this _variable as pointer_ approach that you need to be aware of. If we have two variable names pointing to the same mutable object, then changing one will change the other as well! For example, let's create and modify a list
`x = [1, 2, 3]`
`y = x`

We've created two variables x and y which both point to the same object. Because of this, if we modify the list via one of its names, we'll see that the "other" list will be modified as well

```
x = [1,2,3]
y = x
y[0] = 9

print(y)
# [9,2,3]

print(x)
# [9,2,3]

```


But if you change the whole Y variable like:
`y = [9,8] `

x and y will not point to the same location again.

