# Python Cheat Sheet

## Setting Up a Virtual Environment

```bash
# Create a virtual environment
python3 -m venv myenv

# Activate the virtual environment
# On Windows
myenv\Scripts\activate

# On Unix or MacOS
source myenv/bin/activate
```

## Basic Flask Quick Start

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(debug=True)
```

## Other Useful Python Topics

### Reading a File

```python
with open('file.txt', 'r') as file:
    contents = file.read()
```

### Writing to a File

```python
with open('file.txt', 'w') as file:
    file.write('Hello, Python!')
```

### List Comprehensions

```python
numbers = [1, 2, 3, 4, 5]
squared = [n ** 2 for n in numbers]
```

### Function Definition

```python
def greet(name):
    return f"Hello, {name}!"
```

### Dictionary Comprehension

```python
squares = {x: x*x for x in range(6)}
```

### Working with JSON

```python
import json

# Parsing JSON
data = '{"name": "John", "age": 30}'
parsed = json.loads(data)

# Generating JSON
output = json.dumps(parsed)
```

### Error Handling

```python
try:
    # Code that may raise an error
    result = 10 / 0
except ZeroDivisionError:
    print("Divided by zero!")
finally:
    print("This block always executes")
```

String Formatting with f-strings
```
name = "Alice"
age = 30
greeting = f"Hello, {name}, you are {age} years old."
```
List Slicing
```
my_list = [0, 1, 2, 3, 4, 5]

 Get elements from index 1 to 4

sliced_list = my_list[1:5]
```
Tuple Unpacking
```
a, b = (1, 2)
```
