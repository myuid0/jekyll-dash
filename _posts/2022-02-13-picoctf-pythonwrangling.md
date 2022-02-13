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

We can simply install it using pip utility.

```
$ pip3 install cryptography
Collecting cryptography
  Using cached cryptography-36.0.1-cp36-abi3-manylinux_2_24_x86_64.whl (3.6 MB)
Requirement already satisfied: cffi>=1.12 in /home/myuid0/.local/lib/python3.9/site-packages (from cryptography) (1.15.0)
Requirement already satisfied: pycparser in /home/myuid0/.local/lib/python3.9/site-packages (from cffi>=1.12->cryptography) (2.21)
Installing collected packages: cryptography
Successfully installed cryptography-36.0.1
```

```
$ pip3 list | grep cryptography
cryptography     36.0.1
```

Running the python script now, shows us the usage message.

```
$ python3 ende.py 
Usage: ende.py (-e/-d) [file]
```

`-e = encrypt (converting normal data into an unreadable form)`

`-d = decrypt (converting the unreadable data into its original form)`

All we have to do now is to use the python script to decrypt the `flag.txt.en` file.

```
$ python3 ende.py -d flag.txt.en
Please enter the password:
```

We can pipe the password to it.

```
$ cat pw.txt | python3 ende.py -d flag.txt.en
Please enter the password:picoCTF{4p0110_1n_7h3_h0us3_192ee2db}
```
