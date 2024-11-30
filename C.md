# ~ C Programming Basics 🖥️ ~

Welcome to a concise guide to understanding the fundamentals of **C programming**! This note covers essential topics for beginners, from syntax and structure to common commands and concepts.

---

## **What is C?**  
C is a general-purpose, high-level programming language developed by Dennis Ritchie in 1972. It’s widely used for:  
- System programming (e.g., OS development).  
- Embedded systems.  
- Performance-critical applications.

---

## **Structure of a C Program**  
A basic C program follows this structure:  

```c
#include <stdio.h> // Header file for input/output functions

int main() {
    // Your code starts here
    printf("Hello, World!\n"); // Print statement
    return 0; // Program ends successfully
}
```

### Key Components:
1. **`#include` Directives**: Includes standard libraries like `stdio.h`.  
2. **`main()` Function**: The entry point of any C program.  
3. **Statements**: Instructions for the program, ending with a `;`.  
4. **Comments**: Improve readability using `//` for single-line or `/* ... */` for multi-line.

---

## **Variables and Data Types**  
Variables store data values in memory, and each has a specific **data type**.  

### Common Data Types:
| Data Type  | Description                 | Example      |
|------------|-----------------------------|--------------|
| `int`      | Integer (whole numbers)     | `int x = 10;`|
| `float`    | Decimal numbers             | `float pi = 3.14;` |
| `char`     | Single characters           | `char grade = 'A';` |
| `double`   | Double-precision decimal    | `double gpa = 3.987;` |
| `void`     | No return value             | Used in functions. |

---

## **Input/Output**  

### Printing Output:
Use `printf()` to display text or variables.  
```c
printf("Value of x is: %d", x);
```
- `%d`: Integer  
- `%f`: Float  
- `%c`: Character  

### Taking Input:
Use `scanf()` to get user input.  
```c
scanf("%d", &x); // Store user input in x
```

---

## **Operators**  
C supports various operators for arithmetic, comparison, and logic.

### Arithmetic Operators:
| Operator | Operation   | Example  |
|----------|-------------|----------|
| `+`      | Addition    | `x + y`  |
| `-`      | Subtraction | `x - y`  |
| `*`      | Multiplication | `x * y` |
| `/`      | Division    | `x / y`  |
| `%`      | Modulus     | `x % y`  |

### Comparison Operators:
| Operator | Meaning           | Example       |
|----------|-------------------|---------------|
| `==`     | Equal to          | `x == y`      |
| `!=`     | Not equal to      | `x != y`      |
| `>`      | Greater than      | `x > y`       |
| `<`      | Less than         | `x < y`       |
| `>=`     | Greater or equal  | `x >= y`      |
| `<=`     | Less or equal     | `x <= y`      |

### Logical Operators:
| Operator | Meaning           | Example        |
|----------|-------------------|----------------|
| `&&`     | Logical AND       | `x > 0 && y < 10` |
| `||`     | Logical OR        | `x > 0 || y < 10` |
| `!`      | Logical NOT       | `!(x > 0)`     |

---

## **Control Flow Statements**  
Control the flow of execution using **decision-making** and **looping** statements.

### **If-Else**:
```c
if (condition) {
    // Code if true
} else {
    // Code if false
}
```

### **Switch**:
```c
switch (expression) {
    case 1:
        // Code for case 1
        break;
    case 2:
        // Code for case 2
        break;
    default:
        // Default case
}
```

### **Loops**:
1. **For Loop**:
   ```c
   for (int i = 0; i < 5; i++) {
       printf("%d ", i);
   }
   ```

2. **While Loop**:
   ```c
   int i = 0;
   while (i < 5) {
       printf("%d ", i);
       i++;
   }
   ```

3. **Do-While Loop**:
   ```c
   int i = 0;
   do {
       printf("%d ", i);
       i++;
   } while (i < 5);
   ```

---

## **Functions**  
Functions are reusable blocks of code.  

### Syntax:
```c
return_type function_name(parameters) {
    // Code
    return value;
}
```

**Example:**
```c
int add(int a, int b) {
    return a + b;
}
```

---

## **Arrays**  
An array is a collection of elements of the same type.  

**Declaration:**
```c
int numbers[5] = {1, 2, 3, 4, 5};
```

**Access Elements:**
```c
printf("%d", numbers[2]); // Outputs 3
```

---

## **Pointers**  
Pointers store the memory address of a variable.  

**Syntax:**
```c
int x = 10;
int *ptr = &x; // Pointer to x
printf("%d", *ptr); // Outputs the value of x (10)
```

---

## **Key Concepts**  

1. **Memory Allocation**:
   - **Static Allocation:** Declared at compile-time (e.g., arrays).
   - **Dynamic Allocation:** Managed at runtime using `malloc()` and `free()`.

2. **Preprocessor Directives**:
   - **`#define`**: Create macros or constants.
     ```c
     #define PI 3.14
     ```
   - **`#include`**: Include header files.
     ```c
     #include <math.h>
     ```

3. **Strings**:
   - Strings in C are arrays of characters ending with `\0`.
     ```c
     char str[] = "Hello";
     printf("%s", str);
     ```

---

## **Tips for Beginners**  
1. **Practice Basic Syntax:** Start with simple programs like calculators.  
2. **Focus on Debugging:** Understand error messages and how to fix them.  
3. **Use IDEs or Text Editors:** Tools like Code::Blocks or Visual Studio Code can speed up development.  
4. **Learn Memory Management:** It’s crucial in C for better performance and avoiding memory leaks.  

---

## **Resources**  
- [C Programming Guide by GeeksforGeeks](https://www.geeksforgeeks.org/c-programming-language/)  
- [Learn-C.org Interactive Tutorials](https://www.learn-c.org/)  