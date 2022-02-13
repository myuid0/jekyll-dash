---
layout: post
title:  "picoCTF - Python Wrangling"
description: My writeup on python wrangling challenge.
tags: picoctf general_skills python
---

![](https://i.imgur.com/WkwRyc0.png)

First we have to download the 3 given files.

```
$ wget -q https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/ende.py
$ wget -q https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/pw.txt
$ wget -q https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/flag.txt.en
$ file *
ende.py:     Python script, ASCII text executable
flag.txt.en: ASCII text, with no line terminators
pw.txt:      ASCII text
```

The first file is a python script, then we have a password file, and finally we have the flag in encrypted format.
If we try to run the python file we will get a module missing error.

```
$ python3 ende.py 
Traceback (most recent call last):
  File "/home/myuid0/Documents/picoctf/generalskills/pythonwrangling/ende.py", line 4, in <module>
    from cryptography.fernet import Fernet
ModuleNotFoundError: No module named 'cryptography'
```
