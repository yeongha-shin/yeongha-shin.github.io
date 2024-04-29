---
layout: post
title: RMOT running
subtitle: PaperWithCode
gh-repo: yeongha-shin
gh-badge: [star, fork, follow]
tags: [PaperWithCode]
comments: true
author: Yeongha Shin
---

#  1. 문제 현상
아침에 출근하고 보니 nvidia-smi가 작동되지 않고, hdmi인식이 안되는 현상이 일어나고 있었다
NVIDIA-SMI has failed because it couldn't communicate with the NVIDIA driver. Make sure that the latest NVIDIA driver is installed and running.

# 2. 시도 내용
그래서 https://bluecolorsky.tistory.com/52 이 내용을 참고해서 수행을 하니까
autoinstall부분에서 아래와 같은 오류가 생겼다

Use apt-get to fix missing and broken packages

그래서 이 링크를 참고해서 수행했다.
```
$ sudo apt-get update --fix-missing
$ sudo apt-get install -f
```
그러고 다시 autoinstall을 하고 reboot를 하니까 정상적으로 해결되었다 !

휴우... 다행이다
이렇게 오늘도 하나를 배웠다
