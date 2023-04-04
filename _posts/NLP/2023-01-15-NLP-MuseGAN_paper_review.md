---
layout: post
current: post
cover:  assets/built/images/music_note.jpg
navigation: True
title: MuseGAN paper review(2018)
date: 2023-01-15 11:00:00
tags: [nlp]
class: post-template
subclass: 'post tag-ML'
author: crosstar
---


### 기존 문제
1. 음악은 시계열 데이터이다.
2. 음악은 여러 track과 악기로 이루어져 있다.
3. 음악은 chord, arpeggio, melody로 이루어져 있다. -> polyphonic한 음악에서 시간 순으로 배열하는 게 쉽지 않음.

### 극복을 위해
1. Temporal modle을 위해, 2가지 방법을 제안한다. 
   1) 하나는 사람의 input 없이 음악을 쌩으로 generate한다
   2) 사람의 prior knowledge 주어졌을 시, track의 시간 구조를 따르도록 학습한다
2. track간 inter-dependency를 위해, pop music 작곡순서를 참고하여 3가지 방법을 제안한다.
    1) 각각의 private한 생성자로 트랙을 생성한다
    2) 하나의 generator로 함께 



## Reference
- From artificial neural networks to deep learning for music generation: history, concepts and trends
- https://towardsdatascience.com/generating-music-with-artificial-intelligence-9ce3c9eef806
- https://topten.ai/music-generators-review/