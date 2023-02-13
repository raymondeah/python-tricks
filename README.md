# Python Cheat Codes

## Lists

#### 1. Negative indexing
```python
nums = [1, 2, 3]
last = nums[-1] # 3
```

#### 2. Initializing lists filled with the same element
```python
ones = [1] * 5 # [1, 1, 1, 1, 1]
trues = [True] * 5 # [True, True, True, True, True]
apples = ['apple'] * 5 # ['apple', 'apple', 'apple', 'apple', 'apple']
```

#### 3. Slicing
```python
nums = [1, 2, 3, 4, 5, 6]

left_half = nums[:3] # [1, 2, 3]
right_half = nums[3:] # [4, 5, 6]
middle_two = nums[2:4] # [3, 4]
```

#### 4. List comprehensions
```python
squares = [i*i for i in range(5)] # [0, 1, 4, 9, 16]
```
Conditional logic
```python
prices = [1.99, 15.50, 7.00, 2.50, 21.69]
squares = [p for p in prices if p < 10] # [1.99, 7.00, 2.50]

nums = [5, 7, 4, 8, 1, 9, 2]
evens = [n for n in nums if n % 2 == 0] # [4, 8, 2]
```
Nested comprehensions
```python
matrix = [[i for i in range(3)] for _ in range(3)] # [[0, 1, 2], [0, 1, 2], [0, 1, 2]]
```


## Strings

#### 1. Reversing strings
```python
txt = 'Hello World'
txt_reversed = txt[::-1] # 'dlroW olleH'
```

#### 2. Split
```python
txt = 'You thought I was feeling you?'
words = txt.split() # ['You', 'thought', 'I', 'was', 'feeling', 'you?']

food = 'eggs,milk,butter,sugar'
ingredients = food.split(',') # ['eggs', 'milk', 'butter', 'sugar']
```

#### 3. Join
```python
scrambled = ['re', 'cur', 'sion']
joined = ''.join(scrambled) # 'recursion'

words = ['You', 'thought', 'I', 'was', 'feeling', 'you?'] # 
txt = ' '.join(words) # 'You thought I was feeling you?'

ingredients = ['eggs', 'milk', 'butter', 'sugar']
food = ','.join(ingredients) # 'eggs,milk,butter,sugar'
```


#### 4. F-strings
```python
name = 'Ray'
age = 21

greeting = f'Hello, {name}. You are {age} years old.' # 'Hello, Ray. You are 21 years old.'
```

## Dictionaries

#### 1. Defaultdict
```python
from collections import defaultdict

# normal dictionary
adjacency_list = {}
edges = [[0, 1], [0, 2], [1, 2], [2, 1]]

for u, v in edges:
  if u in adjacency_list:
    adjacency_list[u].append(v)
  else:
    adjacency_list[u] = [v]

# defaultdict
adjacency_list = defaultdict(list)
edges = [[0, 1], [0, 2], [1, 2], [2, 1]]

for u, v in edges:
  adjacency_list[u].append(v)
```

#### 2. Merging dictionaries
```python
dict1 = {'a': 10, 'b': 8}
dict2 = {'b': 6, 'c': 4}
dict3 = {**dict1, **dict2} # {'a': 10, 'b': 14, 'c': 4}
```

## Iteration

#### 1. unpacking
```python
inventory = [['rice', 5.00, 100], ['milk', 3.50, 75], ['bread', 6.99, 200]]

for item, price, quantity in inventory:
  print(item, price, quantity)
```

#### 2. Enumerate
```python
letters = ['a', 'b', 'c']

for i, letter in enumerate(letters):
  print(i, letter)
```

#### 3. Zip
```python
students = ['Ray', 'Sid', 'Bob']
grades = [100, 66, 85]

for student, grade in zip(students, grades):
  print(student + ': ' + grade)
```

## Misc

#### 1. Swapping variables
```python
a = 10
b = 7

a, b = b, a
```

#### 2. not operator
```python
a = False
b = []
c = ()
d = {}
e = ''
f = 0

print((not a) and (not b) and (not c) and (not d) and (not e) and (not f)) # True
```

#### 3. Counter
```python
txt = 'abracadabra'
freq = Counter(txt) # {'a': 5, 'b': 2, 'c': 1, 'd': 1, 'r': 2}
print(freq.most_common(1)) # [('a', 5)]
print(freq.total()) # 11
```



