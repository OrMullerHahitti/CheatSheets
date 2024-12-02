**Python Cheat Sheet**

### Basics

#### Variable Declaration

```python
x = 10  # Integer
y = "Hello"  # String
z = 3.14  # Float
```

#### Data Types

```python
# List, Tuple, Set, Dictionary
a_list = [1, 2, 3]
a_tuple = (1, 2, 3)
a_set = {1, 2, 3}
a_dict = {"key": "value"}
```

#### Common Operations

```python
# Arithmetic
a, b = 5, 3
add = a + b  # 8
sub = a - b  # 2
mul = a * b  # 15
div = a / b  # 1.666...

# Conditional Statements
if a > b:
    print("a is greater than b")
elif a < b:
    print("a is less than b")
else:
    print("a is equal to b")
```

### Functions

```python
def greet(name):
    return f"Hello, {name}!"

greet("Harry")  # Hello, Harry!
```

### List Comprehensions

```python
# Create a list of squares
squares = [x**2 for x in range(10)]  # [0, 1, 4, 9, 16, ...]

# Create a list of even numbers
even_numbers = [x for x in range(20) if x % 2 == 0]  # [0, 2, 4, 6, ...]

# Create a list of tuples (number, square)
tuples = [(x, x**2) for x in range(5)]  # [(0, 0), (1, 1), (2, 4), ...]

# Flatten a nested list
nested_list = [[1, 2, 3], [4, 5], [6]]
flat_list = [num for sublist in nested_list for num in sublist]  # [1, 2, 3, 4, 5, 6]

# Convert strings to uppercase
words = ["hello", "world"]
uppercase_words = [word.upper() for word in words]  # ["HELLO", "WORLD"]

# Filter and modify
numbers = [1, 2, 3, 4, 5, 6]
filtered_and_squared = [x**2 for x in numbers if x % 2 == 0]  # [4, 16, 36]
```

### File Handling

```python
with open("file.txt", "r") as file:
    content = file.read()
```

### Classes

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        return "Woof!"

my_dog = Dog("Buddy", 3)
print(my_dog.bark())  # Woof!
```

---

**Pandas and NumPy Cheat Sheet**

### Importing Libraries

```python
import numpy as np
import pandas as pd
```

### NumPy Basics

#### Creating Arrays

```python
# 1D Array
arr = np.array([1, 2, 3, 4])

# 2D Array
matrix = np.array([[1, 2], [3, 4]])
```

#### Array Operations

```python
# Basic Operations
arr = np.array([1, 2, 3, 4])
arr_sum = np.sum(arr)  # 10
arr_mean = np.mean(arr)  # 2.5
arr_max = np.max(arr)  # 4
arr_min = np.min(arr)  # 1
arr_prod = np.prod(arr)  # 24

# Reshaping Arrays
reshaped = arr.reshape((2, 2))

# Transpose
transposed = matrix.T

# Shape
arr_shape = arr.shape  # (4,)
matrix_shape = matrix.shape  # (2, 2)
```

#### Indexing and Slicing

```python
arr = np.array([1, 2, 3, 4, 5])
subset = arr[1:4]  # [2, 3, 4]

matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
element = matrix[1, 2]  # 6
```

#### Random Numbers

```python
rand_arr = np.random.rand(3, 3)  # 3x3 array with random values
rand_int = np.random.randint(0, 10, size=(2, 2))  # 2x2 array with random integers between 0 and 9
```

#### Mathematical Functions

```python
arr = np.array([0, np.pi/2, np.pi])
sin_values = np.sin(arr)  # [0, 1, 0]
exp_values = np.exp(arr)  # Exponential of each element
log_values = np.log(arr + 1)  # Natural log (added 1 to avoid log(0))
```

### Pandas Basics

#### Creating DataFrames

```python
data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [25, 30, 35]
}
df = pd.DataFrame(data)
```

#### Viewing Data

```python
print(df.head())  # View the first 5 rows
print(df.tail())  # View the last 5 rows
print(df.describe())  # Statistical summary
print(df.info())  # Summary of the DataFrame
```

#### Selecting Data

```python
# Selecting Columns
names = df["Name"]

# Selecting Rows
first_row = df.iloc[0]  # First row by index
filtered_df = df[df["Age"] > 30]  # Rows where Age > 30

# Selecting Specific Elements
element = df.at[0, "Name"]  # Get element at first row and 'Name' column
```

#### Adding and Removing Columns

```python
df["Salary"] = [50000, 60000, 70000]  # Add new column
df.drop("Age", axis=1, inplace=True)  # Remove column 'Age'
```

#### Grouping and Aggregation

```python
# Group by 'Age' and calculate mean salary
grouped = df.groupby("Age")["Salary"].mean()

# Aggregate multiple functions
grouped_multiple = df.groupby("Age").agg({"Salary": ["mean", "sum"]})
```

#### Sorting

```python
# Sort by Age
df_sorted = df.sort_values(by="Age", ascending=False)
```

#### Handling Missing Data

```python
df.dropna()  # Drop missing values
df.fillna(0)  # Fill missing values with 0
df.fillna(df.mean(), inplace=True)  # Fill missing values with column mean
```

#### Merging and Concatenation

```python
# Merging DataFrames
merged_df = pd.merge(df1, df2, on="key")

# Concatenating DataFrames
concatenated_df = pd.concat([df1, df2], axis=0)  # Vertical concatenation
```

### Saving and Loading

```python
df.to_csv("data.csv", index=False)  # Save to CSV
loaded_df = pd.read_csv("data.csv")  # Load from CSV

df.to_excel("data.xlsx", index=False)  # Save to Excel
loaded_df_excel = pd.read_excel("data.xlsx")  # Load from Excel
```

### Important Pandas Functions

- `df.head()`, `df.tail()`: View beginning or end of DataFrame
- `df.describe()`, `df.info()`: Get summary statistics or information
- `df.groupby()`: Group data for aggregation
- `df.merge()`, `pd.concat()`: Combine DataFrames
- `df.drop()`, `df.fillna()`: Handle missing data
- `df.sort_values()`: Sort DataFrame by column
- `df.apply()`: Apply a function along axis of DataFrame

### Important NumPy Functions

- `np.array()`: Create NumPy arrays
- `np.sum()`, `np.mean()`, `np.max()`, `np.min()`: Basic aggregations
- `np.reshape()`, `np.transpose()`: Reshape or transpose arrays
- `np.shape()`: Get the shape of an array
- `np.random.rand()`, `np.random.randint()`: Generate random numbers
- `np.sin()`, `np.exp()`, `np.log()`: Mathematical functions
- `np.concatenate()`, `np.vstack()`, `np.hstack()`: Combine arrays
