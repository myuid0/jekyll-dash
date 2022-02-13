---
layout: post
title:  "picoCTF - Obedient Cat"
description: My writeup on obedient cat challenge.
tags: picoctf general_skills
---

![](https://i.imgur.com/HXkybRx.png)

First step is to download the file, i'll use the wget utility.

```
$ wget -q https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag
$ file flag 
flag: ASCII text
```

Now all we have to do is to read the file and get the flag.

```
$ cat flag 
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}
```
