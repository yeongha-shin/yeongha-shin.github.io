---
layout: post
title: How to set window network drive and samsung printer on ubuntu 20.04
subtitle: window on ubuntu
gh-repo: yeongha-shin
gh-badge: [star, fork, follow]
tags: [OS]
comments: true
author: Yeongha Shin
---

# Ubuntu에서 window 네트워크 드라이브 연결하는 방법

우분투 운영체제에서 윈도우 네트워크 드라이브를 연결하는 것은 가능합니다. 이를 위해서는 cifs-utils 패키지를 설치하여야 합니다. 다음은 그 과정입니다:

먼저 터미널을 열고 다음 명령을 사용하여 cifs-utils를 설치합니다.

sql
Copy code
sudo apt-get update
sudo apt-get install cifs-utils
그런 다음에, 윈도우 네트워크 드라이브를 연결할 디렉토리를 생성합니다. 예를 들어, 홈 디렉토리 내에 windows_share 디렉토리를 생성할 수 있습니다.

bash
Copy code
mkdir ~/windows_share
이제 다음 명령을 사용하여 윈도우 네트워크 드라이브를 연결합니다. 네트워크 드라이브의 경로, 로그인 정보 및 마운트할 디렉토리를 지정해야 합니다.

php
Copy code
sudo mount -t cifs //<Windows 네트워크 드라이브 주소>/<공유 폴더> ~/windows_share -o username=<사용자이름>,password=<비밀번호>,uid=<사용자 ID>,gid=<그룹 ID>
여기서 <Windows 네트워크 드라이브 주소>는 연결하려는 네트워크 드라이브의 주소(예: 192.168.1.100), <공유 폴더>는 공유 폴더의 이름입니다. <사용자이름>과 <비밀번호>는 윈도우 네트워크 드라이브에 액세스하는 데 사용되는 자격 증명입니다. <사용자 ID> 및 <그룹 ID>는 해당 유닉스 사용자 및 그룹의 ID입니다.

모든 정보를 올바르게 입력한 후 Enter를 누르면 윈도우 네트워크 드라이브가 성공적으로 마운트됩니다. 이제 ~/windows_share 디렉토리에서 윈도우 네트워크 드라이브의 파일을 볼 수 있습니다.

이러한 방법으로 우분투에서 윈도우 네트워크 드라이브를 연결할 수 있습니다.

# Ubuntu 에서 samsumg network printer 설치하는 방법
[프린터 설치 방법 링크](https://kgkang.tistory.com/88)
[프린터 드라이버 다운로드 링크]([https://kgkang.tistory.com/88](https://www.samsungsvc.co.kr/solution/24168)https://www.samsungsvc.co.kr/solution/24168)

