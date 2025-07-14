# Error Handling
✏️ Covered topics in this section:
- `try-except` statements
- `ValueError`, `ZeroDivisionError`, `TypeError`, `AttributeError`
- `IndexError`, `KeyError`, `NameError`
- Exception hierarchy and order

---

## 1. What is the expected output of the following statement?
```python
try:
    print(int("abc"))
except ValueError:
    print("Caught a ValueError")
except Exception:
    print("Caught a generic exception")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Caught a ValueError
```

**Explanation**: The code `int("abc")` raises a `ValueError: invalid literal for int() with base 10: 'abc'`. The first matching `except` block is `except ValueError`, so its message is printed and the other `except` blocks are skipped.
</details>

## 2. What is the expected output of the following statement?
```python
try:
    result = 10 / 0
    print(result)
except TypeError:
    print("Caught a TypeError")
except ZeroDivisionError:
    print("Caught a ZeroDivisionError")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Caught a ZeroDivisionError
```

**Explanation**: Dividing by zero raises a `ZeroDivisionError`. The corresponding `except` block is executed.
</details>

## 3. What is the expected output of the following statement?
```python
try:
    print("start")
    print(1 + "2")
    print("end")
except ValueError:
    print("ValueError")
except TypeError:
    print("TypeError")
```
<details><summary>💡 Answer</summary>

**Output**:
```
start
TypeError
```

**Explanation**: The code first prints "start". Then, `1 + "2"` raises a `TypeError` because you cannot add an integer and a string. The program jumps to the `except TypeError` block and prints "TypeError". The line `print("end")` is never reached.
</details>

## 4. What is the expected output of the following statement?
```python
my_list = [1, 2, 3]
try:
    print(my_list[3])
except IndexError:
    print("Index out of range")
except LookupError:
    print("Lookup error")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Index out of range
```

**Explanation**: Accessing `my_list[3]` raises an `IndexError` because the valid indices are 0, 1, and 2. `IndexError` is a subclass of `LookupError`, but the more specific exception handler is matched first.
</details>

## 5. What is the expected output of the following statement?
```python
my_dict = {'a': 1}
try:
    print(my_dict['b'])
except KeyError:
    print("Key not found")
except IndexError:
    print("Index error")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Key not found
```

**Explanation**: Accessing a non-existent key 'b' in a dictionary raises a `KeyError`.
</details>

## 6. What is the expected output of the following statement?
```python
try:
    x = y + 1
except NameError:
    print("Variable not defined")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Variable not defined
```

**Explanation**: The variable `y` is used before it has been assigned a value, which raises a `NameError`.
</details>

## 7. What is the expected output of the following statement?
```python
try:
    num = 5
    num.append(1)
except Exception as e:
    print(type(e).__name__)
```
<details><summary>💡 Answer</summary>

**Output**:
```
AttributeError
```

**Explanation**: Integers do not have an `append` method. This raises an `AttributeError`. The `except Exception as e` block catches this error, and `type(e).__name__` prints the name of the exception class.
</details>

## 8. Multi selection
Which exception will be raised by the following code?
```python
data = {'key': [1, 2]}
print(data['key'][2])
```
- `KeyError`
- `ValueError`
- `IndexError`
- `TypeError`
<details><summary>💡 Answer</summary>

**Output:**
- ❌ `KeyError` - The key 'key' exists.
- ❌ `ValueError` - The value is valid.
- ✅ `IndexError` - The list `[1, 2]` has no element at index 2.
- ❌ `TypeError` - The types are correct for the operations.
</details>

## 9. What is the expected output of the following statement?
```python
try:
    print(1 / 0)
except Exception:
    print("Caught generic exception")
except ZeroDivisionError:
    print("Caught ZeroDivisionError")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Caught generic exception
```

**Explanation**: Although a `ZeroDivisionError` occurs, the first `except` block that matches is `except Exception`, because `ZeroDivisionError` is a subclass of `Exception`. Python executes the first matching block and ignores the rest. This is why specific exceptions should be caught before general ones.
</details>

## 10. What is the expected output of the following statement?
```python
try:
    print("Step 1")
    result = 10 / 2
    print("Step 2")
except ZeroDivisionError:
    print("Error")
else:
    print("Step 3")
finally:
    print("Step 4")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Step 1
Step 2
Step 3
Step 4
```

**Explanation**: No exception occurs, so the `except` block is skipped. The `else` block is executed because the `try` block completed successfully. The `finally` block is always executed, regardless of whether an exception occurred or not.
</details>