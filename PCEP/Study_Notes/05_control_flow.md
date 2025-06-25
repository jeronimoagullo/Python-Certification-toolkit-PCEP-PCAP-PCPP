# Control Flow  
✏️ Covered topics in this section:  
- Comparison/Logical Operators  
- if/elif/else statements  
- while/for loops  
- break/continue/pass  
- Loop else clauses  

---

## 🔄 1. Comparison Operators
The equality operators have the lower priority. Thus, the arithmetic operators are evaluated always before:
 
| Priority | Operators          | Type      |  
|----------|--------------------|-----------|  
| 1        | +, -              | Unary     |  
| 2        | **                | Exponent  |  
| 3        | *, /, //, %       | Multiplicative |  
| 4        | +, -              | Additive  |  
| **5**    | **<, <=, >, >=**  | **Comparison**|  
| **6**    | **==, !=**        | **Equality**|  

**Samples**:  
```python
print(3 + 2 > 4)    # True (5 > 4)  
print(1 == 1.0)     # True (value equality)  
print(1.2 > 1)      # True (1.2 > 1.0)  
```

---

## 🚦 2. Conditional Statements  
### **if-elif-else Structure**
We use `if` statement for conditionals. Everything within the indentation of a `if` statement will be executed if the condition is `True`.

```python
age = 18  
if age < 13:  
    print("Child")  
elif 13 <= age < 18:  
    print("Teen")  
else:  
    print("Adult")
print("sample ended")
```

Output:
```
Adult
sample ended
```

**Golden rule**: The `elif` and `else` statements are optional.


### **Nested Conditionals**
We can nest as many conditionals as desired:

```python
num = 15  
if num > 10:  
    if num % 2 == 0:  
        print("Even >10")  
    else:  
        print("Odd >10")  # This executes  
```

---

## 🔁 3. Loops
Loops are statements to iterate and execute a code snippets many times.

### **while Loop**
The content of a while loop will be executed continously until the condition os not met.

```python
count = 3  
while count > 0:  
    print(count)  # 3, 2, 1  
    count -= 1  
```

**Golden rule**: Don't forget to update the variable of the `while` condition. Otherwise, it will be evaluated as `True` always, executing the code forever, resulting in what is known as `intinitive loop`.

### **for Loop with range()**
The `range(start, stop, step)` function can be used to iterate a certain number of times indicating the starting and ending number as well as the step to increment the values between them. The `step` parameter is optional and it defaults to 1.

```python
# range(start, stop, step)  
for i in range(2, 10, 2):  
    print(i)  # 2, 4, 6, 8  

# Reverse count  
for i in range(5, 0, -1):  
    print(i)  # 5, 4, 3, 2, 1  
```

### **Loop Control Keywords**
- **pass**: It is used when a loop is empty (maybe during development) since an empty loop would result in an error:
```python
for i in range(1,10):
        # TODO: calculate the sum of numbers from 1 to 10
        pass
```
- **continue**: the execution jumps to the end of loop.
- **break**: the execution exits the loop (even if the condition is still met).

```python
# Break/Continue  
for num in range(10):  
    if num == 3:  
        continue  # Skip 3  
    if num == 7:  
        break     # Exit loop  
    print(num)  # 0,1,2,4,5,6  
```

### **Loop else Clause**  
The `else` branch is executed just once, but always, even if the loop body has not be executed.

**Golden rule**: The `else` branch is not executed if we leave the loop with a `break` statement.

```python
for i in range(3):  
    print(i)  
else:  
    print("Loop completed!")  # Executes  

for i in range(5):  
    if i == 3:  
        break  
else:  
    print("This won't execute")  
```

---

## 💡 4. Exam Tips & Pitfalls 
1. **Assignment vs Equality**:  
```python
if x = 5:  # SyntaxError (use == for comparison)  
```

2. **comparison between integers and floats is possible**:
```python
print(1 == 1.0)  # True
print(1.2 < 1)  # False
```

3. **Floating Point Range**:  
```python
# range() only accepts integers  
for i in range(2.5):  # TypeError  
```

4. **Else in Loops**:  
- Only executes if loop completes normally (no break)  

5. **Infinite Loops**:  
```python
while True:  # Needs break condition 
    print("Running...")  
```

🎉 **Congratulations!**
You've completed the **Control Flow** section.
Practice with [control flow questions](../Practice_Exams_Questions/05_control_flow.md) next!
