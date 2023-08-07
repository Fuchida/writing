title: Counting Set Bits
date: 2016
tags: Python

###Description:

Write a function that takes an (unsigned) integer as input, 
and returns the number of bits that are equal to one in the binary representation of that number.

The binary representation of 1234 is 10011010010, so the function should return 5 in this case. 
Because there are five "1" or bits that are set in 10011010010.

###Solution:

```python
def countBits(n):
    return bin(n).count("1")
```

### Source:
[CodeWars](https://www.codewars.com/kata/bit-counting/python "CodeWars")
