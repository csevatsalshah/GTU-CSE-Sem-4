# OOP Mid-2 Unit 5
## Q-1) Explain inheritance with its types and give suitable example.

**Answer:**

Inheritance is a fundamental concept in object-oriented programming (OOP) where a class (subclass or derived class) can inherit properties and behaviors (methods) from another class (superclass or base class). It facilitates code reuse, enhances modularity, and allows for the creation of hierarchical relationships between classes.

**Types of Inheritance:**

1. **Single Inheritance:** In single inheritance, a subclass inherits from only one superclass. It forms a one-to-one relationship between classes.

2. **Multiple Inheritance:** Multiple inheritance occurs when a subclass inherits properties and behaviors from more than one superclass. This is less common and can lead to ambiguity issues if not handled properly.

3. **Multilevel Inheritance:** Multilevel inheritance involves a chain of inheritance where a subclass inherits from a superclass, and then another subclass inherits from the first subclass, forming a hierarchical structure.

4. **Hierarchical Inheritance:** In hierarchical inheritance, multiple subclasses inherit from a single superclass. This results in a tree-like structure where one superclass has multiple subclasses.

5. **Hybrid Inheritance:** Hybrid inheritance is a combination of two or more types of inheritance. For example, it could involve both single and multiple inheritance.

**Example:**

Let's illustrate inheritance with a Java example:

```java
// Superclass
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}

// Subclass inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}

// Subclass inheriting from Dog
class Labrador extends Dog {
    void color() {
        System.out.println("Labrador is golden");
    }
}

public class Main {
    public static void main(String[] args) {
        Labrador lab = new Labrador();
        lab.eat();   // Output: Animal is eating
        lab.bark();  // Output: Dog is barking
        lab.color(); // Output: Labrador is golden
    }
}
```

In this example:
- **Animal** is the superclass, **Dog** is the subclass inheriting from **Animal**, and **Labrador** is a subclass inheriting from **Dog**.
- **Labrador** inherits the **eat()** method from **Animal** and the **bark()** method from **Dog**.
- **Labrador** also introduces its own method **color()**.

**Summary:**

Inheritance is a key concept in OOP that allows classes to inherit properties and behaviors from other classes, promoting code reuse and modularity. It comes in various forms such as single, multiple, multilevel, hierarchical, and hybrid inheritance. In Java, for example, inheritance is implemented using the **extends** keyword.

## Q-2) Write a program to take string input as command line argument. In addition, count occurrence of each character in a given string.

**Answer:**

```java
public class CharacterCount {
    public static void main(String[] args) {
        // Check if user provided input
        if (args.length < 1) {
            System.out.println("Usage: java CharacterCount <input_string>");
            return;
        }

        // Get the input string from user
        String inputString = args[0];

        // Create an array to count characters
        int[] charCount = new int[256]; // Assuming ASCII characters

        // Count occurrence of each character
        for (int i = 0; i < inputString.length(); i++) {
            charCount[inputString.charAt(i)]++;
        }

        // Print character occurrences
        System.out.println("Character Occurrences:");
        for (int i = 0; i < charCount.length; i++) {
            if (charCount[i] > 0) {
                System.out.println((char) i + ": " + charCount[i]);
            }
        }
    }
}
```

**Explanation:**

- This program takes a string input from the user when running the program.
- It checks if the user provided input. If not, it displays a message and exits.
- It creates an array `charCount` to count the occurrence of each character. The size of the array is set to 256 to cover all ASCII characters.
- It loops through each character in the input string and increments the count of that character in the array.
- Finally, it prints the occurrence of each character along with its count.

**Usage:**

1. Compile the program using `javac CharacterCount.java`.
2. Run the program with a string input as follows:

```
java CharacterCount "hello world"
```

**Example Output:**

For the input string `"hello world"`, the program will output the occurrence of each character in the string. For example:

```
Character Occurrences:
 : 1
d: 1
e: 1
h: 1
l: 3
o: 2
r: 1
w: 1
```

This output shows that in the input string `"hello world"`, the character 'l' appears 3 times, 'o' appears 2 times, and other characters appear only once.

## Q-3) Write difference between String class and StringBuffer class.

**Answer:**

```
String Class                        StringBuffer Class
-------------                      -------------------
- Strings are immutable.            - StringBuffer is mutable.
- Once created, value cannot        - Allows modification of the string
  be changed.                         without creating a new object.
- Any modification to a string      - More memory efficient for operations
  creates a new string object.        like concatenation.
- Slower performance for            - Faster performance for operations
  operations involving                involving string manipulation.
  concatenation or modification.
```

**Explanation:**

- **String Class:**
  - Strings are immutable. Once created, their values cannot be changed.
  - Any modification to a string creates a new string object, which can be memory inefficient.
  - Slower performance for operations involving concatenation or modification due to the creation of new objects.

- **StringBuffer Class:**
  - StringBuffer is mutable, allowing modification of the string without creating new objects.
  - More memory efficient for operations like concatenation as it modifies the existing string.
  - Faster performance for operations involving string manipulation due to its mutability.

This two-column layout provides a clear comparison between the two classes, covering their immutability, memory efficiency, and performance aspects.

## Q-4) Explain super keyword with example.

**Answer:**

In Java, the `super` keyword is used to refer to the immediate parent class object. It can be used to access variables and methods of the parent class.

Here's an example illustrating the use of the `super` keyword:

```java
// Parent class
class Parent {
    int num = 10;

    // Method to display value of num
    void display() {
        System.out.println("Value of num in Parent: " + num);
    }
}

// Child class inheriting from Parent
class Child extends Parent {
    int num = 20;

    // Method to display value of num in Child and Parent
    void display() {
        System.out.println("Value of num in Child: " + num);
        System.out.println("Value of num in Parent using super: " + super.num);
    }
}

public class SuperExample {
    public static void main(String[] args) {
        Child obj = new Child();
        obj.display();
    }
}
```

**Explanation:**

- In the example, we have a parent class `Parent` and a child class `Child` inheriting from `Parent`.
- Both classes have a variable `num`, but with different values.
- In the `display()` method of the child class, we use the `super` keyword to access the `num` variable of the parent class.
- This allows us to differentiate between the `num` variable of the child class and the `num` variable of the parent class.
- When `super` is used with a method, it calls the overridden method of the parent class.
- When `super` is used with a variable, it refers to the parent class variable.

**Output:**

```
Value of num in Child: 20
Value of num in Parent using super: 10
```

The output demonstrates the use of the `super` keyword to access both the child and parent class variables.

This detailed explanation provides insight into the usage of the `super` keyword in Java, along with a clear example showcasing its functionality.


## Q-5) Describe abstract class called Shape, which has three subclasses say Triangle, Rectangle, and Circle. Define one method area() in the abstract class and override this area() in these three subclasses to calculate for specific object i.e. area() of Triangle subclass should calculate area of triangle likewise for Rectangle and Circle.

**Answer:**

```java
// Abstract class Shape
abstract class Shape {
    // Abstract method to calculate area
    abstract double area();
}

// Subclass Triangle
class Triangle extends Shape {
    double base;
    double height;

    // Constructor
    Triangle(double base, double height) {
        this.base = base;
        this.height = height;
    }

    // Override area method to calculate area of triangle
    @Override
    double area() {
        return 0.5 * base * height;
    }
}

// Subclass Rectangle
class Rectangle extends Shape {
    double length;
    double width;

    // Constructor
    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    // Override area method to calculate area of rectangle
    @Override
    double area() {
        return length * width;
    }
}

// Subclass Circle
class Circle extends Shape {
    double radius;

    // Constructor
    Circle(double radius) {
        this.radius = radius;
    }

    // Override area method to calculate area of circle
    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}

public class ShapeDemo {
    public static void main(String[] args) {
        // Creating objects of different shapes
        Triangle triangle = new Triangle(5, 3);
        Rectangle rectangle = new Rectangle(4, 6);
        Circle circle = new Circle(3);

        // Calculating and displaying area of each shape
        System.out.println("Area of Triangle: " + triangle.area());
        System.out.println("Area of Rectangle: " + rectangle.area());
        System.out.println("Area of Circle: " + circle.area());
    }
}
```

**Explanation:**

- We define an abstract class `Shape` with an abstract method `area()` to calculate the area of any shape.
- Three subclasses `Triangle`, `Rectangle`, and `Circle` inherit from the `Shape` class and provide their own implementations of the `area()` method.
- In the `Triangle` class, we calculate the area of a triangle using the formula: 0.5 * base * height.
- In the `Rectangle` class, we calculate the area of a rectangle using the formula: length * width.
- In the `Circle` class, we calculate the area of a circle using the formula: π * radius * radius.
- We create objects of each subclass and call the `area()` method to calculate and display the area of each shape.

**Output:**

```
Area of Triangle: 7.5
Area of Rectangle: 24.0
Area of Circle: 28.274333882308138
```

This program demonstrates the concept of abstract classes and method overriding in Java, where the `area()` method is implemented differently in each subclass to calculate the area of specific shapes.


## Q-6) How can we protect sub class to override the method of super class? Explain with example.

**Answer:**

In Java, if you want to prevent a subclass from overriding a method of its superclass, you can declare the method as `final` in the superclass. This ensures that the method implementation in the superclass cannot be changed or overridden by any subclass.

Here's an example demonstrating how to use the `final` keyword to protect a method from being overridden:

```java
// Superclass
class Parent {
    // Final method
    final void display() {
        System.out.println("This is a final method in Parent class.");
    }
}

// Subclass
class Child extends Parent {
    // Attempting to override final method - will result in compilation error
    /*void display() {
        System.out.println("This method cannot be overridden.");
    }*/
}

public class FinalMethodExample {
    public static void main(String[] args) {
        Parent obj = new Parent();
        obj.display(); // Output: This is a final method in Parent class.

        Child obj2 = new Child();
        obj2.display(); // Output: This is a final method in Parent class.
    }
}
```

**Explanation:**

- In the example, the `display()` method in the `Parent` class is declared as `final`, which means it cannot be overridden by any subclass.
- When we attempt to override the `display()` method in the `Child` class, a compilation error occurs because final methods cannot be overridden.
- Despite being inherited by the `Child` class, the `display()` method from the `Parent` class retains its original implementation.

**Output:**

```
This is a final method in Parent class.
This is a final method in Parent class.
```

This example demonstrates how to protect a method in a superclass from being overridden by subclasses using the `final` keyword.


## Q-7) What do you mean by Runtime Polymorphism? Write a program to demonstrate runtime polymorphism.

**Polymorphism:**

Polymorphism is a fundamental concept in object-oriented programming (OOP) where an object can take on different forms or have multiple behaviors depending on its context. It allows objects of different classes to be treated as objects of a common superclass, providing flexibility and extensibility in the code.

**Runtime Polymorphism:**

Runtime polymorphism, also known as dynamic polymorphism, occurs when a call to a method is resolved at runtime rather than at compile time. It allows a subclass to provide a specific implementation of a method that is already defined in its superclass. This is achieved through method overriding.

**Example:**

```java
// Superclass
class Animal {
    // Method to make sound
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

// Subclass Dog inheriting from Animal
class Dog extends Animal {
    // Overriding makeSound method
    void makeSound() {
        System.out.println("Dog barks");
    }
}

// Subclass Cat inheriting from Animal
class Cat extends Animal {
    // Overriding makeSound method
    void makeSound() {
        System.out.println("Cat meows");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        // Creating objects of different types
        Animal animal1 = new Animal();
        Animal animal2 = new Dog();
        Animal animal3 = new Cat();

        // Calls the makeSound method of respective objects
        animal1.makeSound(); // Output: Animal makes a sound
        animal2.makeSound(); // Output: Dog barks
        animal3.makeSound(); // Output: Cat meows
    }
}
```

**Explanation:**

- In the example, we have a superclass `Animal` with a method `makeSound()`.
- Two subclasses `Dog` and `Cat` inherit from the `Animal` class and provide their own implementations of the `makeSound()` method.
- We create objects of the superclass and assign them references of both the superclass and its subclasses.
- When we call the `makeSound()` method on each object, the specific implementation of the method in the respective subclass is executed at runtime. This is known as dynamic binding or runtime polymorphism.
- The method to be executed is determined by the actual type of the object at runtime, allowing for flexibility and extensibility in the code.

**Output:**

```
Animal makes a sound
Dog barks
Cat meows
```

This example demonstrates how dynamic binding works in Java, where the method to be executed is determined by the type of object at runtime, allowing for polymorphic behavior.


## Q-8) Explain ArrayList class.

**ArrayList Class:**

In Java, the `ArrayList` class is a part of the `java.util` package and is used to create resizable arrays. It implements the `List` interface and provides dynamic array-like functionality, allowing elements to be added and removed dynamically. Unlike arrays, `ArrayList` can grow or shrink in size automatically as elements are added or removed.

**Key Features of ArrayList:**

1. **Dynamic Sizing:** ArrayList automatically adjusts its size as elements are added or removed, eliminating the need to specify the size upfront.

2. **Random Access:** Elements in an ArrayList can be accessed using their index, allowing for fast random access to elements.

3. **Generics Support:** ArrayList supports generics, allowing it to store elements of a specific type. This helps in type safety and avoids the need for explicit typecasting.

4. **Iterable:** ArrayList implements the `Iterable` interface, which means it can be easily traversed using enhanced for loops or iterators.

**Example Usage:**

```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        // Creating an ArrayList of Strings
        ArrayList<String> list = new ArrayList<>();

        // Adding elements to the ArrayList
        list.add("Java");
        list.add("Python");
        list.add("C++");

        // Accessing elements by index
        System.out.println("Element at index 0: " + list.get(0)); // Output: Java

        // Iterating through the ArrayList
        System.out.println("Elements in the ArrayList:");
        for (String element : list) {
            System.out.println(element);
        }

        // Removing an element
        list.remove("Python");

        // Checking size of ArrayList
        System.out.println("Size of ArrayList after removal: " + list.size()); // Output: 2
    }
}
```

**Explanation:**

- In the example, we create an `ArrayList` named `list` to store strings.
- We add elements "Java", "Python", and "C++" to the ArrayList using the `add()` method.
- Elements can be accessed by their index using the `get()` method.
- We iterate through the ArrayList using an enhanced for loop and print each element.
- An element can be removed from the ArrayList using the `remove()` method.
- The `size()` method returns the current size of the ArrayList.

**Output:**

```
Element at index 0: Java
Elements in the ArrayList:
Java
Python
C++
Size of ArrayList after removal: 2
```

This example demonstrates the basic usage of the ArrayList class in Java for storing and manipulating a list of elements.



## Q-8 {OR}) Write a program to add input elements in ArrayList collection class, then sort the inserted elements in descending order and display the sorted output. Hint: use Collections.reverseOrder().

```java
import java.util.ArrayList;
import java.util.Collections;

public class ArrayListSortingExample {
    public static void main(String[] args) {
        // Create ArrayList to store integers
        ArrayList<Integer> list = new ArrayList<>();

        // Add elements to the ArrayList
        list.add(5);
        list.add(2);
        list.add(8);
        list.add(1);
        list.add(9);

        // Sort the elements in descending order
        Collections.sort(list, Collections.reverseOrder());

        // Display the sorted output
        System.out.println("Sorted Output (Descending Order):");
        for (int num : list) {
            System.out.println(num);
        }
    }
}
```

This program adds integer elements to an ArrayList, sorts them in descending order using Collections.sort() method with Collections.reverseOrder(), and then displays the sorted output.


## Q-9) Explain Primitive data type and wrapper class data types.

**Primitive Data Types:**

Primitive data types are the most basic data types provided by the Java programming language. They represent single values and are predefined by the language itself. In Java, there are eight primitive data types:

1. `byte`: 8-bit integer data type.
2. `short`: 16-bit integer data type.
3. `int`: 32-bit integer data type.
4. `long`: 64-bit integer data type.
5. `float`: 32-bit floating-point data type.
6. `double`: 64-bit floating-point data type.
7. `char`: 16-bit Unicode character data type.
8. `boolean`: Represents true or false values.

Primitive data types are used to store simple values directly in memory and are more efficient in terms of memory usage and performance compared to objects.

**Wrapper Class Data Types:**

Wrapper classes are classes that encapsulate primitive data types within an object. They provide a way to represent primitive data types as objects, allowing them to be used in situations where objects are required, such as collections, generics, and methods that require objects as arguments.

In Java, there are corresponding wrapper classes for each primitive data type:

1. `Byte`: Wrapper class for `byte`.
2. `Short`: Wrapper class for `short`.
3. `Integer`: Wrapper class for `int`.
4. `Long`: Wrapper class for `long`.
5. `Float`: Wrapper class for `float`.
6. `Double`: Wrapper class for `double`.
7. `Character`: Wrapper class for `char`.
8. `Boolean`: Wrapper class for `boolean`.

Wrapper classes provide utility methods for converting between primitive data types and strings, parsing strings into primitive values, and performing various operations on the encapsulated values.

**Example:**

```java
// Primitive data type
int number = 10;

// Wrapper class data type
Integer wrappedNumber = Integer.valueOf(10);
```

In the example, `number` is a primitive data type of type `int`, while `wrappedNumber` is an object of the `Integer` wrapper class representing the same integer value. Wrapper classes allow primitive data types to be used in object-oriented contexts and provide additional functionality not available with primitive types alone.


## Q-10) Explain in detail how inheritance and polymorphism are supported in Java with necessary examples.

**Inheritance in Java:**

Inheritance is a key concept in object-oriented programming that allows a class to inherit properties and behavior (methods) from another class. In Java, inheritance is implemented using the `extends` keyword. The class that is being inherited from is called the superclass or base class, and the class that inherits from it is called the subclass or derived class.

**Syntax:**

```java
class Superclass {
    // Superclass members
}

class Subclass extends Superclass {
    // Subclass members
}
```

**Example:**

```java
// Superclass
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

// Subclass inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Output: Animal makes a sound
        dog.bark(); // Output: Dog barks
    }
}
```

In the example above:
- `Animal` is the superclass with a method `makeSound()`.
- `Dog` is the subclass that inherits from `Animal`.
- The `Dog` class can access the `makeSound()` method of the `Animal` class, demonstrating inheritance.

**Polymorphism in Java:**

Polymorphism is another important concept in OOP that allows objects of different classes to be treated as objects of a common superclass. It enables flexibility and extensibility in the code by allowing methods to be invoked dynamically at runtime.

**Types of Polymorphism:**

1. **Compile-time Polymorphism (Method Overloading):** It occurs when there are multiple methods with the same name but different parameters in the same class. The appropriate method to be called is determined by the number and types of arguments passed to it at compile time.

2. **Runtime Polymorphism (Method Overriding):** It occurs when a subclass provides a specific implementation of a method that is already defined in its superclass. The method to be executed is determined at runtime based on the actual type of the object.

**Example:**

```java
// Superclass
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

// Subclass overriding makeSound method
class Dog extends Animal {
    void makeSound() {
        System.out.println("Dog barks");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        Animal animal = new Dog();
        animal.makeSound(); // Output: Dog barks
    }
}
```

In the example above:
- `Animal` is the superclass with a method `makeSound()`.
- `Dog` is the subclass that overrides the `makeSound()` method of the superclass.
- An object of type `Animal` is instantiated with reference to a `Dog` object.
- At runtime, the `makeSound()` method of the `Dog` class is invoked, demonstrating runtime polymorphism.

In summary, inheritance allows a subclass to inherit properties and behavior from a superclass, while polymorphism allows objects of different classes to be treated as objects of a common superclass, enabling dynamic method invocation based on the actual type of the object at runtime.


## Q-11) Explain about different types of string methods.

**String Methods:**

| Method Call              | Task Performed                                                  |
|--------------------------|-----------------------------------------------------------------|
| `S2 = s1.toLowerCase()` | Converts the string `s1` to lowercase.                         |
| `S2 = s1.toUpperCase()` | Converts the string `s1` to uppercase.                         |
| `S2 = s1.replace('x', 'y')` | Replace all appearances of 'x' with 'y' in the string `s1`. |
| `S2 = s1.trim()`         | Remove white spaces at the beginning and end of the string `s1`. |
| `S1.equals(s2)`          | Returns true if `s1` and `s2` are equal.                       |
| `S1.equalsIgnoreCase(s2)` | Returns true if `s1` is equal to `s2`, ignoring the case of characters. |
| `S1.length()`            | Gives the length of `s1`.                                      |
| `S1.charAt(n)`           | Gives the nth character of `s1`.                               |
| `S1.compareTo(s2)`       | Returns -ve if `s1` < `s2`, +ve if `s1` > `s2`, and 0 if `s1` = `s2`. |
| `S1.concat(s2)`          | Concatenates `s1` and `s2`.                                    |
| `S1.substring(n)`        | Gives substring starting from the nth character of `s1`.       |
| `S1.substring(n, m)`     | Gives substring starting from the nth character up to the mth character of `s1`. |
| `String.valueOf(p)`      | Returns the string representation of the specified type argument `p`. |
| `toString()`             | Returns the string representation of the object (which is already a string!). |
| `S1.indexOf('x')`        | Gives the position of the first occurrence of 'x' in the string `s1`. |
| `S1.indexOf('x', n)`     | Gives the position of 'x' that occurs after the nth position in the string `s1`. |
| `String.valueOf(variable)` | Converts the parameter value to a string representation.      |

These methods provide various functionalities for manipulating, comparing, searching, converting, and extracting substrings from strings in Java.



## Q-12) What is a Package? What are the benefits of using packages? Write down the steps in creating a package and using it in a Java program with an example.

**Package in Java:**

A package in Java is a namespace that organizes a set of related classes and interfaces. It helps in categorizing the classes and avoids naming conflicts. Packages are used for organizing large Java projects into smaller, manageable units and for providing access protection.

**Benefits of Using Packages:**

1. **Namespace Management:** Packages provide a way to organize classes and interfaces into separate namespaces, which helps in avoiding naming conflicts.

2. **Access Protection:** Packages enable access control by using access modifiers like `public`, `protected`, and `private`. Classes and interfaces within a package can be accessed only by other classes and interfaces within the same package or by classes in other packages if they are declared as `public`.

3. **Modularity and Reusability:** Packages promote modularity and reusability by allowing classes and interfaces to be grouped based on functionality or purpose. They facilitate code reuse across multiple projects.

4. **Organization:** Packages help in organizing large projects into smaller, manageable units, making the codebase easier to understand, navigate, and maintain.

**Steps in Creating a Package and Using it in a Java Program:**

1. **Create Directory Structure:** Create a directory structure that reflects the package hierarchy. Each subdirectory represents a package, and the directory structure must match the package name.

2. **Write Java Files:** Write Java files containing classes or interfaces within the package. Include the `package` statement at the beginning of each file to specify the package name.

3. **Compile Java Files:** Compile the Java files using the `javac` compiler. Make sure to include the `-d` option to specify the destination directory for compiled class files.

4. **Import Package:** In other Java files where you want to use classes or interfaces from the package, import the package using the `import` statement.

5. **Use Classes or Interfaces:** Use the classes or interfaces from the imported package in your Java program.

**Example:**

```java
// MathUtil.java
package PackageV1.util;

public class MathUtil {
    public static int square(int num) {
        return num * num;
    }
}
```

```java
// Main.java
package PackageV1;

import PackageV1.util.MathUtil;

public class Main {
    public static void main(String[] args) {
        int result = MathUtil.square(5);
        System.out.println("Square of 5: " + result); // Output: Square of 5: 25
    }
}
```

**Package Syntax:**

```java
package PackageV1;
```

**Compile Time Syntax:**

```
javac -d . file_name.java
```

**Run File Syntax:**

```
java PackageV1.Main
```

In this example, we create a package `PackageV1.util` containing the `MathUtil` class with a method `square()` to calculate the square of a number. 

In the `Main` class, which belongs to the package `PackageV1`, we import the `MathUtil` class using the `import` statement and use it to calculate the square of 5. Finally, we print the result, which is 25.



## Q-14.1) Explain Method Overloading and Overriding.

**Method Overloading:**

Method overloading is a feature in Java that allows a class to have multiple methods with the same name but different parameters. These methods can have different numbers or types of parameters. Method overloading enables the same method name to be used for different behaviors based on the type or number of arguments passed to it.

**Key Points:**

1. **Same Method Name:** Method overloading involves defining multiple methods within the same class with the same name.

2. **Different Parameters:** The overloaded methods must have different parameter lists. This can include a different number of parameters, different types of parameters, or both.

3. **Compile-Time Polymorphism:** Method overloading is an example of compile-time polymorphism or static polymorphism. The appropriate method to be called is determined at compile time based on the number and types of arguments passed to it.

**Example of Method Overloading:**

```java
public class MathOperations {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method to add two doubles
    public double add(double a, double b) {
        return a + b;
    }
}
```

**Method Overriding:**

Method overriding is a feature in Java that allows a subclass to provide a specific implementation of a method that is already defined in its superclass. When a method in a subclass has the same signature (name, number, and type of parameters) as a method in its superclass, it is said to override the superclass method.

**Key Points:**

1. **Inheritance Relationship:** Method overriding occurs in a subclass that inherits from a superclass. It allows the subclass to provide its own implementation of a method defined in the superclass.

2. **Same Signature:** The overriding method in the subclass must have the same name, return type, and parameter list as the overridden method in the superclass.

3. **Dynamic Polymorphism:** Method overriding is an example of runtime polymorphism or dynamic polymorphism. The method to be executed is determined at runtime based on the actual type of the object.

**Example of Method Overriding:**

```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}
```

In this example, the `Dog` class overrides the `makeSound()` method of its superclass `Animal` with its own implementation. When a `Dog` object calls the `makeSound()` method, the overridden method in the `Dog` class is invoked, demonstrating method overriding.

## Q-14.2) Explain types of polymorphism?

**Polymorphism** refers to the ability of an object to take on multiple forms. In Java, there are two main types of polymorphism: compile-time polymorphism and runtime polymorphism.

**1. Compile-time Polymorphism:**
   - Also known as **static polymorphism** or **early binding**.
   - Occurs when the method to be executed is determined at compile time.
   - Achieved through method overloading and operator overloading.
   - Example: Method overloading, where multiple methods with the same name but different parameters are defined in the same class.

**2. Runtime Polymorphism:**
   - Also known as **dynamic polymorphism** or **late binding**.
   - Occurs when the method to be executed is determined at runtime.
   - Achieved through method overriding and interface implementation.
   - Example: Method overriding, where a subclass provides a specific implementation of a method that is already defined in its superclass.

**Example:**

```java
// Compile-time Polymorphism (Method Overloading)
public class MathOperations {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }
}

// Runtime Polymorphism (Method Overriding)
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}
```

In the above example:
- Method overloading in `MathOperations` demonstrates compile-time polymorphism.
- Method overriding in `Dog` demonstrates runtime polymorphism.


## Q-15.1) Explain following keywords:
a) `super` b) `this`

**a) super:**

In Java, `super` is a keyword that refers to the superclass of the current object instance. It is used to access members (fields and methods) of the superclass, invoke superclass constructors, and prevent method hiding.

**Key Points:**

1. **Accessing Superclass Members:** You can use `super` keyword to access superclass fields and methods within a subclass.

2. **Invoking Superclass Constructor:** You can use `super()` as a constructor call to explicitly invoke a superclass constructor from a subclass constructor. It must be the first statement in the subclass constructor.

3. **Preventing Method Hiding:** If a subclass has a method with the same name as a method in its superclass, using `super` keyword allows you to invoke the superclass method, preventing method hiding.

**Example:**
```java
class Animal {
    String color = "white";

    void display() {
        System.out.println("Color: " + color);
    }
}

class Dog extends Animal {
    String color = "black";

    void display() {
        super.display(); // Invoke superclass method
        System.out.println("Dog Color: " + color);
    }
}
```

**b) this:**

In Java, `this` is a keyword that refers to the current object instance. It is used to access instance variables, invoke constructors, and pass the current object as a parameter.

**Key Points:**

1. **Accessing Instance Variables:** You can use `this` keyword to access instance variables within a class. It helps differentiate between instance variables and parameters with the same name.

2. **Invoking Constructors:** You can use `this()` as a constructor call to invoke another constructor within the same class or call a constructor of the superclass. It must be the first statement in the constructor.

3. **Passing Current Object:** You can use `this` keyword to pass the current object as a parameter to other methods or constructors.

**Example:**
```java
class Student {
    String name;

    Student(String name) {
        this.name = name; // Access instance variable
    }

    Student() {
        this("Unknown"); // Invoke another constructor
    }

    void display() {
        System.out.println("Student Name: " + this.name); // Pass current object
    }
}
```

## Q-15.2) Explain following Java keywords using appropriate examples:
a) `static` b) `final` c) `super`

**a) static:**

In Java, `static` is a keyword that can be applied to variables, methods, and nested classes. It indicates that the variable, method, or nested class belongs to the class itself rather than any specific instance of the class.

**Example:**

```java
class Example {
    static int count = 0; // Static variable

    static void increment() { // Static method
        count++;
    }

    static class NestedClass { // Static nested class
        void display() {
            System.out.println("Static nested class");
        }
    }
}
```

**b) final:**

In Java, `final` is a keyword that can be applied to variables, methods, and classes. It indicates that the variable, method, or class cannot be modified or overridden.

**Example:**

```java
class Example {
    final int value = 10; // Final variable

    final void display() { // Final method
        System.out.println("Final method");
    }
}

final class FinalClass { // Final class
    // Class implementation
}
```

**c) super:**

Already explained in the previous answer {Q-15.1 (a)}.



## Q-16) Consider class A as the parent of class B. Explain among the following which statement will show the compilation error.
i) A a = new A();
ii) A a = new B();
iii) B b = new A(); `Answer`
iv) B b = new B();

In the scenario where class A is the parent of class B, let's analyze each statement:

i) `A a = new A();`
This statement is valid because it creates an instance of class A.

ii) `A a = new B();`
This statement is valid due to polymorphism. Since B is a subclass of A, a reference of type A can point to an object of class B.

iii) `B b = new A();`
This statement will result in a compilation error because class A is the parent of class B. In Java, a reference of a subclass type cannot point to an object of the superclass type without explicit casting.

iv) `B b = new B();`
This statement is valid because it creates an instance of class B. Since B is a subclass of A, it can be assigned to a reference variable of type B.

Therefore, the statement that will show the compilation error is iii) `B b = new A();`.


## Q-17) Write a Java program to take infix expressions and convert it into prefix expressions.

Here's a Java program to implement the conversion from infix to prefix expressions:

```java
import java.util.Stack;

public class InfixToPrefixConverter {

    // Function to check if the given character is an operator
    static boolean isOperator(char c) {
        return c == '+' || c == '-' || c == '*' || c == '/' || c == '^';
    }

    // Function to determine the precedence of operators
    static int precedence(char c) {
        switch (c) {
            case '^':
                return 3;
            case '*':
            case '/':
                return 2;
            case '+':
            case '-':
                return 1;
            default:
                return -1;
        }
    }

    // Function to convert infix expression to postfix expression
    static String infixToPostfix(String infix) {
        StringBuilder postfix = new StringBuilder();
        Stack<Character> stack = new Stack<>();

        for (int i = 0; i < infix.length(); i++) {
            char c = infix.charAt(i);

            // If current character is an operand, add it to postfix
            if (Character.isLetterOrDigit(c)) {
                postfix.append(c);
            }
            // If current character is '(', push it to the stack
            else if (c == '(') {
                stack.push(c);
            }
            // If current character is ')', pop and output from the stack until '(' is encountered
            else if (c == ')') {
                while (!stack.isEmpty() && stack.peek() != '(') {
                    postfix.append(stack.pop());
                }
                stack.pop(); // Pop '('
            }
            // If current character is an operator
            else {
                while (!stack.isEmpty() && precedence(c) <= precedence(stack.peek())) {
                    postfix.append(stack.pop());
                }
                stack.push(c);
            }
        }

        // Pop remaining operators from the stack and append to postfix
        while (!stack.isEmpty()) {
            postfix.append(stack.pop());
        }

        return postfix.toString();
    }

    // Function to reverse a string
    static String reverseString(String str) {
        StringBuilder reversed = new StringBuilder();
        for (int i = str.length() - 1; i >= 0; i--) {
            reversed.append(str.charAt(i));
        }
        return reversed.toString();
    }

    // Function to convert infix expression to prefix expression
    static String infixToPrefix(String infix) {
        String reversedInfix = reverseString(infix);
        String postfix = infixToPostfix(reversedInfix);
        return reverseString(postfix);
    }

    public static void main(String[] args) {
        String infixExpression = "A+B*C-D/E";
        String prefixExpression = infixToPrefix(infixExpression);
        System.out.println("Infix Expression: " + infixExpression);
        System.out.println("Prefix Expression: " + prefixExpression);
    }
}
```

**Vatsal** - `Kuch Samajh me nhi aaya but dekh ke acha lga :) `

This program takes an infix expression as input, converts it to a postfix expression using the Shunting Yard algorithm, and then reverses the postfix expression to obtain the prefix expression.


![alt text](https://i.imgur.com/8Qw2VtL.png)
