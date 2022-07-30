---
layout: post
current: post
cover:  assets/built/images/deeplearning.png
navigation: True
title: Generative Model의 신흥강자, Diffusion Model!
date: 2022-07-29 11:00:00
tags: [ML]
class: post-template
subclass: 'post tag-ML'
author: crosstar
use_math: true
---

### Diffusion Model
- Markov Chain 을 사용한 Latent variable model
- prior로부터 posterior를 얻기 위하여 x1,x2, xT 의 각 time point 별 latent varible에 noise를 더해가는 구조
- 결과적으로 Gaussian noise를 띠게 됨
- 이의 역변환 과정으로 새로운 data를 생성

### Benefits
- scalability
- parallelizabliity

### process
- forward process
- reverse process

### objective function
log likelihood를 사용하며, 초기 이미지의 확률분포와 복원된 이미지의 확률분포 간 KL Divergence

## Reference
- https://www.assemblyai.com/blog/diffusion-models-for-machine-learning-introduction/
- https://arxiv.org/pdf/2006.11239.pdf