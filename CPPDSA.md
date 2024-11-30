# ~ C++ and Data Structures & Algorithms (DSA) 🧑🏻‍💻 ~

This note is a blend of the core concepts of **C++ programming** and the fundamentals of **Data Structures and Algorithms (DSA)**.

---

## **C++ Basics and Advanced Concepts**  

### **Introduction to C++**  
C++ is a powerful, high-performance programming language that supports both **procedural** and **object-oriented programming** paradigms. It’s widely used in competitive programming, game development, and system-level applications.  

- **Developed by:** Bjarne Stroustrup in 1985.  
- **Key Features:**
  - Multi-paradigm (Procedural, OOP).
  - Rich Standard Template Library (STL).
  - Strong memory management through pointers.

---

### **Structure of a C++ Program**

```cpp
#include <iostream> // Standard library for I/O

int main() {
    std::cout << "Hello, World!" << std::endl; // Print to console
    return 0; // End of program
}
```

**Key Components:**
1. **`#include` Directive:** Includes libraries like `<iostream>`.  
2. **`main()` Function:** Entry point of the program.  
3. **`std::cout` and `std::endl`:** Used for output.  

---

### **Variables and Data Types**  
C++ provides several data types to store information.

| **Data Type** | **Description**             | **Example**               |
|---------------|-----------------------------|---------------------------|
| `int`         | Integer                     | `int age = 21;`           |
| `float`       | Decimal number (single precision) | `float pi = 3.14f;`     |
| `double`      | Decimal number (double precision) | `double gpa = 3.987;` |
| `char`        | Single character            | `char grade = 'A';`       |
| `bool`        | Boolean value               | `bool isAlive = true;`    |
| `string`      | Textual data (from `<string>`) | `string name = "John";` |

**Constants:**
Use `const` to define unchangeable variables:  
```cpp
const double PI = 3.14159;
```

---

### **Input and Output**  

**Input:** Use `std::cin` for user input.  
```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    cout << "Enter your age: ";
    cin >> age;
    cout << "Your age is " << age << endl;
    return 0;
}
```

**Output:** Use `std::cout`.  
```cpp
cout << "Hello, C++!" << endl;
```

---

### **Control Flow Statements**

1. **If-Else Statements**:  
```cpp
if (condition) {
    // Code if condition is true
} else {
    // Code if condition is false
}
```

2. **Switch Statement**:  
```cpp
switch (value) {
    case 1: cout << "Case 1"; break;
    case 2: cout << "Case 2"; break;
    default: cout << "Default case";
}
```

3. **Loops**:  
   - **For Loop:**  
     ```cpp
     for (int i = 0; i < 5; i++) {
         cout << i << endl;
     }
     ```
   - **While Loop:**  
     ```cpp
     int i = 0;
     while (i < 5) {
         cout << i << endl;
         i++;
     }
     ```
   - **Do-While Loop:**  
     ```cpp
     int i = 0;
     do {
         cout << i << endl;
         i++;
     } while (i < 5);
     ```

---

### **Functions and Recursion**

#### **Functions**  
Reusable blocks of code for modular programming.  
```cpp
int add(int a, int b) {
    return a + b;
}

int main() {
    cout << add(5, 3); // Outputs 8
    return 0;
}
```

#### **Recursion**  
A function calling itself.  
```cpp
int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n - 1);
}
```

---

### **Object-Oriented Programming in C++**

#### **Classes and Objects**  
A **class** is a blueprint for objects.  
```cpp
class Car {
public:
    string brand;
    int year;

    void displayInfo() {
        cout << brand << " - " << year << endl;
    }
};
```

**Creating Objects:**  
```cpp
Car myCar;
myCar.brand = "Toyota";
myCar.year = 2020;
myCar.displayInfo();
```

#### **Inheritance**  
Allows a class to derive properties and methods from another class.  
```cpp
class Parent {
public:
    void greet() {
        cout << "Hello from Parent" << endl;
    }
};

class Child : public Parent {
public:
    void greet() {
        cout << "Hello from Child" << endl;
    }
};
```

---

### **Pointers and Memory Management**  

#### **Pointers**  
Variables that store memory addresses.  
```cpp
int x = 10;
int *ptr = &x; // Pointer to x
cout << *ptr;  // Dereferencing, outputs 10
```

#### **Dynamic Memory Allocation**  
Allocate memory at runtime.  
```cpp
int *arr = new int[5]; // Dynamic array
delete[] arr;          // Free memory
```

---

### **Standard Template Library (STL)**  

C++ provides a rich set of libraries for handling common data structures.

#### **Vectors**  
Dynamic arrays.  
```cpp
#include <vector>
vector<int> v = {1, 2, 3};
v.push_back(4); // Adds 4
cout << v[0];   // Outputs 1
```

#### **Maps**  
Stores key-value pairs.  
```cpp
#include <map>
map<string, int> m;
m["Alice"] = 90;
cout << m["Alice"]; // Outputs 90
```

#### **Sets**  
Stores unique elements.  
```cpp
#include <set>
set<int> s = {1, 2, 2, 3};
cout << s.size(); // Outputs 3
```

---

### **String Library**  

| **Method**         | **Description**                                  | **Example**                       |
|--------------------|--------------------------------------------------|-----------------------------------|
| `s.length()`       | Returns the length of the string.                | `"Hello".length()` → `5`         |
| `s.substr(a, b)`   | Extracts a substring.                            | `"Hello".substr(1, 3)` → `"ell"` |
| `s.find("str")`    | Finds the position of a substring.               | `"Hello".find("e")` → `1`        |
| `s.compare("str")` | Compares two strings lexicographically.          | `"abc".compare("xyz")` → `-1`    |
| `s.append("str")`  | Appends a string to the end.                     | `"Hi".append(" there")` → `"Hi there"` |

---

# Data Structures and Algorithms (DSA) Basics  

**Data structures** and **Algorithms** that form the foundation of problem-solving in computer science. Mastering these concepts is critical for building efficient and scalable applications.

---

## **Data Structures**  

A **data structure** is a way to organize, manage, and store data for efficient access and modification.

---

### **1. Arrays**  

- **Definition:** A collection of elements stored in contiguous memory locations.  
- **Usage:** Used to store multiple items of the same type.  

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    cout << arr[2]; // Outputs 30
    return 0;
}
```

**Key Operations:**
- Access: `O(1)`
- Search: `O(n)`
- Insertion/Deletion: `O(n)`  

---

### **2. Linked Lists**  

- **Definition:** A linear data structure where elements (nodes) are connected using pointers.  
- **Types:**
  - Singly Linked List
  - Doubly Linked List
  - Circular Linked List  

**Example:**
```cpp
struct Node {
    int data;
    Node* next;
};

Node* head = new Node();
head->data = 10;
head->next = nullptr;
```

**Key Operations:**
- Insertion/Deletion: `O(1)` at the head; `O(n)` elsewhere.
- Search: `O(n)`.  

---

### **3. Stacks**  

- **Definition:** A Last In, First Out (LIFO) data structure.  
- **Applications:** Function calls, undo operations, balancing parentheses.  

**Example Using STL:**
```cpp
#include <stack>
stack<int> s;
s.push(10);
s.push(20);
s.pop(); // Removes 20
```

**Key Operations:**
- Push: `O(1)`
- Pop: `O(1)`
- Peek/Top: `O(1)`

---

### **4. Queues**  

- **Definition:** A First In, First Out (FIFO) data structure.  
- **Applications:** Process scheduling, breadth-first search.  

**Example Using STL:**
```cpp
#include <queue>
queue<int> q;
q.push(10);
q.push(20);
q.pop(); // Removes 10
```

**Key Operations:**
- Enqueue: `O(1)`
- Dequeue: `O(1)`  

---

### **5. Trees**  

- **Definition:** A hierarchical data structure with a root node and child nodes.  
- **Common Types:**
  - Binary Trees
  - Binary Search Trees (BST)
  - AVL Trees (Self-balancing BST)

**Binary Search Tree Example:**
```cpp
struct Node {
    int data;
    Node* left;
    Node* right;
};

Node* createNode(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    newNode->left = nullptr;
    newNode->right = nullptr;
    return newNode;
}
```

**Key Operations:**
- Search: `O(log n)` in balanced trees; `O(n)` in skewed trees.
- Insertion/Deletion: `O(log n)` in balanced trees.

---

### **6. Hash Tables**  

- **Definition:** A data structure that maps keys to values for efficient lookup.  
- **Applications:** Caching, database indexing.  

**Example Using STL:**
```cpp
#include <unordered_map>
unordered_map<string, int> map;
map["apple"] = 10;
cout << map["apple"]; // Outputs 10
```

**Key Operations:**
- Insert/Search/Delete: `O(1)` on average.

---

## **Famous Algorithms**  

### **1. Sorting Algorithms**  

**a) Bubble Sort:**  
Repeatedly swaps adjacent elements if they are in the wrong order.  
```cpp
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}
```
- Time Complexity: `O(n^2)`  

**b) Merge Sort:**  
Divides the array into halves, sorts them, and merges the results.  
```cpp
void merge(int arr[], int l, int m, int r) {
    // Implementation of merging two sorted arrays
}

void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}
```
- Time Complexity: `O(n log n)`  

---

### **2. Searching Algorithms**  

**a) Linear Search:**  
Iterates through the array to find an element.  
```cpp
int linearSearch(int arr[], int n, int x) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == x) return i;
    }
    return -1;
}
```
- Time Complexity: `O(n)`  

**b) Binary Search:**  
Efficiently searches in a sorted array by dividing the search space.  
```cpp
int binarySearch(int arr[], int l, int r, int x) {
    while (l <= r) {
        int mid = l + (r - l) / 2;
        if (arr[mid] == x) return mid;
        if (arr[mid] < x) l = mid + 1;
        else r = mid - 1;
    }
    return -1;
}
```
- Time Complexity: `O(log n)`  

---

### **3. Graph Algorithms**  

**a) Depth-First Search (DFS):**  
Explores as far as possible along a branch before backtracking.  
```cpp
void dfs(int node, vector<bool>& visited, vector<int> adj[]) {
    visited[node] = true;
    for (int neighbor : adj[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor, visited, adj);
        }
    }
}
```
- Time Complexity: `O(V + E)`  

**b) Breadth-First Search (BFS):**  
Explores all neighbors before moving deeper.  
```cpp
void bfs(int start, vector<int> adj[], int V) {
    queue<int> q;
    vector<bool> visited(V, false);
    q.push(start);
    visited[start] = true;

    while (!q.empty()) {
        int node = q.front();
        q.pop();
        for (int neighbor : adj[node]) {
            if (!visited[neighbor]) {
                q.push(neighbor);
                visited[neighbor] = true;
            }
        }
    }
}
```
- Time Complexity: `O(V + E)`  

---

### **4. Dynamic Programming Algorithm: Knapsack Problem**  
Solves optimization problems by breaking them into subproblems.  
```cpp
int knapsack(int W, int wt[], int val[], int n) {
    int dp[n + 1][W + 1];
    for (int i = 0; i <= n; i++) {
        for (int w = 0; w <= W; w++) {
            if (i == 0 || w == 0) dp[i][w] = 0;
            else if (wt[i - 1] <= w) {
                dp[i][w] = max(val[i - 1] + dp[i - 1][w - wt[i - 1]], dp[i - 1][w]);
            } else {
                dp[i][w] = dp[i - 1][w];
            }
        }
    }
    return dp[n][W];
}
```
- Time Complexity: `O(n * W)`  

---

### **5. Shortest Path Algorithm: Dijkstra’s Algorithm**  
Finds the shortest path from a source to all vertices.  
```cpp
void dijkstra(int src, vector<pair<int, int>> adj[], int V) {
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<>> pq;
    vector<int> dist(V, INT_MAX);

    dist[src] = 0;
    pq.push({0, src});

    while (!pq.empty()) {
        int node = pq.top().second;
        pq.pop();

        for (auto neighbor : adj[node]) {
            int weight = neighbor.second;
            int nextNode = neighbor.first;

            if (dist[node] + weight < dist[nextNode]) {
                dist[nextNode] = dist[node] + weight;
                pq.push({dist[nextNode], nextNode});
            }
        }
    }
}
```
- Time Complexity: `O((V + E) log V)`  

---