title: Code Comments of Intent
date: 2014

 Im sure this is already known within the wider software community but nevertheless it is a realization that I have recently reached. That there are Code Comments that explain function and comments that illustrate intent.

Many times while taking a look at open source code, I would know what is happening(syntax, function etc) but then spend extra time trying to understand the intent of the code. To understand why such a decision was made and how it would impact other parts of the code.

I believe comments that explain intent are just as important as those that explain function. like the following.
```python
elif self.mode == 'reset':
    #at 'reset',self.elapsed_time return value is expected.
    #no additional work needs to be done
        
    return self.elapsed_time()
 ```

Comments like these aide the reader in figuring out why another programmer made the decisions they did. Like hearing the inner monologue of your fellow programer when he wrote the code you are now reading.
