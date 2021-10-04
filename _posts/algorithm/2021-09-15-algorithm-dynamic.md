---
layout: post
current: post
cover:  assets/built/images/algorithm.png
navigation: True
title: 프로그래머스 코딩테스트 -  'N으로 표현' 문제 해설 (dynamic programming)
date: 2021-10-04 16:40:00
tags: [algorithm]
class: post-template
subclass: 'post tag-python'
author: crosstar
---

{% include algorithm-table-of-contents.html %}


[문제 풀기](https://www.welcomekakao.com/learn/courses/30/lessons/42895#)


> dynamic programming을 활용하는 문제입니다!
> ## 🧐keypoint
> - 사용횟수가 1 일때, 사용횟수가 2 일 때 경우의 수들을 정리해 보는것이 **첫번째 아이디어**이다. 
> - 사용횟수가 2 인 집합은 사용횟수 1,사용횟수 1 인 집합을 합쳐 만들어낼 수 있다. 횟수 2,3,4 모두 마찬가지다.
> - N을 9번 이상 쓰지 않으니 경우의 수가 그리 많지는 않다.

### N = 3이라고 가정할 경우
- 1회 조합으로 만들어 낼 수 있는 수 : 3
- 2회 조합으로 만들어 낼 수 있는 수 : 6(3+3), 1(3/3), 9(3*3), 33(연속)



{% gist crosstar1228/e42e3d241997ab6b3c85dc6a3ae242c6 %}

### Reference
- https://www.hamadevelop.me/algorithm-n-expression/