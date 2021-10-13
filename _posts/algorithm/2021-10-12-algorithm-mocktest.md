---
layout: post
current: post
cover:  assets/built/images/algorithm.png
navigation: True
title: Lv1 - 프로그래머스 코딩테스트 '모의고사' 문제 해설 (stack,queue)
date: 2021-10-01 16:40:00
tags: [algorithm]
class: post-template
subclass: 'post tag-python'
author: crosstar
---


[문제 링크](https://www.welcomekakao.com/learn/courses/30/lessons/42840)


두 list로부터 hashing을 이용하여 완주하지 못한 1명의 선수를 return하는 문제.

## code

{% gist crosstar1228/86ab2d292ea7dce38da70b41b506d781 %}



### 잘못된 풀이
단순히 completion 리스트를 확인하고 participation에 없는 element를 반환할 경우, 동명이인 발생 시 문제를 처리하지 못한다.(오답)

### 풀이 1. sorting and zip()
sorted로 정렬 후  zip함수를 이용하여 짝이 안맞는 남은 경우를 return

### 풀이 2.hash() 이용
hash() 함수로 특정 주소를 hashing 한 후 남은 값에 mapping된 원소를 리턴.(주소 충돌이 있을 경우 문제가 될 소지가 있는 풀이.)

### 풀이 3. collections.Counter 로 차이 연산
