title: Find the difference between two dictionaries/json
date: 2021-09-13
tags: Python

Use Python to find the difference between two dictionaries
with nested dictionaries.

```python
"""
Provided two dictiories, identify the difference in the two,
ke in mind that a value may also be a dictionary
"""

origin = {
    "fname":"abdul",
    "lname":"salim",
    "profession":"software engineer",
    "phone_number": "612-360-7526",
    "address": {
            "street":"101 broad",
            "city":"plattsburgh",
            "state":"MN",
            "country":"US",
                "cord": {
                "lat":"110",
                "long":"1113"
            }
    }

}

reference = {
    "fname":"abdul",
    "lname":"salim",
    "profession":"plumber",
    "marital_status":"Single",
    "address":{
            "street":"103 broad",
            "city":"plattsburgh",
            "state":"MN",
            "country":"US",
            "cord": {
                "lat":"110",
                "long":"1112"
            }
    }

}

def compare(origin, reference):
    for key, value in origin.items():
        if key not in reference.keys():
            print(f"-{key}:{origin[key]}")
            continue


        if origin[key] != reference[key]:
            print(f"+{key}:{reference[key]}")

        if key in reference.keys() and all([isinstance(origin[key], dict),\
                                            isinstance(reference[key], dict)]):
            compare(origin[key], reference[key])

    for ref_key in reference.keys():
        if ref_key not in origin.keys():
            print(f"+{ref_key}:{reference[ref_key]}")

compare(origin, reference)

```