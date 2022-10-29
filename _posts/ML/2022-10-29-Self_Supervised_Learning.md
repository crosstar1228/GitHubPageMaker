---
layout: post
current: post
cover:  assets/built/images/deeplearning.png
navigation: True
title : Self-Supervised learning 에 대한 고찰
date: 2022-08-11 11:00:00
tags: [ML]
class: post-template
subclass: 'post tag-ML'
author: crosstar
use_math: true
---


> Self- supervised learning에 대한 개념을 정립하고 싶어 이 포스팅을 하게되었다. 

### Self-supervised learning
- 일반적으로 unlabelled data로 representation을 학습하는 경우를 말함.

### 왜 unlabelled data를 학습하나?
- represestation을 적극적으로 학습하는 게 downstream task에 적용하는 데 도움이 됨
- 실제 labelled data는 거의 없으니까.. 이렇게 학습하는 게 도움되지

### 어떤 유형들이 있나?
- Contrastive learning : 문장 여러개를 학습시켰다면 , 문장 간 관계를 학습
- Self-prediction : 문장내에 앞부분이 주어졌을때 뒷부분은 예측하는 모델
- Autoregressive modelling : 주어진 time series data의 앞부분들을 고려하여 다음 t 시점의 data를 예측


## Reference
- https://papers.nips.cc/paper/2014/file/17e23e50bedc63b4095e3d8204ce063b-Paper.pdf