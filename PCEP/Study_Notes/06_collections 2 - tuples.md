
# Tuples
✏️ Covered topics in this section:
- Immutability
- use cases
---

# tuples
A `tuple` is an inmutable sequence. Similar to `list`, but whose values cannot be modified once it is defined.

If you try to mofidy a value of a tuple, the error `TypeError: 'tuple' object does not support item assignment` will be raised.

However, it is possible to reassigned the pointer of a tuple:

```python
t1 = (3, 5, 67)
t2 = (67, 3, 2, 1)
t1, t2 = t2, t1
print(t1, t2) # (67, 3, 2, 1) (3, 5, 67)
```

While a `list` is defined between squre brackets `[]`, a `tuple` is defined by parenthesis `()` or just using commas:

```python
my_tuple1 = (1,2,3,4)
my_tuple2 = 1,2,3,4
```
**Golden Rule**: The elements of a tuple can be of any type.

**Golden Rule 2**: The elements of a tuple can be variables, not just literal values.

## Working with tuples
We access to the element as we do with lists, that is, indexing, slicing, etc. As well as we can iterate over it with `for` loop.

The elements of a tuple are accesible like in lists:
```python
print(my_tuple[0])
print(my_tuple[-1])
print(my_tuple[1:])
print(my_tuple[:-2])

for elem in my_tuple:
    print(elem)
```

**Golden Rule**: We cannot edit a tuple value with any method.

We can use the following operators as lists:
- `+` or `*` (Creating a new tuple)
- `len()` to return the number of elements of tuple
- `in` and `not in`

## Convert a list into a tuple and vice versa

To convert a list to a tuple, use the `tuple()` constructor:

```python
my_list = [1, 2, 3]
my_tuple = tuple(my_list)
print(my_tuple)  # (1, 2, 3)
```

To convert a tuple to a list, use the `list()` constructor:

```python
t = (4, 5, 6)
lst = list(t)
print(lst)  # [4, 5, 6]
```

**Golden Rule:** Conversion does not modify the original object; it creates a new one of the target type.

---

## Tuple Use Cases
- **Multiple return values:** Functions can return multiple values packed in a tuple.
- **Immutable data:** Use tuples for data that should not change.
- **Dictionary keys:** Tuples can be used as keys in dictionaries (lists cannot).
- **Sequence unpacking:** Useful for swapping variables or simultaneous assignments.

**Example:**
```python
def min_and_max(numbers):
    return min(numbers), max(numbers)

result = min_and_max([3, 5, 1, 9])
print(result)  # (1, 9)
min_val, max_val = result  # tuple unpacking
```

---

## 💡 Exam Tips & Pitfalls

1. **Immutability:** Tuples cannot be changed after creation. Any attempt to assign to an index or call mutating methods (like `append`, `remove`, etc.) will raise an error.
  ```python
  t = (1, 2, 3)
  # t[0] = 10  # TypeError!
  # t.append(4)  # AttributeError!
  ```
2. **Single-element tuples:** Must have a trailing comma. Parentheses alone do not make a tuple.
  ```python
  t1 = (5)      # Not a tuple, just int 5
  t2 = (5,)     # This is a tuple
  t3 = 5,       # Also a tuple
  ```
3. **Packing and unpacking:** Tuples can be created by separating values with commas, and unpacked into variables.
  ```python
  a, b, c = (1, 2, 3)  # a=1, b=2, c=3
  x, *rest = (10, 20, 30, 40)  # x=10, rest=[20, 30, 40]
  ```
4. **Mutable objects inside tuples:** The tuple itself is immutable, but if it contains a mutable object (like a list), that object can still be changed.
  ```python
  t = ([1, 2], 3)
  t[0].append(99)  # Allowed! Now t is ([1, 2, 99], 3)
  ```
5. **Tuples as dictionary keys:** Tuples can be used as dictionary keys only if all their elements are immutable (hashable).
  ```python
  d = {(1, 2): 'ok'}  # Valid
  # d = {([1, 2], 3): 'fail'}  # TypeError!
  ```
6. **Parentheses are not always required:** Commas create tuples, parentheses are needed only for empty tuples or to avoid ambiguity.
  ```python
  t = 1, 2, 3  # Tuple
  empty = ()   # Empty tuple
  ```
7. **Indexing and slicing:** Work the same as lists.
  ```python
  t = (10, 20, 30)
  print(t[1:])  # (20, 30)
  ```
8. **Conversion does not affect original:** Using `tuple(list)` or `list(tuple)` creates a new object, leaving the original unchanged.
9. **Limited methods:** Tuples only have `.count()` and `.index()` methods.
10. **Common mistakes:**
  - Forgetting the comma for single-element tuples.
  - Trying to modify tuple contents.
  - Confusing assignment (re-binding a variable) with mutation (changing the object).
  - Assuming tuples are always faster or more memory-efficient than lists (may not matter for small data).

---

🎉 **Congratulations!**
You've completed the **collections 2 - tuples** section.
Practice with [tuples questions](../Practice_Exams_Questions/06_collections%202%20-%20tuples.md) next!
