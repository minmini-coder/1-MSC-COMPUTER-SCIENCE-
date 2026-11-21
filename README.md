# 1-MSC-COMPUTER-SCIENCE-
### UNIT – V: SCIENTIFIC COMPUTING AND APPLICATION DEVELOPMENT

This unit covers NumPy, Pandas, Data Cleaning, Matplotlib, Testing, Debugging, Profiling, Python Packaging, Deployment, Git, GitHub and Mini Project Development.

The notes are organized with definitions, subtopics, explanations, syntax and simple Python programs for easy learning and examination writing.

### 1\. NumPy Arrays

### 1.1 Definition

NumPy (Numerical Python) is a Python library used for scientific computing and numerical calculations. It provides a powerful multidimensional array called `ndarray`.

It performs mathematical operations faster and more efficiently than ordinary Python lists.

### 1.2 Features of NumPy

* Provides multidimensional arrays.

* Performs fast mathematical operations.

* Supports matrix operations.

* Uses less memory for numerical data.

* Supports statistical calculations.

* Provides functions for scientific computing.

### 1.3 Installing and Importing NumPy

Syntax:

```python
pip install numpy
```

Import statement:

```python
import numpy as np
```

Here, `np` is the alias name of NumPy.

### 1.4 Creating NumPy Arrays

The `array()` function is used to create a NumPy array.

Syntax:

```python
np.array(list)
```

Example:

```python
import numpy as np

a = np.array([10, 20, 30, 40])

print(a)
```

Output:

```text
[10 20 30 40]
```

### 1.5 Types of NumPy Arrays

1\. One-Dimensional Array

An array containing elements in a single row.

```python
import numpy as np

a = np.array([1, 2, 3])
print(a)
```

2\. Two-Dimensional Array

An array containing rows and columns.

```python
a = np.array([[1, 2], [3, 4]])
print(a)
```

3\. Three-Dimensional Array

An array containing multiple two-dimensional arrays.

```python
a = np.array([[[1, 2], [3, 4]]])
print(a)
```

### 1.6 Important NumPy Functions

| Function      | Description                        |
| ------------- | ---------------------------------- |
| np.array()    | Creates an array                   |
| np.zeros()    | Creates an array filled with zeros |
| np.ones()     | Creates an array filled with ones  |
| np.arange()   | Creates a sequence of values       |
| np.linspace() | Creates evenly spaced values       |
| np.reshape()  | Changes array shape                |
| np.sum()      | Calculates total                   |
| np.mean()     | Calculates average                 |
| np.max()      | Finds maximum value                |
| np.min()      | Finds minimum value                |

Example:

```python
import numpy as np

a = np.array([10, 20, 30, 40])

print("Sum:", np.sum(a))
print("Mean:", np.mean(a))
print("Maximum:", np.max(a))
print("Minimum:", np.min(a))
```

Output:

```text
Sum: 100
Mean: 25.0
Maximum: 40
Minimum: 10
```

### 1.7 Array Operations

NumPy supports arithmetic operations such as addition, subtraction, multiplication and division.

```python
import numpy as np

a = np.array([10, 20, 30])
b = np.array([1, 2, 3])

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

Output:

```text
[11 22 33]
[ 9 18 27]
[10 40 90]
[10. 10. 10.]
```

Applications of NumPy:

* Scientific calculations.

* Statistical analysis.

* Matrix operations.

* Machine learning.

* Data analysis.

### 2\. Pandas DataFrames

### 2.1 Definition

Pandas is a Python library used for data manipulation and data analysis.

A DataFrame is a two-dimensional data structure that stores data in rows and columns, similar to an Excel spreadsheet or database table.

### 2.2 Features of Pandas

* Handles large datasets.

* Supports rows and columns.

* Provides data filtering and sorting.

* Handles missing values.

* Supports data analysis.

* Reads and writes CSV and Excel files.

### 2.3 Installing and Importing Pandas

Syntax:

```python
pip install pandas
```

Import statement:

```python
import pandas as pd
```

### 2.4 Creating a DataFrame

The `DataFrame()` function is used to create a DataFrame.

Syntax:

```python
pd.DataFrame(data)
```

Example:

```python
import pandas as pd

data = {
    'Name': ['Ravi', 'Priya', 'Arun'],
    'Mark': [85, 90, 75]
}

df = pd.DataFrame(data)

print(df)
```

Output:

```text
    Name  Mark
0   Ravi    85
1  Priya    90
2   Arun    75
```

### 2.5 Important DataFrame Operations

1\. Display first five rows

```python
df.head()
```

2\. Display last five rows

```python
df.tail()
```

3\. Display information

```python
df.info()
```

4\. Display statistical summary

```python
df.describe()
```

5\. Display column names

```python
print(df.columns)
```

6\. Access a particular column

```python
print(df['Name'])
```

7\. Select a particular row

```python
print(df.iloc[0])
```

### 2.6 Reading and Writing CSV Files

CSV means Comma-Separated Values. It is used to store tabular data.

Reading a CSV file:

```python
df = pd.read_csv("students.csv")
print(df)
```

Writing a CSV file:

```python
df.to_csv("output.csv", index=False)
```

### 2.7 Data Filtering

Filtering is used to select rows based on a condition.

Example:

```python
import pandas as pd

data = {
    'Name': ['Ravi', 'Priya', 'Arun'],
    'Mark': [85, 90, 65]
}

df = pd.DataFrame(data)

result = df[df['Mark'] > 80]

print(result)
```

Output:

```text
    Name  Mark
0   Ravi    85
1  Priya    90
```

Applications of Pandas:

* Data analysis.

* Financial analysis.

* Business reports.

* Data science.

* Machine learning.

### 3\. Data Cleaning

### 3.1 Definition

Data Cleaning is the process of identifying and correcting inaccurate, incomplete, duplicate or inconsistent data in a dataset.

It improves the quality and accuracy of data before analysis.

### 3.2 Importance of Data Cleaning

* Improves data accuracy.

* Removes duplicate records.

* Handles missing values.

* Corrects incorrect data.

* Improves analysis results.

* Makes data reliable.

### 3.3 Common Data Cleaning Techniques

### 1\. Handling Missing Values

Missing values are empty or unavailable values in a dataset.

Pandas provides `isnull()` and `fillna()` functions.

Syntax:

```python
df.isnull()
```

Example:

```python
import pandas as pd

data = {
    'Name': ['Ravi', 'Priya', 'Arun'],
    'Mark': [80, None, 70]
}

df = pd.DataFrame(data)

print(df.isnull())
```

To replace missing values:

```python
df['Mark'] = df['Mark'].fillna(0)

print(df)
```

### 2\. Removing Missing Values

The `dropna()` function removes rows containing missing values.

Syntax:

```python
df.dropna()
```

Example:

```python
df = df.dropna()
print(df)
```

### 3\. Removing Duplicate Values

Duplicate values are repeated records in a dataset.

The `drop_duplicates()` function removes duplicate rows.

Syntax:

```python
df.drop_duplicates()
```

Example:

```python
data = {
    'Name': ['Ravi', 'Priya', 'Ravi'],
    'Mark': [80, 90, 80]
}

df = pd.DataFrame(data)

df = df.drop_duplicates()

print(df)
```

### 4\. Renaming Columns

The `rename()` function changes column names.

Syntax:

```python
df.rename(columns={'old':'new'})
```

Example:

```python
df.rename(columns={'Mark':'Marks'}, inplace=True)
```

### 5\. Changing Data Types

The `astype()` function changes the data type of a column.

Syntax:

```python
df['column'] = df['column'].astype(int)
```

Example:

```python
df['Mark'] = df['Mark'].astype(int)
```

### 3.4 Steps in Data Cleaning

* Load the dataset.

* Examine the data.

* Identify missing values.

* Remove duplicate records.

* Correct incorrect values.

* Convert data types.

* Save the cleaned dataset.

Applications:

* Student mark analysis.

* Customer information management.

* Medical data analysis.

* Business data processing.

### 4\. Data Visualization Using Matplotlib

### 4.1 Definition

Matplotlib is a Python library used to create graphs, charts and visual representations of data.

It helps users understand data easily through graphical representation.

### 4.2 Features of Matplotlib

* Creates different types of graphs.

* Supports labels and titles.

* Provides different colours and styles.

* Supports customization.

* Displays numerical data visually.

### 4.3 Installing and Importing Matplotlib

Syntax:

```python
pip install matplotlib
```

Import statement:

```python
import matplotlib.pyplot as plt
```

### 4.4 Types of Charts

![Write a Python program to plot a bar chart using the | KnowledgeBoat](https://images.openai.com/static-rsc-4/nQS7aU-qBj-3yah-CP6YjsnhTkWAQvvWKQBdllQaOyyolBLHuByITwBESejhS262jJVT2F-npsxoSg5pW6y-Tfn9o5p7pm-XINsvvuVYYWUvVdDwnELuk87Gzhma9a0299YuGSymnu7rpfbgWSMJkwI7BEbz2YjNdWByUw082XhmevyAuqxVNdOSdB8u0z8A?purpose=fullsize)

1\. Bar Chart

A bar chart represents data using rectangular bars. It is used to compare different categories.

![Matplotlib: Part 1. An Introduction and Basic Plotting Techniques | by Ebrahim Mousavi | Medium](https://images.openai.com/static-rsc-4/x2o9-TZYmpfqkLIFqoH0ERCJC4LjFKjerXh9ihIadQOcS9MuO69ebfnqj5DEYCfy4D5U82ye4oETyipHIQW_LsTzREO-lYRo1GalZv3Jo1LU8ZrtzJ6f4X7HFHdq3j00YZ5-FgOe01l4WqWTCywyioF6odZVrwNdrlQsfF_QE49P-bF-IpPM2d3l2lpxrmxt?purpose=fullsize)

2\. Line Chart

A line chart connects data points using lines. It is used to show changes over time.

![Exploring Data Visualization Techniques  | Medium](https://images.openai.com/static-rsc-4/jyp8SQKhT3I6LrsCYQWs4cmA7LcTPMqLBgH0BRattFSxi3wgkreU3tpnv9F_zMLoPwb5xPwS1u-ehDwyNEDjXtkUkpBxMYvzwGF6ewxMdozdYkoLivKasYTrdLVTiDcdFboUPHVGmAMICJH903iE1bGEog56GA03o3a27o3Ea0pj5SmckVkcg7igBFsGes-X?purpose=fullsize)

3\. Pie Chart

A pie chart represents data as circular sectors. It is used to show proportions.

![Programming Across Disciplines](https://images.openai.com/static-rsc-4/JOIoYOOrOLuPfVjWymeNmcnIRrFBEoJq44TPk48e7_HPZELPNT4uq3LuDpw6O5NFl6Us7-EfOIctgecaxajm8BkSMAECEpTWaplrQDtiBS0R5OajmxMUf-z3dy756Aob_WsAJ4Bd1ucCexAFGSmkLB6UOnhPWsXFphrKazzldsMsFTs6dvCYcSV9R9JZDifg?purpose=fullsize)

4\. Scatter Plot

A scatter plot displays individual points. It is used to identify relationships between variables.

### 4.5 Bar Chart

Syntax:

```python
plt.bar(x, y)
plt.show()
```

Example:

```python
import matplotlib.pyplot as plt

names = ['Ravi', 'Priya', 'Arun']
marks = [80, 90, 70]

plt.bar(names, marks)

plt.xlabel("Students")
plt.ylabel("Marks")
plt.title("Student Marks")

plt.show()
```

### 4.6 Line Chart

Syntax:

```python
plt.plot(x, y)
plt.show()
```

Example:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [10, 20, 30, 40]

plt.plot(x, y)

plt.title("Line Chart")
plt.xlabel("X Values")
plt.ylabel("Y Values")

plt.show()
```

### 4.7 Pie Chart

Syntax:

```python
plt.pie(values, labels=labels)
plt.show()
```

Example:

```python
import matplotlib.pyplot as plt

values = [40, 30, 20, 10]
labels = ['A', 'B', 'C', 'D']

plt.pie(values, labels=labels,
        autopct='%1.1f%%')

plt.title("Percentage Chart")
plt.show()
```

### 4.8 Scatter Plot

Syntax:

```python
plt.scatter(x, y)
plt.show()
```

Example:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [5, 10, 15, 20]

plt.scatter(x, y)

plt.title("Scatter Plot")
plt.show()
```

### 4.9 Important Matplotlib Functions

| Function      | Purpose                |
| ------------- | ---------------------- |
| plt.plot()    | Creates a line chart   |
| plt.bar()     | Creates a bar chart    |
| plt.pie()     | Creates a pie chart    |
| plt.scatter() | Creates a scatter plot |
| plt.title()   | Adds a title           |
| plt.xlabel()  | Adds X-axis label      |
| plt.ylabel()  | Adds Y-axis label      |
| plt.legend()  | Displays legend        |
| plt.grid()    | Displays grid          |
| plt.show()    | Displays the graph     |
| plt.savefig() | Saves the graph        |

Applications:

* Statistical analysis.

* Scientific research.

* Business reports.

* Data science.

* Educational analysis.

### 5\. Unit Testing Using unittest and pytest

### 5.1 Definition of Unit Testing

Unit Testing is a software testing technique in which individual units or functions of a program are tested separately to verify their correctness.

It helps identify errors at an early stage.

### 5.2 Importance of Unit Testing

* Identifies programming errors.

* Improves code quality.

* Ensures correct output.

* Makes debugging easier.

* Reduces software failures.

* Improves program reliability.

### 5.3 Types of Unit Testing Frameworks

Python provides different testing frameworks. Two important frameworks are:

* unittest

* pytest

### 5.4 unittest

Definition:

`unittest` is a built-in Python testing framework used to test individual functions and classes.

It supports test cases, test suites and test runners.

### Important Features

* Built into Python.

* Supports test cases.

* Provides assertion methods.

* Supports automated testing.

* Helps identify errors.

### Important Methods

| Method           | Description                                   |
| ---------------- | --------------------------------------------- |
| assertEqual()    | Checks whether two values are equal           |
| assertNotEqual() | Checks whether two values are different       |
| assertTrue()     | Checks whether a condition is true            |
| assertFalse()    | Checks whether a condition is false           |
| assertIn()       | Checks whether a value exists in a collection |
| assertRaises()   | Checks whether an exception occurs            |

### Syntax

```python
import unittest

class TestClass(unittest.TestCase):

    def test_example(self):
        self.assertEqual(10, 10)

if __name__ == '__main__':
    unittest.main()
```

### Simple Example

```python
import unittest

def add(a, b):
    return a + b

class TestAddition(unittest.TestCase):

    def test_add(self):
        self.assertEqual(add(5, 3), 8)

if __name__ == '__main__':
    unittest.main()
```

Output:

```text
Ran 1 test
OK
```

### 5.5 pytest

Definition:

Pytest is a popular Python testing framework used to test programs with simple functions and readable test cases.

It requires installation.

Installation:

```python
pip install pytest
```

### Features of pytest

* Simple syntax.

* Easy test execution.

* Supports automated testing.

* Provides detailed error reports.

* Supports parameterized testing.

### Syntax

```python
def test_example():
    assert 10 == 10
```

### Simple Example

Create a file named `test_sample.py`.

```python
def add(a, b):
    return a + b

def test_add():
    assert add(5, 3) == 8
```

Run the test:

```text
pytest
```

Output:

```text
1 passed
```

### 5.6 Difference Between unittest and pytest

| unittest                 | pytest                   |
| ------------------------ | ------------------------ |
| Built into Python        | Requires installation    |
| Uses classes and methods | Uses simple functions    |
| Uses assertion methods   | Uses assert statement    |
| More structured syntax   | Simple syntax            |
| Supports test automation | Supports test automation |

### 6\. Debugging

### 6.1 Definition

Debugging is the process of identifying, analyzing and correcting errors (bugs) in a computer program.

It helps ensure that a program works correctly.

### 6.2 Types of Programming Errors

1\. Syntax Error

Occurs when Python grammar rules are violated.

Example:

```python
print("Hello"
```

The closing bracket is missing.

2\. Runtime Error

Occurs while the program is executing.

Example:

```python
a = 10
b = 0

print(a / b)
```

This produces a `ZeroDivisionError`.

3\. Logical Error

Occurs when the program runs successfully but produces an incorrect result.

Example:

```python
a = 10
b = 20

print(a - b)
```

If the intention is addition, the program contains a logical error.

### 6.3 Debugging Techniques

* Print statements – Display variable values.

* Breakpoints – Pause program execution.

* Step execution – Execute one line at a time.

* Variable inspection – Check variable values.

* Exception handling – Handle runtime errors.

* Debugger tools – Use Python debugging tools.

### 6.4 Debugging Using pdb

Definition:

`pdb` is the built-in Python debugger used to examine and control program execution.

Syntax:

```python
import pdb

pdb.set_trace()
```

Example:

```python
import pdb

a = 10
b = 20

pdb.set_trace()

c = a + b

print(c)
```

### Important pdb Commands

| Command    | Description          |
| ---------- | -------------------- |
| n          | Execute next line    |
| s          | Step into a function |
| c          | Continue execution   |
| p variable | Print variable value |
| q          | Quit debugger        |

Advantages of Debugging:

* Finds program errors.

* Improves code quality.

* Helps understand program execution.

* Reduces development time.

### 7\. Profiling

### 7.1 Definition

Profiling is the process of measuring the performance of a Python program.

It identifies how much time and resources are consumed by different parts of a program.

### 7.2 Importance of Profiling

* Identifies slow functions.

* Measures execution time.

* Improves program performance.

* Reduces unnecessary operations.

* Helps optimize memory usage.

### 7.3 Types of Profiling

1\. Time Profiling

Measures the execution time of a program or function.

2\. Memory Profiling

Measures the amount of memory used by a program.

3\. Function Profiling

Measures the time spent executing individual functions.

### 7.4 Profiling Using time Module

The `time` module measures execution time.

Syntax:

```python
import time

start = time.time()

# Program code

end = time.time()

print(end - start)
```

Example:

```python
import time

start = time.time()

total = 0

for i in range(100000):
    total += i

end = time.time()

print("Time taken:", end - start)
```

### 7.5 Profiling Using cProfile

`cProfile` is a built-in Python module used to measure the performance of functions.

Syntax:

```python
import cProfile

cProfile.run('function_name()')
```

Example:

```python
import cProfile

def calculate():
    total = 0

    for i in range(1000):
        total += i

cProfile.run('calculate()')
```

Applications:

* Performance optimization.

* Scientific computing.

* Large data processing.

* Software development.

### 8\. Python Packaging

### 8.1 Definition

Python Packaging is the process of organizing Python code into reusable and distributable packages.

It allows developers to share their programs with other users.

### 8.2 Features of Python Packaging

* Organizes program files.

* Supports code reuse.

* Makes installation easier.

* Simplifies distribution.

* Helps manage dependencies.

### 8.3 Module and Package

Module:

A module is a single Python file containing functions, variables or classes.

Example:

```python
# mathmodule.py

def add(a, b):
    return a + b
```

Importing the module:

```python
import mathmodule

print(mathmodule.add(5, 3))
```

Package:

A package is a collection of related Python modules organized in a directory.

Example structure:

```text
mypackage/
    __init__.py
    add.py
    subtract.py
```

### 8.4 Creating a Python Package

Step 1: Create a folder named `mypackage`.

Step 2: Create a file named `__init__.py`.

Step 3: Create a module named `add.py`.

```python
def add(a, b):
    return a + b
```

Step 4: Import and use the package.

```python
from mypackage.add import add

print(add(10, 20))
```

Output:

```text
30
```

### 8.5 pip

Definition:

pip is the package installer for Python. It is used to install, upgrade and manage Python packages.

Important Commands:

| Command                      | Purpose                      |
| ---------------------------- | ---------------------------- |
| pip install numpy            | Installs NumPy               |
| pip install pandas           | Installs Pandas              |
| pip uninstall numpy          | Removes NumPy                |
| pip list                     | Lists installed packages     |
| pip show pandas              | Displays package information |
| pip install --upgrade pandas | Upgrades Pandas              |

