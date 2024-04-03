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

# 1. conda 환경 설정
[https://github.com/wudongming97/RMOT]
이 글에서 확인해보면, RMOT는 MOTR의 아나콘다 환경 설정에 따라서 수행하면 된다고 써있다 ! 

# 2. pth 파일 생성
[https://github.com/fundamentalvision/Deformable-DETR]
weight파일 생성을 위해서는 Deformable DETR에서 모델을 기준으로 weight파일을 가져오면 된다고 되어 있는데, 이 말은
이 레포지토리를 기준으로 coco데이터 셋에서 tracning을 돌려서 생기는 pth파일을 가져와야 한다는 뜻이다 ! 
(pth파일이란 파이토치에서 학습을 통해서 생성한 학습 결과를 가중치에 대한 정보만 저장하는 것을 말한다)

하지만 이 스크립트 파일을 돌리려고 하니, GPU사이즈가 기존에 설정 되어 있는 것은 8개의 사이즈 였기 때문에, 내 사이즈에 맞게 1개로 변경했으며,
그리고 배치 사이즈를 변경하지 않았더니,
GPU memory error가 발생했는데 nvidia-smi를 통해서 내 실제 메모리를 확인했을 때 메모리 상의 문제가 존재하지 않았었다.
따라서 sh상에 batch_size라는 명령을 1로 변경하여 수행하였더니, 학습이 진행되기 시작했다 ! 


# 3. Traning 구동

# 4. Test 구동

