## Class Crazy thing:
- In Python, instance methods must have self as their first parameter to receive the object calling them.
- The self parameter is a reference to the current instance of the class, and is used to access variables that belong to the class.

```
class Person:
    def __init__(self, name):
        self.name = name
    def myfunc(self):
        print("Even though this print doesn't have any parameters the function should have self in it")
```
Why? Bcz: 
```

When you create an object like:
p1 = Person("John")

Python internally does:
Person.__init__(p1, "John")
```
- while static methods don’t need self because they aren’t tied to any specific object.
``` 
    @staticmethod
    def myfunc():
```

- Note: The __init__() function is called automatically every time the class is being used to create a new object.