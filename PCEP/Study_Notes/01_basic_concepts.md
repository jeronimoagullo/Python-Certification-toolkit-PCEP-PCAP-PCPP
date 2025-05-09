# Basic concepts

✏️ Covered topics in this section:
- Python interpreter vs. scripting
- Code structure (indentation, comments)
- Keywords and identifiers

## 🖥️ 1. Python Interpreter vs. Scripting  
### **Interactive Interpreter**  
- Runs code line-by-line (e.g., IDLE, Python shell).  
- **Example**:  
```python  
>>> print("Hello World")
Hello World
```

### **Scripting**
Execute a .py file:
```bash
Copy
python myscript.py  
```

- **Key Difference**: Scripts run all code at once; interpreter runs incrementally.

## 📐 2. Code Structure

### Indentation
Mandatory for code blocks (no `{}` like C or javascript):

```python
if True:  
    print("Indented!")  # 4 spaces or 1 tab  
```

**Pitfall**: Mixing tabs and spaces causes errors.

### Comments
- **Single-line**: `#` This is a comment
- **Multi-line**: Use `'''...'''` or `"""..."""`:
 
```python
'''  
This is a  
multi-line comment  
'''
```

- **TIP:** We can comment and decomment rapidly with the keyboard shortcut **CTRL + /** in english keyboards, **CTRL + }** in spanish keyboards or **CTRL + #** in german keyboards.

## 🔑 3. Keywords & Identifiers

### Keywords
Keywords are reserved words (e.g., if, for, while).

- **Full list** (33 keywords in Python 3.11):

```
False      await      else       import     pass  
None       break      except     in         raise  
True       class      finally    is         return  
and        continue   for        lambda     try  
as         def        from       nonlocal   while  
assert     del        global     not        with  
async      elif       if         or         yield
```

## 💡 4. Exam Traps
1. Indentation Errors:

```python
if True:  
print("Oops!")  # Missing indentation → SyntaxError  
```

2. Keyword Misuse:
```python
class = "Math"  # SyntaxError (class is a keyword)  
```

3. Case Sensitivity:
```python
Age = 20  
print(age)  # NameError (Age ≠ age)
```

---

🎉 **Congratulation!!** 

You have completed the section **basic concepts**, now you can go to the [basic concepts questions clicking here](../Practice_Exams_Questions/01_basic_concepts.md).