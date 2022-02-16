---
layout: post
title:  "picoCTF - fixme1.py"
description: My writeup on fixme1.py challenge.
tags: picoctf general_skills
---

![](https://i.imgur.com/A9g2M8R.png)

Starting off by downloading the file.

```
$ wget -q https://artifacts.picoctf.net/c/43/fixme1.py
$ file *
fixme1.py: Python script, ASCII text executable, with very long lines
```

In order to fix the syntax error, we have to execute the file to understand where the problem lies.

```
$ python3 fixme1.py 
  File "/home/myuid0/Documents/picoctf/generalskills/fixme1.py/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
```

We can see that drops an `unexpected indent` error. This error tell us that this line of code has more spaces at the start.

All we have to do is to remove the space in print() function and get the flag.

![](https://i.imgur.com/ERW9NwB.png)

```
$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_05a3c38c}
```
