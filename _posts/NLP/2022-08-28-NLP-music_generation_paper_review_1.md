---
layout: post
current: post
cover:  assets/built/images/music_note.jpg
navigation: True
title: A Comprehensive Survey on Deep Music Generation:
Multi-level Representations, Algorithms, Evaluations, and
Future Directions
date: 2022-08-27 11:00:00
tags: [nlp]
class: post-template
subclass: 'post tag-ML'
author: crosstar
---


## Abstract
- 딥러닝을 활용한 최근의 다양한 음악 작곡 TASK를 소개한 논문
  - DATASETS
  - MUSIC REPRESENTATION
  - EVALUATION METHOD
  - challenges & future directions

### Intro
- **음악은 언어와 같다.** 
  - 악보 : 음악  == 글 : 말


- Music Generation의 대분류 3개
![](https://velog.velcdn.com/images/crosstar1228/post/33ed8e71-a0d8-4853-9c90-c9f1940900dc/image.png)

  1. score generation
  2. performance generation add performance characteristics to scores
     - RENDERING performance
     - composing performance
  3. audio generation : convert score with performance characteristics into audio
     - assign timbre
     - directry generate music in audio

    그 중에서도 SCORE GENERATION이 가장 핫함

- style transfer 적용
  ![](https://velog.velcdn.com/images/crosstar1228/post/3a730a16-e14a-4174-8d27-05807196346f/image.png)


## History
- Iliac Suite : computer 로 만들어진 최초의 score
  - Markov chain 활용(Stochastic Model)

### Traditional Music Generation
1) rule-based
    - linguistic & grammar 활용
    - 음악마다 다른 rule 이 만들어져야 하는 단점
    - 
2) Probability model
   - semi-automatic 한 알고리즘에 Markov chain이나 이외의 기술을 태움
   - 원래의 data로부터 subsequence를 생성하지만, memory가 없어서 input에 따라 조건부 확률이 변동이 심함

3) Neural Network(RNN)
    - RNN으로 feature를 학습하여 단선율의 pitch와 duration을 학습
    - Gradient Vanishing으로 long-term dependency 학습 못하는 단점

### evloutionary
1) GenJam
2) Director Musices
3) Probablistic
   - hierarchical HMM
   - dynamic Bayesian networks

### sound modelling
- physical modeling
- acoustic modeling : signal generator 이용
  - oscillator, modulator, filters와 같이 waveform 조작을 위한 processors
  - 
- 
### lyrics
- 가사 포함 여부에 따라 music audio를 audio와 singing voice로 나눔.

## Deep Music Generation
- Google Magenta : [Melody RNN model](https://magenta.tensorflow.org/2016/07/15/lookback-rnn-attention-rnn)
- Anticipation-RNN : 사용자가 정의한 positional한 제약을 강요함.
- TP-LSTM-NADE and BALSTM : 병렬 RNN으로부터 다선율의 데이터셋에서 translation-invariance를 유지

## Score Generation: VAE, GAN, Transformer, ...
- MusicVAE : longterm dependency, interpolation & reconstruction 퍼포먼스 굳
  - coupled latent variable model
  - binary regularizer
- GAN
  - sequential data에는 학습에 어려움이 있음
  - CNN based GAN으로 개발
  - GAN-based MidiNet : Chord 에 condition되어 마디를 생성하는 알고리즘
  - MuseGAN : multi-track 다선율 음악을 생성하는 최초의 모델
    - 강화학습을 접목하여 RNN-based GAN 적용
- Transformer
  - REMI 
  - Transformer XL
  - 
## Performance Generation : 대부분 RNN



## Representation
1) symbol domain
   - discrete variable
2) audio domain
   - continuous variable

## Reference
- From artificial neural networks to deep learning for music generation: history, concepts and trends
- https://towardsdatascience.com/generating-music-with-artificial-intelligence-9ce3c9eef806
- https://topten.ai/music-generators-review/