title: Colored Output and Automatic Testing
date: 2016

We can get colored output and automatic testing in our python development process by
using `rednose` and `sniffer`.

Below are some example files that you can use.

#### person.py:
```python
#  py:3.5

class Person(object):

    def alias(self):
        return "Fuchida"
```

#### test_person.py:
```python
#  py:3.5

import unittest
from person import Person


class PersonTestCase(unittest.TestCase):

    def setUp(self):
        self.test_alias = 'Fuchida'

    def test_bar(self):
        """alias method returns test_name value """
        self.assertEqual(Person().alias(), self.test_alias,
                         msg="Got: {}, Expected: {}".format(Person().alias(),
                         self.test_alias))
```

#### req.txt:
```python
colorama==0.3.7
nose==1.3.7
python-termstyle==0.1.10
rednose==1.2.1
sniffer==0.3.5
```

#### Setup:
1. Create a virtual environment
2. Install requirements from `req.txt`
3. Add the `person.py` and `test_person.py` files to your environment
4. Run `sniffer -x--rednose`

You will end up with colored output when tests pass or fail and if you change 
the files, the tests will rerun automatically.
