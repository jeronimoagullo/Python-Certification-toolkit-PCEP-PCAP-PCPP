# Lists
✏️ Covered topics in this section:
- Indexing & Slicing
- List Methods (append(), insert(), pop(), etc.)
- Iteration & List Comprehensions
- Multi-dimensional Lists
- Common Pitfalls

---

**Lists**, **tuples** and **dictionaries** are sequences in Python, that is, they can be sequenctially examined (by `for` loop for example). Since they are quite important, we will cover each of them in a separate section.

Another important concept that you should know before going further is the **mutability**. The data in Python can be mutable or immutable depending on the possibility to modify its values. `lists` and `dictionaries` are mutable while `tuples` are inmutables.

## 🧠 1. List Basics
Lists are variable with multiple values, they are defined with sqared brackets:

### **Definition & Creation**
```python
empty = []  # empty list
names = ["Pedro", "Juan", "Jose"]
mixed = [1, "two", 3.0, True]  # Valid but not recommended
```

**Golden Rule**: While lists can hold mixed types, consistent data types improve readability and usability.

---

## 📜 2. Indexing & Slicing
### **Access Elements**
```python
fruits = ["apple", "banana", "orange"]
print(fruits[0])   # apple
print(fruits[-1])  # orange (last element)
```

### **Slicing Rules**
Indexes start by **0** and can use negative values to start from the end. Thus, the value `array[-1]` is the latest value of the list.

```python
nums = [5, 6, 9, 4, 10]
print(nums[0])    # 5
print(nums[3])    # 4
print(nums[-2])   # 4
```

Lists can be indexed to get a sublist using the colon `[:]`. The first value is inclusive and the second exclusive:

```python
nums = [5, 6, 9, 4, 10]
print(nums[1:3])    # [6, 9] (index 1-2)
print(nums[:2])     # [5, 6] (start to index 1)
print(nums[::2])    # [5, 9, 10] (every 2nd element)
print(nums[-3:-1])  # [9, 10] (index -3 to -2)
```

**Key Limitation**: The indices in a slice must be provided from lower (leftmost) to higher (rightmost).

```python
# Invalid slice (start > end)
print(nums[3:1])    # [] is an empty list
```

---

## 🛠️ 3. List Methods
### **Add Elements**
Add values with:
- **append** method: `array.append(8)`, which add the value of `8` to the end of list.
- **insert** method: `array.insert(3, 10)`, which insert the value of `10` to the 3rd position, moving the rest of values to the right.

```python
prices = [4.99]
prices.append(9.99)        # [4.99, 9.99]
prices.insert(1, 5.99)     # [4.99, 5.99, 9.99]
```

### **Remove Elements**
`del` is a keyword in python that is used to elimiate variables, it is not just a method of list. However, we can use it to delete elements squeezing the other values to the corresponding order.

For example, deleting the 2nd index of array `array = [5 7 3 1]` with `del array[2]`. Thus, the new array values are `[5 7 1]`.

Other methods that can be used are:
- `pop()` to remove the latest element of the list and returns its value
- `remove` to remove the latest match of a certain value.

```python
inventory = ["sword", "shield", "magic", "shield", "potion"]
del inventory[0]           # ["shield", "magic", "shield", "potion"]
popped = inventory.pop()   # popped = "potion" (now list is ["shield", "magic", "shield"])
inventory.remove("shield") # ["shield", "magic"]
inventory.remove("shield") # ["magic"]
```

### **Sorting & Reordering Methods**
1. **`sort()`** - In-place sorting (modifies original list):
   ```python
   numbers = [3, 1, 4, 2]
   numbers.sort()            # [1, 2, 3, 4]
   numbers.sort(reverse=True) # [4, 3, 2, 1]

   fruits = ["banana", "Apple", "cherry"]
   fruits.sort()           # ["Apple", "banana", "cherry"] (case-sensitive!)
   ```

2. **`reverse()`** - Reverses order (not the same as `sort(reverse=True)`!):
   ```python
   nums = [1, 3, 2, 4]
   nums.reverse()          # [4, 2, 3, 1] (original order flipped)
   nums.sort(reverse=True) # [4, 3, 2, 1] (full decending sort)
   ```

3. **`sorted()`** - Returns new sorted list (original unchanged):
   ```python
   prices = [4.99, 2.99, 5.49]
   ascending = sorted(prices)      # [2.99, 4.99, 5.49]
   descending = sorted(prices, reverse=True)
   print(prices)                   # Original intact: [4.99, 2.99, 5.49]
   ```

**Key Differences**:
- `sort()` vs `sorted()`: One modifies, the other creates new list
- `reverse()` vs `sort(reverse=True)`:
  - `reverse()` just flips current order
  - `sort(reverse=True)` does full descending sort

---

## 🔢 4. Iteration Techniques
We can use the `in` keyword for iterating over a list

### **Basic Loop**
```python
for fruit in ["apple", "banana", "orange"]:
    print(f"I love {fruit}")
```

### **With Index (enumerate)**
```python
for idx, color in enumerate(["red", "green", "blue"]):
    print(f"Color {idx}: {color}")
```

Output:
```
Color 0: red
Color 1: green
Color 2: blue
```

---

## 📝 5. List Operations
### **Check Presence**
```python
tools = ["hammer", "screwdriver", "wrench"]
print("awl" in tools)     # False
print("wrench" not in tools) # False
```

### **Copy a list**
If we copy directly the array `new_array = array`, we copy only the **pointer**. Thus, if we modify the original `array`, the `old_array` is modified too.

If we want to copy the content of a list, We can copy the whole list to a new list variable with **slicing**

```python
original = [1, 2, 3]
shallow_copy = original[:]
deep_copy = [item for item in original]
```


#### **1. Shallow Copy (Reference Copy) - The Wrong Way**
When you assign a list to a new variable, both variables point to the same list in memory:
```python
original = [1, 2, 3]
copy = original  # Both variables reference the SAME list

original.append(4)
print(copy)  # Output: [1, 2, 3, 4] (unintended change!)
```

#### **2. Proper List Copying Methods**

**Method 1: Slicing [:]**
```python
original = [1, 2, 3]
shallow_copy = original[:]  # Creates new list with same elements

original.append(4)
print(shallow_copy)  # Output: [1, 2, 3] (unchanged)
```

**Method 2: list.copy()**
```python
shallow_copy = original.copy()  # Same effect as slicing
```

---

## 6. List Comprehensions
List comprehension is a great way to create a new array based on another or from a range/iteration basis.

the syntax is:
```python
newlist = [expression for item in iterable if condition == True]
```

For example, the following snippet creates an array with numbers from 1 to 100 except those multiples of 3:
```python
array = [i for i in range(1, 101) if i % 3 != 0]
```

Other samples:

```python
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

# List without "apple"
newlist = [x for x in fruits if x != "apple"]

# List with upper case
newlist = [x.upper() for x in fruits]

# return the list but with "orange" instead of "banana"
newlist = [x if x != "banana" else "orange" for x in fruits]

# list of a list
table = [[i for i in range(1, 6)] for j in range(4)]
```

---

## ⚡ 7. Multi-dimensional Lists
### **2D List (Matrix)**
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
print(matrix[1][2])  # 6
```

### **3D List**
```python
cube = [
    [[1,2], [3,4]],
    [[5,6], [7,8]]
]
print(cube[0][1][1])  # 4
```

---

## 📚 8. Lists in Functions

Python lists are **passed by object reference**. This means:

1. The function receives a reference to the original list
2. Modifications affect the original list
3. Rebinding the parameter doesn't affect the original

### **Example: Modifying Original List**
```python
def modify_list(lst):
    lst.append(100)  # Directly modifies original

numbers = [1, 2, 3]
modify_list(numbers)
print(numbers)  # Output: [1, 2, 3, 100]
```

### **Example: Reassignment Doesn't Modify Original**
```python
def rebind_list(lst):
    lst = [4, 5, 6]  # Only changes local reference
    print("Inside:", lst)  # [4, 5, 6]

values = [1, 2, 3]
rebind_list(values)
print("Outside:", values)  # Still [1, 2, 3]
```

**Golden Rules**
\```
| Operation          | Affects Original? |
|--------------------|-------------------|
| append/remove/clear| ✅ Yes           |
| += assignment      | ✅ Yes           |
| = reassignment     | ❌ No            |
| slicing [:]        | ❌ No            |
\```

---

## 💡 Exam Tips & Pitfalls
1. **Modifying During Iteration**
```python
# Dangerous!
items = [1, 2, 3]
for item in items:
    items.remove(item)  # Unexpected results
```

2. **Shallow Copy Pitfall**
```python
nested = [[1,2], [3,4]]
copy = nested.copy()
copy[0][0] = 99
print(nested)  # [[99,2], [3,4]]
```

3. **Sort vs Sorted Confusion**
```python
nums = [3,1,2]
result = nums.sort()
print(result)  # None (sort() is in-place)
```

4. **List Comprehension Scope**
```python
x = 10
doubled = [x*2 for x in range(3)]
print(x)  # 10 (comprehension has own scope)
```

5. **Accidental Clearing**:
```python
def dangerous_clear(lst):
    lst.clear()  # Destructive operation!

data = [1, 2, 3]
dangerous_clear(data)
print(data)  # Output: []
```

---

🎉 **Congratulations!**
You've completed the **collections 1 - lists** section.
Practice with [lists questions](../Practice_Exams_Questions/06_collections%201%20-%20lists.md) next!