# 🐍 Python Refresher Cheat-Sheet

---

## 🔹 1. Python Basics

```python
# Variables
x = 10        # int
pi = 3.14     # float
name = "Sabbir" # string
is_active = True # bool

# Multiple assignment
a, b, c = 1, 2, 3
a = b = c = 5

# Type checking & casting
type(x)        # <class 'int'>
int("10")      # 10
float(5)       # 5.0
str(100)       # "100"
```

---

## 🔹 2. Strings

```python
s = "Python Rocks!"
s.lower()        # 'python rocks!'
s.upper()        # 'PYTHON ROCKS!'
s.title()        # 'Python Rocks!'
s.strip()        # removes whitespace
s.replace("Rocks", "Rules")  # 'Python Rules!'
"Hello " + "World"           # concatenation
",".join(["a","b","c"])      # 'a,b,c'
"AIUB".startswith("AI")      # True
"AIUB".endswith("UB")        # True
```

f-strings:

```python
name = "Sabbir"
age = 25
print(f"My name is {name}, I am {age}")
```

---

## 🔹 3. Lists

```python
fruits = ["apple", "banana", "cherry"]
fruits.append("mango")
fruits.insert(1, "orange")
fruits.remove("banana")
fruits.pop()     # removes last
fruits.sort()
fruits.reverse()
fruits[0:2]      # slicing ['apple','orange']
```

List comprehensions:

```python
nums = [x for x in range(10) if x % 2 == 0]  # [0,2,4,6,8]
```

---

## 🔹 4. Tuples

```python
t = (1, 2, 3)
t[0]     # 1
# immutable → t[0] = 5 ❌ Error
```

---

## 🔹 5. Sets

```python
s = {1, 2, 3}
s.add(4)
s.remove(2)
s.union({3,4,5})   # {1,2,3,4,5}
s.intersection({2,3}) # {2,3}
```

---

## 🔹 6. Dictionaries

```python
student = {"name": "Sabbir", "age": 25}
student["email"] = "test@gmail.com"
student.keys()    # dict_keys([...])
student.values()  # dict_values([...])
student.items()   # dict_items([...])
```

---

## 🔹 7. Conditionals

```python
x = 10
if x > 5:
    print("Greater")
elif x == 5:
    print("Equal")
else:
    print("Smaller")
```

Ternary:

```python
result = "Even" if x % 2 == 0 else "Odd"
```

---

## 🔹 8. Loops

```python
for i in range(5):
    print(i)

while x > 0:
    x -= 1

# Loop with else
for i in range(3):
    print(i)
else:
    print("Finished")
```

---

## 🔹 9. Functions

```python
def greet(name="World"):
    return f"Hello {name}"

print(greet("Sabbir"))
```
---

## 🔹 10. Lambda

```python
square = lambda x: x**2
```
### **10.1. Lambda with `map()`**

* Apply a function to **every element in a list**.

```python
nums = [1,2,3,4,5]
squared = list(map(lambda x: x**2, nums))
print(squared)  # [1,4,9,16,25]
```

---

### **10.2. Lambda with `filter()`**

* Filter items based on a **condition**.

```python
nums = [1,2,3,4,5]
evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)  # [2,4]
```

---

### **10.3. Lambda with `reduce()`** (from `functools`)

* Reduce a list to a **single value**.

```python
from functools import reduce
nums = [1,2,3,4,5]
sum_all = reduce(lambda x, y: x + y, nums)
print(sum_all)  # 15
```

---

### **10.4. Lambda with `sorted()`**

* Custom sorting using a lambda.

```python
students = [("Alice", 25), ("Bob", 20), ("Charlie", 23)]
# Sort by age
sorted_students = sorted(students, key=lambda x: x[1])
print(sorted_students)
# [('Bob', 20), ('Charlie', 23), ('Alice', 25)]
```

---

### **10.5. Lambda Inside List Comprehensions**

```python
nums = [1,2,3,4,5]
squared = [(lambda x: x**2)(x) for x in nums]
print(squared)  # [1,4,9,16,25]
```

---

### **10.6. Lambda in Dictionaries**

```python
funcs = {
    "square": lambda x: x**2,
    "cube": lambda x: x**3
}

print(funcs )  # 16
print(funcs )    # 27
```



---

## 🔹 11. Error Handling

```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Division by zero")
finally:
    print("Always executed")
```

---

## 🔹 12. File Handling

```python
with open("test.txt", "w") as f:
    f.write("Hello")

with open("test.txt", "r") as f:
    data = f.read()
```

---

## 🔹 13. Classes & OOP

```python
class Person:
    def __init__(self, name):
        self.name = name
    def greet(self):
        return f"Hi, I am {self.name}"

p = Person("Sabbir")
print(p.greet())
```

Inheritance:

```python
class Student(Person):
    def __init__(self, name, id):
        super().__init__(name)
        self.id = id
```

---

## 🔹 14. Modules & Packages

```python
import math
math.sqrt(16)    # 4.0
from datetime import datetime
```

---

## 🔹 15. Useful Built-ins

```python
nums = [1,2,3,4]
sum(nums)     # 10
max(nums)     # 4
min(nums)     # 1
sorted(nums, reverse=True)  # [4,3,2,1]
zip([1,2],[3,4])  # pairs
enumerate(["a","b"])  # (0,'a'), (1,'b')
```

---

## 🔹 16. Iterators & Generators

```python
def gen():
    for i in range(5):
        yield i

for val in gen():
    print(val)
```

---

## 🔹 17. List vs Set vs Dict Comprehensions

```python
[x**2 for x in range(5)]          # list
{x for x in "hello"}              # set
{k:v for v,k in enumerate("abc")} # dict
```

---

## 🔹 18. Virtual Environment (important for ML work)

```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
pip install numpy
```

---

## 🔹 19. NumPy (Quick Refresher)

```python
import numpy as np
arr = np.array([1,2,3])
arr.shape
arr.reshape(3,1)
np.zeros((2,2))
np.ones((2,2))
np.random.rand(2,2)
np.dot([1,2],[3,4])   # 11
```

---

## 🔹 20. Pandas (Quick Refresher)

```python
import pandas as pd
df = pd.DataFrame({"A":[1,2,3],"B":[4,5,6]})
df.head()
df.describe()
df["A"]
df[df["A"]>1]
```

---

## 🔹 21. Matplotlib (Quick Refresher)

```python
import matplotlib.pyplot as plt
plt.plot([1,2,3],[4,5,6])
plt.title("Line")
plt.show()
```

---
