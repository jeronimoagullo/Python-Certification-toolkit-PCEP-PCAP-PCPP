# Data Types & Variables practice questions

✏️ Covered topics in this section:
- Variables (rules, naming conventions)
- Numeric types (int, float, complex)
- Strings (str), escape sequences, multiline strings
- Booleans (True/False)
- Type conversion (int(), str(), float())


## Question 1: Valid Variable Name
**Multi Selection**
Which of the following variable names are valid in Python?

- `Var`
- `_temp`
- `3rd_user`
- `elif`
- `total-sum`

<details><summary>💡 Answer</summary>

**Output:**

  - ❌ `Var` is valid.  
  - ✅ `_temp` is valid. You can use underscore.
  - ❌ `3rd_user` is invalid because it starts with number
  - ❌ `elif` is invalid because it is a keyword
  - ❌ `total-sum` is invalid (hyphen not allowed).  

</details>

---

## Question 2: Numeric types
What is the expected output of the following statement? 

```python
number = 10_000
print(number)
print(type(number))
```

<details><summary>💡 Answer</summary>

**Output**:
```
10000
<class 'int'>
```

**Explanation**:  
The reason is that underscores (`_`) are ignored in numbers, which can be used in Python for improving readability of numbers.
</details>

## Question 3: Numeric types
Replace the `???` with the required code with Scientific Notation to display the number 0.0005:

```python
number = ???
print(number)
```

<details><summary>💡 Answer</summary>

**Solution**:
```
number = 5e-4
print(number)
```
</details>

---

## Question 4: Strings
**Multi Selection**
Which of the following statements are valid to defined a string variable?

- `mystring = 'python'`
- `mystring = "python"`
- `mystring = "'python"'`
- `mystring = '"python"'`
- `mystring = ""python""`

<details><summary>💡 Answer</summary>

**Output**:
- ✅ `mystring = 'python'` -> strings can be defined with single quotes `'`
- ✅ `mystring = "python"` -> strings can be defined with double quotes `"`
- ❌ `mystring = "'python"'` -> if you use double quotes to open a string, you must close it with double quotes too
- ✅ `mystring = '"python"'` -> In this case the output string is `"python"`, but it is a valid string definition and no error will raised
- ❌ `mystring = ""python""` -> It raises a Syntax error due to twice double quotes. If you want to display `"python"` you can use the scape sequence `\"`.
</details>

---

## Question 5: Strings
What is the expected output of the following statement? 

```python
print("Price: $" + str(99.9))?
```

<details><summary>💡 Answer</summary>

**Output**:
`Price: $99.9`

**Explanation**:
The addition operator (`+`) can be used for string concatenation. Keep in mind that `str()` is used here for casting the float value into a string.
</details>

---

## Question 6: Boolean types 
What is the expected output of the following statement? 

```python
print(bool("0"))?
```

<details><summary>💡 Answer</summary>

**Output**:
`True`

**Explanation**:
A non-empty string is truthy.
</details>

---

## Question 7: Type Conversion with int()  
```python
print(int(3.9))
```

<details><summary>💡 Answer</summary>

**Output**: `3`

**Explanation**
`int()` truncates the decimal value, does not round it.
</details>

---

## Question 8: Numeric types and casting
What is the expected output of the following statement? 

```python
print(int(2.9) + float("3"))?
```

<details><summary>💡 Answer</summary>

**Output**:
`2 + 3.0 = 5.0` (float).

**Explanation**:
What is happening here is **float Dominance**, that is, if any operand is float, the result is float. Besides, `int()` casting always floot de value `int(2.9)=2`.

</details>

---

## Question 9: Integer vs Float Comparison  
```python
print(3 == 3.0)
```

<details><summary>💡 Answer</summary>

**Output**
```
True
```

**Explanation**:
Python compare the values correctly even the types are different `int` vs `float`.
</details>

---

## Question 10: Scientific Notation
**Multi Selection**
Which of the following statement is the correct way to express a scientific notation?

- `print(3e8)`
- `print(3E8)`
- `print(3exp8)`

<details><summary>💡 Answer</summary>

```python
print(3e8)
```

</details>

---

## Question 11: String Escape Sequences  
**Multi Selection**  
Which are used for newline and tab?

- `\n`
- `\t`
- `\`
- `\r`

<details><summary>💡 Answer</summary>

- ✅ `\n` → newline  
- ✅ `\t` → tab  
- ❌ `\` → backslash  
- ❌ `\r` → carriage return  
</details>

---

## Question 12: Multiline String Output
What is the expected output of the following code snippet?

```python
print("Hello\\nWorld\\t!")
```

<details><summary>💡 Answer</summary>

**Output**:
```
Hello
World	!
```
**Explanation**:
`\\n` = newline, `\\t` = tab
</details>

---

## Question 13: Boolean Arithmetic
```python
print(True + 5)
```

<details><summary>💡 Answer</summary>

**Output**:
```
6
```

**Explanation**:
`True` is equivalent to `1` in numeric operations.
</details>

---

## Question 14: Boolean Conversion  
```python
print(bool(""))
```

<details><summary>💡 Answer</summary>

**Output**:
```
False
```

**Explanation**:
Empty strings are falsy.
</details>

---

## Question 15: Boolean type
**Multi Selection**  
Which are false?

- `0`  
- `None`  
- `[]`  
- `"False"`

<details><summary>💡 Answer</summary>

**Solution**:
- ✅ `0`  
- ✅ `None`  
- ✅ `[]`  
- ❌ `"False"` → Non-empty string → truthy

</details>

---

## Question 16: Type Conversion Functions  
**Multi Selection**  
Which functions are used for explicit conversion?

- `int()`
- `float()`  
- `string()`  
- `boolean()`

<details><summary>💡 Answer</summary>

**Solution**:
- ✅ `int()`
- ✅ `float()`  
- ❌ `string()` → The correct conversion to string is `str()`
- ❌ `boolean()` → The correct conversion to boolean is `bool()`

</details>

---

## Question 17: Implicit Type Conversion  
```python
print(3 + 2.5)
```

<details><summary>💡 Answer</summary>

**Output**:
```
5.5
```

**Explication**:
`int` + `float` → `float`
</details>

---

## Question 18: Float Dominance  
**Multi Selection**  
Which of the following statements are true?

- Mixing `int` and `float` results in `float`  
- `/` with `int` values result in `float`
- `//` with `int` values result in `int`  

<details><summary>💡 Answer</summary>

**Solution**:
- ✅ Mixing `int` and `float` results in `float`   
- ❌ `/` with `int` values result in `float` → the result is a `int`
- ✅ `//` with `int` values result in `int`
</details>

---

## Question 19: String to Float  
```python
print(float("3.14"))
```

<details><summary>💡 Answer</summary>

**Output**:
```
3.14
```

**Explanation**:
String is converted to float.
</details>

---

## Question 20: Float Precision Pitfall  
```python
print(0.1 + 0.2 == 0.3)
```

<details><summary>💡 Answer</summary>

**Output**
```
False
```

**Explanation**
Floating point arithmetic ≠ precise.
</details>

---

## Question 21: Comparing Floats  
**Multi Selection**  
Which are the best practices when comparing `float` values?

- Round before compare  
- Use `==` directly  
- Use `math.isclose()`  
- Convert to `int` before comparing  

<details><summary>💡 Answer</summary>

**Solution**:
- ✅ Round before compare  
- ❌ Use `==` directly → As shown in previous question, it can deal into `False` due to precision mismatch
- ✅ Use `math.isclose()`  
- ❌ Convert to `int` before comparing → It would truncated the value missing the decimal part
</details>

---