# Collections: lists, tuples and dictionaries
✏️ Covered topics in this section:  
- **Lists**: indexing, slicing, methods (append(), insert(), pop())
- **Tuples**: immutability, use cases
- **Dictionaries**: keys, values, dict(), keys(), items()


## 1. What is the expected output of the following statement?

```python
a = "A"
b = "B"
c = "C"
d = " "

lst = [a, b, c, d]
lst.sort()

print(lst)
```

<details><summary>💡 Answer</summary>

**Output**:
```
['A', 'B', 'C', ' ']
```

**Explanation**: TODO

</details>

## 2. What is the expected output of the following statement?

```python
list_1 = [1, 2, 3]
list_2 = list_1
list_3 = list_2

del list_1[0]
del list_2[0]

print(list_3)
```

<details><summary>💡 Answer</summary>

**Output**:
```
3
```

**Explanation**: TODO

</details>

## 3. What is the expected output of the following statement?

```python
list_1 = [1, 2, 3]
list_2 = list_1
list_3 = list_2

del list_1[0]
del list_2

print(list_3)
```

<details><summary>💡 Answer</summary>

**Output**:
```
[2, 3]
```

**Explanation**: TODO

</details>

## 4. What is the expected output of the following statement?

```python
list_1 = [1, 2, 3]
list_2 = list_1
list_3 = list_2

del list_1[0]
del list_2[:]

print(list_3)
```

<details><summary>💡 Answer</summary>

**Output**:
```
[]
```

**Explanation**: TODO

</details>

## 5. What is the expected output of the following statement?

```python
list_1 = [1, 2, 3]
list_2 = list_1[:]
list_3 = list_2[:]

del list_1[0]
del list_2[0]

print(list_3)
```

<details><summary>💡 Answer</summary>

**Output**:
```
[1, 2, 3]
```

**Explanation**: TODO

</details>

## 6. What is the expected output of the following statement?

```python
my_list = [[0, 1, 2, 3] for i in range(3)]
print(my_list[3][2])
```

<details><summary>💡 Answer</summary>

**Output**:
```
IndexError: list index out of range
```

**Explanation**: You may have thought on "2". However, `my_list` list contains the values `[[0, 1, 2, 3], [0, 1, 2, 3], [0, 1, 2, 3]]`. That is, the list has a size of 3x4. Consequently, accesing to `[3][2]` is out of range. Otherwise, accesing to `[2][3]` would return "2" since it means the 4th value of the 3rd list.

</details>


## 7. What is the expected output of the following statement?
```python
data = [1, 2, 3]  
data += [4]  
data = data + [5]  
print(len(data))  
```
<details><summary>💡 Answer</summary>

**Output**: 5 (both operations extend the list)

**Explanation**:

</details>  

## 8. What is the expected output of the following statement? 
```python
my_tuple = 1., .25, 10, 3.0, "10"
print(my_tuple)
```

<details><summary>💡 Answer</summary>


**Output**:
```
(1.0, 0.25, 10, 3.0, '10')
```

**Explanation**: A tuple has always parenthesis but you can define their values just separating them by commas. Besides, a tuple can have different variable types like integer, float or strings.
 </details>

## 9. What is the expected output of the following statement? 
```python
ls = [1,2]

for v in range(2):
        ls.insert(-1, ls[v])

print(ls)
```

<details><summary>💡 Answer</summary>


**Output**:
```
[1, 1, 1, 2]
```

**Explanation**: The first argument is the index of the element before which to insert. The method `insert` add the element `ls[v]` before the position `-1`. The sequence of the `for` loop is:

```
v: 0  list: [1, 1, 2]
v: 1  list: [1, 1, 1, 2]
```

 </details>

## 10. Multi selection
What does the method `items()` returns in Python Dictionary?

- The method `items()` returns the lists
- The method `items()` returns the tuples
- The method `items()` returns the keys in a list
- The method `items()` returns the values in a list

<details><summary>💡 Answer</summary>

**Output:**

 - ❌ The method `items()` returns the lists
 - ❌ The method `items()` returns the tuples
 - ❌ The method `items()` returns the keys in a list
 - ✅ The method `items()` returns the values in a list

</details>

## 11. What is the expected output of the following statement? 
```python
list = [False, True, "3", 4, 2]
print(0 in list)
```

<details><summary>💡 Answer</summary>


**Output**:
```
True
```

**Explanation**: The element `0` is equivalent to `False` in a boolean context. The `in` operator checks if the element is in the list. Since `False` is in the list, `0 in list` evaluates to `True`.

</details>

## 12. What is the expected output of the following statement? 
```python
list = [1,2,3,4,5,6,7,8,9]
print(list[::2])
```

<details><summary>💡 Answer</summary>A

**Output**:
```
[1,3,5,7,9]
```

**Explanation**: Slicing with a step of 2 returns every other element starting from the first.

</details>

## 13. What is the expected output of the following statement?
```python
nums = [3, 1, 4, 1, 5, 9, 2]
result = nums.sort()
print(result)
```
<details><summary>💡 Answer</summary>

**Output**:
`None`

**Explanation**: The `sort()` method sorts the list in-place and returns `None`. To get the sorted list, you would need to print `nums` itself after the sort.
</details>

## 14. What is the expected output of the following statement?
```python
numbers = [10, 20, 30, 40, 50]
for number in numbers:
    if number == 30:
        numbers.remove(number)
print(numbers)
```
<details><summary>💡 Answer</summary>

**Output**:
`[10, 20, 40, 50]`

**Explanation**: Modifying a list while iterating over it can lead to unexpected behavior. In this case, removing `30` works as expected, but it's a dangerous practice because it can cause the loop to skip elements.
</details>

## 15. What is the expected output of the following statement?
```python
new_list = [x if x % 2 == 0 else x * 2 for x in range(5)]
print(new_list)
```
<details><summary>💡 Answer</summary>

**Output**:
`[0, 2, 2, 6, 4]`

**Explanation**: This list comprehension keeps even numbers as they are and multiplies odd numbers by 2.
</details>

## 16. What is the expected output of the following statement?
```python
nested_list = [[1, 2], [3, 4]]
shallow_copy = nested_list[:]
shallow_copy[0][0] = 99
print(nested_list)
```
<details><summary>💡 Answer</summary>

**Output**:
`[[99, 2], [3, 4]]`

**Explanation**: Slicing creates a shallow copy. The outer list is new, but the inner lists are references to the original inner lists. Modifying an element of an inner list in the copy also modifies it in the original.
</details>

## 17. What is the expected output of the following statement?
```python
def modify_list(my_list):
    my_list.append(4)
    my_list = [10, 20]

data = [1, 2, 3]
modify_list(data)
print(data)
```
<details><summary>💡 Answer</summary>

**Output**:
`[1, 2, 3, 4]`

**Explanation**: The function first appends `4` to the original list. Then, `my_list = [10, 20]` reassigns the local variable `my_list` to a new list, which does not affect the original `data` list.
</details>

## 18. What is the type of `single`?
```python
single = (1)
```
<details><summary>💡 Answer</summary>

**Output**:
`<class 'int'>`

**Explanation**: To create a single-element tuple, a trailing comma is required: `single = (1,)`. Without the comma, it's just an integer in parentheses.
</details>

## 19. What is the expected output of the following statement?
```python
t = ([1, 2], [3, 4])
t[0][0] = 99
print(t)
```
<details><summary>💡 Answer</summary>

**Output**:
`([99, 2], [3, 4])`

**Explanation**: Tuples are immutable, meaning you cannot change their elements. However, if an element is a mutable object (like a list), you can modify the contents of that mutable object.
</details>

## 20. What is the value of `c`?
```python
a, b, *c = (1, 2, 3, 4, 5)
```
<details><summary>💡 Answer</summary>

**Output**:
`[3, 4, 5]`

**Explanation**: The `*c` syntax in tuple unpacking collects all remaining elements into a list. Thus, `a` is 1 and `b` is 2.
</details>

## 21. Multi selection
Which of the following can be a valid dictionary key?
- `[1, 2]`
- `(1, 2)`
- `{'a': 1}`
- `(1, [2, 3])`
<details><summary>💡 Answer</summary>

**Output:**
- ❌ `[1, 2]` (Lists are mutable)
- ✅ `(1, 2)` (Tuples of immutable elements are hashable)
- ❌ `{'a': 1}` (Dictionaries are mutable)
- ❌ `(1, [2, 3])` (Tuple contains a mutable list)
</details>

## 22. What is the expected output of the following statement?
```python
t1 = (1, 2)
t2 = (3, 4)
print(t1 * 2 + t2)
```
<details><summary>💡 Answer</summary>

**Output**:
`(1, 2, 1, 2, 3, 4)`

**Explanation**: The `*` operator repeats the tuple, and the `+` operator concatenates tuples, creating a new tuple.
</details>

## 23. What is the expected output of the following statement?
```python
t = (5,)
print(type(t))
```
<details><summary>💡 Answer</summary>

**Output**:
`<class 'tuple'>`

**Explanation**: The trailing comma makes this a single-element tuple.
</details>

## 24. What is the expected output of the following statement?
```python
d = {'a': 1, 'b': 2, 'c': 3}
item = d.popitem()
print(item, len(d))
```
<details><summary>💡 Answer</summary>

**Output**:
`('c', 3) 2`

**Explanation**: `popitem()` removes and returns the last inserted key-value pair as a tuple. In Python 3.7+, dictionaries preserve insertion order.
</details>

## 25. What is the expected output of the following statement?
```python
config = {'user': 'admin', 'retries': 3}
print(config.get('password', 'default'))
```
<details><summary>💡 Answer</summary>

**Output**:
`default`

**Explanation**: The `get()` method returns the value for a key if it exists, otherwise it returns the default value provided (in this case, 'default'). It does not raise a `KeyError`.
</details>

## 26. What is the final state of `d1`?
```python
d1 = {'a': 1, 'b': 2}
d2 = {'b': 3, 'c': 4}
d1.update(d2)
```
<details><summary>💡 Answer</summary>

**Output**:
`{'a': 1, 'b': 3, 'c': 4}`

**Explanation**: The `update()` method merges the second dictionary into the first. If a key exists in both, the value from the second dictionary overwrites the first.
</details>

## 27. What is the expected output of the following statement?
```python
d = {'a': 1, 'b': 2, 'a': 3}
print(d)
```
<details><summary>💡 Answer</summary>

**Output**:
`{'a': 3, 'b': 2}`

**Explanation**: When a dictionary is created with duplicate keys, the last value provided for that key is the one that is kept.
</details>

## 28. What is the expected output of the following statement?
```python
keys = ['a', 'b', 'c']
values = [1, 2, 3]
d = dict(zip(keys, values))
print(d)
```
<details><summary>💡 Answer</summary>

**Output**:
`{'a': 1, 'b': 2, 'c': 3}`

**Explanation**: The `zip()` function pairs up elements from two lists, and the `dict()` constructor can then create a dictionary from those pairs.
</details>

## 29. Multi selection
Which of the following are true about dictionaries?
- They are ordered collections.
- They can have duplicate keys.
- They are mutable.
- They can be used as dictionary keys.
<details><summary>💡 Answer</summary>

**Output:**
- ❌ They are ordered collections. (Insertion order is preserved in Python 3.7+, but they are not ordered in the same way as lists.)
- ❌ They can have duplicate keys. (Keys must be unique.)
- ✅ They are mutable.
- ❌ They can be used as dictionary keys. (Dictionaries are mutable and therefore not hashable.)
</details>

## 30. What is the expected output of the following statement?
```python
my_dict = {}
my_dict[(1,2)] = 'a'
my_dict[1,2] = 'b'
print(my_dict)
```
<details><summary>💡 Answer</summary>

**Output**:
`{(1, 2): 'b'}`

**Explanation**: `my_dict[1,2]` is equivalent to `my_dict[(1,2)]`. Both expressions refer to the same tuple key `(1, 2)`. Therefore, the second assignment overwrites the value of the first.
</details>

## 31. Multi selection
What is the only true statement about the following code?
```
nums = [1,2,3]
vals = nums
del vals[:]
```

- `nums` and `vals` have the same length
- `vals` is larger than `nums`
- `nums` is larger then `vals`
- It will raise an error

<details><summary>💡 Answer</summary>

**Output:**

 - ✅ `nums` and `vals` have the same length
 - ❌ `vals` is larger than `nums`
 - ❌ `nums` is larger then `vals`
 - ❌ It will raise an error

**Explanation**: The list pointers are the same. Thus, removing all the elements affect to both at the same time.

  </details>

