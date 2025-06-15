Defining functions (def)
Parameters vs. arguments
return vs. print()
input()
print() formatting (f-strings, sep=, end=)
input() and type conversion
Multi-line print() statements
Local vs. global scope (global keyword)



## 1. What does `print(type(input()))` always return?
<details><summary>💡 Answer</summary>

**Output**: `<class 'str'>`.

**Explanation**: The `input()` function returns always a `string` variable.
</details>  

## 2. What is the expected output of the following statement? 
```python
def func(a=1, b=2):
    return a * b

print(func(b=4))
```  
<details><summary>💡 Answer</summary>

**Output**: `4`.

**Explanation**: `a=1, b=4 → 1*4=4`.
</details>


## 3. What is the expected output of the following statement? 
```python
def addition(a, b=4, c):
    print(a + b + c)

addition(a=3, c=2)
```

<details><summary>💡 Answer</summary>

**Output**: 
```
SyntaxError - a non-default argument (c) follows a default argument (b=4)
```

**Explanation**: `c` is a required argument, but it follows a default argument `b=4`.
</details>



## 4. What is the expected output of the following statement? 
```python
def greetings():
    return
    print("Good morning!!")

greetings()
```

<details><summary>💡 Answer</summary>

**Output**: Nothing will be displayed, the `greetings` function returns `None`.

**Explanation**: the function returns as soon as the `return` statement is reached. Since it doesn't return a value, it returns `None` implicitly.
</details>


## 5. What is the expected output of the following statement? 
```python
def is_int(data):
    if type(data) == int:
        return True
    elif type(data) == float:
        return False

print(is_int(10))
print(is_int(10.0))
print(is_int("10"))
```

<details><summary>💡 Answer</summary>

**Output**:
```
True
False
None
```

**Explanation**: 10 and 10.0 are `int` and `float` respectively. However, `"10"` is an string which doesn't have a `return` statement, thus, it returns `None` implicitly.
 </details>


## 6. What is the expected output of the following statement? 
```python
def test_func():
    var=5
    print("Variable in function:", var)


var = 1
test_func()
print("Variable outside function:", var)

```

<details><summary>💡 Answer</summary>


**Output**:
```
Variable in function: 5
Variable outside function: 1
```

**Explanation**: The variable `var` is assigned to `1` firstly. When the function `test_func` is executed, the variable `var` is shadowed by the local variable `var` changing its value to 5. When the function returns, the variable `var` keeps its original value.
 </details>


## 7. What is the expected output of the following statement? 
```python
def test_func():
    global var
    var=5
    print("Variable in function:", var)


var = 1
test_func()
print("Variable outside function:", var)
```

<details><summary>💡 Answer</summary>


**Output**:
```
Variable in function: 5
Variable outside function: 5
```

**Explanation**: The variable `var` is declared as `global` within the `test_func`. Thus, its value is kept outside the function.
 </details>



## 8. What is the expected output of the following statement? 
```python
def factorial(n):
    return n * factorial(n - 1)

print(factorial(4))
```

<details><summary>💡 Answer</summary>


**Output**:
```
Error: RecursionError: maximum recursion depth exceeded
```

**Explanation**: The function calls itself resulting in recursion. However, there is no termination condition raising the error `RecursionError`.
 </details>

## 9. Multi selection
Where must be defined a function?

- In any place of the code after the first invocation
- It must be placed before the first invocation of the function
- It must be placed always in a separate script

<details><summary>💡 Answer</summary>

**Output:**

  - ❌ In any place of the code after the first invocation
  - ✅ It must be placed before the first invocation of the function
  - ❌ It must be placed always in a separate script
  </details>

## 10. Multi selection
What of the following alternatives will affect a list that is passed as an argument to a function?

- Removing an element of the list with `del` keyword
- Modifying an element of the list like `list[0] = 10`
- Adding an element to the list with `list.append(10)`
- Redefining the list with `list = [1, 2, 3]`

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ Removing an element of the list with `del` keyword
  - ✅ Modifying an element of the list like `list[0] = 10`
  - ✅ Adding an element to the list with `list.append(10)`
  - ❌ Redefining the list with `list = [1, 2, 3]`
  </details>


## 11. What is the expected output of the following statement? 

```python
def sum_fun(in1=4, in2=2):
    return in1 * in2

print(sum_fun(3))
```

<details><summary>💡 Answer</summary>

**Output**:
```
6
```

**Explanation**:
The function `sum_fun` has default arguments `in1=4` and `in2=2`. When called as `sum_fun(3)`, `in1` becomes `3`, `in2` remains `2`.Thus, the function returns `3 * 2 = 6`.

</details>

## 12. What is the output of the following code using f-strings?

```python
def greet(name, age):
    return f"{name.upper()} is {age} years old"

print(greet(age=25, name="alice"))
```

<details><summary>💡 Answer</summary>

**Output**: `ALICE is 25 years old`

**Explanation**: The function uses an f-string to format the output. The `name` parameter is converted to uppercase, and the parameters are passed using keyword arguments in reverse order, which is allowed.
</details>

## 13. What is the output of the following code with multiple return values?

```python
def process_data(data):
    return len(data), min(data), max(data)

result = process_data([5, 2, 8, 1, 9])
print(type(result), result)
```

<details><summary>💡 Answer</summary>

**Output**: `<class 'tuple'> (5, 1, 9)`

**Explanation**: The function returns a tuple containing the length, minimum, and maximum of the input list. Multiple return values are automatically packed into a tuple.
</details>

## 14. What is the output of the following statement?

```python
def modify_args(a, b):
    a = 100
    b[0] = 100

x = 1
y = [1, 2, 3]
modify_args(x, y)
print(x, y)
```

<details><summary>💡 Answer</summary>

**Output**: `1 [100, 2, 3]`

**Explanation**: `x` is an integer (immutable) so changes inside the function don't affect the original. `y` is a list (mutable), so modifying its elements affects the original list.
</details>

## 15. What is the output of the following code with default parameters?

```python
def create_user(name, role='user', active=True):
    return f"{name} ({'active' if active else 'inactive'}) - {role}"

print(create_user('Alice'))
print(create_user('Bob', active=False))
print(create_user(role='admin', name='Charlie'))
```

<details><summary>💡 Answer</summary>

**Output**:
```
Alice (active) - user
Bob (inactive) - user
Charlie (active) - admin
```

**Explanation**: Shows different ways to call functions with default parameters and keyword arguments. The second call overrides only the `active` parameter, leaving `role` as default.
</details>

## 16. What is the output of the following code with nested functions and variable scope?

```python
def outer():
    x = 'local'
    def inner():
        nonlocal x
        x = 'nonlocal'
        print("Inner:", x)
    inner()
    print("Outer:", x)
    return x

result = outer()
print("Result:", result)
```

<details><summary>💡 Answer</summary>

**Output**:
```
Inner: nonlocal
Outer: nonlocal
Result: nonlocal
```

**Explanation**: The `nonlocal` keyword allows the inner function to modify the `x` variable from the enclosing scope, affecting both the outer function's variable and the returned value.
</details>

## 17. What is the output of the following statement?

```python
def print_table():
    print('Name', 'Age', 'City', sep=' | ', end='\n---\n')
    print('Alice', 30, 'New York', sep=' | ')
    print('Bob', 25, 'London', sep=' | ', end='!')

print_table()
```

<details><summary>💡 Answer</summary>

**Output**:
```
Name | Age | City
---
Alice | 30 | New York
Bob | 25 | London!
```

**Explanation**: The `sep` parameter controls the separator between arguments (default is space), and `end` controls what's printed at the end (default is newline). The first print ends with a custom separator line, and the last print ends with '!' instead of a newline.
</details>

## 18. What is the expected output of the following statement? 

```python
tup = (1, ) + (1, )
tup = tup + tup
print(len(tup))
```

<details><summary>💡 Answer</summary>

**Output**:
```
4
```

**Explanation**:
The tuple `tup` is created by concatenating `(1,)` with itself, which results in `(1, 1)`. When concatenated again with itself, the result is `(1, 1, 1, 1)`, which has a length of `4`.

</details>

## 19. What is the expected output of the following statement? 

```python
dict = {'one':'two','three':'one','two':'three'}
v = dict['one']

for k in range(len(dict)):
    v = dict[v]

print(v)
```

<details><summary>💡 Answer</summary>

**Output**:
```
two
```

**Explanation**: The sequence of the `for` loop is the following:
```
k: 0  v: three
k: 1  v: one
k: 2  v: two
```

</details>

## 20. What is the expected output of the following statement?

```python
def count_down(n):
    if n == 0:
        return
    print(n)
    count_down(n - 1)

count_down(3)
```

<details><summary>💡 Answer</summary>

**Output**:
```
3
2
1
```

**Explanation**: The function recursively counts down from `n` to `0`, printing each number.
</details>

