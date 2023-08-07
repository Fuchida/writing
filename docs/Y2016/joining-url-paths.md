title: Joining URL Paths
date: 2016

When you want to join an absolute url path `http://domain.com` with a relative path
`/authenticate` changes are you'd want do something like this

```python
# py:2.7
absolute = "http://domain.com"
relative = "/authenticate"

joined_path = absolute + absolute
# http://domain.com/authenticate
```

Problems would occur if the absolute path changes to `http://domain.com/` or
to `http://domain.com/index.html`.

A better option would be to use `urljoin` to properly handle both of the above cases.

```python
# py:2.7
from urlparse import urljoin

absolute = "http://domain.com"
relative = "/authenticate"

joined_path = urljoin("http://domain.com/index.html", "/authenticate")
# "http://domain.com/authenticate"
```
