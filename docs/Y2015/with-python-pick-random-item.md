title: With Python pick random item
date: 2015

If you have a list of items or a sequence and you want to pic a random item from said sequence. Here is a quick way to do it

```python
from random import choice

letters = ['a', 'b', 'c', 'd']

print(choice(letters))
```
