---
layout: post
title: What is ROS?
subtitle: ROS, GAZEBO
gh-repo: yeongha-shin
gh-badge: [star, fork, follow]
tags: [ROS]
comments: true
author: Yeongha Shin
---

# ROS란 무엇인가? 왜 ROS를 사용해야 하는가?
- Plumbing : 두개 이상의 기기들이 동시에 구동될 수 있다는 장점이 있다 !
- 시각화 상의 장점이 존재한다!

# ROS의 core concept !
### Node
: 실행가능한 가장 작은 프로그램 단위

### 패키지
: 노드들의 집합이 이루고 있는 프로젝트 단위

### Message
: 데이터 들을 말한다

### Topic
: 데이터들에 대해서 말하는 메시지의 통로

# ROS의 통신 종류
### Topic
: publisher, subscriber를 통해서 데이터를 듣는 사람의 반응에 상관없이 지속적인 데이터 발송을 진행한다
- 통신을 하는데 있어서, 개체의 인원 제한이 없다 !

### Service

### Action

# ROS의 구동 원리
### 1. ROS Master
- Node 들 사이의 커뮤니케이션을 관리해주는 역할을 하는 것을 말한다

```
roscore
```
위의 커맨드를 사용해서 구동하도록 한다

### 2. ROS Nodes
### 3. ROS Topics
### 4. ROS Messages

# ROS installation

