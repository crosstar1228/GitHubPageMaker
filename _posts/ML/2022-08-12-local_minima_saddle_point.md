---
layout: post
current: post
cover:  assets/built/images/deeplearning.png
navigation: True
title: Paper Review - Identifying and attacking the saddle point problem in high-dimensional non-convex optimization
date: 2022-08-11 11:00:00
tags: [ML]
class: post-template
subclass: 'post tag-ML'
author: crosstar
use_math: true
---


> Keyword : Saddle Point, SFN(Saddle-Free Newton Method) SGD


![](https://velog.velcdn.com/images/crosstar1228/post/3666f71f-bc42-4c8a-baf5-4ca4cb767c30/image.png)
### Conclusion
1) 고차원의 non-convex function에서는 포괄적으로(generically) saddle point가 문제되는 경우가 많다
2) 고차원의 non-convex function에서는 대체로 local minima 문제는 통계적/경험적으로 매우 드문 경우이다
3) 이에 따라 일반화된 trust region 방법이 개발됨
   1) 도함수가 아닌 신뢰 지역(trust region)의 모양을 감지
   2) 곡률 정보를 알 수 있음
### Saddle point 에서 벗어나기
4) Saddle-Free Method : Hessian 값의 역으로 절댓값의 gradient value를 재조정
    - 이 방법으로 Gradient Descent와 Newton Method를 적절이 섞어 사용함으로서 빠르게 saddle point에서 벗어날 수 있음   

## Reference
- https://papers.nips.cc/paper/2014/file/17e23e50bedc63b4095e3d8204ce063b-Paper.pdf