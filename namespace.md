## Namespace

in a Python program, there are four types of namespaces:

1. Built-In
    
2. Global
    
3. Enclosing
    
4. Local

The built-in namespace contains the names of all of Python’s built-in objects. These are available at all times when Python is running. You can list the objects in the built-in namespace with the following command:



```
>>> dir(__builtins__)

['ArithmeticError', 'AssertionError', 'AttributeError',  'BaseException','BlockingIOError', 'BrokenPipeError', 'BufferError',

 'BytesWarning', 'ChildProcessError', 'ConnectionAbortedError',  'ConnectionError', 'ConnectionRefusedError', 'ConnectionResetError',  'DeprecationWarning', 'EOFError', 'Ellipsis', 'EnvironmentError',  'Exception', 'False', 'FileExistsError', 'FileNotFoundError',  'FloatingPointError', 'FutureWarning', 'GeneratorExit', 'IOError',  'ImportError', 'ImportWarning', 'IndentationError', 'IndexError',  'InterruptedError', 'IsADirectoryError', 'KeyError', 'KeyboardInterrupt',

 'LookupError', 'MemoryError', 'ModuleNotFoundError', 'NameError', 'None',  'NotADirectoryError', 'NotImplemented', 'NotImplementedError', 'OSError',  'OverflowError', 'PendingDeprecationWarning', 'PermissionError', 'ProcessLookupError', 'RecursionError', 'ReferenceError', 'ResourceWarning',  'RuntimeError', 'RuntimeWarning', 'StopAsyncIteration', 'StopIteration',  'SyntaxError', 'SyntaxWarning', 'SystemError', 'SystemExit', 'TabError',  'TimeoutError', 'True', 'TypeError', 'UnboundLocalError',  'UnicodeDecodeError', 'UnicodeEncodeError', 'UnicodeError',  'UnicodeTranslateError', 'UnicodeWarning', 'UserWarning', 'ValueError',  'Warning', 'ZeroDivisionError', '_', '__build_class__', '__debug__',  '__doc__', '__import__', '__loader__', '__name__', '__package__',

 '__spec__', 'abs', 'all', 'any', 'ascii', 'bin', 'bool', 'bytearray',  'bytes', 'callable', 'chr', 'classmethod', 'compile', 'complex',  'copyright', 'credits', 'delattr', 'dict', 'dir', 'divmod', 'enumerate',  'eval', 'exec', 'exit', 'filter', 'float', 'format', 'frozenset',

 'getattr', 'globals', 'hasattr', 'hash', 'help', 'hex', 'id', 'input',  'int', 'isinstance', 'issubclass', 'iter', 'len', 'license', 'list',  'locals', 'map', 'max', 'memoryview', 'min', 'next', 'object', 'oct',  'open', 'ord', 'pow', 'print', 'property', 'quit', 'range', 'repr',

 'reversed', 'round', 'set', 'setattr', 'slice', 'sorted', 'staticmethod',  'str', 'sum', 'super', 'tuple', 'type', 'vars', 'zip']
```

The Python interpreter creates the built-in namespace when it starts up. This namespace remains in existence until the interpreter terminates

  

The global namespace contains any names defined at the level of the main program. Python creates the global namespace when the main program body starts, and it remains in existence until the interpreter terminates.

Strictly speaking, this may not be the only global namespace that exists. The interpreter also creates a global namespace for any module that your program loads with the import statement. 

As you learned in the previous tutorial on functions, the interpreter creates a new namespace whenever a function executes. That namespace is local to the function and remains in existence until the function terminates.

Functions don’t exist independently from one another only at the level of the main program.

```
>>> def f():

...    print('Start f()')

	   def g():

	        print('Start g()')

			print('End g()')

			return

		g()

		print('End f()')

		return

>>> f()

# Outputs:

Start f()

Start g()

End g()

End f()
```
In this example, function g() is defined within the body of f(). Here’s what’s happening in this code:

- Lines 1 to 12 define f(), the enclosing function.
    
- Lines 4 to 7 define g(), the enclosed function.
    

When the main program calls f(), Python creates a new namespace for f(). Similarly, when f() calls g(), g() gets its own separate namespace. The namespace created for g() is the local namespace, and the namespace created for f() is the enclosing namespace.

Each of these namespaces remains in existence until its respective function terminates. Python might not immediately reclaim the memory allocated for those namespaces when their functions terminate, but all references to the objects they contain cease to be valid


![[Pasted image 20231205115929.png]]

This is the LEGB rule as it’s commonly called in Python literature (although the term doesn’t actually appear in the [Python documentation](https://docs.python.org/3)). The interpreter searches for a name from the inside out, looking in the local, enclosing, global, and finally the built-in scope.
