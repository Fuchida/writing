title: Set to List Converation 
date: 2021-09-13
tags: Python

Today I learned that converting an ordered list to a set 
and back to a list does not maintain the original order.

```sh
>>> [32.0,36.0,39.0,40.0]
[32.0, 36.0, 39.0, 40.0]

>>> set([32.0,36.0,39.0,40.0])
{32.0, 40.0, 36.0, 39.0}

>>> list(set([32.0,36.0,39.0,40.0]))
[32.0, 40.0, 36.0, 39.0]
```