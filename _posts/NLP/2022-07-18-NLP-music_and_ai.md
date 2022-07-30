---
layout: post
current: post
cover:  assets/built/images/music_note.jpg
navigation: True
title: Music Generation and AI, present and future
date: 2022-07-18 11:00:00
tags: [nlp]
class: post-template
subclass: 'post tag-ML'
author: crosstar
---


## 목차
- [music & ai 역사](https://velog.io/@tobigsvoice1516/5%EC%A3%BC%EC%B0%A8-MUSIC-COMPOSITION-WITH-DEEP-LEARNING-A-REVIEW
)
- [OpenAI - JukeBox](https://openai.com/blog/jukebox/) [[Github](https://github.com/openai/jukebox/)]
- Datasets

## AI Music Genration의 시초
- 90년대 David Bowie 의 Verbasizer (앱)
- 단어를 임의로 재배치하여 음악 가사에 사용될 수 있도록 재조합하는 앱이었음

- 2016년 Sony의 App Flow Machine
  - 비틀즈 스타일 멜로디를 창조해 냄
### Music Generation 도 크게 다르지 않아
- 머신러닝에서 모델은 다량의 데이터를 학습하고 그 안에서 '패턴'을 찾아냅니다. 
- Music Generation에서는 그 패턴이 Chord, Tempo, lengths, note 간 관계성 등이됩니다. 
- 
### Symbolic approach, Non-symbolic approach

## Music Generation의 고질적인 문제 1 : LONG TERM DEPENDENCY
- 해결법 1 : autoencoder로 저차원 space로 mapping
  - 불필요한 정보를 버리게 됨
  - 이후 upsampling
- MuseNet : midi data 기반 많은 양의 데이터 학습
- Transfomer 계열 모델로 학습

### 아이디어 : 
o learn a lower-dimensional encoding of the audio with the goal of losing the less important
information but retaining most of the musical information
## 문제 2 : Diversity(variation)

### JukeBox[[Paper](https://arxiv.org/abs/2005.00341)]
- long context 를 autoregressiveTransformer 이용한 multi-sclae VQ-VAE로 해결
- 
## Lyric Conditioning
- 노래의 duration에 linear 하게 가사의 문자들을 align하는 방법
- 가사를 위한 encoder를 더하고, **music decoder로부터 의 query**로부터 **가사 encoder로부터의 key, value 쌍** 으로의 attetion layer를 적용함.

### VQ-VAE codebook collapse
- codebook에 mapping된 embedding vector들이 많이 쓰이지 않는 현상
- Random Restart:codebook vector 사용량이 평균이하로 떨어지면 , encoder output 중 하나로 다시 reset


https://magenta.tensorflow.org/perceiver-ar


### Sparse Transformer
- sparsifies the attention pattern by
  reshaping the input sequence into a **2-D sequence** of
  shape


## Google Deepmind (2022.06)
[[Paper](https://arxiv.org/abs/2202.07765)]
### Perceiver AR
- modality 에 대하여 agnostic(인지불능)인 구조
  - cross attention : long-range input -> small latent
  - maintaining end-to-end causal masking
https://soundraw.io/ 
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

