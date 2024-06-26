---
layout: post
title: How to install ByteTrack
subtitle: MOT SOTA
gh-repo: yeongha-shin
gh-badge: [star, fork, follow]
tags: [Tracking]
comments: true
author: Yeongha Shin
---
# 나의 목표는?
https://github.com/ifzhang/ByteTrack/tree/main

byteTrack 이라고 하는 MOT(multi object Tracking) 분야에서 꽤 높은 SOTA 순위를 차지하고 있는 코드이다.
그리고 무엇보다도 내가 궁극적으로 실행하고 싶은 SMIALTrack에서 기조를 두고 사용하고 있는 코드이기 때문에,
Dependency를 맞춰주기 위해서 사전적으로 구동해보려고 한다!


# 사전적인 설치
## Anaconda Install
https://ieworld.tistory.com/12

## Pytorch install
https://jooona.tistory.com/140
(conda로 안되면 pip로 해볼것,
그리고 무조건 print(torch.cuda.is_available())를 확인해볼것 !)

## Docker install
https://jjeongil.tistory.com/1968
도커를 통해서 개발 환경을 컨테이너화 한다!

# 빌드 실행
## docker 빌드
### docker 이미지 생성
docker build -t bytetrack:latest . (기존 byteTrack readme에서는 sudo가 없는데, sudo 까지 앞에 붙여야 실행 가능하다!)
이것은 도커 이미지를 만드는 단계임 (도커 이미지는 : 실행단위를 말한다) : 참고로 꽤 오래 걸리는 명령어이다 !

## Docker running
- error debugging 1) 
그 이후에, https://github.com/Xilinx/Vitis-AI/issues/18
docker run을 수행하기 전에 sudo chmod 666 /var/run/docker.sock명령어를 수행해야,
docker : unknown server OS 이 에러가 사라지게 된다

- error debugging 2)
  그리고 Error response from daemon: could not select device driver "" with capabilities: [[gpu]] 

이 원인이 생길 수 있는데,
그러한 경우에는 nvidia-toolkit을 설치해야 한다
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html

https://velog.io/@johyonghoon/docker-Error-response-from-daemon-could-not-select-device-driver-with-capabilities-gpu-%ED%95%B4%EA%B2%B0

- 그러고 나서 docker run을 돌리면 된다 !
  
# Dataset 준비
## 1. MOT17 Download
https://motchallenge.net/
여기서 MOT17에 대해서 all files를 다운 받은 다음에,
파일 폴더 이름을 "mot" 로 변환해야 한다. 지금은 MOT17로 되어 있어서 디렉토리를 인식하지 못할 것이다 !

## 2. coco format으로 변환
```
python3 tools/convert_mot17_to_coco.py
```









