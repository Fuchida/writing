title: Find Duplicates in a List 
date: 2021-09-17
tags: Python

```
Problem: 
Given a list of integers identify duplicates

Example:
    1 input: [2,4,5,6,2]
      output: [2]

    2 input: [3,5,6,7,3,7,11,7]
      output [3,7]
```

```python
def find_duplicates(data):
    prev_seen = []
    duplicates = set()
    
    for item in data:
        if item in prev_seen:
            duplicates.add(item)
        else:
            prev_seen.append(item)
    
    return duplicates

data = [3,5,6,7,3,7,11,7,8,8,8]

print(find_duplicates(data))
# >> {8, 3, 7}
```