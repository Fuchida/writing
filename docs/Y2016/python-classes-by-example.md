title: Python Classes by Example
date: 2016

### Basic structure of a class
```python
# py:3.5
class Person(object):

    def __init__(self, name, gender):
        self.name = name
        self.gender = gender

    def get_name(self):
        return self.name

    def get_gender(self):
        return self.gender

    def __str__(self):
        return "%s is a %s" % (self.get_name(), self.get_gender())
```

###Subclassing
```
# py:3.5
class Citizen(Person):

    def __init__(self, name, country, gender):
        super.__init__(self, name, gender)
        self.country = country

    def get_nationality(self):
        return self.country

class SecretAgent(Citizen):

    def __init__(self, name, country, gender, isActive):
        super().__init__(name, country, gender)
        self.isActive = isActive
   	# Method overriding
    def get_name(self):
        return "###Redacted###"

    def get_gender(self):
        return "###Redacted###"

    def get_nationality(self):
        return "###Redacted###"

    def get_status(self):
        return self.isActive
```
```
>>> jack = Citizen("Jack", "Tanzania", "Male")
>>> print jack.get_name()
Jack

>>> Light909 = SecretAgent("Jane", "Ukraine", "Female", False)
>>> Dark552 = SecretAgent("Jim", "Spain", "Male", True)
>>> print Light909.get_name()
###Redacted###
```
