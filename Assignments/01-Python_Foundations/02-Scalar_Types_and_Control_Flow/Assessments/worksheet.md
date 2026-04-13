# 📝 Worksheet: 03 - Scalar Types and Control Flow

Use this worksheet to reinforce your understanding of variables, comparisons, and decision logic.

---

## 🧠 Section 1: Scalar Types

1. What is the output of the following code?

```python
x = 10
print(type(x))
```

`Answer:` `<class 'int'>`

2. What scalar type would best represent:
   - A person's name: string
   - Their age: int
   - Whether they passed a test: bool

---

### ✏️ Task: Type Practice

```python
# Create a variable for each type and print its value and type
# Example: an int, float, str, and bool
year = 1776
print(type(year))
e = 2.718
print(type(e))
address = '3410 Taft Blvd'
print(type(address))
is_okay = False
print(type(is_okay))

```

---

## 🔁 Section 2: Comparison Operators

3. What does the `!=` operator mean?

`Answer:` it checks if two values are not equal, returning `True` if they are different values, and `False` otherwise.

4. What will the following code print?

```python
a = 5
b = 3
print(a < b or b < 10)
```

`Answer:` `True`

---

## 🔀 Section 3: Control Flow

5. Write a conditional that prints "Pass" if a grade is >= 70, and "Fail" otherwise.

```python
# Your code:
if grade >= 70:
   print("Pass")
else
   print("Fail")
```

6. What does `elif` allow you to do?

`Answer:` chain multiple conditionals together to check different things and enter a different respective code block

---

### ✏️ Task: Your Turn

Write a program that asks for the weather and prints:
- "Bring sunscreen" if it's sunny
- "Take an umbrella" if it's raining
- "Check the forecast" otherwise

```python
weather = "sunny"

if weather == "sunny":
   print("Bring sunscreen")
elif weather == "raining":
   print("Take an umbrella")
else:
   print("Check the forecast")
```
