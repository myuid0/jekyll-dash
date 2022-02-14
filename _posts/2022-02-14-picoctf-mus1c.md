---
layout: post
title:  "picoCTF - mus1c"
description: My writeup on mus1c challenge.
tags: picoctf general_skills python
---

![](https://i.imgur.com/JpTmbjj.png)

First of all, let's download the 'song'.

```
$ wget -q https://jupiter.challenges.picoctf.org/static/c594d8d915de0129d92b4c41e25a2313/lyrics.txt
$ file lyrics.txt 
lyrics.txt: ASCII text
```

```
$ cat lyrics.txt 
Pico's a CTFFFFFFF
my mind is waitin
It's waitin

Put my mind of Pico into This
my flag is not found
put This into my flag
put my flag into Pico


shout Pico
shout Pico
shout Pico

My song's something
put Pico into This

Knock This down, down, down
put This into CTF
...
```

picoCTF provides us a hint: `Do you think you can master rockstar?` I googled around `rockstar decrypt` and gave me the answer! 

There is a programming language called [Rockstar](https://codewithrockstar.com/){:target="_blank"}. The official site provides an [interpreter](https://codewithrockstar.com/online){:target="_blank"}.

Pasting the lyrics gives us some ASCII numbers:

![](https://i.imgur.com/hokn4UN.png)

By checking the ascii table, we can get the flag `114 -> r` I coded a python script that prints the flag.

```python
data = [114, 114, 114, 111, 99, 107, 110, 114, 110, 48, 49, 49, 51, 114]

flag = ''.join(chr(i) for i in data)

print(f'Flag -> picoCTF{{{flag}}}')
```

```
$ python3 flag.py 
Flag -> picoCTF{rrrocknrn0113r}
```
