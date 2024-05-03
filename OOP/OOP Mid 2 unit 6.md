# OOP Mid-2 Unit 6
`Created by Vatsal Shah`
`Disclaimer - AI is Used While Making This and Add Figure in Answer Accordingly if Required`

## Q-1.1) Define Interface and explain how it differs from the class.

### Interface
**Interface** in Java is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. It represents a contract or a set of abstract methods that a class implementing the interface must provide.

Key points:
- **Abstract Methods**: Interfaces can declare method signatures without providing implementations. These methods are implicitly public and abstract.
- **Constants**: Interfaces can contain constant variables, which are implicitly public, static, and final.
- **No Constructors**: Interfaces cannot have constructors because they cannot be instantiated.
- **Multiple Inheritance**: Unlike classes, a Java class can implement multiple interfaces, enabling multiple inheritance of type.
- **Contract**: Implementing a Java interface implies a commitment to provide implementations for all the abstract methods declared in the interface.

### Difference from Class
1. **Method Definitions**: Classes can have both method declarations and method definitions (implementations), while interfaces can only have method declarations.
2. **Variables**: Classes can have instance variables and static variables, while interfaces can only have constant variables (final and static).
3. **Instantiation**: Classes can be instantiated to create objects, while interfaces cannot be instantiated.
4. **Constructor**: Classes can have constructors for initializing objects, while interfaces cannot have constructors.
5. **Access Modifiers**: Members of a class can have different access modifiers (public, private, protected, package-private), while all members of an interface are public by default.
6. **Inheritance**: Classes support both single and multiple inheritance (through interfaces), while interfaces only support multiple inheritance.
7. **Implementation**: Classes provide concrete implementations of methods, while interfaces only declare method signatures, leaving the implementation to the implementing classes.
8. **Usage**: Classes are used to define objects with state and behavior, while interfaces are used to define contracts that classes must adhere to.

### Summary:
In summary, an **interface** in Java defines a set of method signatures that implementing classes must provide, serving as a contract for behavior. It differs from a **class** in several aspects, including method definitions, variable types, instantiation, inheritance, and usage. Interfaces are widely used in Java to achieve abstraction, polymorphism, and design flexibility by allowing classes to be decoupled from specific implementations.

## Q-1.2) Write a java program to implement the multiple inheritance concepts for calculating area of circle and square.

```java
// Interface for shape
interface Shape {
    double calculateArea();
}

// Circle class implementing Shape interface
class Circle implements Shape {
    private double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}

// Square class implementing Shape interface
class Square implements Shape {
    private double side;

    Square(double side) {
        this.side = side;
    }

    @Override
    public double calculateArea() {
        return side * side;
    }
}

// Multiple inheritance using interfaces
class CircleSquare implements Shape {
    private Circle circle;
    private Square square;

    CircleSquare(double radius, double side) {
        circle = new Circle(radius);
        square = new Square(side);
    }

    // Calculating area of circle and square and returning sum
    @Override
    public double calculateArea() {
        return circle.calculateArea() + square.calculateArea();
    }
}

// Main class to test multiple inheritance
public class Main {
    public static void main(String[] args) {
        double radius = 5;
        double side = 4;

        CircleSquare circleSquare = new CircleSquare(radius, side);
        System.out.println("Area of Circle and Square combined: " + circleSquare.calculateArea());
    }
}
```

### Explanation:
- The program defines an **interface** named `Shape` with a method `calculateArea()` to calculate the area of different shapes.
- Two classes `Circle` and `Square` implement the `Shape` interface and provide their implementations of the `calculateArea()` method.
- Another class `CircleSquare` demonstrates multiple inheritance by implementing the `Shape` interface and containing instances of both `Circle` and `Square`.
- The `CircleSquare` class calculates the combined area of a circle and a square by invoking the `calculateArea()` methods of its constituent shapes.
- Finally, the `Main` class tests the multiple inheritance concept by creating an instance of `CircleSquare` and calculating the combined area of a circle and a square.

## Q-1.3) Explain the interface with an example program.

### Interface
An **interface** in Java is a reference type that can contain only method signatures, constants, default methods, static methods, and nested types. It represents a contract or a set of abstract methods that must be implemented by the classes that implement the interface.

### Example Program:
```java
// Interface representing a printable object
interface Printable {
    void print();
}

// Class implementing the Printable interface
class Document implements Printable {
    private String content;

    Document(String content) {
        this.content = content;
    }

    @Override
    public void print() {
        System.out.println("Printing document: " + content);
    }
}

// Main class to test the interface
public class Main {
    public static void main(String[] args) {
        // Creating an instance of Document
        Document document = new Document("Sample document content");

        // Calling the print method on the Document object
        document.print();
    }
}
```

### Explanation:
- The program defines an **interface** named `Printable` with a single abstract method `print()`.
- The `Document` class implements the `Printable` interface and provides an implementation for the `print()` method.
- Inside the `print()` method of the `Document` class, it prints the content of the document.
- In the `Main` class, an instance of the `Document` class is created, and the `print()` method is invoked on that instance.
- This demonstrates how interfaces define a contract for classes to implement specific behavior, allowing for polymorphism and abstraction in Java programs.



## Q-2.1) What is an Exception? List out various built-in exceptions in JAVA and explain any one Exception class with a suitable example.

### Exception
An **exception** in Java is an object that describes an unusual or erroneous situation that occurs during the execution of a program. Exceptions can disrupt the normal flow of the program and need to be handled appropriately to prevent the program from crashing.

### Built-in Exceptions in Java:

| Exception                  | Meaning                                                                                           |
|--------------------------|---------------------------------------------------------------------------------------------------|
| ArithmeticException     | Occurs when an arithmetic operation is attempted with inappropriate operands, such as division by zero. |
| NullPointerException  | Occurs when attempting to access or call methods on an object that is `null`.                                |
| ArrayIndexOutOfBoundsException | Occurs when trying to access an array element with an invalid index.                                                   |
| NumberFormatException  | Occurs when attempting to convert a string to a numeric format, but the string does not contain a valid numeric value. |
| FileNotFoundException      | Occurs when attempting to access a file that does not exist.                                                                    |
| IOException                   | Represents any I/O (input/output) error that occurs during file operations.                                                  |
| ClassNotFoundException | Occurs when trying to load a class using its string name, but the class definition is not found.                                       |
| InterruptedException       | Occurs when a thread is waiting, sleeping, or otherwise occupied, and another thread interrupts it.                                          |
| IllegalArgumentException      | Occurs when passing an illegal or inappropriate argument to a method.                                                                                   |
| RuntimeException        | Represents various exceptions that occur during the execution of Java programs. It is a superclass of all built-in exceptions that are not checked.  |

### Example: NullPointerException
```java
public class Main {
    public static void main(String[] args) {
        String str = null;
        try {
            // Trying to get the length of a null string
            int length = str.length(); // This will throw a NullPointerException
        } catch (NullPointerException e) {
            // Handling the NullPointerException
            System.out.println("Exception caught: " + e.getMessage());
        }
    }
}
```
In this example, we deliberately set the `str` variable to `null`, and then we attempt to call the `length()` method on it. Since `str` is `null`, trying to access its method will throw a `NullPointerException`. We catch this exception using a `try-catch` block and handle it gracefully by printing a custom message.

## Q-2.2) What is Exception? Demonstrate how you can handle different types of exception separately.

### Exception
An **exception** in Java is an object that represents an unusual or erroneous situation that occurs during the execution of a program. It disrupts the normal flow of the program and needs to be handled appropriately to prevent the program from crashing.

### Handling Different Types of Exceptions Separately
```java
public class Main {
    public static void main(String[] args) {
        try {
            int result = divide(10, 0); // This will throw an ArithmeticException
            System.out.println("Result: " + result); // This line won't be executed
        } catch (ArithmeticException e) {
            // Handling ArithmeticException separately
            System.out.println("ArithmeticException caught: " + e.getMessage());
        } catch (NullPointerException e) {
            // Handling NullPointerException separately
            System.out.println("NullPointerException caught: " + e.getMessage());
        } catch (Exception e) {
            // Handling other exceptions with a generic catch block
            System.out.println("Generic Exception caught: " + e.getMessage());
        }
    }

    // Method to perform division
    public static int divide(int num, int denom) {
        return num / denom; // This may throw ArithmeticException
    }
}
```

In this example:
- We have a method `divide()` that performs division, and we attempt to divide by zero intentionally.
- Inside the `main()` method, we use a `try-catch` block to handle exceptions.
- We catch `ArithmeticException` and `NullPointerException` separately using separate `catch` blocks. These blocks will catch exceptions of the specified types.
- We also have a generic `catch` block (`catch (Exception e)`) to catch any other exceptions that are not explicitly handled. This ensures that the program doesn't crash unexpectedly due to unhandled exceptions.
- By handling different types of exceptions separately, we can provide specific error messages or take appropriate actions based on the type of exception encountered.



## Q-3) Write a JAVA program to read student.txt file and display the content.

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFile {
    public static void main(String[] args) {
        String fileName = "student.txt";

        try (BufferedReader br = new BufferedReader(new FileReader(fileName))) {
            String line;
            System.out.println("Contents of " + fileName + ":");
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.err.println("Error reading file: " + e.getMessage());
        }
    }
}
```

This program reads the contents of a file named "student.txt" and displays them on the console. It uses a `BufferedReader` to read the file line by line, and then prints each line to the console. The `try-with-resources` statement is used to ensure that the `BufferedReader` is properly closed after reading, even if an exception occurs.




## Q-4) Differentiate between final, finally and finalize. What will happen if we make class and method as final?

### final
- **final** is a keyword in Java used to apply restrictions on class, method, and variable.
- When a class is declared as final, it cannot be subclassed.
- When a method is declared as final, it cannot be overridden by subclasses.
- When a variable is declared as final, its value cannot be changed once assigned.

### finally
- **finally** is a block associated with the try-catch block in Java.
- It is used to execute important code such as closing resources, regardless of whether an exception is thrown or not.
- Code inside the finally block always executes, even if an exception occurs or if there is a return statement inside the try or catch blocks.

### finalize
- **finalize** is a method in Java that is called by the garbage collector before reclaiming the memory occupied by an object.
- It is used for performing cleanup operations such as releasing system resources or closing files before an object is garbage collected.
- The `finalize()` method is called by the garbage collector, and its execution is not guaranteed. It may not be called if the program terminates before the garbage collector runs.

### Effects of making a class and method as final:
- **Final Class**: If a class is declared as final, it cannot be subclassed. This means that other classes cannot inherit from it. It is often used for creating immutable classes or classes with sensitive implementations that should not be altered.
- **Final Method**: If a method is declared as final, it cannot be overridden by subclasses. This ensures that the behavior of the method remains consistent across all subclasses. It is often used to prevent subclasses from changing the behavior of critical methods in a class.



## Q-5) Explain abstract class with an example.

### Abstract Class
An **abstract class** in Java is a class that cannot be instantiated on its own and is meant to be subclassed. It can contain abstract methods (methods without a body) as well as concrete methods (methods with a body). Abstract classes are used to define a common interface for a group of related classes and to provide a partial implementation of the interface.

### Example:
```java
// Abstract class representing a shape
abstract class Shape {
    // Abstract method to calculate area
    abstract double calculateArea();

    // Concrete method to display the area
    void displayArea() {
        System.out.println("Area: " + calculateArea());
    }
}

// Concrete subclass representing a circle
class Circle extends Shape {
    private double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    // Implementation of abstract method to calculate area for circle
    @Override
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}

// Concrete subclass representing a rectangle
class Rectangle extends Shape {
    private double length;
    private double width;

    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    // Implementation of abstract method to calculate area for rectangle
    @Override
    double calculateArea() {
        return length * width;
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating instances of Circle and Rectangle
        Circle circle = new Circle(5);
        Rectangle rectangle = new Rectangle(4, 6);

        // Calling displayArea method for both shapes
        circle.displayArea();
        rectangle.displayArea();
    }
}
```

### Summary:
- Abstract classes in Java are classes that cannot be instantiated and are meant to be subclassed.
- They can contain abstract methods (methods without a body) and concrete methods (methods with a body).
- Abstract classes are used to define a common interface for a group of related classes and provide a partial implementation of the interface.
- Subclasses of an abstract class must provide implementations for all abstract methods unless they are also declared as abstract.

  

## Q-6) Write a program to rise and handle divide by zero exception.

```java
public class Main {
    public static void main(String[] args) {
        try {
            int result = divide(10, 0); // This will throw an ArithmeticException
            System.out.println("Result: " + result); // This line won't be executed
        } catch (ArithmeticException e) {
            // Handling ArithmeticException
            System.out.println("Cannot divide by zero: " + e.getMessage());
        }
    }

    // Method to perform division
    public static int divide(int num, int denom) {
        return num / denom; // This may throw ArithmeticException
    }
}
```

### Summary:
- The program demonstrates how to handle the divide by zero exception using a try-catch block.
- It defines a `divide()` method that attempts to perform division with a denominator of zero, which will throw an `ArithmeticException`.
- Inside the `main()` method, the division operation is wrapped in a try-catch block to catch the `ArithmeticException` that may occur.
- If an `ArithmeticException` occurs (due to attempting to divide by zero), a custom error message is printed to the console.



Q-7) Write a method for computing xy doing repetitive multiplication. X and Y are of type integer and are to be given as command line arguments. Raise and handle exception(s) for invalid values of x and y.

```java
public class PowerCalculation {
    public static void main(String[] args) {
        try {
            if (args.length != 2) {
                throw new IllegalArgumentException("Exactly two arguments are required.");
            }

            int x = Integer.parseInt(args[0]);
            int y = Integer.parseInt(args[1]);

            if (x < 0 || y < 0) {
                throw new IllegalArgumentException("Both x and y must be non-negative integers.");
            }

            long result = power(x, y);
            System.out.println(x + " raised to the power of " + y + " is: " + result);
        } catch (NumberFormatException e) {
            System.out.println("Invalid arguments. Both x and y must be integers.");
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }

    // Method to compute x^y using repetitive multiplication
    public static long power(int x, int y) {
        if (y == 0) {
            return 1;
        }

        long result = 1;
        for (int i = 0; i < y; i++) {
            result *= x;
        }
        return result;
    }
}
```

### Output:
```plaintext
$ java PowerCalculation 2 5
2 raised to the power of 5 is: 32

$ java PowerCalculation 3 4
3 raised to the power of 4 is: 81

$ java PowerCalculation 0 3
Both x and y must be non-negative integers.

$ java PowerCalculation 2.5 4
Invalid arguments. Both x and y must be integers.

$ java PowerCalculation 2
Exactly two arguments are required.
```


### Q-8.1) Explain usage of class FileInputStream and FileOutputStream by giving an example.

The `FileInputStream` and `FileOutputStream` classes in Java are used to read from and write to files, respectively. They are part of the `java.io` package and are commonly used for handling file input and output operations.

#### Example:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class FileIOExample {
    public static void main(String[] args) {
        // Example of using FileInputStream to read from a file
        try (FileInputStream fis = new FileInputStream("input.txt")) {
            int data;
            System.out.println("Contents of input.txt:");
            while ((data = fis.read()) != -1) {
                System.out.print((char) data);
            }
        } catch (IOException e) {
            System.err.println("Error reading file: " + e.getMessage());
        }

        // Example of using FileOutputStream to write to a file
        try (FileOutputStream fos = new FileOutputStream("output.txt")) {
            String text = "Hello, world!";
            byte[] bytes = text.getBytes();
            fos.write(bytes);
            System.out.println("\nData has been written to output.txt");
        } catch (IOException e) {
            System.err.println("Error writing to file: " + e.getMessage());
        }
    }
}
```

#### Explanation:
- In the example above, `FileInputStream` is used to read from a file named "input.txt". We create an instance of `FileInputStream` and use its `read()` method to read bytes from the file. We read byte by byte until the end of the file is reached (`read()` returns -1).
- Similarly, `FileOutputStream` is used to write data to a file named "output.txt". We create an instance of `FileOutputStream` and use its `write()` method to write bytes to the file. We convert the string "Hello, world!" to bytes using the `getBytes()` method and then write these bytes to the file.
- Both `FileInputStream` and `FileOutputStream` are used inside a try-with-resources block to ensure that the underlying resources are properly closed after use, even if an exception occurs.
- IOExceptions are caught and handled to provide error messages in case of any file-related errors.

#### Summary:
- `FileInputStream` and `FileOutputStream` are used for file input and output operations in Java.
- `FileInputStream` is used for reading from a file, while `FileOutputStream` is used for writing to a file.
- Both classes are used inside try-with-resources blocks to ensure proper resource management and exception handling.
- IOExceptions are commonly caught and handled when working with file input and output operations to provide meaningful error messages to the user.

### Q-8.2) Write short notes about I/O stream classes.

In Java, I/O stream classes are used to handle input and output operations. They provide a uniform way of reading from and writing to various sources, such as files, network connections, and in-memory buffers. There are two types of I/O streams: byte streams and character streams.

- **Byte Streams**: Byte streams are used for handling raw binary data. They are represented by classes that have "InputStream" or "OutputStream" in their names, such as `FileInputStream`, `FileOutputStream`, `ByteArrayInputStream`, and `ByteArrayOutputStream`. Byte streams are used when working with binary files or when dealing with low-level I/O operations.

- **Character Streams**: Character streams are used for handling character data. They are represented by classes that have "Reader" or "Writer" in their names, such as `FileReader`, `FileWriter`, `BufferedReader`, and `BufferedWriter`. Character streams are used when working with text files or when dealing with character-based I/O operations. They automatically handle character encoding and decoding, making them suitable for handling text data.

I/O stream classes in Java support various operations such as reading from or writing to files, buffering data for improved performance, and handling exceptions during I/O operations. They are essential for performing input and output tasks in Java applications.

### Q-8.3) Explain File class with its methods.

The `File` class in Java represents a file or directory path. It provides methods for working with files and directories, such as creating, deleting, renaming, and querying file properties. Here are some commonly used methods of the `File` class:

| Method                              | Description                                                                                                      |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------|
| `File(String pathname)`             | Constructs a `File` object representing the file or directory specified by the pathname.                        |
| `boolean exists()`                  | Returns `true` if the file or directory exists; otherwise, returns `false`.                                      |
| `boolean isFile()`                  | Returns `true` if the `File` object represents a file; otherwise, returns `false`.                                |
| `boolean isDirectory()`             | Returns `true` if the `File` object represents a directory; otherwise, returns `false`.                           |
| `boolean createNewFile()`           | Creates a new, empty file if it does not exist.                                                                  |
| `boolean mkdir()`                   | Creates a new directory if it does not exist.                                                                    |
| `String[] list()`                   | Returns an array of strings naming the files and directories in the directory represented by the `File` object. |
| `boolean delete()`                  | Deletes the file or directory represented by the `File` object.                                                  |

The `File` class provides platform-independent access to file system operations, making it useful for handling files and directories in Java applications.

### Q-8.4) Explain file I/O using byte stream with appropriate example. hint: use FileInputStream, FileOutputStream

File I/O using byte streams involves reading and writing raw binary data. Here's an example demonstrating file I/O using `FileInputStream` and `FileOutputStream`:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class ByteStreamExample {
    public static void main(String[] args) {
        try {
            // Creating a FileInputStream to read from a file
            FileInputStream fis = new FileInputStream("input.txt");

            // Creating a FileOutputStream to write to a file
            FileOutputStream fos = new FileOutputStream("output.txt");

            // Reading bytes from input.txt and writing them to output.txt
            int data;
            while ((data = fis.read()) != -1) {
                fos.write(data);
            }

            // Closing streams
            fis.close();
            fos.close();

            System.out.println("File copied successfully using byte stream.");
        } catch (IOException e) {
            System.err.println("Error copying file: " + e.getMessage());
        }
    }
}
```

In this example:
- We create a `FileInputStream` to read bytes from a file named "input.txt".
- We create a `FileOutputStream` to write bytes to a file named "output.txt".
- We read bytes from "input.txt" using a loop and write them to "output.txt".
- Both streams are properly closed after use to release system resources.

### Q-8.5) Explain file I/O using character stream with appropriate example. hint: use FileReader, FileWriter

File I/O using character streams involves reading and writing character data. Here's an example demonstrating file I/O using `FileReader` and `FileWriter`:

```java
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class CharacterStreamExample {
    public static void main(String[] args) {
        try {
            // Creating a FileReader to read from a file
            FileReader fr = new FileReader("input.txt");

            // Creating a FileWriter to write to a file
            FileWriter fw = new FileWriter("output.txt");

            // Reading characters from input.txt and writing them to output.txt
            int data;
            while ((data = fr.read()) != -1) {
                fw.write(data);
            }

            // Closing streams
            fr.close();
            fw.close();

            System.out.println("File copied successfully using character stream.");
        } catch (IOException e) {
            System.err.println("Error copying file: " + e.getMessage());
        }
    }
}
```

In this example:
- We create a `FileReader` to read characters from a file named "input.txt".
- We create a `FileWriter` to write characters


### Q-9) Explain Comparable and Cloneable interface.

#### Comparable Interface:
The `Comparable` interface in Java is used to define the natural ordering of objects of a class. It contains only one method, `compareTo()`, which compares the current object with another object of the same type and returns an integer value indicating their relative order.

```java
public interface Comparable<T> {
    int compareTo(T o);
}
```

The `compareTo()` method returns:
- a negative integer if the current object is less than the other object.
- zero if the current object is equal to the other object.
- a positive integer if the current object is greater than the other object.

Classes that implement the `Comparable` interface can be sorted using methods like `Collections.sort()` or `Arrays.sort()`.

#### Example:
```java
import java.util.*;

class Student implements Comparable<Student> {
    private String name;
    private int id;

    public Student(String name, int id) {
        this.name = name;
        this.id = id;
    }

    public int compareTo(Student other) {
        return this.id - other.id;
    }

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", id=" + id +
                '}';
    }
}

public class ComparableExample {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("Alice", 101));
        students.add(new Student("Bob", 103));
        students.add(new Student("Charlie", 102));

        Collections.sort(students); // Sort students based on id

        for (Student student : students) {
            System.out.println(student);
        }
    }
}
```

#### Cloneable Interface:
The `Cloneable` interface in Java is a marker interface that indicates that the objects of a class can be cloned. It doesn't contain any methods. Classes that implement `Cloneable` must override the `clone()` method from the `Object` class to specify how the cloning should be done.

```java
public interface Cloneable {
}
```

The `clone()` method creates and returns a copy of the object. It performs a shallow copy by default, meaning it creates a new instance of the same class and copies all fields' values. If the fields are references to other objects, the references themselves are copied, not the actual objects.

#### Example:
```java
class Person implements Cloneable {
    private String name;

    public Person(String name) {
        this.name = name;
    }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                '}';
    }
}

public class CloneableExample {
    public static void main(String[] args) {
        Person original = new Person("Alice");

        try {
            Person cloned = (Person) original.clone();
            System.out.println("Original: " + original);
            System.out.println("Cloned: " + cloned);
        } catch (CloneNotSupportedException e) {
            e.printStackTrace();
        }
    }
}
```

In this example, `Person` class implements `Cloneable` interface and overrides the `clone()` method to perform cloning. The `clone()` method is used to create a copy of the `Person` object.



### Q-10) What is an Exception? Explain the exception hierarchy. Explain how to throw, catch, and handle Exceptions.

#### What is an Exception?
An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. Exceptions are objects in Java that represent errors or exceptional conditions that arise during the execution of a program. These can be due to a variety of reasons, such as invalid input, resource unavailability, or programming errors.

#### Exception Hierarchy:
In Java, exceptions are organized in a hierarchical structure. At the top of the hierarchy is the `Throwable` class, which is the superclass of all errors and exceptions. The two main subtypes of `Throwable` are `Error` and `Exception`.

- **Error**: Errors represent abnormal conditions that are not expected to be caught by the application. These are usually severe and indicate serious problems that typically cannot be recovered from, such as `OutOfMemoryError` or `StackOverflowError`.
  
- **Exception**: Exceptions represent exceptional conditions that can be handled by the application. Exceptions are further divided into two categories: checked exceptions and unchecked exceptions.
  
  - **Checked Exceptions**: Checked exceptions are exceptions that must be either caught or declared in the method signature using the `throws` keyword. Examples include `IOException` and `ClassNotFoundException`.
  
  - **Unchecked Exceptions**: Unchecked exceptions, also known as runtime exceptions, do not need to be explicitly caught or declared. They typically indicate programming errors or logical errors that occur at runtime, such as `NullPointerException` or `ArrayIndexOutOfBoundsException`.

#### Throwing Exceptions:
To throw an exception in Java, you use the `throw` keyword followed by an instance of the exception class.

```java
public class Example {
    public void method() {
        // Throw an ArithmeticException
        throw new ArithmeticException("Cannot divide by zero");
    }
}
```

#### Catching Exceptions:
To catch an exception in Java, you use a `try-catch` block. The `try` block contains the code that may throw an exception, and the `catch` block catches the exception and handles it.

```java
public class Example {
    public void method() {
        try {
            // Code that may throw an exception
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            // Handle the exception
            System.out.println("An arithmetic exception occurred: " + e.getMessage());
        }
    }
}
```

#### Handling Exceptions:
Exception handling in Java allows you to gracefully handle errors or exceptional conditions that may occur during program execution. Here's how you handle exceptions:

- **Try-Catch Block**: Use a `try-catch` block to catch exceptions and handle them gracefully. The `try` block contains the code that may throw an exception, and the `catch` block catches the exception and handles it appropriately.

- **Finally Block**: You can use a `finally` block to execute code that needs to be run regardless of whether an exception is thrown or not. This block is useful for releasing resources or closing connections.

- **Throwing Exceptions**: You can throw exceptions using the `throw` keyword to indicate that an error has occurred and needs to be handled by the calling code.

- **Handling Multiple Exceptions**: You can handle multiple types of exceptions by using multiple `catch` blocks, each catching a different type of exception.

- **Propagating Exceptions**: If a method is unable to handle an exception, it can propagate the exception to its caller using the `throws` keyword in the method signature.

```java
public class Example {
    public void method() {
        try {
            // Code that may throw an exception
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            // Handle the exception
            System.out.println("An arithmetic exception occurred: " + e.getMessage());
        } finally {
            // Code that always executes, regardless of whether an exception is thrown
            System.out.println("Finally block executed");
        }
    }
}
```

Exception handling allows you to write robust and reliable code by gracefully handling errors and exceptional conditions that may occur during program execution. It helps in maintaining the stability and reliability of the application.



```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class WordCount {
    public static void main(String[] args) {
        if (args.length != 1) {
            System.out.println("Usage: java WordCount <filename>");
            return;
        }

        String filename = args[0];
        int wordCount = 0;

        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                String[] words = line.split("\\s+");
                wordCount += words.length;
            }
            System.out.println("Number of words in file '" + filename + "': " + wordCount);
        } catch (IOException e) {
            System.err.println("Error reading file: " + e.getMessage());
        }
    }
}
```

This program takes a filename as a command-line argument and counts the number of words in the specified text file. It reads the file line by line, splits each line into words using whitespace characters as delimiters, and increments the word count accordingly. Finally, it prints the total number of words found in the file.



### Q-12) Write a program that illustrates interface inheritance. Interface P is extended by Pl and P2. Interface P12 inherits from both Pl and P2. Each interface declares one constant and one method. class Q implements P12. Instantiate Q and invoke each of its methods. Each method displays one of the constants.

```java
// Interface P
interface P {
    int CONSTANT_P = 10;
    void methodP();
}

// Interface Pl extending P
interface Pl extends P {
    int CONSTANT_Pl = 20;
    void methodPl();
}

// Interface P2 extending P
interface P2 extends P {
    int CONSTANT_P2 = 30;
    void methodP2();
}

// Interface P12 inheriting from Pl and P2
interface P12 extends Pl, P2 {
    int CONSTANT_P12 = 40;
    void methodP12();
}

// Class Q implementing P12
class Q implements P12 {
    public void methodP() {
        System.out.println("Constant from P: " + CONSTANT_P);
    }
    public void methodPl() {
        System.out.println("Constant from Pl: " + CONSTANT_Pl);
    }
    public void methodP2() {
        System.out.println("Constant from P2: " + CONSTANT_P2);
    }
    public void methodP12() {
        System.out.println("Constant from P12: " + CONSTANT_P12);
    }
}

public class InterfaceInheritanceExample {
    public static void main(String[] args) {
        Q q = new Q();
        q.methodP();
        q.methodPl();
        q.methodP2();
        q.methodP12();
    }
}
```

#### Output:
```
Constant from P: 10
Constant from Pl: 20
Constant from P2: 30
Constant from P12: 40
```

In this program:
- Interfaces `P`, `Pl`, and `P2` declare constants and methods.
- Interface `P12` inherits from both `Pl` and `P2`.
- Class `Q` implements interface `P12` and provides implementations for all its methods.
- In the `main` method, we instantiate class `Q` and invoke each of its methods, which display the constants defined in the respective interfaces.



### Q-13) What is an Exception? Explain try, catch, and finally with example.

#### What is an Exception?
An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. Exceptions are objects in Java that represent errors or exceptional conditions that arise during the execution of a program. These can be due to a variety of reasons, such as invalid input, resource unavailability, or programming errors.

#### Try-Catch-Finally:
In Java, exception handling is done using the `try-catch-finally` blocks. Here's a brief explanation of each:

- **Try Block**: The `try` block contains the code that may throw an exception. It is followed by one or more `catch` blocks to handle different types of exceptions.

- **Catch Block**: A `catch` block is used to catch and handle exceptions. It specifies the type of exception it can handle, and if the exception occurs in the `try` block, control is transferred to the corresponding `catch` block.

- **Finally Block**: The `finally` block is optional and is used to execute code that must be run regardless of whether an exception occurs or not. It is typically used to release resources or close connections.

#### Example:
```java
public class ExceptionExample {
    public static void main(String[] args) {
        try {
            // Code that may throw an exception
            int result = divide(10, 0);
            System.out.println("Result: " + result); // This line will not be executed
        } catch (ArithmeticException e) {
            // Handle the ArithmeticException
            System.err.println("Arithmetic Exception: " + e.getMessage());
        } finally {
            // Code that always executes, regardless of whether an exception is thrown
            System.out.println("Finally block executed");
        }
    }

    public static int divide(int a, int b) {
        return a / b; // This line may throw an ArithmeticException
    }
}
```

In this example:
- We have a `divide` method that may throw an `ArithmeticException` if the divisor is zero.
- Inside the `main` method, we have a `try` block containing the division operation.
- If an `ArithmeticException` occurs during the division, control is transferred to the corresponding `catch` block, where we handle the exception.
- Regardless of whether an exception occurs or not, the `finally` block is executed, where we print a message indicating that it has been executed.

#### Output (if divisor is 0):
```
Arithmetic Exception: / by zero
Finally block executed
```

#### Summary:
Exception handling in Java using `try-catch-finally` blocks allows you to gracefully handle errors or exceptional conditions that may occur during program execution. The `try` block contains the code that may throw an exception, the `catch` block handles the exception, and the `finally` block executes code that must run regardless of whether an exception occurs or not.



### Q-14) What is the keyword "throw" used for? What is the keyword "throws" used for?

#### "throw" Keyword:
The "throw" keyword in Java is used to explicitly throw an exception within a method or block of code. When an exceptional situation occurs that cannot be handled locally, the "throw" keyword is used to throw an instance of an exception class.

```java
public class ThrowExample {
    public static void main(String[] args) {
        try {
            // Throwing an ArithmeticException explicitly
            throw new ArithmeticException("Explicitly thrown exception");
        } catch (ArithmeticException e) {
            System.err.println("Caught ArithmeticException: " + e.getMessage());
        }
    }
}
```

In this example, the "throw" keyword is used to throw an ArithmeticException explicitly. This exception is then caught and handled in the catch block.

#### "throws" Keyword:
The "throws" keyword in Java is used in method declarations to indicate that the method may throw one or more types of exceptions. It specifies the exceptions that the method may throw, but does not handle them within the method itself. Instead, it delegates the responsibility of handling these exceptions to the caller of the method.

```java
public class ThrowsExample {
    // Method declaration with "throws" keyword
    public static void method() throws IOException {
        // Method code that may throw an IOException
        throw new IOException("Exception thrown from method");
    }

    public static void main(String[] args) {
        try {
            // Calling method that throws IOException
            method();
        } catch (IOException e) {
            System.err.println("Caught IOException: " + e.getMessage());
        }
    }
}
```

In this example, the "method" is declared with the "throws" keyword, indicating that it may throw an IOException. When calling the "method" from the main method, we either handle the IOException using a try-catch block or propagate it using the "throws" keyword in the main method declaration.

#### Summary:
- The "throw" keyword is used to explicitly throw an exception within a method or block of code.
- The "throws" keyword is used in method declarations to indicate that the method may throw one or more types of exceptions, but does not handle them within the method itself.



### Q-15) Differentiate between Abstract class and Interfaces.

| Aspect                 | Abstract Class                                       | Interface                                             |
|------------------------|------------------------------------------------------|-------------------------------------------------------|
| Definition             | An abstract class is a class that cannot be instantiated on its own and may contain abstract methods. | An interface is a reference type in Java that contains only abstract methods and constants. |
| Instantiation          | An abstract class cannot be instantiated directly.   | An interface cannot be instantiated directly.        |
| Inheritance            | An abstract class can provide a partial implementation through concrete methods. | An interface cannot provide any implementation and only contains method signatures. |
| Multiple Inheritance   | Java does not support multiple inheritance for classes, but an abstract class can extend only one other class. | Java supports multiple inheritance for interfaces, allowing a class to implement multiple interfaces. |
| Accessibility          | Abstract classes can have constructors and member variables with various access modifiers. | Interface methods are by default public and cannot have any other access modifier (except default in Java 8+). |
| Extensibility          | An abstract class can be extended using the "extends" keyword. | An interface can be implemented using the "implements" keyword. |
| Purpose                | Abstract classes are used when there is a need to define a common base class with some implementation details for a group of related classes. | Interfaces are used to define a contract for classes that implement them, providing a way to achieve abstraction and multiple inheritance. |
| Versioning             | Adding a new method to an abstract class requires modifying the class, which may affect existing subclasses. | Adding a new method to an interface does not affect existing implementations, as they are required to provide an implementation for all interface methods. |

#### Summary:
- Abstract classes and interfaces are both used to achieve abstraction and define contracts for classes.
- Abstract classes allow partial implementation and single inheritance, while interfaces allow full abstraction and multiple inheritance.
- Choosing between an abstract class and an interface depends on the specific requirements of the design and the relationship between classes.



### Q-16) Explain the following Java keywords using appropriate examples:

a) throw:
The "throw" keyword in Java is used to explicitly throw an exception within a method or block of code. It is followed by an instance of an exception class, which represents the exceptional situation that occurred.

Example:
```java
public class ThrowExample {
    public static void main(String[] args) {
        try {
            // Throwing an ArithmeticException explicitly
            throw new ArithmeticException("Explicitly thrown exception");
        } catch (ArithmeticException e) {
            System.err.println("Caught ArithmeticException: " + e.getMessage());
        }
    }
}
```
In this example, the "throw" keyword is used to throw an ArithmeticException explicitly. This exception is then caught and handled in the catch block.

b) throws:
The "throws" keyword in Java is used in method declarations to indicate that the method may throw one or more types of exceptions. It specifies the exceptions that the method may throw, but does not handle them within the method itself. Instead, it delegates the responsibility of handling these exceptions to the caller of the method.

Example:
```java
public class ThrowsExample {
    // Method declaration with "throws" keyword
    public static void method() throws IOException {
        // Method code that may throw an IOException
        throw new IOException("Exception thrown from method");
    }

    public static void main(String[] args) {
        try {
            // Calling method that throws IOException
            method();
        } catch (IOException e) {
            System.err.println("Caught IOException: " + e.getMessage());
        }
    }
}
```
In this example, the "method" is declared with the "throws" keyword, indicating that it may throw an IOException. When calling the "method" from the main method, we either handle the IOException using a try-catch block or propagate it using the "throws" keyword in the main method declaration.

c) finally:
The "finally" keyword in Java is used to define a block of code that will be executed regardless of whether an exception occurs or not. It is often used to release resources or perform cleanup operations.

Example:
```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            // Code that may throw an exception
            int result = divide(10, 0);
            System.out.println("Result: " + result); // This line will not be executed
        } catch (ArithmeticException e) {
            // Handle the ArithmeticException
            System.err.println("Arithmetic Exception: " + e.getMessage());
        } finally {
            // Code that always executes, regardless of whether an exception is thrown
            System.out.println("Finally block executed");
        }
    }

    public static int divide(int a, int b) {
        return a / b; // This line may throw an ArithmeticException
    }
}
```
In this example, the "finally" block is used to execute code that must be run regardless of whether an exception occurs or not. In this case, it prints a message indicating that it has been executed.



### Q-17) Differentiate between checked and unchecked exception?

| Aspect                 | Checked Exception                                    | Unchecked Exception                                  |
|------------------------|------------------------------------------------------|------------------------------------------------------|
| Definition             | Checked exceptions are checked at compile-time, meaning the compiler checks if they are handled or declared. | Unchecked exceptions are not checked at compile-time and are typically programming errors or runtime conditions. |
| Inheritance            | Checked exceptions are subclasses of `Exception` class but not subclasses of `RuntimeException`. | Unchecked exceptions are subclasses of `RuntimeException` or `Error` classes. |
| Handling Requirement   | Checked exceptions must be either caught or declared using the `throws` keyword in the method signature. | Unchecked exceptions do not need to be explicitly caught or declared. |
| Examples               | Examples of checked exceptions include `IOException`, `ClassNotFoundException`, and `SQLException`. | Examples of unchecked exceptions include `NullPointerException`, `ArrayIndexOutOfBoundsException`, and `ArithmeticException`. |
| Usage                  | Checked exceptions are used to handle expected conditions that might occur during the execution of a program, such as file I/O errors or database connectivity issues. | Unchecked exceptions are used to represent unexpected conditions that might occur due to programming errors or unforeseen runtime conditions. |

#### Summary:
- Checked exceptions are checked at compile-time and must be handled or declared.
- Unchecked exceptions are not checked at compile-time and typically represent programming errors or runtime conditions.
- Checked exceptions are subclasses of `Exception` but not `RuntimeException`, while unchecked exceptions are subclasses of `RuntimeException` or `Error`.
- Checked exceptions are used to handle expected conditions, while unchecked exceptions represent unexpected conditions.

### Q-18) Exemplify throw and throws clause of exception handling?

**throw:**
The "throw" keyword in Java is used to explicitly throw an exception within a method or block of code. It is followed by an instance of an exception class, which represents the exceptional situation that occurred.

Example:
```java
public class ThrowExample {
    public static void main(String[] args) {
        try {
            // Throwing an ArithmeticException explicitly
            throw new ArithmeticException("Explicitly thrown exception");
        } catch (ArithmeticException e) {
            System.err.println("Caught ArithmeticException: " + e.getMessage());
        }
    }
}
```

In this example, the "throw" keyword is used to throw an ArithmeticException explicitly. This exception is then caught and handled in the catch block.

**throws:**
The "throws" keyword in Java is used in method declarations to indicate that the method may throw one or more types of exceptions. It specifies the exceptions that the method may throw, but does not handle them within the method itself. Instead, it delegates the responsibility of handling these exceptions to the caller of the method.

Example:
```java
public class ThrowsExample {
    // Method declaration with "throws" keyword
    public static void method() throws IOException {
        // Method code that may throw an IOException
        throw new IOException("Exception thrown from method");
    }

    public static void main(String[] args) {
        try {
            // Calling method that throws IOException
            method();
        } catch (IOException e) {
            System.err.println("Caught IOException: " + e.getMessage());
        }
    }
}
```

In this example, the "method" is declared with the "throws" keyword, indicating that it may throw an IOException. When calling the "method" from the main method, we either handle the IOException using a try-catch block or propagate it using the "throws" keyword in the main method declaration.

### Q-19) Demonstrate the use of try-catch block by catching ArithmeticExceptions and InputMismatchExceptions?

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class ExceptionHandlingExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        try {
            System.out.print("Enter a number: ");
            int num1 = scanner.nextInt();

            System.out.print("Enter another number: ");
            int num2 = scanner.nextInt();

            int result = num1 / num2;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.err.println("Arithmetic Exception: " + e.getMessage());
        } catch (InputMismatchException e) {
            System.err.println("Input Mismatch Exception: " + e.getMessage());
        } finally {
            // Close the scanner
            scanner.close();
        }
    }
}
```

In this example:
- We use a try-catch block to handle exceptions that may occur during user input.
- Inside the try block, we attempt to read two integers from the user and perform division.
- If an ArithmeticException occurs (e.g., if the second number is zero), it is caught and handled in the corresponding catch block.
- If an InputMismatchException occurs (e.g., if the user enters a non-integer value), it is caught and handled in the second catch block.
- The finally block is used to close the scanner, ensuring that system resources are released even if an exception occurs.

## End of Unit-6 QB
*You Can Check Out Other Files For More QB Solution*


![alt text](https://i.imgur.com/8Qw2VtL.png)
    
**Created By Vatsal Shah**
    
`csevatsalshah@gmail.com`
