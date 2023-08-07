title: Find the absolute diagonal difference of a matrix 
date: 2023-07-15
tags: Python

```python
def diagonalDifference(data):
    size = len(data[0])
    primary = 0
    secondary = 0
    
    for index in range(size):
        primary += data[index][index]
        secondary += data[index][size - index - 1]
        
    return abs(primary - secondary)
```
