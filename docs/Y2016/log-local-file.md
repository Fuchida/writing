title: Local File Logging
date: 2016
tags: python

Here is a small function to log to a local file in python, 
I use it all the time.

```python
#  py:2.7, 3.5
def get_local_logger():
    """
    Log to local .log file
    """

    logger = logging.getLogger(__file__)
    hdlr = logging.FileHandler(__file__ + '.log')
    
    time_name_fmt = '%(asctime)s|%(name)s|%(filename)s'
    log_detail_fmt = ':%(lineno)s|%(levelname)s|%(message)s'
    logging_format = time_name_fmt + log_detail_fmt

    formatter = logging.Formatter(logging_format)
    hdlr.setFormatter(formatter)
    logger.addHandler(hdlr)
    logger.setLevel(logging.INFO)

    return logger
```

```python
>> local_logger = get_local_logger()
>> local_logger.INFO("Logging to local file!")
```
