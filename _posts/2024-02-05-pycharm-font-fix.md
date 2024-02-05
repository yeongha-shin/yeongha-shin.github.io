---
layout: post
title: How to fix matplotlib font find error?
subtitle: Follow my lead!
gh-repo: yeongha-shin
gh-badge: [star, fork, follow]
tags: [python-fix]
comments: true
author: Yeongha Shin
---

I got this error, in pycharm project 

~~~
findfont: Font family ['Times New Roman'] not found. Falling back to DejaVu Sans.
~~~

So I use this command line, and then fix it !

~~~
$ sudo apt install msttcorefonts -qq
$ rm ~/.cache/matplotlib -rf
~~~
