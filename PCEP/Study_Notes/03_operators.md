# Operators

✏️ Covered topics in this section:

- Arithmetic (+, -, **, /, //, %)
- Comparison (==, >, <=, !=)
- Logical (and, or, not)
- Assignment (=, +=, *=)
- Operator precedence

## ➗ 1. Arithmetic Operators
### **Sum, substraction and multiplication**
```python
  print(4 - 2)   # 2
  print(29 + 3)  # 32
  print(3 * 4)   # 12
```

### **Division**
- **Float division** (`/`) → Always returns float:  
  ```python  
  print(4 / 2)   # 2.0 (float)  
  print(5 / 2)   # 2.5 (float)
  ```
- **Integer division** (`//`) → returns int/float based on operands:
  ```python
  print(7 // 2)    # 3 (int)
  print(7.0 // 2)  # 3.0 (float)
  ```

- **Modulus** (`%`) → Returns remainder:
  ```python
  print(10 % 3)  # 1 (10 - 3*3 = 1)
  ```

### **Exponent (`**`)**
- Right-to-left precedence:
```python
print(2 ** 3 ** 2)  # 512 (3**2=9 → 2**9)
```

## 🔀 2. Logical Operators  
### **`and`, `or`, `not`**  
- **`and`**: `True` only if **both operands are true**.  
- **`or`**: `True` if **at least one operand is true**.  
- **`not`**: Inverts the boolean value.

The evaluation order is firstly `not`, then `and` and finally `or`. In case that two statements has the same priority, they will be evaluated from **left to right**.

### **Truth Tables**  
| `A`     | `B`     | `A and B` | `A or B` | `not A` |  
|---------|---------|-----------|----------|---------|  
| `True`  | `True`  | `True`    | `True`   | `False` |  
| `True`  | `False` | `False`   | `True`   | `False` |  
| `False` | `True`  | `False`   | `True`   | `True`  |  
| `False` | `False` | `False`   | `False`  | `True`  |  

---

### **Examples**  
```python  
# AND  
print(True and False)   # False  
print(5 > 3 and 2 == 2) # True  

# OR  
print(False or True)    # True  
print(10 < 5 or 3 != 3) # False  

# NOT  
print(not True)         # False  
print(not 0)            # True (0 is falsy)
```


## 🔄 3. Assignment Shortcuts
Works for all binary operators: -=, *=, /=, etc.

```python
x += 5 # x = x + 5
```

## 🎯 4. Order of Operations
1. `()`
2. `**`
3. `*, /, //, %`
4. `+, -`

Example:
```python
print(3 + 4 * 2)   # 11
print((3 + 4) * 2) # 14
```

## 🔨 5. Bitwise Operators

### **Operators & Usage**
Bitwise operators work directly on binary representations of integers:
- `&` (AND): Compares each bit - 1 only if both bits are 1  
  ```python
  5 & 3         # (1)since 0101 & 0011 = 0001 (1)
  ```
- `|` (OR): 1 if either bit is 1  
  ```python
  ```5 | 3      # (7) since 0101 | 0011 = 0111 (7)
- `~` (NOT): Flips all bits (including sign bit)  
  ```python
  ~5 → -6 (in Two's complement)*
  ```
- `^` (XOR): 1 if bits are different  
  ```python
  5 ^ 3         # (6) 0101 ^ 0011 = 0110 (6)
  ```
- `<<` (Left Shift): Adds n zeros at the end → ×2ⁿ  
  ```python
  8 << 1        # (16) 1000 → 10000 (16)
  ```
- `>>` (Right Shift): Removes n bits from end → ÷2ⁿ  
  ```python
  8 >> 1        # (4) 1000 → 0100 (4)
  ```

### **Truth Table (1 = True, 0 = False)**

| A | B | A & B | A \| B | A ^ B |
|---|-----|-------|--------|-------|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |


### Differences between logical `and` / `or` and bit `&` / `|`
```
# Logical vs Bitwise
print(True and False)   # False (boolean)
print(5 and 3)          # True (boolean)
print(5 & 3)            # 1 (bitwise: 101 & 011 = 001)
```

### Negation and two-complement
The bit negation of a natural number is always a negative number since it results in a **two's complement**. All the values are stored in computers in 32 or 64 bits, that is, preceded by several zeros. All those zeros are converted to ones, which result in a negative number.

```python
print(~5)             # -6 (Two's complement: ~x = -x-1)
```

**Golden Rule:**: The bit negation of any natural number is `~x = -x - 1`.


### **Bitmask Operations**
We can use bitmask operations to modify the value of specific bits of a variable:

```python
flags = 0b1101  # Current flags (bits 3,2,1,0)
mask = 0b0100   # Bit we want to modify

# Toggle bit 2 (XOR)
flags ^= mask   # 0b1001 (bit 2 flipped)

# Check if bit 2 is set
if flags & mask:
    print("Bit 2 is ON")ç

# Set multiple bits
flags |= 0b1010 # Sets bits 3 and 1

# Reset a bit using a mask
flags &= ~mask
```
---

## ✨ 6. Operator Precedence

| Priority | Operators         | Description        |
|----------|-------------------|--------------------|
| 1        | ~ + -             | Unary              |
| 2        | **                | Exponent           |
| 3        | * / // %          | Multiplicative     |
| 4        | + -               | Additive           |
| 5        | << >>             | Bit shifts         |
| 6        | < <= > >=         | Comparison         |
| 7        | == !=             | Equality           |
| 8        | &                 | Bitwise AND        |
| 9        | \|                | Bitwise OR         |
| 10       | = += -= *= /= etc | Assignment         |


**Golden Rule**: Use () to override precedence when unsure.


## 💡 7. Exam Traps
1. **`/` vs `//`:**
```python
print(10 / 3)  # 3.333...
print(10 // 3) # 3
```

2. **Float contagion**:
```python
print(5 // 2.0)  # 2.0 (not 2)
print(3 + 2.0)  # 5.0 (not 5)
```

3. **The result of a normal division is always a float**: Even if the numbers are `int`:
```python
print(1 / 1)     # 1.0 (not 1)
```

4. **Boolean math**:
```python
print(True * 3)   # 3
print(False + 5)  # 5
```

5. **Short-Circuit Evaluation**:

- `and`: Stops at the first False.
- `or`: Stops at the first True.

```python
print(False and (5/0))  # No error (second operand not evaluated)
```

6. **Truthy/Falsy Values:**

- **Falsy**: 0, "", [], None, False.
- **Truthy**: Everything else.

```python
print(not "hello")  # False (non-empty string is truthy)
```

7. **Negation of a natural number is a negative number**:

```python
x = 4
print(~x)       # -5
```

The reason is that (assuming 32-bit coding) the 4 is coded as `00000000 00000000 00000000 00000100` in binary form. If we do the negation of bits, it represents `11111111 11111111 11111111 11111011`, which is the **two's complement of `-5`**. You can calculate the two's complement inverting bits and sum 1. Other formula for any natural number is `~x = -x - 1`

---

🎉 **Congratulation!!**

You have completed the section **operators**, now you can go to the [operators questions clicking here](../Practice_Exams_Questions/03_operators.md).