# Data Types & Variables

✏️ Covered topics in this section:
- Variables (rules, naming conventions)
- Numetric types (int, float, bases)
- Strings (str), escape sequences, multiline strings
- Booleans (True/False)
- Type conversion (int(), str(), float())

## 📛 1. Variable Naming Rules
- ✅ **Valid Names**:
  - Start with letter/`_`, never with a number → `age`, `_temp`
  - Contain letters, numbers, `_` → `user2`, `total_sum`
  - Case-sensitive → `Var ≠ var`
  - **Allowed but Not Recommended**: Unicode chars (`Adiós_Señora`, `переменная`)

- ❌ **Invalid Names**:
  - Keywords (`if`, `for`, `while`)
  - Start with number → `3rd_user`

---

## 🔢 2. Numeric Types
There are two numeric types: integers (`int`) and float (`float`). Even they are different types, you can compare their values:

```python
3 == 3.0 # True
```

### **Bases**
- Decimal: Any number by default.
- Binary: `0b1010` (10 in decimal)
- Hex: `0x1F` (31)
- Octal: `0o777` (511) *(Note: Older Python versions use `0c777`)*

### **Readability of large numbers**
To improve readability of large numbers we can use two methods:
- Use `_`, which doesn't modify the number value -> `1_000_000` = `1000000`.
- Scientific Notation -> `3e8` = `300000000.0`.

---

## 📜 3. Strings(`str`)
Strings are variables that store text. They are defined by simple quotes (`' `) or double quotes (`"`).

### Escape Sequences:
- `\n` → Newline
- `\t` → Tab
- `\\` → Backslash

```python
print("Hello\nWorld\t!")
# Output:
# Hello
# World   !
```

### **Quoted text**
It is possible to use quotes (`"`) within a string. There are two alternatives:
- Use `' '` for the whole string definition and then `"` for the quoted fragment.
- Use the scape sequence `\"` for the quoted fragment.
  
```python
print('I said "Python!"')       # Single quotes for double inside
print("She said \"Awesome\"")   # Escape with \
```

### Multi-line strings
It is possible to create multi-line strings using three quotes (`'''` or `"""`):

```python
my_multiline = """I can create a really large string
                over
                different lines"""
```

### Concatenation
The operators `+` and `*` have a special behaviour when using with strings:
- Concatenate (`+`): Add one string to another, always from left to right.
```python
name = "Jero"
country = "Spain"
print("I am " + name + " and I live in " + country)
# output -> I am Jero and I live in Spain
```

- Replication (`*`): Using with a string and a number higher than 0, the string is replicated as many times as the number (otherwise the result is an empty string):
```python
print("+" * 5)  # +++++
print("+" * -1) # Nothing is display. It is an empty string
```

## 🎲 4. Booleans (True/False)
Boolean variables are logic values with can be `True` or `False`, they will be use to compare values, check conditions, etc.

### Key Rules
`True = 1` and `False = 0` in numeric contexts:

```python
print(True + 5)   # 6
print(False * 3)  # 0
```

### Truthy/Falsy Values:
- **Falsy**: 0, "", None, [], {}, ()
- **Truthy**: Any non-zero/falsy value.

```python
print(bool(""))    # False
print(bool("Hi"))  # True
```

## 🔄 5. Type Conversion
**Explicit Conversion**
- **int()**: Converts to integer (truncates floats):

```python
print(int(3.9))    # 3 (not rounded!)
print(int("100"))  # 100
```

- **float()**: Converts to float:
```python
print(float(5))    # 5.0
print(float("3.14"))  # 3.14
```

- **str()**: Converts to string:
```python
print(str(True) + " test")  # "True test"
```

- **bool()**: Converts to boolean:
```python
print(bool("python")) # True. All non-empty strings are evaluated as True
```

**Golden Rule**: **Float Dominance**. If any operand is float, result is float:
```python
print(3 + 2.5)  # 5.5 (float)
```

## 💡 6. Exam Tips & Pitfalls
1. **Boolean Values in numeric context:**
   - `True == 1` → **True** (True is evaluated as 1).
   - `False == 0` → **True** (False is evaluated as 0)
   - `True == 5` -> **False**, however `bool(5)` -> **True**
``` python
print(True + False)  # Output: 1
```

2. **Float Precision:** Specially in comparisons
   - `0.1 + 0.2 == 0.3` → **False** (use rounding for comparisons).

3. **Float Dominance**: If any operand is float, result is float
```python
print(3 + 2.5)  # 5.5 (float)
```

4. **Replication of strings by a negative number**: The result of the replication of a string by a negative number is an empty string:
```python
print("hi!" * -5) # Nothing is display. It is an empty string
```

5. **Concatenation of string and a number**: IT is not possible to concatenate a number directly to a string. Use the `str()` casting:

```python
print("python" + 3) # It will raise and error
print("python" + str(3)) # output: python3
```

---

🎉 **Congratulation!!**

You have completed the section **data types and variables**, now you can go to the [Data types and variable questions clicking here](../Practice_Exams_Questions/02_data_types_variables_q.md).