---
layout: post
title:  "picoCTF - Serpentine"
description: My writeup on Serpentine challenge.
tags: picoctf general_skills python
---

![](https://i.imgur.com/AMr4KLy.png)

Let's download the python script first.

```
$ wget -q https://artifacts.picoctf.net/c/97/serpentine.py
$ file serpentine.py 
serpentine.py: Python script, ASCII text executable, with very long lines
```

Running the script, prints a menu and waits for our input.

```
$ python3 serpentine.py 

Welcome to the serpentine encourager!

a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) 
```

We only care about the b option, but looks like the script is broken.

```
What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!
```

There is a `print_flag()` function.

```python
def print_flag():
  flag = str_xor(flag_enc, 'enkidu')
  print(flag)
```

All we have to do is to call the function.

```python
 elif choice == 'b':
      print_flag()
```

```
$ python3 serpentine.py

Welcome to the serpentine encourager!

a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_ae743140}
```
