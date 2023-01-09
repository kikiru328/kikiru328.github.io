---
title : "[DL Specilization] DeepLearning - Binary Classification"
excerpt : "Google Coursera - DeepLearning Nerual Network"

categories: 
    - Google Coursera
tags: 
    - [DeepLearning, Study, Google, Coursera]

toc : true
toc_sticky : true

date : 2023-01-03
last_modified_dat : 2023-01-03
---
<font size="2"> <span style="color:gray">Introduction</span></font>  
<font size="1"> <span style="color:gray">Google Coursera에서 무료로 Deep Learning 수업을 하는 것을 알게되었다.  
복습과 예습, 그리고 부족한 부분을 채우기 위해서 이 수업을 들으려고 한다.  
수업은 모두 [Google Coursera](https://www.coursera.org/specializations/deep-learning)에서 진행하며, `DeepLearning.AI`에서 제공한다. </span></font>

# **Basic of Neural Network Programming**
---

<font size='2'>딥러닝의 기본에 대해서 학습합니다.</font>  

## **Binary Classification Programming**

머신러닝, 혹은 딥러닝을 훈련시키는 과정에서 사용되는 X 데이터와 Y 데이터의 설명이다.  
![](https://user-images.githubusercontent.com/60537388/210516486-849e1d94-feeb-40a5-975f-de10388a428a.png){: align-center}

하나의 훈련 표본은 (x,y)로 구성되어 있다. 여기서 x는 x 차원을 가진 feature vector이며 y는 0 혹은 1 중 하나의 값을 갖는다.  
머신러닝에서 사용하는 Train 데이터, Test 데이터는 간략하게
Mtraing, Mtest 라고 정의한다.  

Train 데이터 내용에선, Label Vector 인 Y값을 제외한 X는 nx열을 m개로 행렬을 구성하고 있다 (nx, m).  
이는 `python`에서 아래와 같이 확인 할 수 있다.  
```python
X_train.shape
> (nx , m)
```
Label Vector인 Y 데이터는 단일 행으로 존재하기 때문에 (1 * m) 행렬을 갖고 있다.
```python
Y_train.shape
> (1, m)
```

## **Logistic Regression**  
로지스틱 회귀는 지도 학습 문제에서 결과값 Label Y가 0 혹은 1 인 경우 사용하는 학습 알고리즘이다.  

X 값에 따라 원하는 값은 \\(\hat{y}\\) (y hat) 이므로   
\\[\hat{y} = P(y=1 | x)\\]
X에 따라 \\(y=1\\)이 될 기댓값은 \\(0 \leqq \hat{y} \leqq 1 \\)이 될 것이다. 

Logistic Regression은 두 파라미터를 갖는데,  
\\(X\in R^{nx * m} \\)일 때,  
\\(w\in R^{nx} \\)와 상수 \\(b\in R \\)를 갖는다.  
따라 `Output` = \\(\hat{y} = w^{T}x + b\\)라고 볼 수 있다.  

하지만 `\\(w^{T}x + b\\)는 x에 따라 음수 혹은 1이상을 나타낸다.  
따라서 `Sigmoid` 함수를 사용하게 된다.  

\\[Z = (w^{T}x + b)\\]
\\[Sigmoid = \sigma(w^{T}x + b) = \sigma(Z)\\]
\\[\sigma(x) = \frac{1}{1+e^{-z}}\\]


위 함수로 `Sigmoid` 함수 그래프는 아래와 같다.  
![](https://user-images.githubusercontent.com/60537388/210531317-f609523f-b3ba-42ac-9ab3-56840a9316d6.png){: width="40%" height="40%" align-center}





