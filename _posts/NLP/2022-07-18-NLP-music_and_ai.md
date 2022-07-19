---
layout: post
current: post
cover:  assets/built/images/deeplearning.png
navigation: True
title: Music Generation and AI, present and future
date: 2022-07-18 11:00:00
tags: [nlp]
class: post-template
subclass: 'post tag-ML'
author: crosstar
---


# 안녕
music & ai 역사
https://velog.io/@tobigsvoice1516/5%EC%A3%BC%EC%B0%A8-MUSIC-COMPOSITION-WITH-DEEP-LEARNING-A-REVIEW



https://openai.com/blog/jukebox/

[Github](https://github.com/openai/jukebox/)

## Music Generation의 고질적인 문제 1 : LONG TERM DEPENDENCY
- 해결법 1 : autoencoder로 저차원 space로 mapping
  - 불필요한 정보를 버리게 됨
  - 이후 upsampling
- MuseNet : midi data 기반 많은 양의 데이터 학습
- Transfomer 계열 모델로 학습
## 문제 2 : Diversity(variation)

### JukeBox[[Paper](https://arxiv.org/abs/2005.00341)]
- long context 를 autoregressiveTransformer 이용한 multi-sclae VQ-VAE로 해결
- 
## Lyric Conditioning
- 노래의 duration에 linear 하게 가사의 문자들을 align하는 방법
- 가사를 위한 encoder를 더하고, **music decoder로부터 의 query**로부터 **가사 encoder로부터의 key, value 쌍** 으로의 attetion layer를 적용함.
- 

https://soundraw.io/ -> ai는 아님
https://magenta.tensorflow.org/
https://www.aiva.ai/
-> 음악 작곡

https://towardsdatascience.com/generating-music-with-artificial-intelligence-9ce3c9eef806
https://topten.ai/music-generators-review/

Datasets
https://paperswithcode.com/task/music-generation

1. Sota models
   MuseGAN
   Melnet
   MidiNet

