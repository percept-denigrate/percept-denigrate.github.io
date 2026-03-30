---
tags:
  - project
---

[Github](https://github.com/percept-denigrate/timestrike) - [Pypi](https://pypi.org/project/timestrike/)

---

Timestrike is a Python library I made to conduct timing attacks.

The idea came to me while doing a CTF challenge where I had to do a timing attack. I realized the Python script I has to write was pretty much the exact same script I had written for a previous CTF challenge. So I decided to publish it as a library.

The library provides two functions: 

- `get_length` to obtain the length of the key
- `get_key` to obtain its content.

They only require the user to define the function that gives the processing time of a given string.
