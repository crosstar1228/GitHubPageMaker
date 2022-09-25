---
layout: post
current: post
cover:  assets/built/images/music_note.jpg
navigation: True
title: Symbolic Music Representation - 1D, 2D 
Future Directions
date: 2022-09-13 11:00:00
tags: [nlp]
class: post-template
subclass: 'post tag-ML'
author: crosstar
---
> Music representation은 크게 Symbol domain 과 audio domain으로 나뉩니다. 그 중 midi 파일의 표현 방식이자, discrete한 representation을 가지는
> **Symbolic music generation**에 대해 알아봅시다. 

## Symbolic Music Domain
- discrete 하고 표현이 명확함
- dynamic 과 같은 악보 외적인 사항을 학습할 수 있음
- 특정악기에 customizing되어 있어서, 새로운 악기에 기존 modeling technique를 적용하는 것이 어려움

## 1D representation
- 일반적인 표현 방법
- note 간 관계 표현이 어려움(이전 note가 다음 note 시작까지 지속된다 등의 정보)

### 1. Event-Based
- Midi-like event
![](https://velog.velcdn.com/images/crosstar1228/post/063a5409-734b-4782-bde0-e7d71b66c7bb/image.png)

### 2. Sequence-Based
- pitch, duration, chord 와 다른 음악 정보를 여러 list형태로 표현


## 2D representation
- sampling time에 의해 note를 2D matrix로 표현
- 더 높은 resolution을 필요로 함
  - rhythm이 복잡해지는 등 time dimension이 높아지면 장기적 의존관계를 학습하기 어려움
### Piano Roll
![](https://velog.velcdn.com/images/crosstar1228/post/3856593a-eecb-410a-9ead-ff81f5893df4/image.png)


- Automatic Piano에 의해 영감을 받음
- (pitch 수 + resting state + holding state) * (resolution)모양
  - 높이는 일반적으로 130개
  - 너비는 일반적으로 
- 하나의 matrix는 하나의 track을 의미하며, 여러 개의 track은 여러 matrix로 표현됨
- pretty_midi 또는 Pypianoroll python toolkit이용하여 손쉽게 변환 가능
- 일반적으로 binary
  - 각 position은 note가 그 position에서 연주되고 있는지 아닌지를 표현


- note-off 정보가 없어서 16분음표 2개 반복과, 8분음표 하나를 같게 인식함
- 이를 개선하는 방법에는
  - hold replay
  - time step을 note beginning과 note end로 나눔
  - hold 를 표현하는 symbol인 '_' 를 사용(monophonic melody에만 가능)

- Conlon pianoroll : CNN에서 receptive field가 크지 않아도 되는 장점

## Reference
- A Comprehensive Survey on Deep Music Generation(2020)