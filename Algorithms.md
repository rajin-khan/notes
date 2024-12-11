# ~ Algorithms in C++ 📜 ~

This note covers essential algorithms categorized by their complexity: Easy, Basic, Moderate, and Advanced. Each algorithm is accompanied by a fully implemented C++ solution. A special section is dedicated to interview questions commonly asked in top tech companies like FAANG.

## Algorithms covered in this note:

---

| **Problem Name**              | **Theoretical Explanation**                                                                                                                                       | **Theoretical Solution**                                                                                                                                                                                                                  |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **EASY** |
| **Linear Search**              | Search for a target value in an unsorted array by iterating through all elements.                                                                                 | Start from the first element and check each one until the target is found or the array ends.                                                                                                                                             |
| **Binary Search**              | Search for a target value in a sorted array using a divide-and-conquer approach.                                                                                  | Repeatedly divide the array into halves, and narrow down the search space based on comparisons with the middle element.                                                                                                                   |
| **Bubble Sort**                | Sort an array by repeatedly swapping adjacent elements if they are in the wrong order.                                                                             | Compare each pair of adjacent elements and swap them if needed. Repeat this process until no swaps are needed.                                                                                                                            |
| **Insertion Sort**             | Sort an array by building a sorted portion one element at a time.                                                                                                 | Pick an element from the unsorted part and insert it into the correct position in the sorted part.                                                                                                                                        |
| **Selection Sort**             | Sort an array by repeatedly selecting the smallest element from the unsorted portion and moving it to the sorted portion.                                          | Find the smallest element in the unsorted portion and swap it with the first unsorted element. Repeat for all elements.                                                                                                                  |
| **Fibonacci Sequence**         | Generate a sequence where each number is the sum of the two preceding ones.                                                                                       | Start with two numbers (0 and 1), and iteratively calculate the next numbers by adding the previous two.                                                                                                                                 |
| **Palindrome Check**           | Determine whether a string reads the same backward as forward.                                                                                                   | Compare characters from the beginning and end of the string moving towards the center, ensuring they match.                                                                                                                              |
| **Factorial (Recursive)**      | Calculate the product of all integers from 1 to a given number `n`.                                                                                              | Use recursion: multiply `n` by the factorial of `(n-1)` until reaching the base case `n = 0`.                                                                                                                                             |
| **BASIC** |
| **Merge Sort**                 | Divide an array into halves, sort each half, and merge the sorted halves.                                                                                         | Recursively divide the array into two halves, sort them, and merge the sorted halves.                                                                                                                                                     |
| **Quick Sort**                 | Sort an array by selecting a pivot element and partitioning the array into elements less than and greater than the pivot.                                          | Recursively partition the array into smaller arrays around a pivot element and sort the partitions.                                                                                                                                       |
| **Reverse an Array**           | Reverse the order of elements in an array.                                                                                                                       | Swap elements from the start and end of the array, moving toward the center.                                                                                                                                                              |
| **Kadane’s Algorithm**         | Find the maximum sum of a contiguous subarray.                                                                                                                   | Use a sliding window technique to maintain the current sum and update the maximum sum whenever the current sum exceeds it.                                                                                                               |
| **Longest Common Subsequence** | Find the length of the longest subsequence present in two strings.                                                                                               | Use dynamic programming to store the lengths of common subsequences between substrings.                                                                                                                                                   |
| **GCD (Greatest Common Divisor)** | Find the largest integer that divides two numbers without leaving a remainder.                                                                                   | Use the Euclidean algorithm: repeatedly replace the larger number by the remainder of dividing it by the smaller number until the remainder is 0.                                                                                         |
| **Power Function**             | Calculate `x` raised to the power `y`.                                                                                                                           | Use recursion to repeatedly multiply `x` by itself `y` times, or optimize with iterative squaring for faster computation.                                                                                                                 |
| **MODERATE** |
| **Merge Intervals**            | Combine overlapping intervals into a single interval.                                                                                                            | Sort intervals by their start times, then iterate and merge overlapping intervals by adjusting their end times.                                                                                                                           |
| **Cycle Detection in Graph**   | Determine whether a directed graph contains a cycle.                                                                                                             | Use depth-first search (DFS) and a recursion stack to detect back edges that indicate cycles.                                                                                                                                            |
| **Matrix Multiplication**      | Multiply two matrices and compute the resultant matrix.                                                                                                          | Compute the value of each element in the resultant matrix by taking the dot product of the corresponding row and column.                                                                                                                  |
| **Topological Sort**           | Generate a linear ordering of vertices in a directed acyclic graph (DAG).                                                                                        | Use Kahn’s Algorithm or DFS to generate a valid order where all edges point from earlier vertices to later ones.                                                                                                                          |
| **Floyd-Warshall Algorithm**   | Find the shortest paths between all pairs of vertices in a weighted graph.                                                                                        | Use dynamic programming to iteratively improve the shortest path between every pair of vertices by considering intermediate vertices.                                                                                                     |
| **ADVANCED** |
| **Dijkstra’s Algorithm**       | Find the shortest path from a source vertex to all other vertices in a weighted graph.                                                                            | Use a priority queue to iteratively update the shortest distances to neighboring vertices, starting from the source.                                                                                                                      |
| **Bellman-Ford Algorithm**     | Find the shortest paths from a source vertex to all vertices, allowing for negative weight edges.                                                                 | Iterate through all edges multiple times to update shortest paths, and check for negative weight cycles in a final pass.                                                                                                                  |
| **Knapsack Problem**           | Maximize the value of items in a bag with a limited weight capacity.                                                                                             | Use dynamic programming to calculate the maximum value achievable for each weight limit.                                                                                                                                                  |
| **KMP Algorithm**              | Search for a pattern in a text efficiently.                                                                                                                      | Precompute a prefix array to skip unnecessary comparisons, reducing the time complexity of pattern matching to O(n + m).                                                                                                                  |
| **Traveling Salesman Problem** | Find the shortest route visiting every city exactly once and returning to the starting city.                                                                      | Use backtracking or dynamic programming to explore all possible routes and calculate their costs, retaining the minimum.                                                                                                                  |

---

## **Easy Algorithms**  

These algorithms are fundamental, often used to introduce algorithmic concepts and improve problem-solving skills.

---

### **1. Linear Search**  
**Problem:** Given an array, find the index of a target value if it exists; otherwise, return -1.  

```cpp
#include <iostream>
using namespace std;

// Linear Search Implementation
int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 30;

    int result = linearSearch(arr, n, target);
    if (result != -1)
        cout << "Element found at index: " << result << endl;
    else
        cout << "Element not found" << endl;

    return 0;
}
```

---

### **2. Binary Search**  
**Problem:** Given a sorted array, find the index of a target value using binary search.  

```cpp
#include <iostream>
using namespace std;

// Binary Search Implementation
int binarySearch(int arr[], int left, int right, int target) {
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 40;

    int result = binarySearch(arr, 0, n - 1, target);
    if (result != -1)
        cout << "Element found at index: " << result << endl;
    else
        cout << "Element not found" << endl;

    return 0;
}
```

---

### **3. Bubble Sort**  
**Problem:** Sort an array using the bubble sort algorithm.  

```cpp
#include <iostream>
using namespace std;

// Bubble Sort Implementation
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr) / sizeof(arr[0]);

    bubbleSort(arr, n);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

### **4. Insertion Sort**  
**Problem:** Sort an array using the insertion sort algorithm.  

```cpp
#include <iostream>
using namespace std;

// Insertion Sort Implementation
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {12, 11, 13, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);

    insertionSort(arr, n);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

### **5. Selection Sort**  
**Problem:** Sort an array using the selection sort algorithm.  

```cpp
#include <iostream>
using namespace std;

// Selection Sort Implementation
void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIdx = i;

        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIdx]) {
                minIdx = j;
            }
        }

        swap(arr[i], arr[minIdx]);
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);

    selectionSort(arr, n);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

### **6. Fibonacci Sequence (Iterative)**  
**Problem:** Print the first `n` numbers in the Fibonacci sequence.

```cpp
#include <iostream>
using namespace std;

// Fibonacci Sequence Implementation
void fibonacci(int n) {
    int a = 0, b = 1;
    cout << a << " " << b << " ";
    for (int i = 2; i < n; i++) {
        int next = a + b;
        cout << next << " ";
        a = b;
        b = next;
    }
}

int main() {
    int n = 10;
    cout << "Fibonacci Sequence: ";
    fibonacci(n);

    return 0;
}
```

---

### **7. Palindrome Check**  
**Problem:** Check if a given string is a palindrome.  

```cpp
#include <iostream>
#include <string>
using namespace std;

// Palindrome Check Implementation
bool isPalindrome(string str) {
    int left = 0, right = str.length() - 1;

    while (left < right) {
        if (str[left] != str[right]) return false;
        left++;
        right--;
    }
    return true;
}

int main() {
    string str = "radar";
    if (isPalindrome(str))
        cout << str << " is a palindrome" << endl;
    else
        cout << str << " is not a palindrome" << endl;

    return 0;
}
```

---

### **8. Factorial (Recursive)**  
**Problem:** Calculate the factorial of a number using recursion.  

```cpp
#include <iostream>
using namespace std;

// Factorial Implementation
int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n - 1);
}

int main() {
    int n = 5;
    cout << "Factorial of " << n << " is " << factorial(n) << endl;

    return 0;
}
```

---
## **Basic Algorithms**  

These algorithms form the foundation of solving moderately complex problems and are essential for understanding how to manipulate data structures and optimize solutions.

---

### **1. Merge Sort**  
**Problem:** Sort an array using the merge sort algorithm (divide and conquer).  

```cpp
#include <iostream>
using namespace std;

// Merges two subarrays
void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1;
    int n2 = r - m;

    int L[n1], R[n2];

    for (int i = 0; i < n1; i++) L[i] = arr[l + i];
    for (int j = 0; j < n2; j++) R[j] = arr[m + 1 + j];

    int i = 0, j = 0, k = l;

    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) arr[k++] = L[i++];
        else arr[k++] = R[j++];
    }

    while (i < n1) arr[k++] = L[i++];
    while (j < n2) arr[k++] = R[j++];
}

// Merge sort function
void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}

int main() {
    int arr[] = {12, 11, 13, 5, 6, 7};
    int n = sizeof(arr) / sizeof(arr[0]);

    mergeSort(arr, 0, n - 1);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

### **2. Quick Sort**  
**Problem:** Sort an array using the quick sort algorithm.  

```cpp
#include <iostream>
using namespace std;

// Partition function
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = low - 1;

    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[high]);
    return i + 1;
}

// Quick sort function
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {10, 7, 8, 9, 1, 5};
    int n = sizeof(arr) / sizeof(arr[0]);

    quickSort(arr, 0, n - 1);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

### **3. Reverse an Array**  
**Problem:** Reverse the contents of an array in place.  

```cpp
#include <iostream>
using namespace std;

// Reverse array function
void reverseArray(int arr[], int n) {
    int start = 0, end = n - 1;
    while (start < end) {
        swap(arr[start], arr[end]);
        start++;
        end--;
    }
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int n = sizeof(arr) / sizeof(arr[0]);

    reverseArray(arr, n);

    cout << "Reversed array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

### **4. Kadane’s Algorithm**  
**Problem:** Find the maximum sum of a contiguous subarray.  

```cpp
#include <iostream>
#include <climits>
using namespace std;

// Kadane's algorithm function
int maxSubArraySum(int arr[], int n) {
    int maxSum = INT_MIN, currentSum = 0;

    for (int i = 0; i < n; i++) {
        currentSum += arr[i];
        if (currentSum > maxSum) maxSum = currentSum;
        if (currentSum < 0) currentSum = 0;
    }

    return maxSum;
}

int main() {
    int arr[] = {-2, -3, 4, -1, -2, 1, 5, -3};
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "Maximum contiguous sum is " << maxSubArraySum(arr, n) << endl;

    return 0;
}
```

---

### **5. Longest Common Subsequence (LCS)**  
**Problem:** Find the length of the longest subsequence present in both strings.  

```cpp
#include <iostream>
#include <vector>
using namespace std;

// LCS function
int lcs(string X, string Y) {
    int m = X.length(), n = Y.length();
    vector<vector<int>> dp(m + 1, vector<int>(n + 1, 0));

    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            if (X[i - 1] == Y[j - 1])
                dp[i][j] = 1 + dp[i - 1][j - 1];
            else
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1]);
        }
    }

    return dp[m][n];
}

int main() {
    string X = "AGGTAB";
    string Y = "GXTXAYB";

    cout << "Length of LCS is " << lcs(X, Y) << endl;

    return 0;
}
```

---

### **6. GCD (Greatest Common Divisor)**  
**Problem:** Find the GCD of two numbers using the Euclidean algorithm.  

```cpp
#include <iostream>
using namespace std;

// GCD function
int gcd(int a, int b) {
    if (b == 0) return a;
    return gcd(b, a % b);
}

int main() {
    int a = 56, b = 98;

    cout << "GCD of " << a << " and " << b << " is " << gcd(a, b) << endl;

    return 0;
}
```

---

### **7. Power Function**  
**Problem:** Calculate `x` raised to the power of `y` using recursion.  

```cpp
#include <iostream>
using namespace std;

// Power function
int power(int x, int y) {
    if (y == 0) return 1;
    return x * power(x, y - 1);
}

int main() {
    int x = 2, y = 5;

    cout << x << " raised to the power of " << y << " is " << power(x, y) << endl;

    return 0;
}
```

---

## **Moderate Algorithms**

These algorithms involve more intricate problem-solving techniques, focusing on optimization and advanced manipulation of data structures. They are frequently encountered in technical interviews.

---

### **1. Merge Intervals**  
**Problem:** Given an array of intervals, merge all overlapping intervals.  

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

// Merge Intervals Function
vector<pair<int, int>> mergeIntervals(vector<pair<int, int>>& intervals) {
    vector<pair<int, int>> merged;

    // Sort intervals by the start time
    sort(intervals.begin(), intervals.end());

    for (auto interval : intervals) {
        if (merged.empty() || merged.back().second < interval.first) {
            merged.push_back(interval); // Add non-overlapping interval
        } else {
            merged.back().second = max(merged.back().second, interval.second); // Merge intervals
        }
    }

    return merged;
}

int main() {
    vector<pair<int, int>> intervals = {{1, 3}, {2, 6}, {8, 10}, {15, 18}};
    vector<pair<int, int>> result = mergeIntervals(intervals);

    cout << "Merged Intervals: ";
    for (auto interval : result) {
        cout << "[" << interval.first << ", " << interval.second << "] ";
    }

    return 0;
}
```

---

### **2. Detect Cycle in a Graph (DFS)**  
**Problem:** Detect if a directed graph contains a cycle using Depth-First Search (DFS).  

```cpp
#include <iostream>
#include <vector>
using namespace std;

bool dfs(int node, vector<vector<int>>& adj, vector<int>& visited, vector<int>& recStack) {
    visited[node] = 1;
    recStack[node] = 1;

    for (int neighbor : adj[node]) {
        if (!visited[neighbor] && dfs(neighbor, adj, visited, recStack)) return true;
        if (recStack[neighbor]) return true; // Cycle detected
    }

    recStack[node] = 0;
    return false;
}

bool hasCycle(int V, vector<vector<int>>& adj) {
    vector<int> visited(V, 0), recStack(V, 0);

    for (int i = 0; i < V; i++) {
        if (!visited[i] && dfs(i, adj, visited, recStack)) return true;
    }

    return false;
}

int main() {
    int V = 4;
    vector<vector<int>> adj = {{1}, {2}, {3}, {0}}; // Directed graph adjacency list

    if (hasCycle(V, adj)) {
        cout << "Graph contains a cycle" << endl;
    } else {
        cout << "No cycle in the graph" << endl;
    }

    return 0;
}
```

---

### **3. Longest Increasing Subsequence (LIS)**  
**Problem:** Find the length of the longest increasing subsequence in an array.  

```cpp
#include <iostream>
#include <vector>
using namespace std;

// LIS Function
int lis(vector<int>& nums) {
    int n = nums.size();
    vector<int> dp(n, 1); // Each element is a subsequence of length 1

    for (int i = 1; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (nums[i] > nums[j]) {
                dp[i] = max(dp[i], dp[j] + 1);
            }
        }
    }

    return *max_element(dp.begin(), dp.end());
}

int main() {
    vector<int> nums = {10, 9, 2, 5, 3, 7, 101, 18};
    cout << "Length of LIS: " << lis(nums) << endl;

    return 0;
}
```

---

### **4. Matrix Multiplication**  
**Problem:** Multiply two matrices and print the resultant matrix.  

```cpp
#include <iostream>
using namespace std;

// Matrix Multiplication Function
void multiplyMatrices(int A[2][2], int B[2][2], int C[2][2]) {
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < 2; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }
}

int main() {
    int A[2][2] = {{1, 2}, {3, 4}};
    int B[2][2] = {{5, 6}, {7, 8}};
    int C[2][2];

    multiplyMatrices(A, B, C);

    cout << "Resultant Matrix: " << endl;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            cout << C[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

---

### **5. Topological Sort (Kahn’s Algorithm)**  
**Problem:** Perform topological sorting on a directed acyclic graph (DAG).  

```cpp
#include <iostream>
#include <vector>
#include <queue>
using namespace std;

// Topological Sort Function
vector<int> topologicalSort(int V, vector<vector<int>>& adj) {
    vector<int> inDegree(V, 0);
    for (int i = 0; i < V; i++) {
        for (int neighbor : adj[i]) {
            inDegree[neighbor]++;
        }
    }

    queue<int> q;
    for (int i = 0; i < V; i++) {
        if (inDegree[i] == 0) q.push(i);
    }

    vector<int> topoOrder;
    while (!q.empty()) {
        int node = q.front();
        q.pop();
        topoOrder.push_back(node);

        for (int neighbor : adj[node]) {
            inDegree[neighbor]--;
            if (inDegree[neighbor] == 0) q.push(neighbor);
        }
    }

    return topoOrder;
}

int main() {
    int V = 6;
    vector<vector<int>> adj = {{}, {0}, {1}, {1}, {2, 3}, {3}};
    vector<int> result = topologicalSort(V, adj);

    cout << "Topological Sort: ";
    for (int node : result) {
        cout << node << " ";
    }

    return 0;
}
```

---

### **6. Floyd-Warshall Algorithm**  
**Problem:** Find the shortest distances between all pairs of vertices in a weighted graph.  

```cpp
#include <iostream>
#include <vector>
#include <climits>
using namespace std;

// Floyd-Warshall Algorithm
void floydWarshall(vector<vector<int>>& graph, int V) {
    vector<vector<int>> dist = graph;

    for (int k = 0; k < V; k++) {
        for (int i = 0; i < V; i++) {
            for (int j = 0; j < V; j++) {
                if (dist[i][k] != INT_MAX && dist[k][j] != INT_MAX) {
                    dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j]);
                }
            }
        }
    }

    cout << "Shortest distances: " << endl;
    for (int i = 0; i < V; i++) {
        for (int j = 0; j < V; j++) {
            if (dist[i][j] == INT_MAX) cout << "INF ";
            else cout << dist[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    vector<vector<int>> graph = {
        {0, 3, INT_MAX, 7},
        {8, 0, 2, INT_MAX},
        {5, INT_MAX, 0, 1},
        {2, INT_MAX, INT_MAX, 0}
    };
    int V = graph.size();

    floydWarshall(graph, V);

    return 0;
}
```

---

## **Advanced Algorithms**

These algorithms involve complex problem-solving techniques, combining multiple concepts and often requiring an in-depth understanding of data structures and mathematical reasoning. They are crucial for tackling advanced computational problems in competitive programming and technical interviews.

---

### **1. Dijkstra’s Algorithm**  
**Problem:** Find the shortest path from a source vertex to all other vertices in a weighted graph.  

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <climits>
using namespace std;

// Dijkstra's Algorithm
void dijkstra(vector<vector<pair<int, int>>>& graph, int src, int V) {
    vector<int> dist(V, INT_MAX);
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<>> pq;

    dist[src] = 0;
    pq.push({0, src});

    while (!pq.empty()) {
        int u = pq.top().second;
        pq.pop();

        for (auto neighbor : graph[u]) {
            int v = neighbor.first;
            int weight = neighbor.second;

            if (dist[u] + weight < dist[v]) {
                dist[v] = dist[u] + weight;
                pq.push({dist[v], v});
            }
        }
    }

    cout << "Vertex\tDistance from Source" << endl;
    for (int i = 0; i < V; i++) {
        cout << i << "\t" << dist[i] << endl;
    }
}

int main() {
    int V = 5;
    vector<vector<pair<int, int>>> graph(V);

    // Adding edges: (u, v, weight)
    graph[0].push_back({1, 2});
    graph[0].push_back({4, 1});
    graph[1].push_back({2, 3});
    graph[4].push_back({3, 2});
    graph[3].push_back({2, 1});

    dijkstra(graph, 0, V);

    return 0;
}
```

---

### **2. Bellman-Ford Algorithm**  
**Problem:** Find the shortest paths from a source vertex to all vertices, allowing negative weight edges.  

```cpp
#include <iostream>
#include <vector>
#include <climits>
using namespace std;

// Bellman-Ford Algorithm
void bellmanFord(vector<vector<int>>& edges, int V, int src) {
    vector<int> dist(V, INT_MAX);
    dist[src] = 0;

    for (int i = 1; i <= V - 1; i++) {
        for (auto edge : edges) {
            int u = edge[0], v = edge[1], weight = edge[2];
            if (dist[u] != INT_MAX && dist[u] + weight < dist[v]) {
                dist[v] = dist[u] + weight;
            }
        }
    }

    // Check for negative weight cycle
    for (auto edge : edges) {
        int u = edge[0], v = edge[1], weight = edge[2];
        if (dist[u] != INT_MAX && dist[u] + weight < dist[v]) {
            cout << "Graph contains negative weight cycle" << endl;
            return;
        }
    }

    cout << "Vertex\tDistance from Source" << endl;
    for (int i = 0; i < V; i++) {
        cout << i << "\t" << dist[i] << endl;
    }
}

int main() {
    int V = 5;
    vector<vector<int>> edges = {
        {0, 1, -1}, {0, 2, 4},
        {1, 2, 3}, {1, 3, 2}, {1, 4, 2},
        {3, 2, 5}, {3, 1, 1}, {4, 3, -3}
    };

    bellmanFord(edges, V, 0);

    return 0;
}
```

---

### **3. Knapsack Problem (Dynamic Programming)**  
**Problem:** Given weights and values of items, maximize the value within a weight limit.  

```cpp
#include <iostream>
#include <vector>
using namespace std;

// Knapsack Function
int knapsack(vector<int>& weights, vector<int>& values, int W, int n) {
    vector<vector<int>> dp(n + 1, vector<int>(W + 1, 0));

    for (int i = 1; i <= n; i++) {
        for (int w = 1; w <= W; w++) {
            if (weights[i - 1] <= w) {
                dp[i][w] = max(values[i - 1] + dp[i - 1][w - weights[i - 1]], dp[i - 1][w]);
            } else {
                dp[i][w] = dp[i - 1][w];
            }
        }
    }

    return dp[n][W];
}

int main() {
    vector<int> weights = {1, 3, 4, 5};
    vector<int> values = {1, 4, 5, 7};
    int W = 7;

    cout << "Maximum value in knapsack: " << knapsack(weights, values, W, weights.size()) << endl;

    return 0;
}
```

---

### **4. KMP String Matching Algorithm**  
**Problem:** Search for a pattern in a given string using the KMP algorithm.  

```cpp
#include <iostream>
#include <vector>
using namespace std;

// Compute prefix array
void computeLPS(string pattern, vector<int>& lps) {
    int length = 0, i = 1;
    lps[0] = 0;

    while (i < pattern.length()) {
        if (pattern[i] == pattern[length]) {
            length++;
            lps[i] = length;
            i++;
        } else {
            if (length != 0) {
                length = lps[length - 1];
            } else {
                lps[i] = 0;
                i++;
            }
        }
    }
}

// KMP Search
void KMPSearch(string text, string pattern) {
    int n = text.length();
    int m = pattern.length();
    vector<int> lps(m, 0);

    computeLPS(pattern, lps);

    int i = 0, j = 0;
    while (i < n) {
        if (pattern[j] == text[i]) {
            i++;
            j++;
        }

        if (j == m) {
            cout << "Pattern found at index " << i - j << endl;
            j = lps[j - 1];
        } else if (i < n && pattern[j] != text[i]) {
            if (j != 0) {
                j = lps[j - 1];
            } else {
                i++;
            }
        }
    }
}

int main() {
    string text = "ABABDABACDABABCABAB";
    string pattern = "ABABCABAB";

    KMPSearch(text, pattern);

    return 0;
}
```

---

### **5. Traveling Salesman Problem (TSP)**  
**Problem:** Find the shortest route that visits each city exactly once and returns to the starting city.  

```cpp
#include <iostream>
#include <vector>
#include <climits>
using namespace std;

int tsp(vector<vector<int>>& graph, vector<bool>& visited, int pos, int n, int count, int cost, int& ans) {
    if (count == n && graph[pos][0]) {
        ans = min(ans, cost + graph[pos][0]);
        return ans;
    }

    for (int i = 0; i < n; i++) {
        if (!visited[i] && graph[pos][i]) {
            visited[i] = true;
            tsp(graph, visited, i, n, count + 1, cost + graph[pos][i], ans);
            visited[i] = false;
        }
    }

    return ans;
}

int main() {
    vector<vector<int>> graph = {
        {0, 10, 15, 20},
        {10, 0, 35, 25},
        {15, 35, 0, 30},
        {20, 25, 30, 0}
    };

    int n = graph.size();
    vector<bool> visited(n, false);
    visited[0] = true;

    int ans = INT_MAX;
    cout << "Minimum cost: " << tsp(graph, visited, 0, n, 1, 0, ans) << endl;

    return 0;
}
```

---

## **Interview Questions - Common Algorithms**

This section features 20 of the most common algorithmic problems asked in technical interviews, especially in FAANG companies.
## Algorithms covered:

| **Problem Name**              | **Theoretical Explanation**                                                                                                   | **Theoretical Solution**                                                                                                                                                                         |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Two Sum**                    | Find two indices in an array such that their sum equals a given target.                                                       | Use a hash map to store the complement of the target for each number. Check if the complement exists in the map to find the pair in O(n) time.                                                    |
| **Reverse a Linked List**      | Reverse the order of nodes in a singly linked list.                                                                           | Iterate through the linked list, reversing the `next` pointers of each node and updating the head pointer to point to the last node.                                                             |
| **Merge Two Sorted Lists**     | Merge two sorted linked lists into one sorted linked list.                                                                    | Recursively or iteratively compare nodes from both lists, appending the smaller node to the merged list until all nodes are processed.                                                           |
| **Find Missing Number**        | Find the missing number in a sequence from 0 to n where one number is missing.                                                | Use the formula for the sum of the first `n` natural numbers, subtract the sum of the array, and the difference is the missing number.                                                           |
| **Maximum Depth of Binary Tree** | Calculate the maximum depth (longest path from the root to a leaf) of a binary tree.                                          | Use recursion to traverse the left and right subtrees, returning the maximum depth for each subtree plus one.                                                                                    |
| **Valid Parentheses**          | Check if a string containing parentheses is valid (balanced and correctly ordered).                                           | Use a stack to push opening parentheses and pop when encountering matching closing parentheses. If the stack is empty at the end, the string is valid.                                           |
| **Rotated Array Search**       | Search for a target element in a rotated sorted array.                                                                        | Use binary search logic by identifying the sorted portion of the array in each iteration and narrowing the search space accordingly.                                                             |
| **Longest Substring Without Repeating Characters** | Find the length of the longest substring without repeating characters.                                                        | Use a sliding window and a hash map to track the characters in the current substring, updating the maximum length whenever a repeating character is encountered.                                   |
| **Climbing Stairs**            | Find the number of distinct ways to climb a staircase where you can take 1 or 2 steps at a time.                              | Use dynamic programming or Fibonacci logic to compute the number of ways, as each step depends on the sum of the previous two steps.                                                             |
| **Merge Intervals**            | Combine overlapping intervals into a single interval.                                                                         | Sort intervals by start time, then iterate and merge intervals that overlap, updating their end time as needed.                                                                                   |
| **Product of Array Except Self** | Return an array where each element is the product of all elements except itself, without division.                           | Use prefix and suffix arrays to store cumulative products from the left and right, and multiply the two arrays to get the result for each index.                                                  |
| **Subarray Sum Equals K**      | Count the number of subarrays that sum to a given value `k`.                                                                  | Use a hash map to store cumulative sums and their frequencies. Check if `current_sum - k` exists in the map to identify subarrays that add up to `k`.                                             |
| **Find Peak Element**          | Find a peak element (greater than its neighbors) in an array.                                                                | Use binary search to find an element that is greater than its neighbors. If the middle element is smaller than its neighbor, move to the larger half of the array.                                |
| **House Robber**               | Find the maximum amount that can be robbed from houses without robbing adjacent houses.                                       | Use dynamic programming to calculate the maximum loot for each house, considering the maximum value from robbing the previous houses without violating the adjacency constraint.                  |
| **Binary Tree Level Order Traversal** | Perform a level-order traversal (breadth-first search) of a binary tree.                                                         | Use a queue to traverse nodes level by level, adding their children to the queue and storing the values of each level in a 2D list.                                                              |
| **Word Break**                 | Check if a string can be segmented into valid words from a dictionary.                                                        | Use dynamic programming to track whether substrings of the string exist in the dictionary, building the solution incrementally from smaller substrings.                                           |
| **Minimum Window Substring**   | Find the minimum substring in a string `s` that contains all characters of another string `t`.                                | Use a sliding window and hash maps to track character counts in the current window and compare them with the required counts in `t`. Adjust the window to find the minimum valid substring.       |
| **Median of Data Stream**      | Find the median of a dynamically growing stream of numbers.                                                                   | Use two heaps (max-heap for the left half and min-heap for the right half) to dynamically balance and calculate the median in O(log n) time for insertion and O(1) time for retrieval.              |
| **Trapping Rain Water**        | Calculate the amount of water trapped between heights in a histogram-like structure.                                          | Use two arrays to precompute the maximum heights to the left and right of each bar, and calculate the water trapped at each position using `min(leftMax, rightMax) - height[i]`.                   |
| **Binary Search Tree Validation** | Validate whether a binary tree is a valid binary search tree (BST).                                                          | Recursively check if every node's value lies within a valid range defined by its parent nodes, ensuring left children are smaller and right children are larger.                                   |

---

### **1. Two Sum**  
**Problem:** Find two numbers in an array that add up to a target.  

```cpp
// Problem: Find two indices in an array such that nums[i] + nums[j] = target
#include <iostream>
#include <unordered_map>
using namespace std;

vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> hash;
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (hash.find(complement) != hash.end()) {
            return {hash[complement], i};
        }
        hash[nums[i]] = i;
    }
    return {};
}

int main() {
    vector<int> nums = {2, 7, 11, 15};
    int target = 9;

    vector<int> result = twoSum(nums, target);
    cout << "Indices: " << result[0] << ", " << result[1] << endl;

    return 0;
}
```

---

### **2. Reverse a Linked List**  
**Problem:** Reverse a singly linked list.  

```cpp
// Problem: Reverse a given singly linked list
#include <iostream>
using namespace std;

struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(nullptr) {}
};

ListNode* reverseList(ListNode* head) {
    ListNode* prev = nullptr;
    ListNode* curr = head;

    while (curr) {
        ListNode* nextNode = curr->next;
        curr->next = prev;
        prev = curr;
        curr = nextNode;
    }
    return prev;
}

int main() {
    ListNode* head = new ListNode(1);
    head->next = new ListNode(2);
    head->next->next = new ListNode(3);

    ListNode* reversed = reverseList(head);
    while (reversed) {
        cout << reversed->val << " ";
        reversed = reversed->next;
    }

    return 0;
}
```

---

### **3. Merge Two Sorted Linked Lists**  
**Problem:** Merge two sorted linked lists into one sorted list.  

```cpp
// Problem: Merge two sorted linked lists into a single sorted linked list
#include <iostream>
using namespace std;

struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(nullptr) {}
};

ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
    if (!l1) return l2;
    if (!l2) return l1;

    if (l1->val < l2->val) {
        l1->next = mergeTwoLists(l1->next, l2);
        return l1;
    } else {
        l2->next = mergeTwoLists(l1, l2->next);
        return l2;
    }
}

int main() {
    ListNode* l1 = new ListNode(1);
    l1->next = new ListNode(2);
    l1->next->next = new ListNode(4);

    ListNode* l2 = new ListNode(1);
    l2->next = new ListNode(3);
    l2->next->next = new ListNode(4);

    ListNode* merged = mergeTwoLists(l1, l2);
    while (merged) {
        cout << merged->val << " ";
        merged = merged->next;
    }

    return 0;
}
```

---

### **4. Find Missing Number**  
**Problem:** Find the missing number in a sequence from 0 to n.  

```cpp
// Problem: Find the missing number in an array containing numbers 0 to n
#include <iostream>
#include <vector>
using namespace std;

int missingNumber(vector<int>& nums) {
    int n = nums.size();
    int total = n * (n + 1) / 2;
    int sum = 0;

    for (int num : nums) {
        sum += num;
    }
    return total - sum;
}

int main() {
    vector<int> nums = {0, 1, 3};
    cout << "Missing Number: " << missingNumber(nums) << endl;

    return 0;
}
```

---

### **5. Maximum Depth of Binary Tree**  
**Problem:** Find the maximum depth of a binary tree.  

```cpp
// Problem: Calculate the maximum depth of a binary tree
#include <iostream>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

int maxDepth(TreeNode* root) {
    if (!root) return 0;
    return 1 + max(maxDepth(root->left), maxDepth(root->right));
}

int main() {
    TreeNode* root = new TreeNode(1);
    root->left = new TreeNode(2);
    root->right = new TreeNode(3);
    root->left->left = new TreeNode(4);
    root->left->right = new TreeNode(5);

    cout << "Maximum Depth: " << maxDepth(root) << endl;

    return 0;
}
```

---

### **6. Valid Parentheses**  
**Problem:** Check if a string containing parentheses is valid.  

```cpp
// Problem: Check if a string of parentheses is valid (balanced and correct order)
#include <iostream>
#include <stack>
using namespace std;

bool isValid(string s) {
    stack<char> stk;
    for (char c : s) {
        if (c == '(' || c == '{' || c == '[') {
            stk.push(c);
        } else {
            if (stk.empty()) return false;
            char top = stk.top();
            if ((c == ')' && top == '(') || (c == '}' && top == '{') || (c == ']' && top == '[')) {
                stk.pop();
            } else {
                return false;
            }
        }
    }
    return stk.empty();
}

int main() {
    string s = "{[()]}";
    if (isValid(s))
        cout << "Valid Parentheses" << endl;
    else
        cout << "Invalid Parentheses" << endl;

    return 0;
}
```

---

### **7. Rotated Array Search**  
**Problem:** Search for a target in a rotated sorted array.  

```cpp
// Problem: Search for a target value in a rotated sorted array
#include <iostream>
#include <vector>
using namespace std;

int search(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;

        if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid])
                right = mid - 1;
            else
                left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right])
                left = mid + 1;
            else
                right = mid - 1;
        }
    }

    return -1;
}

int main() {
    vector<int> nums = {4, 5, 6, 7, 0, 1, 2};
    int target = 0;

    cout << "Target found at index: " << search(nums, target) << endl;

    return 0;
}
```

---

### **8. Longest Substring Without Repeating Characters**  
**Problem:** Find the length of the longest substring without repeating characters.

```cpp
// Problem: Find the length of the longest substring without repeating characters
#include <iostream>
#include <unordered_map>
using namespace std;

int lengthOfLongestSubstring(string s) {
    unordered_map<char, int> charIndex;
    int maxLength = 0, start = 0;

    for (int i = 0; i < s.length(); i++) {
        if (charIndex.find(s[i]) != charIndex.end() && charIndex[s[i]] >= start) {
            start = charIndex[s[i]] + 1;
        }
        charIndex[s[i]] = i;
        maxLength = max(maxLength, i - start + 1);
    }
    return maxLength;
}

int main() {
    string s = "abcabcbb";
    cout << "Length of Longest Substring: " << lengthOfLongestSubstring(s) << endl;

    return 0;
}
```

---

### **9. Climbing Stairs**  
**Problem:** Calculate the number of distinct ways to climb `n` stairs, taking 1 or 2 steps at a time.

```cpp
// Problem: Calculate the number of ways to climb n stairs with steps of 1 or 2
#include <iostream>
#include <vector>
using namespace std;

int climbStairs(int n) {
    if (n <= 2) return n;
    int a = 1, b = 2;
    for (int i = 3; i <= n; i++) {
        int temp = a + b;
        a = b;
        b = temp;
    }
    return b;
}

int main() {
    int n = 5;
    cout << "Ways to climb " << n << " stairs: " << climbStairs(n) << endl;

    return 0;
}
```

---

### **10. Merge Intervals**  
**Problem:** Merge overlapping intervals into a single interval.

```cpp
// Problem: Merge overlapping intervals into one
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

vector<vector<int>> merge(vector<vector<int>>& intervals) {
    sort(intervals.begin(), intervals.end());
    vector<vector<int>> merged;

    for (auto& interval : intervals) {
        if (merged.empty() || merged.back()[1] < interval[0]) {
            merged.push_back(interval);
        } else {
            merged.back()[1] = max(merged.back()[1], interval[1]);
        }
    }
    return merged;
}

int main() {
    vector<vector<int>> intervals = {{1, 3}, {2, 6}, {8, 10}, {15, 18}};
    vector<vector<int>> result = merge(intervals);

    cout << "Merged Intervals: ";
    for (auto& interval : result) {
        cout << "[" << interval[0] << ", " << interval[1] << "] ";
    }
    return 0;
}
```

---

### **11. Product of Array Except Self**  
**Problem:** Return an array where each element is the product of all elements except itself.

```cpp
// Problem: Compute product of array except self without division
#include <iostream>
#include <vector>
using namespace std;

vector<int> productExceptSelf(vector<int>& nums) {
    int n = nums.size();
    vector<int> result(n, 1);

    int left = 1;
    for (int i = 0; i < n; i++) {
        result[i] *= left;
        left *= nums[i];
    }

    int right = 1;
    for (int i = n - 1; i >= 0; i--) {
        result[i] *= right;
        right *= nums[i];
    }

    return result;
}

int main() {
    vector<int> nums = {1, 2, 3, 4};
    vector<int> result = productExceptSelf(nums);

    cout << "Product of Array Except Self: ";
    for (int val : result) {
        cout << val << " ";
    }

    return 0;
}
```

---

### **12. Subarray Sum Equals K**  
**Problem:** Find the number of subarrays that sum to a given value `k`.

```cpp
// Problem: Count subarrays with a sum equal to k
#include <iostream>
#include <unordered_map>
using namespace std;

int subarraySum(vector<int>& nums, int k) {
    unordered_map<int, int> prefixSum;
    prefixSum[0] = 1;

    int count = 0, sum = 0;
    for (int num : nums) {
        sum += num;
        if (prefixSum.find(sum - k) != prefixSum.end()) {
            count += prefixSum[sum - k];
        }
        prefixSum[sum]++;
    }
    return count;
}

int main() {
    vector<int> nums = {1, 1, 1};
    int k = 2;

    cout << "Number of subarrays: " << subarraySum(nums, k) << endl;

    return 0;
}
```

---

### **13. Find Peak Element**  
**Problem:** Find a peak element in an array (an element greater than its neighbors).

```cpp
// Problem: Find a peak element in the array
#include <iostream>
#include <vector>
using namespace std;

int findPeakElement(vector<int>& nums) {
    int left = 0, right = nums.size() - 1;

    while (left < right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] > nums[mid + 1]) {
            right = mid;
        } else {
            left = mid + 1;
        }
    }
    return left;
}

int main() {
    vector<int> nums = {1, 2, 3, 1};
    cout << "Peak Element Index: " << findPeakElement(nums) << endl;

    return 0;
}
```

---

### **14. House Robber**  
**Problem:** Find the maximum amount that can be robbed from houses without robbing adjacent houses.

```cpp
// Problem: Maximize robbery without robbing adjacent houses
#include <iostream>
#include <vector>
using namespace std;

int rob(vector<int>& nums) {
    if (nums.empty()) return 0;
    if (nums.size() == 1) return nums[0];

    int prev1 = 0, prev2 = 0;
    for (int num : nums) {
        int temp = max(prev1, prev2 + num);
        prev2 = prev1;
        prev1 = temp;
    }
    return prev1;
}

int main() {
    vector<int> nums = {2, 7, 9, 3, 1};
    cout << "Maximum Robbery Amount: " << rob(nums) << endl;

    return 0;
}
```

---

### **15. Binary Tree Level Order Traversal**  
**Problem:** Perform a level order traversal of a binary tree.

```cpp
// Problem: Perform level order traversal of a binary tree
#include <iostream>
#include <vector>
#include <queue>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

vector<vector<int>> levelOrder(TreeNode* root) {
    vector<vector<int>> result;
    if (!root) return result;

    queue<TreeNode*> q;
    q.push(root);

    while (!q.empty()) {
        int size = q.size();
        vector<int> level;

        for (int i = 0; i < size; i++) {
            TreeNode* node = q.front();
            q.pop();
            level.push_back(node->val);

            if (node->left) q.push(node->left);
            if (node->right) q.push(node->right);
        }
        result.push_back(level);
    }
    return result;
}

int main() {
    TreeNode* root = new TreeNode(3);
    root->left = new TreeNode(9);
    root->right = new TreeNode(20);
    root->right->left = new TreeNode(15);
    root->right->right = new TreeNode(7);

    vector<vector<int>> result = levelOrder(root);

    cout << "Level Order Traversal: ";
    for (auto level : result) {
        for (int val : level) {
            cout << val << " ";
        }
        cout << endl;
    }

    return 0;
}
```

---

### **16. Word Break**  
**Problem:** Determine if a given string can be segmented into valid words from a dictionary.

```cpp
// Problem: Check if a string can be segmented into valid dictionary words
#include <iostream>
#include <vector>
#include <unordered_set>
using namespace std;

bool wordBreak(string s, vector<string>& wordDict) {
    unordered_set<string> dict(wordDict.begin(), wordDict.end());
    vector<bool> dp(s.length() + 1, false);
    dp[0] = true;

    for (int i = 1; i <= s.length(); i++) {
        for (int j = 0; j < i; j++) {
            if (dp[j] && dict.find(s.substr(j, i - j)) != dict.end()) {
                dp[i] = true;
                break;
            }
        }
    }

    return dp[s.length()];
}

int main() {
    string s = "leetcode";
    vector<string> wordDict = {"leet", "code"};

    if (wordBreak(s, wordDict))
        cout << "The string can be segmented." << endl;
    else
        cout << "The string cannot be segmented." << endl;

    return 0;
}
```

---

### **17. Minimum Window Substring**  
**Problem:** Find the minimum window in a string that contains all characters of another string.

```cpp
// Problem: Find the minimum window in s that contains all characters of t
#include <iostream>
#include <unordered_map>
#include <string>
using namespace std;

string minWindow(string s, string t) {
    unordered_map<char, int> tCount, windowCount;
    for (char c : t) tCount[c]++;

    int required = tCount.size(), formed = 0, l = 0, r = 0;
    int minLength = INT_MAX, start = 0;

    while (r < s.length()) {
        char c = s[r];
        windowCount[c]++;

        if (tCount.count(c) && windowCount[c] == tCount[c]) formed++;

        while (l <= r && formed == required) {
            char d = s[l];
            if (r - l + 1 < minLength) {
                minLength = r - l + 1;
                start = l;
            }
            windowCount[d]--;
            if (tCount.count(d) && windowCount[d] < tCount[d]) formed--;
            l++;
        }
        r++;
    }

    return minLength == INT_MAX ? "" : s.substr(start, minLength);
}

int main() {
    string s = "ADOBECODEBANC";
    string t = "ABC";

    cout << "Minimum Window Substring: " << minWindow(s, t) << endl;

    return 0;
}
```

---

### **18. Find Median in a Stream**  
**Problem:** Find the median of a stream of numbers.

```cpp
// Problem: Find the median of a stream of integers
#include <iostream>
#include <queue>
using namespace std;

class MedianFinder {
    priority_queue<int> maxHeap; // Left half
    priority_queue<int, vector<int>, greater<int>> minHeap; // Right half

public:
    void addNum(int num) {
        if (maxHeap.empty() || num <= maxHeap.top()) {
            maxHeap.push(num);
        } else {
            minHeap.push(num);
        }

        if (maxHeap.size() > minHeap.size() + 1) {
            minHeap.push(maxHeap.top());
            maxHeap.pop();
        } else if (minHeap.size() > maxHeap.size()) {
            maxHeap.push(minHeap.top());
            minHeap.pop();
        }
    }

    double findMedian() {
        if (maxHeap.size() == minHeap.size()) {
            return (maxHeap.top() + minHeap.top()) / 2.0;
        }
        return maxHeap.top();
    }
};

int main() {
    MedianFinder mf;
    mf.addNum(1);
    mf.addNum(2);
    cout << "Median: " << mf.findMedian() << endl;
    mf.addNum(3);
    cout << "Median: " << mf.findMedian() << endl;

    return 0;
}
```

---

### **19. Trapping Rain Water**  
**Problem:** Calculate the amount of rainwater trapped between heights.

```cpp
// Problem: Calculate the total water trapped between heights
#include <iostream>
#include <vector>
using namespace std;

int trap(vector<int>& height) {
    int n = height.size();
    if (n == 0) return 0;

    vector<int> leftMax(n), rightMax(n);
    leftMax[0] = height[0];
    for (int i = 1; i < n; i++) {
        leftMax[i] = max(leftMax[i - 1], height[i]);
    }

    rightMax[n - 1] = height[n - 1];
    for (int i = n - 2; i >= 0; i--) {
        rightMax[i] = max(rightMax[i + 1], height[i]);
    }

    int water = 0;
    for (int i = 0; i < n; i++) {
        water += min(leftMax[i], rightMax[i]) - height[i];
    }

    return water;
}

int main() {
    vector<int> height = {0, 1, 0, 2, 1, 0, 1, 3, 2, 1, 2, 1};
    cout << "Total water trapped: " << trap(height) << endl;

    return 0;
}
```

---

### **20. Binary Search Tree Validation**  
**Problem:** Validate if a binary tree is a binary search tree (BST).

```cpp
// Problem: Validate if a binary tree is a BST
#include <iostream>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

bool validate(TreeNode* root, TreeNode* minNode, TreeNode* maxNode) {
    if (!root) return true;
    if ((minNode && root->val <= minNode->val) || (maxNode && root->val >= maxNode->val)) return false;
    return validate(root->left, minNode, root) && validate(root->right, root, maxNode);
}

bool isValidBST(TreeNode* root) {
    return validate(root, nullptr, nullptr);
}

int main() {
    TreeNode* root = new TreeNode(2);
    root->left = new TreeNode(1);
    root->right = new TreeNode(3);

    if (isValidBST(root))
        cout << "The tree is a valid BST." << endl;
    else
        cout << "The tree is not a valid BST." << endl;

    return 0;
}
```

---

