# Control Flow  
✏️ Covered topics in this section:  
- Comparison/Logical Operators  
- if/elif/else statements  
- while/for loops  
- break/continue/pass  
- Loop else clauses  

---

## 1. What is the expected output of the following statement?
```python
x = 7
y = 10
if x > y:
    print("x is greater")
elif x == y:
    print("equal")
else:
    print("y is greater")
```
<details><summary>💡 Answer</summary>

**Output**:
`y` is greater

**Explanation**: The else branch is executed because `x < y`, that is, the other two conditions are not met.
</details>

## 2. What is the expected output of the following statement?
```python
num = 5
if num % 2 == 0:
    print("Even")
else:
    print("Odd")
```
<details><summary>💡 Answer</summary>

**Output**:
Odd

**Explanation**: `5 % 2 != 0`, so the else branch is executed.
</details>

## 3. What is the expected output of the following statement?
```python
x = 3
y = 3
if x:
    if y:
        print("Both nonzero")
    else:
        print("y is zero")
else:
    print("x is zero")
```
<details><summary>💡 Answer</summary>

**Output**:
Both nonzero

**Explanation**: Both `x` and `y` are nonzero, so the innermost `if` is executed.
</details>

## 4. What is the expected output of the following statement?
```python
for i in range(2, 7, 2):
    print(i, end=" ")
```
<details><summary>💡 Answer</summary>

**Output**:
`2 4 6`

**Explanation**: `range(2,7,2)` generates 2, 4, 6.
</details>

## 5. What is the expected output of the following statement?
```python
for i in range(3, 0, -1):
    print(i)
```
<details><summary>💡 Answer</summary>

**Output**:
```
3
2
1
```

**Explanation**: Counts down from 3 to 1.
</details>

## 6. What is the expected output of the following statement?
```python
x = 0
while x < 3:
    print(x)
    x += 1
else:
    print("Done")
```
<details><summary>💡 Answer</summary>

**Output**:
```
0
1
2
Done
```

**Explanation**: The `else` clause runs after the while loop ends.
</details>

## 7. What is the expected output of the following statement?
```python
for ch in "abc":
    if ch == "b":
        continue
    print(ch)
```
<details><summary>💡 Answer</summary>

**Output**:
```
a
c
```

**Explanation**: The `continue` skips printing for `b`.
</details>

## 8. What is the expected output of the following statement?
```python
n = 0
while n < 3:
    print(n)
    if n == 1:
        break
    n += 1
else:
    print("Finished")
```
<details><summary>💡 Answer</summary>

**Output**:
```
0
1
```

**Explanation**: The `else` clause does not execute because the loop was terminated by `break`.
</details>

## 9. What is the expected output of the following statement?
```python
for i in range(2):
    pass
print("Done")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Done
```

**Explanation**: The pass statement does nothing. The loop runs but does not print anything.
</details>

## 10. Multi selection
Which of the following will result in an infinite loop?
- while True: pass
- while False: print("Hello")
- while 1 == 1: print("Loop")
<details><summary>💡 Answer</summary>

**Output:**
- ✅ while True: pass — Infinite loop
- ❌ while False: print("Hello") — Never executes
- ✅ while 1 == 1: print("Loop") — Infinite loop
</details>

## 11. What is the expected output of the following statement?
```python
for i in range(1, 10, 3):
    print(i)
```
<details><summary>💡 Answer</summary>

**Output**:
```
1
4
7
```

**Explanation**: The range starts at 1, increments by 3, and stops before 10.
</details>

## 12. What is the expected output of the following statement?
```python
x = 2
if x > 1:
    if x < 3:
        print("A")
    else:
        print("B")
else:
    print("C")
```
<details><summary>💡 Answer</summary>

**Output**:
```
A
```

**Explanation**: Both conditions are true, so 'A' is printed.
</details>

## 13. What is the expected output of the following statement?
```python
for i in range(3):
    for j in range(2):
        print(i, j)
```
<details><summary>💡 Answer</summary>

**Output**:
```
0 0
0 1
1 0
1 1
2 0
2 1
```

**Explanation**: Nested for loops iterate over all combinations.
</details>

## 14. What is the expected output of the following statement?
```python
x = 0
while x < 2:
    x += 1
    if x == 2:
        continue
    print(x)
```
<details><summary>💡 Answer</summary>

**Output**:
```
1
```

**Explanation**: When `x` becomes 2, `continue` skips the print.
</details>

## 15. What is the expected output of the following statement?
```python
for i in range(3):
    if i == 1:
        break
    print(i)
```
<details><summary>💡 Answer</summary>

**Output**:
```
0
```

**Explanation**: The loop breaks when `i == 1`.
</details>

## 16. What is the expected output of the following statement?
```python
x = 5
y = 10
if x > 0:
    if y > 0:
        print("Both positive")
    else:
        print("y not positive")
else:
    print("x not positive")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Both positive
```

**Explanation**: Both numbers are positive.
</details>

## 17. What is the expected output of the following statement?
```python
for i in range(2, 8, 2):
    print(i, end="-")
```
<details><summary>💡 Answer</summary>

**Output**:
`2-4-6-`

**Explanation**: Prints numbers from 2 to 6 in steps of 2, separated by dashes.

</details>

## 18. Multi selection
Which statements about the else clause in loops are correct?
- The else block runs only if the loop does not break.
- The else block always runs after the loop.
- The else block is only available in while loops.
<details><summary>💡 Answer</summary>

**Output:**
- ✅ The else block runs only if the loop does not break.
- ❌ The else block always runs after the loop. (Not if loop breaks)
- ❌ The else block is only available in while loops. (It works with for loops too)
</details>

## 19. What is the expected output of the following statement?
```python
for i in range(3):
    print(f"Outer loop: {i}")
    for j in range(3):
        if i == 1 and j == 1:
            break
        if i == 2 and j == 1:
            continue
        print(f"  Inner loop: {j}")
else:
    print("Loop finished without break.")
```
<details><summary>💡 Answer</summary>

**Output**:
```
Outer loop: 0
  Inner loop: 0
  Inner loop: 1
  Inner loop: 2
Outer loop: 1
  Inner loop: 0
Outer loop: 2
  Inner loop: 0
  Inner loop: 2
Loop finished without break.
```

**Explanation**: The `break` statement in the nested loop only terminates the inner loop, not the outer one. The `continue` statement skips the current iteration of the inner loop. Since the outer loop completes all its iterations without being terminated by a `break` statement, its `else` clause is executed.
</details>

## 20. What is the expected output of the following statement?
```python
numbers = [1, 2, 3, 4, 5, 6]
i = 0
while i < len(numbers):
    if numbers[i] % 2 == 0:
        del numbers[i]
    else:
        i += 1
print(numbers)
```
<details><summary>💡 Answer</summary>

**Output**:
`[1, 3, 5]`

**Explanation**: The `while` loop iterates through the list using an index `i`. When an even number is found at `numbers[i]`, it is deleted. Crucially, the index `i` is *not* incremented in this case. This is because after deleting an element, the next element shifts to the current index `i`, and needs to be checked. The index `i` is only incremented when the element is odd. This process correctly removes all even numbers from the list.
</details>
