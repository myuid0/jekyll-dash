---
layout: post
title:  "picoCTF - Wave a flag"
description: My writeup on Wave a flag challenge.
tags: picoctf general_skills
---

![](https://i.imgur.com/W7Meelc.png)

As always let's download the file.

```
$ wget -q https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
$ file warm 
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=506b7be935d8940c672ab0d40d2e03ebd746155b, with debug_info, not stripped
```

We have an ELF file, ELF is an executable file. Let's execute it.

```
$ chmod +x warm 
$ ./warm 
Hello user! Pass me a -h to learn what I can do!
```

By passing the `-h` argument we get the flag.

```
$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
```

There is another way to get the flag without running the binary, using the `strings` command.

Strings shows us all the human-readable characters in a binary.

```
$ strings warm | grep -iwn "picoCTF"
19:Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
```
