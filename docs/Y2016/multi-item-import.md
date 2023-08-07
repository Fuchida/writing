title: Multi Item Import
date: 2016
tags: python

Here is a clean way to import multiple items
from the same module.

```python
    # py:2.7
  
    # Do this 
    from module import (func1, func2, func3
                        func4, func5, func6,
                        func7, func8, func9
                        )
    
    # Instead of this
    from module import func1, func2, func3, func4, func5, func6, func7, func8, func9
```
