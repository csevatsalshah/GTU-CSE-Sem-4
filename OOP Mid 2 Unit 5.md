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
