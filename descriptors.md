## Descriptors

Descriptors are a powerful feature in Python that allow you to define how attributes are accessed and modified on instances of a class.

A descriptor is an object that defines one or more of the following methods:

- __get__(self, instance, owner): Gets the value of the attribute from the instance of the class or its parent class.
    
- __set__(self, instance, value): Sets the value of the attribute on the instance of the class or its parent class.
    
- __delete__(self, instance): Deletes the attribute from the instance of the class or its parent class.
    

Descriptors are typically used to implement computed properties, type checking and validation, and other advanced behavior for attributes.

Here's an example of a descriptor that implements a read-only property:

![[Pasted image 20231205122217.png]]

In this example, ReadOnlyDescriptor is a descriptor that stores a value and returns it when the x attribute is accessed. Since ReadOnlyDescriptor only defines a __get__ method and not a __set__ method, the x attribute is read-only and attempting to set its value will raise an AttributeError

Visit [https://www.youtube.com/watch?v=ovsvGtWD90Y](https://www.youtube.com/watch?v=ovsvGtWD90Y)
