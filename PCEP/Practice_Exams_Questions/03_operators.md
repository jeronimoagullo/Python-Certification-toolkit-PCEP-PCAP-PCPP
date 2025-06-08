# Operators practice questions

✏️ Covered topics in this section:

- Arithmetic (+, -, **, /, //, %)
- Comparison (==, >, <=, !=)
- Logical (and, or, not)
- Assignment (=, +=, *=)
- Operator precedence

## 1. What is the expected output of the following statement?

```py
print(2 ** 3 ** 0)
```
<details><summary>💡 Answer</summary>

**Output**:
The answer is `2`.

**Explanation:**
The reason is that exponent operations have Right-to-left precedence → `3**0 = 1 → 2**1 = 2`
</details>

## 2. What is the expected output of the following statement?

```py
print(15 % 4 + 2 / 1)
```

<details><summary>💡 Answer</summary>

**Output**:
The answer is `3 + 2.0 = 5.0`.

**Explanation:**
Module and division operations have precedence over additions.
</details>

## 3. What operator makes that the division of 8 by 3 returns a float result?

<details><summary>💡 Answer</summary>

Trick question! `//` returns int, use `/` for float 
</details>


## 4. What is the expected output of the following statement? 
```python  
print(4 / 2)  
print(type(4 // 2.0))  
```  
<details>
<summary>📝 Click to reveal solution</summary>  

**Output**:  
```python
2.0  
<class 'float'>  
```  
**Explanation**:  
- `4 / 2` returns a float (`2.0`).  
- `4 // 2.0` even it is integer deivison. The float contagion occurs due to `2.0` → result is `2.0` (float).  
</details>


## 5. What is the expected output of the following statement? 
```python
print(not (True or False and not True))?
```

<details><summary>💡 Answer</summary>


**Output**:
`False` 


**Explanation**: The logic statements are evaluated in order: `not`, `and` and finaly `or`. Thus, step by step:
- Inner `not True` → `False` 
- `False and False` → `False` 
- `True or False` → `True` 
- `not True` → `False`
 </details>

## 6. What is the expected output of the following statement? 
```python
print(5 > 3 and 2 == 2.0)
```

<details><summary>💡 Answer</summary>

**Output**: `True`

**Explanation**: `5>3` is `True` as well as the evaluation of `2==2.0` since types are ignored in `==` for numbers. 
</details>

## 7. What is the expected output of the following statement? 

```python
x = 1
x = x == x
print(x)
```

<details><summary>💡 Answer</summary>


**Output**:
```
True
```

**Explanation**: The evaluation of `x==x` is obviosly `True`, which is later assinged to variable `x`.
 </details>

---

## 8. What is the expected output of the following statement?
```python
print(7 // 3 + 7 % 3)
```
<details><summary>💡 Answer</summary>

**Output:**
```
3.0
```

**Explanation:**
`7 // 3 = 2` (integer division), `7 % 3 = 1` (remainder), `2 + 1.0 = 3.0`. Since the result of 7%3 is a float, the final result is also a float.
</details>

---

## 9. What is the result of this comparison?
```python
print(3 * 2 == 6 and 4 / 2 == 2)
```
<details><summary>💡 Answer</summary>

**Output:**
True

**Explanation:**
Arithmetic operations are evaluated before the logical operations. Besides, since both conditions are True, the result is True.
</details>

---

## 10. What is the expected output of the following statement?
```python
x = 2
y = 3
print(x ** y)
```
<details><summary>💡 Answer</summary>

**Output:**
8

**Explanation:**
2 ** 3 = 8 (exponentiation).
</details>

---

## 11. What is the expected output of the following statement?
```python
print(10 / 3)
print(10 // 3)
```
<details><summary>💡 Answer</summary>

**Output:**
```
3.3333333333333335
3
```

**Explanation:**
`/` gives float division, `//` gives integer division.
</details>

---

## 12. Which expression evaluates to True?
- a) `5 == 5.0`
- b) `5 is 5.0`
- c) `5 != 5`

<details><summary>💡 Answer</summary>

**Output:**
- a) True (== compares value, int and float with same value are equal)
- b) False (is compares identity, not value)
- c) False (5 equals 5)
</details>

---

## 13. What is the expected output of the following statement?
```python
x = 5
y = 2
x += y
print(x)
```
<details><summary>💡 Answer</summary>

**Output:**
7

**Explanation:**
x += y is equivalent to x = x + y.
</details>

---

## 14. What is the expected output of the following statement?
```python
print(2 * 3 ** 2)
```
<details><summary>💡 Answer</summary>

**Output:**
18

**Explanation:**
Exponentiation has higher precedence: 3 ** 2 = 9, then 2 * 9 = 18.
</details>

---

## 15. Which of the following is NOT a valid assignment operator in Python?
- a) `=`
- b) `+=`
- c) `==`

<details><summary>💡 Answer</summary>

**Output:**
c) `==` is a comparison operator, not assignment.
</details>

---

## 16. What is the expected output of the following statement?
```python
print(4 > 2 and 2 > 4)
```
<details><summary>💡 Answer</summary>

**Output:**
False

**Explanation:**
First is True, second is False, so the result is False.
</details>

---

## 17. What is the expected output of the following statement?
```python
print(10 % 4 * 2)
```
<details><summary>💡 Answer</summary>

**Output:**
4

**Explanation:**
10 % 4 = 2, 2 * 2 = 4.
</details>

---

## 18. What is the expected output of the following statement?
```python
print(1 == True)
print(0 == False)
```
<details><summary>💡 Answer</summary>

**Output:**
```
True
True
```

**Explanation:**
In Python, True is 1 and False is 0.
</details>

---

## 19. Which statement is evaluated as `True`?
- a) `2 ** 3 ** 2 == 512`
- b) `2 ** (3 ** 2) == 512`
- c) `(2 ** 3) ** 2 == 64`
- d) `All of the above`

<details><summary>💡 Answer</summary>

**Output:**
d) All of the above

**Explanation:**
```
2 ** 3 ** 2 = 2 ** 9 = 512
(2 ** 3) ** 2 = 8 ** 2 = 64
```
</details>

---

## 20. What is the expected output of the following statement?
```python
x = 10
y = 3
z = x // y + x % y * 2
print(z)
```
<details><summary>💡 Answer</summary>

**Output:**
5

**Explanation:**
x // y = 3, x % y = 1, 1 * 2 = 2, 3 + 2 = 5.
</details>

---
