# Dictionaries

✏️ Covered topics in this section:
- What is a dictionary
- Keys and values
- Defining and using dictionaries
- Adding/removing keys
- Common methods (`keys()`, `items()`, `values()`, etc.)
- Loops with dictionaries
- Converting lists/tuples to dictionaries
- Exam Tips & Pitfalls

---

## 1. What is a Dictionary?
A **dictionary** (`dict`) is an unordered, mutable collection of key-value pairs. Each key must be unique and immutable (e.g., string, number, tuple of immutables), while values can be any type.

**Definition:**
```python
d = {'a': 1, 'b': 2}
```
Or using the `dict()` constructor:
```python
d = dict(a=1, b=2)
```

- **Key:** The identifier (must be unique and immutable)
- **Value:** The data associated with the key (can be any type)

**Accessing values:**
```python
print(d['a'])  # 1
```
If a key does not exist, a `KeyError` is raised:
```python
# print(d['x'])  # KeyError!
```

**Adding new keys:**
```python
d['c'] = 3  # Adds new key-value pair
```

**Removing a key:**
```python
del d['b']  # Removes key 'b'
```

**Check if a key exists:**
```python
if 'a' in d:
    print('Key exists!')
```

**Unordered:**
Dictionaries do not store data in order (before Python 3.7; from 3.7+, insertion order is preserved, but you should not rely on it for exams).

**Golden Rule:** Dictionaries are not lists or tuples. Indexing by integer position does not work.

**Tuple unpacking with dictionaries:**
```python
t = ('x', 99)
d = dict([t])  # {'x': 99}
```

---

## 2. Dictionaries and For Loops

**Iterating over keys:**
```python
for key in d:
    print(key)
# or
for key in d.keys():
    print(key)
```

**Iterating over values:**
```python
for value in d.values():
    print(value)
```

**Iterating over key-value pairs:**
```python
for key, value in d.items():
    print(key, value)
```

**Sorting keys:**
```python
for key in sorted(d.keys()):
    print(key, d[key])
```

**Common dictionary methods:**
- `keys()`: Returns a view of the dictionary's keys.
- `values()`: Returns a view of the values.
- `items()`: Returns a view of (key, value) tuples.
- `popitem()`: Removes and returns the last inserted key-value pair (raises error if empty).
- `update()`: Updates the dictionary with another dictionary or key-value pairs.
- `copy()`: Returns a shallow copy of the dictionary.
- `clear()`: Removes all items from the dictionary.

**Example:**
```python
d = {'a': 1, 'b': 2}
d.update({'c': 3})  # {'a': 1, 'b': 2, 'c': 3}
d2 = d.copy()
d.clear()  # d is now {}
```

**Note:** There is no `count()` method for dictionaries.

---

## 3. Convert Lists and Tuples to Dictionaries

- From a list of pairs:
```python
lst = [('a', 1), ('b', 2)]
d = dict(lst)  # {'a': 1, 'b': 2}
```
- From two lists (keys and values):
```python
keys = ['x', 'y']
values = [10, 20]
d = dict(zip(keys, values))  # {'x': 10, 'y': 20}
```
- From a tuple of pairs:
```python
tpl = (('foo', 123), ('bar', 456))
d = dict(tpl)  # {'foo': 123, 'bar': 456}
```

**Golden Rule:** Keys must be unique and immutable.

---

## 💡 4. Exam Tips & Pitfalls

1. **KeyError:** Accessing a missing key raises `KeyError`. Use `in` to check existence, or `get()` to provide a default:
   ```python
   d = {'a': 1}
   # d['b']  # KeyError!
   print(d.get('b', 0))  # 0
   ```
2. **Mutable values:** If a value is mutable (like a list), changes affect all references:
   ```python
   d = {'x': []}
   d['x'].append(1)  # d['x'] is now [1]
   ```
3. **Unhashable keys:** Lists and other mutable types cannot be used as keys.
   ```python
   # d = {[1,2]: 'fail'}  # TypeError!
   d = {(1,2): 'ok'}  # Valid
   ```
4. **No integer indexing:** `d[0]` does not return the first item; keys are not positions.
5. **No `count()` method:** Dictionaries do not have a `count()` method.
6. **Copy vs assignment:** `copy()` creates a shallow copy; `d2 = d` just creates a new reference.
7. **Modifying during iteration:** Don't change the dictionary size while iterating over it.
8. **Duplicate keys:** If duplicate keys are defined, the last one prevails:
   ```python
   d = {'a': 1, 'a': 2}  # {'a': 2}
   ```
9.  **Golden Rule:** Always check if a key exists before accessing it, unless you're sure.

---

🎉 **Congratulations!**
You've completed the **collections 3 - dictionaries** section.
Practice with [dictionaries questions](../Practice_Exams_Questions/06_collections%203%20-%20dictionaries.md) next!

