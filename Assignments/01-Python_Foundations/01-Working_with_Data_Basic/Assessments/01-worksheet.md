# 📝 Worksheet: 02 - Working with Data

Use this worksheet to review and reinforce your understanding of Python data containers.

---

## 🧠 Section 1: Lists

1. What method adds an item to the end of a list?  
   `Answer:` `append()`

2. How can you remove an item from a list by value?  
   `Answer:` `remove()`

3. What’s the result of this code?

```python
nums = [2, 4, 6]
nums.append(8)
print(nums)
```

   `Answer:` `[2, 4, 6, 8]`

---

### ✏️ Task: List Practice

```python
# Create a list of your top 3 favorite foods.
# Add another food to the list.
# Remove one item and print the list.

foods = ["MacNCheese","Steak","Protein Bars"]
foods.append("Yogurt")
foods.remove("MacNCheese")

print(foods)
```

---

## 🔒 Section 2: Tuples

4. What is a key difference between a list and a tuple?  
   `Answer:` A list is mutable while a tuple is immutable

5. Can you change the contents of a tuple once it is created? Why or why not?  
   `Answer:` No you cannot, by definition, tuples are immutable. You must overwrite the previous one entirely to change its contents.

---

### ✏️ Task: Tuple Practice

```python
# Create a tuple with your favorite 3 numbers.
# Unpack it into three variables and print each.

t = (5, 21, 25)
fav1 = t[0]
fav2 = t[1]
fav3 = t[2]

```


---

## 🔑 Section 3: Dictionaries

6. What does the `.get()` method do differently from accessing a key directly?  
   `Answer:` It has a failsafe option to return a value in the case the key doesn't exist.

7. How do you loop through both keys and values in a dictionary?  
   `Answer:` using the `items()` function

---

### ✏️ Task: Dictionary Practice

```python
# Create a dictionary with keys: 'name', 'age', and 'hobby'.
# Print each key and value in the format "key: value".

d = {
   'name': 'Rykir',
   'age': 21,
   'hobby': 'Coding'
}

for thing in d.items():
   print(thing)

```

---

## 🧾 Submit Checklist

- [X] I practiced creating and modifying lists.
- [X] I understand how tuples are different from lists.
- [X] I accessed and looped through dictionary items.
