---
layout: post
title:  "picoCTF - fixme2.py"
description: My writeup on fixme2.py challenge.
tags: picoctf general_skills
---

![](https://i.imgur.com/nXZ3OKf.png)

Let's download the python script.

```
$ wget -q https://artifacts.picoctf.net/c/68/fixme2.py 
$ file *
fixme2.py: Python script, ASCII text executable, with very long lines
```

Again let's execute it to understand where the problem lies.

```
$ python3 fixme2.py 
  File "/home/myuid0/Documents/picoctf/generalskills/fixme2.py/fixme2.py", line 22
    if flag = "":
            ^
SyntaxError: invalid syntax
```

We have an invalid syntax error under if statement.

All we have to do is to comment the if statement in order to directly execute the print() function and get the flag.

![](https://i.imgur.com/lObCYZJ.png)

```
$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_b4d595d9}
```
