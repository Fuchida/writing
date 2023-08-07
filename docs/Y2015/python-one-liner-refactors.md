title: Python one liner refactors
date: 2015

I like it when I find one liner that make the code better and
and faster to understand.

The worst one liners are those that force you to twist you mind
in weird ways in order to understand them.

A simple one, utilizing the bool return value from the "in" operator
```python
def is_wanted(self, item):
    if item in self.wanted_items:
        return True
    return False
```
```python
def is_wanted(self, item):
    return item in self.wanted_items
```
Using list comprehension and the "any" built in function

```python
def is_wanted(self, item):
    for type in self.wanted_types:
        if item.upper().startswith(type):
            return True
        else:
            return False
```
```python
def is_wanted_type(self, item):
    return any([item.upper().startswith(type) for type in self.wanted_types])
```
