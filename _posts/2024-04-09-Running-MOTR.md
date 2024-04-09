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
'''
conda create -n deformable_detr python=3.7 pip
'''

'''
conda activate deformable_detr
'''

'''
pip install -r requirements.txt
'''

( 이 부분은 내가 추가한 부분이다. GPU not supported라는 오류가 나와서 )
'''
conda install pytorch torchvision -c pytorch
'''

(그랬더니 이제는 이런 오류가 나오기 시작했다)
Traceback (most recent call last):                                              
  File "setup.py", line 69, in <module>                                         
    ext_modules=get_extensions(),
  File "setup.py", line 47, in get_extensions
    raise NotImplementedError('Cuda is not availabel')
NotImplementedError: Cuda is not availabel

'''
conda install pytorch torchvision cudatoolkit -c pytorch
'''
이렇게 설치했어야 하는 모양이다

ImportError: cannot import name '_NewEmptyTensorOp' from 'torchvision.ops.misc'
이제는 이런 오류가 생기기 시작했다.

그래서 이렇게 해결했다
[https://velog.io/@sjj995/ImportError-cannot-import-name-NewEmptyTensorOp-from-torchvision.ops.misc]

ModuleNotFoundError: No module named 'MultiScaleDeformableAttention'
그다음생긴 오류

알고보니 sh make.sh를 제대로 하지 못해서였고, 여기서 내가 추가적으로 해야 하는건 왜인지 모르겠지만 Cuda is not available이 나오는건
source ~/.bashrc가 안되어서 였다
그 이후에 sh make.sh를 하니 제대로 되었다 !

# 2. pth 파일 위치 설정
r50_motr_submit.sh에 대해서 ptr 경로 파일과, 그리고 main.py에 대해서 데이터 파일 위치에 대해서 경로 수정을 해주어야 한다
(그전에 FairMOT처럼 dataset 파일 디렉토리 구조를 변경해두어야 한다)





