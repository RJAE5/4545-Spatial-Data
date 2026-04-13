# 📝 Worksheet: 04 - Loops and Iteration

Practice and reflect on how loops work in Python.

---

## 🔁 Section 1: For Loops

1. What does `range(5)` produce?

`Answer:` A range item from 0 to 5, starting at 0, but stopping at 4.

2. Write a `for` loop that prints numbers 1 to 10, but skips 5.

```python
# Your code:
for i in range(1,11):
    if i == 5:
        continue
    print(i)
```

---

## 🔁 Section 2: While Loops

3. What’s the difference between a `for` loop and a `while` loop?

`Answer:` a `for` loop has the stopping condition and incrementing built in but a `while` loop is dependent on on that logic elsewhere

4. What happens if a `while` loop's condition never becomes `False`?

`Answer:` It becomes an infinite loop, repeating until the program crashes

---

### ✏️ Task: Countdown with While

```python
# Use a while loop to count down from 5 to 1.
count = 5
while count > 0:
    print(count)
    count -= 1
```

---

## 📁 Section 3: File Reading and `with`

5. What does the `with` statement do when opening a file?

`Answer:` saves it as a variable

6. How do you loop over each line in a file?

`Answer:` via a loop, probably a `for` loop

---

### ✏️ Task: File Filter

Write code that prints only the lines in a file that contain the word `"error"`.

```python
# Your code here
with open('sample.txt', 'r') as f:
    for line in f:
        if "error" in line:
            print(line.strip())
```
