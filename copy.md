
## Copy VS Shallow Copy

A shallow copy is shallow because it only copies the object but not its child objects. Instead, the child objects refer to the original object’s child objects.

This can be demonstrated by the following example:

```
import copy

groups = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

new_groups = copy.copy(groups)
```

The shallowness means only the “outer” list gets copied. But the inner lists still refer to the lists of the original list. Due to this, changing a number in the copied list affects the original list:
```
new_groups[0][0] = 100000

print(new_groups[0])

print(groups[0])

Output:

[100000, 2, 3]

[100000, 2, 3]

  

new_groups[0] = "Something else"

print(new_groups)
print(groups)

Output:

Something else

[100000, 2, 3]
```


A deep copy creates a completely independent copy of the original object.

=> copy.deepcopy


Copies Are Shallow by Default

The easiest way to copy a list (or most built-in mutable collections) is to use the built-
in constructor for the type itself.

![Screenshot from 2023-12-05 12-53-24](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/f3194221-e222-40b9-aa26-a9b30aa5937c)


For lists and other mutable sequences, the shortcut l2 = l1[:] also makes a copy.
However, using the constructor or [:] produces a shallow copy (i.e., the outermost container is duplicated, but the copy is filled with references to the same items held by the original container). This saves memory and causes no problems if all the items are immutable. But if there are mutable items, this may lead to unpleasant surprises
