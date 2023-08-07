title: Python Command line arguments
date: 2017
tags: Python

Here is some simple code that allows you 
to call different functions based on user provided options.

There are more robust tools out there but if you just want
something quick this should be enough.

```python
# 3.x.py

from os import sys

def run_option_a():
    print("Hello from option A !")

def run_option_b():
    print("Hello from option B !") 

if __name__ == "__main__":

    if len(sys.argv) >= 2:
        if sys.argv[1] == '-a':
            run_option_a()

        elif sys.argv[1] == '-b':
            run_option_b()

        else:
            print('Unrecognized command')
    else:
        print ('* Please enter -a for option A or -b for option B')

# Usage:
    python file_name.py -a
    python file_name.py -b

```
