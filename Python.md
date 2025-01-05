# **Python - The Complete Guide**

Python is one of the most versatile programming languages, known for its simplicity, readability, and a vast ecosystem of libraries that make it ideal for a wide range of applications, including Machine Learning (ML), Data Analysis, Web Development, and more.

---

## **Table of Contents**

1. **Introduction to Python**  
2. **Python Basics**  
   - Syntax and Variables  
   - Data Types and Operations  
   - Control Flow Statements  
   - Functions and Modules  
3. **Object-Oriented Programming (OOP) in Python**  
   - Classes and Objects  
   - Inheritance and Polymorphism  
4. **Data Structures in Python**  
   - Lists, Tuples, Sets, and Dictionaries  
5. **File Handling in Python**  
6. **Advanced Topics for ML Prerequisites**  
   - List Comprehensions  
   - Lambda Functions  
   - Generators and Iterators  
7. **Best Use Cases for Python**  
   - Data Analysis, Machine Learning, Web Scraping, Automation, and more  
8. **Introduction to Popular Python Libraries**  
   - **NumPy**  
   - **Pandas**  
   - **Matplotlib**  
   - **Seaborn**  
   - **BeautifulSoup**  
   - **SciKit Learn**  

---

## **1. Introduction to Python**

**What is Python?**  
Python is a high-level, interpreted, and dynamically typed language. Its concise syntax and wide range of libraries make it suitable for beginners and professionals alike.

**Key Features of Python**  
- **Simple Syntax**: Easy to read and write, similar to pseudocode.  
- **Cross-Platform**: Runs on all major operating systems.  
- **Extensive Libraries**: Access to thousands of libraries for diverse applications.  
- **Interpreted**: Executes code line-by-line, making debugging easier.  
- **Community Support**: One of the largest developer communities.

---

## **2. Python Basics**

### **2.1 Syntax and Variables**

**Hello, World!**  
```python
print("Hello, World!")
```

**Variables**  
Python does not require explicit type declarations.
```python
x = 10       # Integer
y = 3.14     # Float
name = "Alice"  # String
is_active = True  # Boolean
```

---

### **2.2 Data Types and Operations**

**Basic Data Types**  
- **int**: Integer values  
- **float**: Decimal values  
- **str**: Strings of text  
- **bool**: True/False  

**Arithmetic Operators**  
```python
x = 10
y = 3
print(x + y)  # Addition
print(x - y)  # Subtraction
print(x * y)  # Multiplication
print(x / y)  # Division
print(x % y)  # Modulus
print(x ** y) # Exponentiation
```

**String Operations**  
```python
name = "Alice"
print(name.upper())        # Convert to uppercase
print(name.lower())        # Convert to lowercase
print(name[0])             # Access first character
print(name[1:3])           # Slice string (Index 1 to 2)
```

---

### **2.3 Control Flow Statements**

**Conditional Statements**  
```python
x = 10
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x equals 5")
else:
    print("x is less than 5")
```

**Loops**  
```python
# For Loop
for i in range(5):
    print(i)

# While Loop
x = 0
while x < 5:
    print(x)
    x += 1
```

---

### **2.4 Functions and Modules**

**Defining Functions**  
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

**Importing Modules**  
```python
import math

print(math.sqrt(16))  # Square root
print(math.pi)        # Value of pi
```

---

## **3. Object-Oriented Programming (OOP) in Python**

**Defining Classes**  
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hi, my name is {self.name} and I am {self.age} years old."

person = Person("Alice", 30)
print(person.greet())
```

**Inheritance**  
```python
class Animal:
    def speak(self):
        return "I make a sound."

class Dog(Animal):
    def speak(self):
        return "Woof!"

dog = Dog()
print(dog.speak())
```

---

## **4. Data Structures in Python**

**Lists**  
```python
numbers = [1, 2, 3, 4, 5]
numbers.append(6)  # Add an element
numbers.remove(3)  # Remove an element
print(numbers[0])  # Access first element
```

**Tuples** (Immutable)  
```python
coordinates = (10, 20)
print(coordinates[0])  # Access first element
```

**Sets** (Unique Elements)  
```python
unique_numbers = {1, 2, 3, 3}
print(unique_numbers)  # {1, 2, 3}
```

**Dictionaries** (Key-Value Pairs)  
```python
person = {"name": "Alice", "age": 30}
print(person["name"])  # Access value by key
person["age"] = 31     # Update value
```

---

## **5. File Handling in Python**

**Reading Files**  
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

**Writing Files**  
```python
with open("example.txt", "w") as file:
    file.write("Hello, World!")
```

---

## **6. Advanced Topics for ML Prerequisites**

### **6.1 List Comprehensions**
```python
squares = [x**2 for x in range(5)]
print(squares)  # [0, 1, 4, 9, 16]
```

### **6.2 Lambda Functions**
```python
add = lambda x, y: x + y
print(add(5, 3))  # 8
```

### **6.3 Generators**
```python
def count_up_to(n):
    count = 1
    while count <= n:
        yield count
        count += 1

for number in count_up_to(5):
    print(number)
```

---

## **7. Best Use Cases for Python**

1. **Machine Learning and AI**: TensorFlow, PyTorch, Scikit Learn.  
2. **Data Analysis**: NumPy, Pandas, Matplotlib.  
3. **Web Development**: Django, Flask.  
4. **Web Scraping**: BeautifulSoup, Selenium.  
5. **Automation**: Automate repetitive tasks using scripts.  

---

## **8. Introduction to Popular Python Libraries**

Here is an overview of key libraries, their importance, and their use cases:

---

### **NumPy**  
NumPy is the core library for numerical computations in Python.

**Key Features**:
- Supports large, multi-dimensional arrays.  
- Provides mathematical functions for linear algebra, statistics, etc.

**Example**:
```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
print(arr.mean())  # 3.0
```

---

### **Pandas**  
Pandas is essential for data manipulation and analysis.

**Key Features**:
- DataFrames for structured data.  
- Supports data cleaning, merging, and transformation.

**Example**:
```python
import pandas as pd

data = {"Name": ["Alice", "Bob"], "Age": [25, 30]}
df = pd.DataFrame(data)
print(df)
```

---

### **Matplotlib**

Matplotlib is the go-to library for creating static, interactive, and animated visualizations in Python. It works well for creating publication-quality plots.

#### **Key Features**
- Create line plots, bar charts, scatter plots, histograms, and more.  
- Highly customizable visualizations.  
- Integration with NumPy and Pandas.

#### **Basic Example: Line Plot**
```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [10, 20, 25, 30]

plt.plot(x, y, label="Line 1", color="blue", marker="o")
plt.title("Line Plot Example")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.legend()
plt.show()
```

#### **Bar Chart**
```python
categories = ['A', 'B', 'C']
values = [5, 10, 7]

plt.bar(categories, values, color='orange')
plt.title("Bar Chart Example")
plt.show()
```

#### **Histogram**
```python
data = [10, 20, 20, 30, 30, 30, 40]

plt.hist(data, bins=5, color="green")
plt.title("Histogram Example")
plt.xlabel("Value")
plt.ylabel("Frequency")
plt.show()
```

---

### **Seaborn**

Seaborn is a library built on top of Matplotlib for creating more visually appealing statistical plots.

#### **Key Features**
- Simplifies complex visualizations like heatmaps and violin plots.  
- Integrates seamlessly with Pandas DataFrames.  
- Ideal for exploring datasets.

#### **Basic Example: Scatter Plot**
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
tips = sns.load_dataset("tips")
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="time", style="sex")
plt.title("Scatter Plot with Seaborn")
plt.show()
```

#### **Heatmap**
```python
import numpy as np

data = np.random.rand(5, 5)
sns.heatmap(data, annot=True, cmap="coolwarm")
plt.title("Heatmap Example")
plt.show()
```

#### **Pair Plot**
```python
sns.pairplot(tips, hue="sex")
plt.show()
```

---

### **BeautifulSoup**

BeautifulSoup is a library used for web scraping to extract data from HTML and XML files.

#### **Key Features**
- Navigate and search through HTML/XML documents.  
- Extract specific elements like text, links, or tables.  
- Handles poorly formatted HTML gracefully.

#### **Basic Example: Extracting Links**
```python
from bs4 import BeautifulSoup
import requests

url = "https://example.com"
response = requests.get(url)

soup = BeautifulSoup(response.content, "html.parser")
links = soup.find_all("a")

for link in links:
    print(link.get("href"))
```

#### **Extracting Table Data**
```python
table = soup.find("table")
rows = table.find_all("tr")

for row in rows:
    columns = row.find_all("td")
    for col in columns:
        print(col.text.strip())
```

---

### **SciKit Learn**

SciKit Learn is a robust library for Machine Learning and Data Science tasks.

#### **Key Features**
- Supports supervised and unsupervised learning.  
- Tools for model evaluation, preprocessing, and pipeline building.  
- Integrates seamlessly with NumPy and Pandas.

#### **Basic Example: Linear Regression**
```python
from sklearn.linear_model import LinearRegression
import numpy as np

# Training data
X = np.array([[1], [2], [3], [4]])
y = np.array([2, 4, 6, 8])

model = LinearRegression()
model.fit(X, y)

# Predict values
predictions = model.predict([[5], [6]])
print(predictions)  # [10, 12]
```

#### **Classification with Decision Trees**
```python
from sklearn.tree import DecisionTreeClassifier

# Sample data
X = [[0, 0], [1, 1]]
y = [0, 1]

model = DecisionTreeClassifier()
model.fit(X, y)

print(model.predict([[2, 2]]))  # [1]
```

#### **K-Means Clustering**
```python
from sklearn.cluster import KMeans
import numpy as np

data = np.array([[1, 2], [1, 4], [1, 0], [10, 2], [10, 4], [10, 0]])
kmeans = KMeans(n_clusters=2, random_state=0).fit(data)

print(kmeans.labels_)  # Cluster labels for each data point
print(kmeans.cluster_centers_)  # Coordinates of cluster centers
```

---

### **Data Science Workflow Using Python Libraries**

1. **Data Loading and Cleaning**:
   - Use Pandas to load and preprocess datasets.
   ```python
   import pandas as pd
   df = pd.read_csv("data.csv")
   df.dropna(inplace=True)  # Remove null values
   ```

2. **Exploratory Data Analysis (EDA)**:
   - Visualize distributions with Matplotlib and Seaborn.
   ```python
   sns.histplot(df["age"], kde=True)
   plt.show()
   ```

3. **Feature Engineering**:
   - Use NumPy for mathematical operations.
   ```python
   df["age_squared"] = np.square(df["age"])
   ```

4. **Model Training**:
   - Build and train models with SciKit Learn.
   ```python
   from sklearn.model_selection import train_test_split
   X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

   model = LinearRegression()
   model.fit(X_train, y_train)
   ```

5. **Model Evaluation**:
   - Evaluate models using metrics like accuracy and R-squared.
   ```python
   from sklearn.metrics import accuracy_score
   y_pred = model.predict(X_test)
   print(accuracy_score(y_test, y_pred))
   ```

---

### **Conclusion**

Python is an incredibly versatile programming language with applications ranging from simple scripting to complex Machine Learning tasks. By mastering the basics and familiarizing yourself with popular libraries like NumPy, Pandas, Matplotlib, Seaborn, BeautifulSoup, and SciKit Learn, you will have all the tools needed to excel in Data Science, ML, and Web Development.