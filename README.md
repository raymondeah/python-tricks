# Python Essential Tips

## Lists

### 1. Negative indexing
Lists can be indexed from the back by using negative indices.
```python
nums = [1, 2, 3]
last = nums[-1] # 3
```

### 2. Initializing lists filled with the same element
Lists filled with the same element can be created with the * operator.
```python
ones = [1] * 5 # [1, 1, 1, 1, 1]
trues = [True] * 5 # [True, True, True, True, True]
apples = ['apple'] * 5 # ['apple', 'apple', 'apple', 'apple', 'apple']
```

### 3. Slicing
Lists can be sliced with the slice operator (:). The index to begin including elements (inclusive) goes on the left side of the colon and the index to end including elements (non-inclusive) goes on the right side of the colon.
```python
nums = [1, 2, 3, 4, 5, 6]

left_half = nums[:3] # [1, 2, 3]
right_half = nums[3:] # [4, 5, 6]
middle_two = nums[2:4] # [3, 4]
```

### 4. List comprehensions
List comprehensions are a concise way to create lists. 
```python
squares = [i*i for i in range(5)] # [0, 1, 4, 9, 16]
```
Comprehensions with conditional logic:
```python
prices = [1.99, 15.50, 7.00, 2.50, 21.69]
squares = [p for p in prices if p < 10] # [1.99, 7.00, 2.50]

nums = [5, 7, 4, 8, 1, 9, 2]
evens = [n for n in nums if n % 2 == 0] # [4, 8, 2]
```
Nested comprehensions:
```python
matrix = [[i for i in range(3)] for _ in range(3)] # [[0, 1, 2], [0, 1, 2], [0, 1, 2]]
```


## Strings

### 1. Reversing strings
Strings can be reversed by using the third argument of the slicing operator. -1 indicates to reconstruct the string by stepping backwards from the end.
```python
txt = 'Hello World'
txt_reversed = txt[::-1] # 'dlroW olleH'
```

### 2. Split
The split method splits strings on every instance of the supplied sequence into a list.
```python
txt = 'You thought I was feeling you?'
words = txt.split() # ['You', 'thought', 'I', 'was', 'feeling', 'you?']

food = 'eggs,milk,butter,sugar'
ingredients = food.split(',') # ['eggs', 'milk', 'butter', 'sugar']
```

### 3. Join
The join method joins a list of strings together, placing the supplied sequence in between each string.
```python
scrambled = ['re', 'cur', 'sion']
joined = ''.join(scrambled) # 'recursion'

words = ['You', 'thought', 'I', 'was', 'feeling', 'you?'] # 
txt = ' '.join(words) # 'You thought I was feeling you?'

ingredients = ['eggs', 'milk', 'butter', 'sugar']
food = ','.join(ingredients) # 'eggs,milk,butter,sugar'
```


### 4. F-strings
Strings can be easily formatted using f-strings.
```python
name = 'Ray'
age = 21

greeting = f'Hello, {name}. You are {age} years old.' # 'Hello, Ray. You are 21 years old.'
```

## Dictionaries

### 1. Defaultdict
The collection module's defaultdict offers a helpful syntactic sugar for dictionaries. The empty case is automatically detected and handled by the supplied default object. 
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
adjacency_list = defaultdict(list) # the default object to insert when the key does not exist is an empty list
edges = [[0, 1], [0, 2], [1, 2], [2, 1]]

for u, v in edges:
  adjacency_list[u].append(v)
```

### 2. Merging dictionaries
Dictionaries can be easily merged using **.
```python
dict1 = {'a': 10, 'b': 8}
dict2 = {'b': 6, 'c': 4}
dict3 = {**dict1, **dict2} # {'a': 10, 'b': 14, 'c': 4}
```

## Iteration

### 1. Unpacking
Elements of lists and tuples can be unpacked directly in the header of a for loop.
```python
inventory = [['rice', 5.00, 100], ['milk', 3.50, 75], ['bread', 6.99, 200]]

for item, price, quantity in inventory:
  print(item, price, quantity)
```

### 2. Enumerate
The enumerate function is helpful when you are iterating through a list and need access to both the index as well as the element at the current index.
```python
letters = ['a', 'b', 'c']

for i, letter in enumerate(letters):
  print(i, letter)
```

### 3. Zip
The zip function is helpful when you need to iterate through two or more lists in parallel.
```python
students = ['Ray', 'Sid', 'Bob']
grades = [100, 66, 85]

for student, grade in zip(students, grades):
  print(student + ': ' + grade)
```

## Misc

### 1. Swapping variables
You can swap variables without using a temporary variable using this one-line trick.
```python
a = 10
b = 7

a, b = b, a
```

### 2. not operator
The not operator returns True for "falsy" values, such as False, 0, and empty lists, tuples, dictionaries, and strings.
```python
a = False
b = []
c = ()
d = {}
e = ''
f = 0

print((not a) and (not b) and (not c) and (not d) and (not e) and (not f)) # True
```

### 3. Counter
Counter from the collections module is a Pythonic way to count frequencies of objects.
```python
from collections import Counter
txt = 'abracadabra'
freq = Counter(txt) # {'a': 5, 'b': 2, 'c': 1, 'd': 1, 'r': 2}
print(freq.most_common(1)) # [('a', 5)]
print(freq.total()) # 11
```



