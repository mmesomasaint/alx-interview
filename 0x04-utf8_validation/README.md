# 0x04-utf8_validation

## Introduction

UTF-8 is a variable-width character encoding that can represent any Unicode character. It is the most widely used encoding on the web, and is supported by all major browsers and operating systems.

UTF-8 works by representing each character as a sequence of one to four bytes. The first byte of a character indicates how many bytes are in the sequence. For example, a single-byte character will have a first byte with a value of 0-127. A two-byte character will have a first byte with a value of 192-223, and so on.

UTF-8 is a very efficient encoding, because it can represent all Unicode characters using a relatively small number of bytes. It is also a backward-compatible encoding, which means that all ASCII characters are valid UTF-8 characters.

## Task

Write a method that determines if a given `data set` represents a valid `UTF-8 encoding`.

- Prototype: `def validUTF8(data)`
- Return: `True` if data is a valid UTF-8 encoding, else return `False`
- A character in UTF-8 can be `1 to 4 bytes long`
- The data set can contain `multiple characters`
- The data will be represented by a `list of integers`
- Each integer represents `1 byte of data`, therefore you only need to handle the `8 least significant bits` of each integer

### Code Test

Below is a `Test file` for the prototype function `def validUTF8(data)` called: `0-main.py`

```
carrie@ubuntu:~/0x04-utf8_validation$ cat 0-main.py
#!/usr/bin/python3
"""
Main file for testing
"""

validUTF8 = __import__('0-validate_utf8').validUTF8

data = [65]
print(validUTF8(data))

data = [80, 121, 116, 104, 111, 110, 32, 105, 115, 32, 99, 111, 111, 108, 33]
print(validUTF8(data))

data = [229, 65, 127, 256]
print(validUTF8(data))

carrie@ubuntu:~/0x04-utf8_validation$
```

The code will return:

```
carrie@ubuntu:~/0x04-utf8_validation$ ./0-main.py
True
True
False
carrie@ubuntu:~/0x04-utf8_validation$
```
