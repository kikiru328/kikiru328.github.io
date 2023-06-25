---
title: "[DL Specialization] [1-1nd] Neural Network - Introduction"
excerpt: "Google Coursera - Nerual Network"

categories:
  - CourseraDL
tags:
  - [Nerual Network, Study, Google, DeepLearning]

toc: true
toc_sticky: true

date: 2023-01-03T14:00:00-15:00
last_modified_at: 2023-01-03T14:00:00-15:00
---
<div class='notice' markdown='1'>
<b><font size='2'>Introduction</font></b>  
Google Coursera에서 무료로 Deep Learning 수업을 하는 것을 알게되었다.
복습과 예습, 그리고 부족한 부분을 채우기 위해서 이 수업을 들으려고 한다.<br>
수업은 모두 Google Coursera에서 진행하며, [Google Coursera - DeepLearning](https://www.coursera.org/specializations/deep-learning)에서 제공한다.

`이번내용은 [1-1]주차 입니다.`

</div>

# **Neural Network and Deep learning**

---

<font size='2'>딥러닝의 기본과 신경망 트레이닝에 대해서 학습합니다.</font>

## **What is a Nerual Network**

Deep learning이라는 단어는 `신경망 트레이닝`을 일컫는 말이다.  
집값 예측을 예시로 들면 다음과 같다.

![](https://user-images.githubusercontent.com/60537388/210482955-1f4bcefb-1847-492c-a010-99cb3173a858.png){: width="400" height="400" align="left" }

![](https://user-images.githubusercontent.com/60537388/210483046-5cfb8c86-72ca-4757-a221-754f300d04ce.png){: width="400" height="400" align="center" }  
<br/>

집 크기와 집값의 관계에서 파란색 선형함수는 우측의 node가 구현하게 된다. 이 것이 가장 기초적인 신경망의 단계이다.  
이 처럼 단순한 신경망의 단계가 여러 변수와 함께 적용이 되면 다음과 같다.  
![](https://user-images.githubusercontent.com/60537388/210484141-416e5075-d0dc-4906-ab70-23e206459e63.png){: align="center" }
<br/>
좌측 총 4개의 변수가 숨겨진 노드(은닉층)에 특성을 부여하고, 특성에 맞는 마지막 노드(출력층)에서 결과를 예측할 수 있다. 모든 노드에 특성이 연결되어 있어 `신경망`이라고 불린다.

## **Supervised Learning with Neural Network**

지도 학습에서는 일부 입력값 x와 출력값 y에 대한 함수 매핑을 의미  
따라 무엇이 X, Y 가 되는지 면밀히 살펴보고 정해야한다.

지도학습 딥러닝은 다음과 같다

|     Input(x)      |       Output(y)       |    Application     |      Type       |
| :---------------: | :-------------------: | :----------------: | :-------------: |
|   Home Features   |         Price         |    Real Estate     |  Standard N.N   |
|   Ad, user info   |   Click on ad (0/1)   | Online Advertising |  Standard N.N   |
|       Image       |    Object(1,,1000)    |   Photo tagging    |       CNN       |
|       Audio       |    Text transcript    | Speech recognition |       RNN       |
|      English      |        Chinese        |  Machine Learning  |       RNN       |
| Image, Radar info | Postion of other cars | Autonomous driving | Cusuomal Hybrid |

```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```