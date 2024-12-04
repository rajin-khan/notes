# ~ Java and OOP (Object Oriented Programming) ☕️ ~

Welcome to the world of **Java programming**! This note introduces the essentials of Java, a powerful, versatile programming language, and the foundational principles of **Object-Oriented Programming (OOP)**.  

---

## **What is Java?**  
Java is a high-level, platform-independent programming language developed by **Sun Microsystems** (now Oracle) in 1995.  
- **Key Features:**  
  - Write Once, Run Anywhere (WORA)  
  - Strongly typed and object-oriented  
  - Robust memory management with automatic garbage collection  
  - Extensive libraries and frameworks  

---

## **Structure of a Java Program**  
Every Java program must contain a **class** and a **main() method** as the entry point.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); // Print statement
    }
}
```

### **Key Components**:
1. **Class**: Blueprint for creating objects.  
2. **`main()` Method**: The entry point of execution.  
3. **`System.out.println()`**: Outputs text to the console.  

---

## **Basic Syntax**  
### **Variables and Data Types**  
In Java, variables must be declared with a specific **data type**.  

| **Data Type** | **Description**           | **Example**             |
|---------------|---------------------------|-------------------------|
| `int`         | Integer (whole numbers)   | `int x = 10;`           |
| `float`       | Decimal numbers (single precision) | `float pi = 3.14f;` |
| `double`      | Decimal numbers (double precision) | `double gpa = 3.987;` |
| `char`        | Single character          | `char grade = 'A';`     |
| `String`      | Sequence of characters    | `String name = "John";` |
| `boolean`     | True/False values         | `boolean isJavaFun = true;` |

### **Constants**  
Use `final` to declare constants:  
```java
final int DAYS_IN_WEEK = 7;
```

---

## **Input and Output**

### **Printing Output**:
Use `System.out.println()` for printing:  
```java
System.out.println("The value is: " + x);
```

### **Taking Input**:
Use the **Scanner** class for user input:  
```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);
System.out.print("Enter your age: ");
int age = sc.nextInt(); // Reads an integer
```

---

## **Operators**

### **Arithmetic Operators**:
| **Operator** | **Operation**   | **Example** |
|--------------|-----------------|-------------|
| `+`          | Addition        | `x + y`     |
| `-`          | Subtraction     | `x - y`     |
| `*`          | Multiplication  | `x * y`     |
| `/`          | Division        | `x / y`     |
| `%`          | Modulus         | `x % y`     |

### **Comparison Operators**:
| **Operator** | **Meaning**    | **Example**   |
|--------------|----------------|---------------|
| `==`         | Equal to       | `x == y`      |
| `!=`         | Not equal to   | `x != y`      |
| `>`          | Greater than   | `x > y`       |
| `<`          | Less than      | `x < y`       |
| `>=`         | Greater or equal | `x >= y`   |
| `<=`         | Less or equal  | `x <= y`      |

### **Logical Operators**:
| **Operator** | **Meaning**     | **Example**         |
|--------------|-----------------|---------------------|
| `&&`         | Logical AND     | `x > 0 && y < 10`   |
| `||`         | Logical OR      | `x > 0 || y < 10`   |
| `!`          | Logical NOT     | `!(x > 0)`          |

---

## **Control Flow**

### **If-Else Statements**:
```java
if (condition) {
    // Code if true
} else {
    // Code if false
}
```

### **Switch Statement**:
```java
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Invalid day");
}
```

### **Loops**:
1. **For Loop**:
   ```java
   for (int i = 0; i < 5; i++) {
       System.out.println(i);
   }
   ```

2. **While Loop**:
   ```java
   int i = 0;
   while (i < 5) {
       System.out.println(i);
       i++;
   }
   ```

3. **Do-While Loop**:
   ```java
   int i = 0;
   do {
       System.out.println(i);
       i++;
   } while (i < 5);
   ```

---

## **Common Java Keywords**

| **Keyword**    | **Usage**                          |
|----------------|------------------------------------|
| `public`       | Access modifier for visibility    |
| `static`       | Shared by all instances of a class|
| `void`         | Indicates no return value         |
| `extends`      | Indicates inheritance             |
| `implements`   | Indicates interface implementation|

---

## **Basic Tips for Java:**  
1. Practice writing **simple programs** like calculators or file processors.  
2. Understand OOP principles by implementing small projects.  
3. Use IDEs like **IntelliJ IDEA** or **Eclipse** for efficient development.  
4. Focus on error handling using `try-catch` blocks.  

---


## **Introduction to Object-Oriented Programming (OOP)**

OOP is a programming paradigm based on the concept of **objects**. It focuses on structuring programs into reusable, modular components.

---

## **Classes and Objects**

### **Defining a Class**
A **class** is a blueprint for objects.  
```java
public class Car {
    String brand; // Attributes
    int year;

    // Constructor
    public Car(String brand, int year) {
        this.brand = brand;
        this.year = year;
    }

    // Methods
    public void displayInfo() {
        System.out.println(brand + " was manufactured in " + year);
    }
}
```

### **Creating Objects**
Objects are instances of a class.  
```java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Toyota", 2020); // Creating an object
        myCar.displayInfo(); // Calling a method
    }
}
```

---

## Key Concepts for OOP:

---

## **Inheritance**  

**Inheritance** allows one class (child) to acquire the properties and methods of another class (parent).  

### **Syntax:**
```java
class Parent {
    void display() {
        System.out.println("This is the parent class");
    }
}

class Child extends Parent {
    void show() {
        System.out.println("This is the child class");
    }
}
```

### **Example:**
```java
public class Main {
    public static void main(String[] args) {
        Child obj = new Child();
        obj.display(); // Parent's method
        obj.show();    // Child's method
    }
}
```

### **Method Overriding**
The child class can redefine the parent class's methods.  
```java
class Parent {
    void message() {
        System.out.println("Parent's message");
    }
}

class Child extends Parent {
    @Override
    void message() {
        System.out.println("Child's message");
    }
}
```

---

## **Polymorphism**  

### **Method Overloading**
Same method name, but different parameters.  
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

### **Method Overriding**
Allows a child class to modify a method in its parent class (as shown earlier).

---

## **Encapsulation**  

Encapsulation hides data by making fields private and providing public getters and setters.  
```java
class Student {
    private String name;

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }
}
```

---

## **Abstraction**

Abstraction hides implementation details using **abstract classes** or **interfaces**.  

### **Abstract Class:**
```java
abstract class Animal {
    abstract void sound();

    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```

### **Interface:**
```java
interface Animal {
    void sound();
}

class Cat implements Animal {
    public void sound() {
        System.out.println("Cat meows");
    }
}
```
---

## Useful additional libraries:

---

## **String Library**

The **String** class provides several methods for manipulating strings.

| **Method**              | **Description**                                  | **Example**                            |
|-------------------------|--------------------------------------------------|----------------------------------------|
| `length()`              | Returns the length of the string.                | `"Hello".length()` → `5`               |
| `charAt(index)`         | Returns the character at the specified index.    | `"Java".charAt(1)` → `'a'`             |
| `substring(start, end)` | Extracts a substring.                            | `"Hello".substring(0, 2)` → `"He"`     |
| `equals()`              | Compares two strings for equality.               | `"Java".equals("java")` → `false`      |
| `equalsIgnoreCase()`              | Compares two strings for equality, ignoring the case.               | `"Java".equalsIgnoreCase("java")` → `true`      |
| `toLowerCase()`         | Converts all characters to lowercase.            | `"JAVA".toLowerCase()` → `"java"`      |
| `toUpperCase()`         | Converts all characters to uppercase.            | `"java".toUpperCase()` → `"JAVA"`      |
| `split(delimiter)`      | Splits the string into an array of substrings.   | `"a,b,c".split(",")` → `["a", "b", "c"]` |
| `trim()`                | Removes leading and trailing spaces.             | `" Hello ".trim()` → `"Hello"`         |
| `replace(old, new)`     | Replaces occurrences of a character or string.   | `"aabbcc".replace("b", "x")` → `"aaxxcc"` |

---

## **Common Java Libraries**

### **1. Math Library**
The **`Math`** class provides utilities for mathematical operations.  
| **Method**          | **Description**                       | **Example**         |
|---------------------|---------------------------------------|---------------------|
| `Math.abs(x)`       | Absolute value of `x`.               | `Math.abs(-10)` → `10` |
| `Math.pow(a, b)`    | `a` raised to the power of `b`.       | `Math.pow(2, 3)` → `8.0` |
| `Math.sqrt(x)`      | Square root of `x`.                  | `Math.sqrt(16)` → `4.0` |
| `Math.max(a, b)`    | Returns the larger of `a` or `b`.     | `Math.max(10, 20)` → `20` |
| `Math.random()`     | Generates a random number (0.0–1.0). | `Math.random()` → `0.534` |

---

### **2. Collections Framework**
The **`java.util`** package provides data structures like lists, maps, and sets.  

#### **ArrayList**:
A resizable array.  
```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Java");
list.add("Python");
System.out.println(list);
```

#### **HashMap**:
Stores key-value pairs.  
```java
import java.util.HashMap;

HashMap<Integer, String> map = new HashMap<>();
map.put(1, "One");
map.put(2, "Two");
System.out.println(map.get(1)); // Outputs: One
```

---

## **Tips for OOP:**  
1. **Understand OOP Principles**: Practice with small projects implementing encapsulation, inheritance, etc.  
2. **Work with Libraries**: Explore built-in libraries like `java.util` and `java.io`.  
3. **Focus on Debugging**: Use IDE features like breakpoints and debugging tools.  
4. **Write Reusable Code**: Practice writing modular and reusable functions.  

---

## **Resources:**  
- [Official Java Documentation](https://docs.oracle.com/en/java/)  
- [Java Programming Tutorials - GeeksforGeeks](https://www.geeksforgeeks.org/java/)  