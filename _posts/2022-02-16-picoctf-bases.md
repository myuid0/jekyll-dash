---
layout: post
title:  "picoCTF - Bases"
description: My writeup on Bases challenge.
tags: picoctf general_skills
---

![](https://i.imgur.com/PHNNDTw.png)

It gives us a string `bDNhcm5fdGgzX3IwcDM1`, by experience is base64.

Base64 encode binary data into text so we can more easily transfer them in things like e-mail.

Base64 alphabet is A-Z, a-z, 0-9, +, /, and = for padding.

We can use command line to decode.

```
$ echo bDNhcm5fdGgzX3IwcDM1 | base64 --decode
l3arn_th3_r0p35
```
