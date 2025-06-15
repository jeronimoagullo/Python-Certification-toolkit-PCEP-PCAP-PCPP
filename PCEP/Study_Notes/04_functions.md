# Functions & I/O Operations
✏️ Covered topics in this section:
- Defining functions (`def`)
- Parameters vs. arguments
- `return` statement
- `input()` and type conversion
- `print()` formatting (f-strings, `sep=`, `end=`)
- Variable scope (`global` keyword)

---

## 🛠️ 1. Defining Functions
The functions allow to reuse code that is executed more than one time and makes our code more readable.

### Basic Syntax:
A function is defined using the `def` keyword, parenthesis for perameters (it can be empty) and colon. Then, the content of function is indented.

```python
def function_name(parameters):
    # Code block
    return value  # Optional
```

**Example**:
```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
```

**Golden Rule**: The function definition must appear before its execution. Otherwise, the error `NameError: name 'message' is not defined` will be raised.

**Golden Rule (2)**: A Function and a variable cannot shared the name.

---

## 🎯 2. Parameters vs. Arguments
- **Parameters**: Variables listed in function definition
- **Arguments**: Actual values passed during call

**Golden Rule**: The parameters exists only within the function call, while the arguments exists even outside of the function.

### **Default Parameters**
Calling a function which expects a parameter without a parameter value would result in a `TypeError` message. However, we can prevent it providing the function parameter with a default value:

```python
def power(base, exponent=2):
    return base ** exponent

print(power(3))     # 9 (uses default exponent=2)
print(power(3, 3))  # 27
```

### positional parameters vs keyword parameters
We can call a function providing the parameters in ordered or using the name of the parameters to enter in other order, for example:

```python
def worker_greet(name, job):
    print("I am", name, " and works as", job)

worker_greet("Pedro", "developer")
worker_greet(job = "seller", name = "Juan")
```

If you enter a parameter that doesn't exist an `TypeError` will be raised.

**Golden Rule**: If you mix positional parameters with keyword parameters, you need to use positional parameters before, otherwise, an error `TypeError` will be raised.

---

## 🔄 3. `return` and `None` keywords
### The `return` keyword
The `return` keyword is used at the end of a function with two variants:
- **Without expression**: In this case, the function just returns execution to the main code when the `return` keyword is reached. It is explicitly executed at the end of the function if it is not written.
- **With expressions**: In this case, the function also returns the execution to the main code and it returns too the value of the expression(s).

```python
def calculations(a, b):
    sum = a+b
    sub = a-b
    return sum, sub

sum, sub = calculations(4, 5) # sum = 9 and sub = -1
```

**Golden Rule**: You don't need to assigned the return values, you can just execute the function ignoring the returned values.

### `None` keyword
`None` is "nothing". It is returns by a function without a `return` expression.

```python
def is_even(n):
    if(n % 2 == 0):
        return True
```

The above function return `True` if the argument is a even number, but what does it return otherwise? Since there is no `return` expression for other branches, the return value will be `None`.

---

## 🖨️ 4. `print()` function
The `print` function is a native python function which allows us to send (display) text on console.

### **f-strings (Python 3.6+)**
```python
name = "Bob"
print(f"Hello {name.upper()}!")  # Hello BOB!
```

### **`sep` & `end` Parameters**
`sep` modifies the default separator (space) and `end` modifies the carriage return (`\n`) of ending lines:

```python
print("Python", "version", "3.10", sep="~", end="!\\n")
# Output: Python~version~3.10!
```


## ⌨️ 5. `input()` Function
- The `input()` function allows the user to enter text from the keyboard

- **Always returns string** - requires type conversion with `int()` or `float()`, for example:
```python
age = int(input("Enter your age: "))
print(f"You'll be {age+5} in 5 years")
```

- **Multi-input**: It is likely to enter more than one input:
```python
x, y = map(float, input("Enter two numbers: ").split())
print(x + y)
```

---

## 🌐 6. Variable Scope & Function Arguments  
### **6.1. Local vs Global Variables**  
- **Local**: Accessible only within the function.  
- **Global**: Accessible across functions (use `global` to modify).  

**Example (Global Modification)**:  
```python
count = 10  # Global

def update():
    global count  # Explicitly declare
    count = 20   # Modifies global

update()
print(count)  # Output: 20
```

**Example (Local Shadowing)**:  
```python
count = 20  

def try_update():
    count = 30  # Creates new local variable (does not modify global)

try_update()
print(count)  # Output: 20 (global unchanged)
```

**Golden Rule**:  
- You can *read* global variables without `global`.  
- To *modify* them, use `global`.  

### **6.2. The `nonlocal` Keyword**  
- Used in nested functions to modify a variable in the nearest enclosing scope that is not global.  
- Unlike `global`, `nonlocal` looks for the variable in the nearest enclosing scope.  
- The variable must exist in the enclosing scope (unlike `global` which can create a new one). Otherwise, a `SyntaxError` will be raised.

**Example (nonlocal in Nested Functions)**:  
```python
def outer():
    x = "local"
    def inner():
        nonlocal x  # Refers to x from the outer function
        x = "nonlocal"  # Modifies x in the outer scope
        print("Inner:", x)
    inner()
    print("Outer:", x)  # Shows the modified value
    return x

result = outer()
print("Result:", result)
# Output:
# Inner: nonlocal
# Outer: nonlocal
# Result: nonlocal
```

### **6.3. Function Arguments: Pass-by-Object-Reference**  
Python passes arguments **by object reference**. This means:  
- **Immutable objects** (e.g., `int`, `str`, `tuple`):  
  - Changes inside the function **won’t** affect the original.  
  ```python
  def increment(num):
      num += 1  # Creates a new local `num`
      print(num)  # 6

  value = 5
  increment(value)
  print(value)  # Output: 5 (unchanged)
  ```  

- **Mutable objects** (e.g., `list`, `dict`, `set`):  
  - Changes inside the function **will** affect the original.  
  ```python
  def append_item(lst):
      lst.append(4)  # Modifies the original list

  my_list = [1, 2, 3]
  append_item(my_list)
  print(my_list)  # Output: [1, 2, 3, 4]
  ```

**Key Pitfall**:  
Rebinding a mutable variable (e.g., `lst = [4,5]`) creates a new local object instead of modifying the original.  

---

### **6.3. When Changes Persist After Function Returns**  
| **Scenario**               | **Change Visible Outside?** | **Reason**                          |  
|----------------------------|----------------------------|-------------------------------------|  
| Modify mutable argument    | ✅ Yes                     | Original object is modified.        |  
| Reassign mutable argument  | ❌ No                      | Creates a new local object.         |  
| Modify immutable argument  | ❌ No                      | Immutability forces a new object.   |  
| Use `global` keyword       | ✅ Yes                     | Explicitly modifies global scope.   |  

**Example (Mutable vs Reassignment)**:  
```python
def modify_or_replace(lst):
    lst.append(1)    # ✅ Affects original
    lst = [100]      # ❌ Local reassignment (no effect outside)

my_list = [0]
modify_or_replace(my_list)
print(my_list)       # Output: [0, 1] (not [100])
```

---

## 💡 7. Exam Tips & Pitfalls
1. **Return vs Print**:
Functions without `return` give `None`

2. **Scope Shadowing**:
```python
value = 5

def test():
    print(value)  # Error if value is modified below since it was not defined locally
    value = 10

test()  # UnboundLocalError
```

3. **Variables can be used within functions even without `global` keyword**:
This means that you can use any variable outside the scope of a function within the function (if the variable was defined before), however, if you change it within the function, the value will not be modified outside the function (you would need to use `global` keyword):

```python
var1 = 30
var2 = 30

def update_values():
    global var2
    var1 = var2 = 40
    print(var1, var2)   # 40, 40

update_values()
print(var1, var2)   # 30, 40
```

---

🎉 **Congratulations!**
You've completed the **Functions & I/O** section.
Practice with [function questions](../Practice_Exams_Questions/04_functions.md) next!