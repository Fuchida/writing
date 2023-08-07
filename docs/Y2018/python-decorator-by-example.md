title: Python Decorator by Example
date: 2018

A Python decorator allows you to execute some code before
and after the wrapped function is executed.

We typically use decorators for validation, logging, introspection or whenever
we need to extend the functionality of an existing function without modifying it directly.

### Basic Setup for a decorator
```python
# py:3
def logger(func):

    def wrap(*args, **kwards):
        if "House" in args:
            print "House Logging"
        else:
            print "logging"
        return func(*args, **kwards)
    return wrap

@logger
def say_hello(word):
    print word
```

```
say_hello("House")
>> House Logging
>> House
```
