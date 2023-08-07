title: Creating String Pairs with Python
date: 2016

### Description:

Complete the solution so that it splits the string into pairs of two characters. 
If the string contains an odd number of characters then it should replace the missing second 
character of the final pair with an underscore ('_').

```python
solution('abc') # should return ['ab', 'c_']
solution('abcdef') # should return ['ab', 'cd', 'ef']
```

### Solution:
```python
    # py:3.4
    def solution(letters):
    
    split_letters = [ letters[index-1] + letters[index] \
    for index in range(len(letters)) if index % 2 ] 
        
    if  len(letters) % 2:
        split_letters.append(letters[-1] + '_')
    
    return split_letters
```

### Source:
[CodeWars](https://www.codewars.com/kata/split-strings/python "CodeWars")

