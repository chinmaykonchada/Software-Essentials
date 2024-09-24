# C++ OOPS Concepts

The main aim of OOP is to bind together the data and the functions that operate on them so that no other part of the code can access this data except that function.

![alt text](image.png)

Refer: https://gist.github.com/krishnadey30/cb64bf875f29b5a6c91f79ea38a2ba4e
## Class
It is a user-defined data type, which holds its own data members and member functions, which can be accessed and used by creating an instance of that class. A class is like a blueprint for an object.

- The only **difference between a structure and a class** is that structure members have **public access** by default and class members have **private access** by default

The **::** operator in C++ is called the **scope resolution operator**. It is used to define or access members (variables or functions) of a class, struct, or namespace that are outside the current scope

## Static Member functions in C++
A function is made static by using static keyword with function name. These functions work for the class as whole rather than for a particular object of a class.

## Object
An Object is an identifiable entity with some characteristics and behaviour. **An Object is an instance of a Class**. When a class is defined, **no memory is allocated** but when it is instantiated (i.e. an object is created) memory is allocated.

## Encapsulation
It refers to the **bundling of data (variables) and methods** (functions) in a class
- encapsulation restricts direct access to some of the object's components, which is typically achieved by setting access levels like `private`, `protected`, or `public`.

### Key Points of Encapsulation in C++
- Access Specifiers:
    - Private: Members declared as private can only be accessed within the class itself. They are hidden from outside access.
    - Protected: Members declared as protected are accessible within the class itself and in derived (child) classes.
    - Public: Members declared as public can be accessed from outside the class.
- Getters and Setters:
    - You can use public methods, known as getters (to retrieve data) and setters (to modify data), to provide controlled access to the private data members.
- Data Hiding:
    - By marking data members as private
- Advantages:
    - Data Integrity: Encapsulation helps protect the internal state of an object from unintended or harmful modifications.
    - Maintainability: Changes to the internal implementation of a class won't affect the code that uses the class.
    - Modularity: By grouping related data and functions into a class, you promote a modular structure, making it easier to manage code.
- Encapsulation also leads to **data abstraction** or hiding.

## constructor
In C++, a constructor is a **special member function** of a class that is automatically called when an **object of the class is created.** Its primary purpose is to initialize the data members of a class.
### Types of Constructors in C++:
Default Constructor:
- If you **don’t define a constructor**, C++ provides a **default constructor automatically**.
- If you define any constructor **with parameters**, the default constructor is **not provided automatically**.

Parameterized Constructor:

Copy Constructor:
- A constructor that creates a new object as a copy of an existing object.
- It takes a reference to an object of the same class as an argument and initializes the new object with the values of the existing object.

```
class Example {
public:
    int x;
    // Parameterized constructor
    Example(int val) {
        x = val;
    }

    // Copy constructor
    Example(const Example& obj) {
        x = obj.x;
    }
};

int main() {
    Example obj1(10);     // Parameterized constructor called
    Example obj2 = obj1;  // Copy constructor called
    cout << obj2.x;       // Output: 10
}
```
### Special Characteristics of Constructors:
Constructor Overloading: C++ allows multiple constructors within the same class as long as they have different signatures. This is called constructor overloading.

No Return Type: Constructors do not have a return type, not even void.

Automatic Invocation: A constructor is called automatically when an object of the class is created, and it cannot be invoked explicitly like normal member functions.

Implicit and Explicit Constructor Calls: Constructors can be called implicitly by creating an object or explicitly using the constructor syntax.

destructor: 
- A destructor in C++ is a special member function of a class that is automatically called when an object is destroyed or goes out of scope. The destructor is used to perform any necessary cleanup, such as releasing resources, closing files, or freeing dynamically allocated memory.

## virtual function
A virtual function in C++ is a member function in a base class that is declared using the keyword virtual and is intended to be overridden by derived classes

**Note:-** Base class pointer can hold a Derived class object but vice versa is not true

It allows **Runtime polymorphism**, which means that the appropriate function is selected based on the object type at runtime rather than compile time.

Using **Base Class Pointers**:
- A pointer to a derived class is a pointer of a base class pointing to a derived class, but it will hold its aspect.
- This pointer of the base class will be able to temper functions and variables of its own class and can still point to the derived class object.
- You can store a derived class object in a pointer of the base class type. This avoids object slicing and allows access to derived class members through virtual functions (polymorphism).
```
#include <iostream>
using namespace std;

// Base class
class Animal {
public:
    // Virtual function
    virtual void sound() {
        cout << "This is a generic animal sound" << endl;
    }
};

// Derived class 1
class Dog : public Animal {
public:
    // Override the virtual function
    void sound() override {
        cout << "Dog barks" << endl;
    }
};

// Derived class 2
class Cat : public Animal {
public:
    // Override the virtual function
    void sound() override {
        cout << "Cat meows" << endl;
    }
};

int main() {
    Animal* animal;  // Pointer to base class
    
    Dog dog;
    Cat cat;
    
    // Point to a Dog object
    animal = &dog;
    animal->sound();  // Output: Dog barks (due to virtual function)
    
    // Point to a Cat object
    animal = &cat;
    animal->sound();  // Output: Cat meows (due to virtual function)
    
    return 0;
}

output:
Dog barks
Cat meows
```
Explanation of the Example:
- Virtual Function in Base Class:
- Overriding in Derived Classes:
- Base Class Pointer:
- Polymorphism:
## Abstraction
Abstraction means displaying only essential information and hiding the details.

In C++, abstraction can be achieved using:

**1. Abstract Classes:** These are classes that cannot be instantiated on their own and serve as a **blueprint for derived classes**. They often contain at **least one pure virtual function**, which forces derived classes to provide specific implementations.
```
#include <iostream>
using namespace std;

// Abstract class
class Shape {
public:
    // Pure virtual function (no implementation here)
    virtual void draw() = 0;
    
    // Virtual function with a default implementation
    virtual void color() {
        cout << "Default color is black" << endl;
    }
};

class Circle : public Shape {
public:
    // Provide specific implementation of the pure virtual function
    void draw() override {
        cout << "Drawing a circle" << endl;
    }
    
    // Override the color function
    void color() override {
        cout << "The color of the circle is blue" << endl;
    }
};

class Rectangle : public Shape {
public:
    // Provide specific implementation of the pure virtual function
    void draw() override {
        cout << "Drawing a rectangle" << endl;
    }
    
    // Use the default color implementation from the Shape class
};

int main() {
    Shape* shape1 = new Circle();
    Shape* shape2 = new Rectangle();
    
    shape1->draw();   // Output: Drawing a circle
    shape1->color();  // Output: The color of the circle is blue
    
    shape2->draw();   // Output: Drawing a rectangle
    shape2->color();  // Output: Default color is black (inherited behavior)

    // Clean up dynamic memory
    delete shape1;
    delete shape2;

    return 0;
}

output:
Drawing a circle
The color of the circle is blue
Drawing a rectangle
Default color is black

Explanation:

Abstract Class (Shape):

Shape is an abstract class that defines a pure virtual function draw(). This means any derived class must implement this function. You can't create an object of Shape directly because it contains pure virtual functions, making it abstract.
Pure Virtual Function (draw()):

The draw() function is declared as a pure virtual function (= 0), meaning derived classes like Circle and Rectangle must provide their specific implementations.
Partial Abstraction (color()):

The color() function in the Shape class is a regular virtual function with a default implementation, which derived classes can override if they choose to.
Implementation in Derived Classes:

The Circle class provides its own implementation of both draw() and color(), while the Rectangle class only provides the draw() implementation and inherits the default behavior of color().
Pointer to Base Class:

Shape* shape1 = new Circle(); allows us to use a pointer to the abstract base class (Shape) to refer to derived class objects (Circle and Rectangle). This is an example of polymorphism, where the exact method called (for draw() or color()) depends on the object type at runtime.
```


**2. Interfaces:** In C++, interfaces are not defined explicitly like in some other languages (e.g., Java), but they are **achieved using abstract classes with only pure virtual functions**. These classes define the "what" (methods that must be implemented) without providing the "how" (the actual implementation).

**Conclusion:**
Abstraction in C++ allows you to define what an object does through interfaces (abstract classes) without exposing how it does it. This makes your code more modular, maintainable, and easier to extend by focusing only on the essential details and hiding unnecessary implementation complexities.

## Inheritance
## Polymorphism