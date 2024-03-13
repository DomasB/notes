---
tags:
  - Python
  - Programming
  - exceptions
Link:
  - https://rollbar.com/blog/throwing-exceptions-in-python/
---
Main idea: Exceptions in Python can happen because of syntax errors or they can be thrown manually to control code flow. Exceptions can be handled using Try-Except-Else-Finally pattern.

## Sections:

### Python Exceptions Overview

- Python has a robust error handling framework using pre-defined exceptions.
- Python has error types and can handle each error differently.

### Syntax Errors vs Exceptions

- Syntax errors are coding errors where code doesn't adhere to Python language rule, leading to a `SyntaxError` exception and termination of the program. Syntax errors can't be handled.
- Python throws the `TypeError` exception when operations are performed on incompatible data types.
- There are more built in exceptions. Full list can be found [here](https://docs.python.org/3/library/exceptions.html#concrete-exceptions)
- Exceptions occur during runtime due to various error conditions but can be handled within the code.
- Example:
```python
if (a < b)
	print('a is less than b')
	# Throws SyntaxError
	
a = 'foo' b = 'bar'
print(a % b)
# Throws TypeError
```

### Throwing Exceptions

- Custom exceptions can be raised using the `raise` keyword.
- Instead of raising a generic exception, exception type can be specified
- Example: 
```python
if date_provided.date() < current_date.date():
	raise Exception("Date provided can't be in the past")
	# or
	raise ValueError("Date provided can't be in the past")
```

### Using Assertions

- Assertions (`assert`) check a condition and raise an `AssertionError` if the condition is false.
- Assertions help reduce `if` condition checking.
- Example: 
```python
assert(date_provided.date() >= current_date.date()), "Date provided can't be in the past"
```

### Catching Exceptions with Try-Except

- Most programming languages have `try-catch` blocks, but python has `try-except`.
- Multiple `except` blocks can be used to handle different exception types.
- Example: 
```python
import sys

try:
	assert (sys.version_info[0] == 3), "Python version must be 3"
except Exception as e:
	print(e)
```

### Try-Except-Else-Finally Structure

- The `else` block runs if no exceptions are raised in the `try` block.
- The `finally` block runs regardless of whether an exception was raised, ideal for cleanup tasks.
- Example: 
```python
try:
	f = open("testfile.txt", 'r')
except FileNotFoundError as fne: 
	print(fne)
	print('Creating file...')
	f = open("testfile.txt", 'w')
	f.write('2')
else:
	data=f.readline(1)
	print(data)
finally:
	print('Closing file')
	f.close()
```

## Related ideas

- Python Programming Fundamentals
- Error Handling Best Practices
- Understanding Python Syntax and Structure