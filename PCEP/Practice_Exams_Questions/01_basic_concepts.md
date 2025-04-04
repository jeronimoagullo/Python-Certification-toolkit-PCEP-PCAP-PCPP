# Basic concepts questions

✏️ Covered topics in this section:
- Python interpreter vs. scripting
- Code structure (indentation, comments)
- Keywords and identifiers

### Question 1: Python Interpreter vs. Scripting  
**Multi Selection**  
Which of the following statements correctly distinguishes between the Python interactive interpreter and scripting?  

- The interactive interpreter executes code line-by-line, while a script runs all code at once.
- In the interactive interpreter, indentation is optional, but it is mandatory in a script.
- Scripts can only be run using an IDE, not from the command line.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Interactive interpreter executes line-by-line, scripts run all code at once.)
  - ❌ (Indentation is mandatory in both contexts where code blocks exist.)
  - ❌ (Scripts can be executed from the command line using `python myscript.py`.)
</details>

---

### Question 2: Indentation Importance  
**Multi Selection**  
Regarding code structure in Python, which statements about indentation are correct?

- Indentation defines code blocks and must be consistent (e.g., 4 spaces or 1 tab).
- Mixing tabs and spaces is acceptable if the code is executed in an interactive interpreter.
- Incorrect indentation will raise a SyntaxError.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Indentation is required to define code blocks.)
  - ❌ (Mixing tabs and spaces can lead to errors, regardless of the environment.)
  - ✅ (Improper indentation causes SyntaxError.)
</details>

---

### Question 3: Comments in Python  
**Multi Selection**  
Which of the following is true about comments in Python?

- Single-line comments start with `#`.
- Multi-line comments can be created using triple quotes (`'''` or `"""`).
- Comments are executed by Python, so they affect the program's performance.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Single-line comments use `#`.)
  - ✅ (Triple quotes can be used for multi-line comments.)
  - ❌ (Comments are ignored by the interpreter and do not affect performance.)
</details>

---

### Question 4: Expected Output – Interactive Interpreter  
**What is the expected output of the following statement?**  

```python
>>> print("Hello World")
```

<details><summary>💡 Answer</summary>

**Output:**

```
Hello World
```

**Explanation:**
The interactive interpreter prints the string passed to the print function.
</details>

### Question 5: Keywords and Identifiers  
**Multi Selection**  
Which of the following are valid identifiers in Python?

- `my_var`
- `2ndValue`
- `if`

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (`my_var` is valid.)
  - ❌ (Identifiers cannot start with a number.)
  - ❌ (`if` is a reserved keyword.)
</details>

---

### Question 6: Python Reserved Keywords  
**Multi Selection**  
Identify the correct statements regarding Python reserved keywords:

- Python has 33 reserved keywords in version 3.11.
- Reserved keywords can be used as variable names if you mix uppercase and lowercase.
- Keywords such as `while` and `for` cannot be used as identifiers.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Python 3.11 has 33 keywords.)
  - ❌ (Keywords cannot be used as variable names, regardless of case.)
  - ✅ (Keywords like `while` and `for` are reserved and cannot be used as identifiers.)
</details>

---

### Question 7: Code Structure and Execution  
**Multi Selection**  
Which aspects are important for Python code structure?

- Correct indentation to define code blocks.
- Consistent use of comment styles for documentation.
- Parentheses around every single expression.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Indentation is crucial.)
  - ✅ (Comments help document and clarify code.)
  - ❌ (Parentheses are not required for every expression.)
</details>

---

### Question 8: Indentation Error Trap  
**Multi Selection**  
Consider the following code snippet:

```python
if True:
print("Oops!")
```

Which of the following statements are true?

- The code will raise an error due to incorrect indentation.
- The code is valid because Python ignores whitespace.
- Proper indentation would prevent a SyntaxError.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Lack of indentation causes an error.)
  - ❌ (Python does not ignore necessary whitespace in code blocks.)
  - ✅ (Correct indentation is required to avoid SyntaxError.)
</details>

---

### Question 9: Exam Traps – Common Pitfalls  
**Multi Selection**  
Which of the following are common exam traps mentioned in the basic concepts?

- Forgetting to indent code blocks.
- Using a Python keyword as a variable name.
- Overusing semicolons at the end of each line.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (Missing indentation is a common trap.)
  - ✅ (Using keywords as identifiers causes errors.)
  - ❌ (Semicolons are optional in Python and not an exam trap.)
</details>

---

### Question 10: Running Python Code  
**Multi Selection**  
Which of the following are valid ways to run Python code?

- Typing code directly into the interactive interpreter using `python` or `python3`.
- Writing code in a `.py` file and running it via `python filename.py`.
- Using a `.txt` file renamed to `.py` even if it contains invalid Python syntax.
- Using an IDE like VSCode or PyCharm to execute Python scripts.

<details><summary>💡 Answer</summary>

**Output:**

  - ✅ (You can run code in the interactive shell.)
  - ✅ (You can run `.py` scripts from the command line.)
  - ❌ (File extension alone doesn’t make code valid Python. Syntax must be correct.)
  - ✅ (IDEs provide tools to run Python code.)
</details>

---