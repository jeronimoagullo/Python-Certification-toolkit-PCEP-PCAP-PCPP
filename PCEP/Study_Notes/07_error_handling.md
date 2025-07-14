# Error Handling in Python

✏️ Covered topics in this section:
- What is a bug?
- Python's error detection
- try-except statements
- Main exceptions
- Debugging techniques
- Exam Tips & Pitfalls

---

## 1. Introduction: What is a "Bug"?
A **bug** is an error in your code that causes it to behave unexpectedly or crash. Bugs can be:
- **Syntax errors:** Mistakes in the code structure (e.g., missing colon, unmatched parentheses).
- **Runtime errors (exceptions):** Errors that occur while the program is running (e.g., dividing by zero, accessing an undefined variable).
- **Logical errors:** Code runs but produces incorrect results.

---

## 2. Python is Blind: When Errors Are Detected
Python only checks for errors when code is executed—not before. This means that syntax errors are detected only when the interpreter reaches the faulty line.

**Example:**
```python
print("Hello")
print("World"  # SyntaxError: unexpected EOF while parsing
```

---

## 3. The try-except Statement
Error handling in Python is done with `try-except` blocks.

**Basic Structure:**
```python
try:
    # Code that might cause an error
    x = int(input("Enter a number: "))
    y = 10 / x
except ZeroDivisionError:
    print("You can't divide by zero!")
except ValueError:
    print("Please enter a valid integer!")
except Exception:
    print("Some other error occurred!")
```

- **try:** Place code that may raise an exception here.
- **except:** Handle specific exceptions. You can have multiple excepts for different error types.
- **Default except:** Use `except Exception:` (or just `except:`) to catch any error not previously handled.

**Golden Rule:** Only catch exceptions you are prepared to handle. Catching all exceptions can hide bugs.

**Multiple excepts:**
```python
try:
    # risky code
except ValueError:
    # handle ValueError
except TypeError:
    # handle TypeError
```

**Catching all exceptions (not recommended unless necessary):**
```python
try:
    # risky code
except:
    print("An error occurred!")
```

---

## 4. Main Exceptions in Python
Some common exceptions you should know for the PCEP exam:
- **ValueError:** Invalid value (e.g., `int('abc')`).
- **ZeroDivisionError:** Division by zero (e.g., `1/0`).
- **TypeError:** Wrong type of argument (e.g., adding string and int).
- **AttributeError:** Accessing an attribute/method that doesn't exist.
- **SyntaxError:** Invalid Python code structure (usually found before running code).
- **IndexError:** Accessing an invalid index in a sequence.
- **KeyError:** Accessing a missing key in a dictionary.
- **NameError:** Using a variable that hasn't been defined.

**Examples:**
```python
# ValueError
int('abc')  # ValueError

# ZeroDivisionError
10 / 0  # ZeroDivisionError

# TypeError
'2' + 2  # TypeError

# AttributeError
x = 5
x.append(1)  # AttributeError

# IndexError
lst = [1,2]
lst[10]  # IndexError

# KeyError
d = {'a': 1}
d['b']  # KeyError

# NameError
print(undeclared_var)  # NameError
```

---

## 5. Debugging
Debugging is the process of finding and fixing bugs.

- **Rubber Duck Method:** Explain your code line-by-line to a rubber duck (or anyone!). This often helps you spot mistakes.
- **Print Debugging:** Use `print()` statements to check variable values and program flow.
- **Debug Mode / IDE Debugger:** Use your IDE's debugger to set breakpoints and step through code.
- **Read Error Messages:** Python's error messages often tell you exactly where and what went wrong.

**Example:**
```python
print("Before risky code")
try:
    risky()
except Exception as e:
    print("Error:", e)
print("After error handling")
```

---

## 💡 6. Exam Tips & Pitfalls
1. **Syntax errors stop code from running at all.**
2. **Only code inside try block is protected.** Code after the try block is not covered.
3. **Order of excepts matters:** More specific exceptions should come before general ones.
4. **Don't catch exceptions you can't handle.**
5. **Use exception objects:**
   ```python
   try:
       1/0
   except ZeroDivisionError as e:
       print(e)  # division by zero
   ```
6. **Never ignore exceptions silently:** Always provide some feedback or logging.
7. **Common mistakes:**
   - Misspelling exception names (e.g., `ZeroDivisonError` instead of `ZeroDivisionError`).
   - Using except without try.
   - Catching too broad exceptions.
   - Not reading the error message carefully.
8. **Golden Rule:** Learn to read and understand Python's error messages—they are your best debugging tool!

---

🎉 **Congratulations!**
You've completed the **error handling** section.
Practice with [error handling questions](../Practice_Exams_Questions/07_error_handling.md) next!

---

## 7. (EXTRA) Unit Testing
Unit testing is a crucial part of ensuring your code is reliable and works as expected. Python's `unittest` module provides a rich set of tools for constructing and running tests.

**Example:**
```python
import unittest

def add(x, y):
    return x + y

class TestAddFunction(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(1, 2), 3)
        self.assertEqual(add(-1, 1), 0)
        self.assertEqual(add(-1, -1), -2)

if __name__ == '__main__':
    unittest.main()
```

**Key Concepts:**

- **Test Case:** A single test for a specific piece of functionality.
- **Test Suite:** A collection of test cases.
- **Assertion:** A statement that checks if a condition is true.

**Best Practices:**

- **Write tests before writing code:** This approach is known as Test-Driven Development (TDD).
- **Keep tests independent:** Each test should be able to run independently of others.
- **Use descriptive names:** Use clear and descriptive names for tests and test cases.