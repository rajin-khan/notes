#  ~ **Dart - Basic Language Guide** 🎯 ~

Dart is a modern, object-oriented, open-source programming language developed by Google. It is optimized for building high-performance applications across multiple platforms, especially with **Flutter** for mobile, web, and desktop development.

---

## **Key Features of Dart**

- **Optimized for UI Development**: Dart is built for creating stunning user interfaces with tools like Flutter.
- **Null Safety**: Provides robust support for null safety, reducing runtime errors.
- **Ahead-of-Time (AOT) Compilation**: Produces highly optimized native code for fast execution.
- **Hot Reload**: Boosts developer productivity by instantly reflecting code changes during development.
- **Support for Multiple Paradigms**: Includes object-oriented, functional, and asynchronous programming.

---

## **Setting Up Dart**

### Installation
1. **Install Dart SDK**: Download from [dart.dev](https://dart.dev/get-dart).  
2. **Verify Installation**:  
   ```bash
   dart --version
   ```

### Writing Your First Dart Program
1. Create a file named `hello.dart`:
   ```dart
   void main() {
       print('Hello, Dart!');
   }
   ```
2. Run the program:
   ```bash
   dart run hello.dart
   ```

---

## **Dart Basics**

### **1. Variables and Data Types**

#### **Declaring Variables**
```dart
var name = 'John';  // Inferred as String
String city = 'New York';
int age = 25;
double height = 5.9;
bool isStudent = true;
```

#### **Constants and Final**
- **`const`**: Compile-time constant.
- **`final`**: Runtime constant.

```dart
const pi = 3.14;
final currentTime = DateTime.now();
```

---

### **2. Control Flow Statements**

#### **Conditional Statements**
```dart
void main() {
    int age = 20;
    if (age >= 18) {
        print('You are an adult.');
    } else {
        print('You are a minor.');
    }
}
```

#### **Loops**
```dart
void main() {
    // For loop
    for (int i = 0; i < 5; i++) {
        print(i);
    }

    // While loop
    int j = 0;
    while (j < 5) {
        print(j);
        j++;
    }

    // Do-while loop
    int k = 0;
    do {
        print(k);
        k++;
    } while (k < 5);
}
```

---

### **3. Functions**

#### **Defining and Calling Functions**
```dart
void greet(String name) {
    print('Hello, $name!');
}

void main() {
    greet('Alice');
}
```

#### **Optional Parameters**
```dart
void introduce(String name, [int? age]) {
    print('Name: $name');
    if (age != null) {
        print('Age: $age');
    }
}

void main() {
    introduce('John');
    introduce('Jane', 25);
}
```

#### **Named Parameters**
```dart
void display({required String title, String subtitle = ''}) {
    print('Title: $title');
    print('Subtitle: $subtitle');
}

void main() {
    display(title: 'Hello Dart', subtitle: 'Introduction');
}
```

---

### **4. Object-Oriented Programming in Dart**

#### **Classes and Objects**
```dart
class Person {
    String name;
    int age;

    Person(this.name, this.age);

    void introduce() {
        print('Hi, my name is $name and I am $age years old.');
    }
}

void main() {
    Person p = Person('Alice', 30);
    p.introduce();
}
```

#### **Inheritance**
```dart
class Animal {
    void eat() {
        print('This animal eats food.');
    }
}

class Dog extends Animal {
    void bark() {
        print('This dog barks.');
    }
}

void main() {
    Dog d = Dog();
    d.eat();
    d.bark();
}
```

#### **Abstract Classes**
```dart
abstract class Shape {
    void draw();
}

class Circle extends Shape {
    void draw() {
        print('Drawing a Circle');
    }
}

void main() {
    Shape s = Circle();
    s.draw();
}
```

---

### **5. Collections**

#### **List**
```dart
void main() {
    List<int> numbers = [1, 2, 3, 4];
    print(numbers[0]);  // Access first element
    numbers.add(5);     // Add an element
}
```

#### **Set**
```dart
void main() {
    Set<String> fruits = {'apple', 'banana', 'orange'};
    fruits.add('apple');  // Duplicate not added
    print(fruits);
}
```

#### **Map**
```dart
void main() {
    Map<String, int> scores = {'Alice': 90, 'Bob': 85};
    print(scores['Alice']);
    scores['Charlie'] = 95;  // Add new key-value pair
}
```

---

### **6. Asynchronous Programming**

#### **Future**
```dart
Future<String> fetchData() async {
    return Future.delayed(Duration(seconds: 2), () => 'Data loaded');
}

void main() async {
    print('Fetching data...');
    String data = await fetchData();
    print(data);
}
```

#### **Stream**
```dart
Stream<int> countStream(int max) async* {
    for (int i = 1; i <= max; i++) {
        await Future.delayed(Duration(seconds: 1));
        yield i;
    }
}

void main() async {
    await for (int value in countStream(5)) {
        print(value);
    }
}
```

---

### **7. Null Safety**

Dart enforces null safety to prevent null-related errors.

```dart
void main() {
    String? name; // Nullable
    name = 'Dart';
    print(name?.length); // Safe access
}
```

---

### **8. Important Libraries**

#### **dart:core**  
Contains fundamental classes like `String`, `int`, and `List`.  

#### **dart:async**  
For asynchronous programming with `Future` and `Stream`.

#### **dart:math**  
Provides mathematical functions and constants.
```dart
import 'dart:math';

void main() {
    print(sqrt(16)); // 4.0
}
```

#### **dart:io**  
For file and network operations.

```dart
import 'dart:io';

void main() {
    print('Enter your name: ');
    String? name = stdin.readLineSync();
    print('Hello, $name!');
}
```

---

### **9. Best Practices**

- Use **const** and **final** wherever possible for immutability.
- Leverage **null safety** to write safer code.
- Follow the Dart **naming conventions**:
  - Classes: PascalCase (`MyClass`)
  - Variables and functions: camelCase (`myVariable`)
- Use the **Flutter Analyzer** and tools like `dartfmt` for clean code.

---

### **10. Resources**

- **Dart Official Docs**: [dart.dev](https://dart.dev)
- **Learn Dart for Free**: [DartPad](https://dartpad.dev)
- **Books**: *Dart Apprentice* by Razeware