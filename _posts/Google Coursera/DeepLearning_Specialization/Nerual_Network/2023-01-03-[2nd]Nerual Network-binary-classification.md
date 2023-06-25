---
title: "[DL Specialization] [1-2nd] Nerual Network - Binary Classification"
excerpt: "Google Coursera - Nerual Network Binary Classification"

categories:
  - CourseraDL
tags:
  - [Nerual Network, Study, Google,DeepLearning]

toc: true

toc_sticky: true

date: 2023-01-03T20:00:00-21:00
last_modified_at: 2023-01-03T20:00:00-21:00
---

<div class='notice' markdown='1'>
<b><font size='2'>Introduction</font></b>  
Google Coursera에서 무료로 Deep Learning 수업을 하는 것을 알게되었다.
복습과 예습, 그리고 부족한 부분을 채우기 위해서 이 수업을 들으려고 한다.<br>
수업은 모두 Google Coursera에서 진행하며, [Google Coursera - DeepLearning](https://www.coursera.org/specializations/deep-learning)에서 제공한다.

`이번내용은 [1-2]주차 입니다.`
</div>

# **<u>[Basic of Neural Network Programming]</u>**
Neural Network, 신경망을 구현시에 필요한 기술은 여러가지가 있지만, 대표적으로는 2가지로 구성된다.  
1. m개의 training set이 있으면, m개의 example을 사용시 for 반복문을 사용하지 않고 처리가 가능하지만, `Nerual Network를 구현시에는 전체 training set을 for 반복문을 사용하지 않고 처리를 한다.`
2. Nerual Network을 구현할때, Forward Propagation, 순전과 Backward Propagation, 역전 계산을 진행한다.
   
----------
# **<u>[Logisitic Regression as a Neural Network]</u>**
우리가 흔히 알고 있는 Logisitic Regression은 Neural Network와 비슷한 형태를 띄기에 설명이 편리하다.  
입력 데이터에 따라서 분류하는 것은 Binary Classification, 이진분류와 Mutliclass Classification, 다중분류로 나누어진다. 따라서 Logisitic Regression은 Binary Classification 이므로, Neural Network Binary Classification 구조로 설명이 가능하다.  

예를 한번 들어보자  

(고양이 그림)

위와 같이 고양이 데이터를 컴퓨터가 인지시, Binary Classification로서 고양이를 1, 아니면 0으로 Label을 출력하게 된다. 고양이 데이터는 \\(64px \times 64px \\), RGB값으로 3개의 채널이 분리된 행렬이 합쳐진 형태이다. RGB의 값들을 하나의 feature vector x 에 나열하면 \\(64 \times 64 \times 3\\) 의 차원으로 나타난다. 전체 차원은 12288차원이며, x의 차원을 의미하는 \\(n_x\\)는 12288이다.  

---------
## **<u>[Neural Network 표기법]</u>**
Nerual Network 설명에 들어가기 앞서, 우선 <u>표기법</u>을 알아보자.

<details>
<summary><font size='1'>수학표기법</font></summary>
<div markdown='1'>
\\(\mathbb{R} \\) : 실수(float)을 의미한다.
</div>
</details>  


1. \\((x,y)\\) \\(x \in \mathbb{R^{n_x}} \\) , \\(y \in \lbrace0,1\rbrace \\)  : 한 개의 example.
2. m training example : \\(\lbrace(x^{(1)}, y^{(1)}),(x^{(2)},y^{(2)}),\dots,(x^{(m)},y^{(m)}) \rbrace \\)
3. Training Set, Test set은 \\(m_{train}, m_{test} \\) 로 표기.
4. ***Vectorization*** 된 `모든 입력 x`를 나타내기 위한 `행렬`은 대문자 X로 표기. : ( \\(X \in \mathbb{R^{n_x\times m}} \\) )
   \\(\text{X = } \begin{bmatrix}\vert & \vert &  & \vert \\\ x^{(1)} & x^{(2)} & \dots\ & x^{m} \\\ \vert & \vert &  & \vert \end{bmatrix} \\)
5. output label `y` 또한 `행렬` 구성이 되며, 대문자 Y로 표기. : ( \\(Y \in \mathbb{R^{1\times m}} \\) )
   
---------

## **<u>Logisitic Regression</u>**
Logisitic Regression은 다음과 같이 정의된다.  
<br>
\\[\text{Given }x,\text{want }\hat{y} = P(y = 1|x), x \in \mathbb{R^{n_x}} \\]  
<details>
<summary><font size='1'>수학표기법</font></summary>
<div markdown='1'>
\\(\hat{y} \\)   : y hat. y가 1이 될 수 있는 확률.
</div>
</details>  
<br>
위 수식을 설명하면, <u>주어진 input x 에 대해서 y가 1이 될 수 있는 확률을 구하는 것이다.</u>  
그리고 Output의 parameter는 \\(w \in \mathbb{R^{n_x}} \\) 와 \\(b \in \mathbb{R} \\) 이므로 아래와 같다.  
<br>
\\[\text{output} \hat{y} = w^Tx + b \\]  
<br>
하지만 Logisitic Regression은 Binary Classification에 효과가 뛰어나지는 않다.  
이진 분류는 0과 1로 구분되어야 하지만, Logisitic Regression에 따르면 y의 값이 1보다 클 수도 있으며, -1 이하로 값이 도출 될 수 있기 때문이다.  

따라서 이를 해결하기 위해 sigmoid function 이용하게 된다.
(sigmoid)
sigmoid function은 다음과 같다.  
<br>
\\[\sigma(z)=\frac{1}{1+e^{-z}}, \begin{aligned}\text{if }z \text{ is large, }\sigma(z) \approx \frac{1}{1+0} = 1\\\ \text{if }z \text{ is small, }\sigma(z) \approx \frac{1}{1+\infty} = 0 \end{aligned} \\]
<br>
따라서 Logisitic Regression의 Output은 다음과 같이 사용된다.  
<br>
\\[\text{Output}\;\hat{y} = \sigma(\underbrace{w^{T}x + b}_{z}) \\]
<br>

---------
## **<u>[Logisitic Regression Cost Function]</u>**
가중치 \\(w,b \\) parameter를 학습시키기 위해 Cost Function, 비용 함수를 정의해야한다.  
\\(x^{(i)},\, y^{(i)},\, z^{(i)} \\) 로 정의가 되며, \\(i\,\\)는 traning example이다.

Logistic Regression를 다시 정리하면 다음과 같다.  
<br>
\\[\hat{y} = \sigma{(w^{T}x + b)},\; \text{where}\, \sigma{(z)} = \frac{1}{1+e^{-z}} \\]

\\[\text{Given}\, \lbrace(x^{(i)},x^{(2)}), \dots, (x^{(m)},y^{(m)})\rbrace,\; \text{want}\, (\hat{i}) \approx y^{(i)} \\]
<br>

그리고 Loss function으로 \\(\mathscr{L}(\hat{y}, y)=\frac{1}{2}(\hat{y}-y)^2\\)를 사용할 수 있다. 하지만, convex, 볼록한 부분이 있지 않기에 <u>Local Optima, 국소 최적 <span style='color:gray'><font size='2'>(Parameter가 국소 최적에 빠져 더이상 개선이 되지 않음)</font></span>에 빠질 가능성이 높기 때문에 적합하지 않다.</u> 따라서 `Convex`한 최적화 Loss function을 정의해야 한다.  
<br>
\\[\mathscr{L}(\hat{y}, y)=-(y \log \hat{y}+(1-y) \log (1-\hat{y}))\\]
<br>  
정의된 loss function이 Binary Classification에 적합한 이유는 아래와 같다.  
<br>
\\[\begin{matrix}(\text{if}\,y = 1 )&:\,\mathscr{L}(\hat{y}, y)\,=\,&-\log\hat{y}\; \leftarrow\; \text{want}\,\log{(\hat{y})}\, \text{large,want}\, \hat{y}\,\text{large} \\\ (\text{if}\,y = 0 )&:\,\mathscr{L}(\hat{y}, y)\,=\,&-\log1-\hat{y}\; \leftarrow\; \text{want}\,\log{(1-\hat{y})}\, \text{large,want}\, \hat{y}\,\text{small}\end{matrix}\\]
<details>
<summary><font size='1'>수학표기법</font></summary>
<div markdown='1'>
\\(\mathscr{L}(\hat{y}, y)\\)  : \\(y\\)에 대한 \\(\hat{y}\\)의 손실함수 값.
</div>
</details>
<br>
위에서 정의한 loss function은 하나의 Example에 대해서 정의되었기 때문에 Cost function을 정의하면 다음과 같다.  
<br>
\\[\begin{matrix}Cost\,Function : J(w,b) &=& \frac{1}{m}\sum_{i=1}^{m}\mathscr{L}(\hat{y}^{(i)},y^{i}) \\\ &=& -\frac{1}{m}\sum_{i=1}^m[y^{(i)}\log(\hat{y}^{(i)})+(1-y^{(i)}\log(1-\hat{y}^{(i)}))] \end{matrix}\\]  
<br>
따라서 `Cost function은 parameter에 대한 비용`을 의미하게 된다. 그리고 모델을 학습하면서 parameter \\(w,b \\) 를 찾고 전체적인 학습 모델 cost, \\(J\\)를 줄이게 된다.

-------
## **<u>[Gradient Descent]</u>**
Cost function은 비용 함수이기 때문에, 최소화 되는 것이 적절하다. Cost Function을 최소화 시키는 \\(w,b \\)를 찾아야 하며, Cost Function의 그래프는 아래와 같이 볼록한 형태를 보인다.  
(사진)  
\\(w,b \\)를 상수라 가정하여 \\(J(w,b)\\)가 최소화 되는 **parameter** \\(w,b \\)를 찾아야 한다.  
\\(J\\), Cost Function은 여러 Local Optima가 있는 Non-convex가 **아닌** `convex function`에 있기 때문에 이러한 cost function을 사용하게 되는 것이다.  

**Gardient Descent**, 기울기 하강 알고리즘을 정리하자면
1. \\(w,b \\)를 초기화 한다. (0 혹은 랜덤)
2. 기울기가 가장 높은 방향으로 내려가며 최소값을 찾는다.

2차원 그래프를 그리기 위해서 b 값을 생략하고 그리면 다음과 같다.  
(그래프)  
Global Optima 전역 최솟값을 찾기 위해 Gradient Descent를 진행하게 된다.  
<br>  
\\[\begin{matrix}Repeat\;&\lbrace& \\\ &w& := w - \alpha\underbrace{\frac{dJ(w)}{dw}}_{dw} \\\ &\rbrace& \end{matrix}\\]  
<details>
<summary><font size='1'>수학표기법</font></summary>
<div markdown='1'>
\\(:=\\)  > 업데이트.
</div>
</details>
<br>
미분항이 \\(dw\\)라면 \\(w:= w-\alpha dw\\)로 나타낼 수 있다. 여기서 \\(\alpha\\)는 Learning Rate \\(\mathbb{R}\\) 이다.  
우측을 기준으로 Gradient Descent을 시작하면 미분항 dw는 그 지점으로 기울기 (\\(\mathbb{R}\\)이다. 
\\(\alpha\\)값도 \\(\mathbb{R}\\), 미분항도 양수이기에 \\(w\\)의 값은 점점 감소하여 <u>Global Optima로 향하게 된다.</u>
왼쪽을 기준으로 Gradient Descent을 시작하면 기울기는 `음수`로 지정되어 \\(w\\)는 증가한다.
따라서 \\(w\\)가 증가함에 따라 Global Optima를 향하게 된다.  

지금까지는 Gradient Descent에서 \\(b\\)를 0으로 초기화하여 진행하였다. Logisitic Regression은 \\(w, b\\) 두 개의 parameter가 존재하기에, \\(J(w,b)\\)에 대한 Gradient Descent는 다음과 같다.  
<br> 
\\[\begin{matrix}Repeat\;&\lbrace& \\\ &w& := w - \alpha\frac{\partial J(w,b)}{\partial w} \\\ &b& := b - \alpha\frac{\partial J(w,b)}{\partial b} \\\ &\rbrace& \end{matrix}\\]  
<details>
<summary><font size='1'>수학표기법</font></summary>
<div markdown='1'>
\\(\partial\\)  : 미적분학 표기법에 따르면 한개의 변수에 대한 미분은 \\(d\\), 두 개 이상의 변수는 \\(\partial\\)표시를 사용.
</div>
</details>
<br>

-------------
### **<u>[ + 참고 : Derivatives]</u>**
비전공자이고, 수학을 크게 잘하는 편이 아니였기 때문에 미분에 대해서 정리해봤습니다.
미분은 크게 얘기를 하면, 함수 내의 `기울기`를 구하는 것으로 생각하면 쉽습니다.  
(그래프)  
위와 같이 2차원 선형 그래프시, <u>x값의 변화에 따른 y값의 변화는 `기울기`</u>를 의미하는데  
만약 x축 a이 2일 경우 함수값에 의거하여 y값이 6이 될 것입니다.  
그렇다면 a 가 2.001로 증가했을 경우에는 y값은 6.003 로 증가하다면, 
x값 증가 변화량 0.001이 y값 증가 변화량 0.003 의 변화가 일어났기에
0.001 -> 0.003, `총 3배`가 이루어졌음으로 확인 할 수 있습니다.  
이는 곧 `기울기가 3`이라는 뜻이고 함수로 정의하자면 아래와 같습니다.  
<br>
\\[\frac{df_{(a)}}{da} = 3\\]  
<br>
이 과정을 `미분`이라고 합니다.

----------
## **<u>[Computation Graph]</u>**
Nerual Network은 계산을 Forward Propagation(순전), Backward Propagation(역전)으로 구성된다.  
계산 그래프를 그려보면 쉽게 알 수 있다.  

손실 함수 J가 아래와 같이 예를 들면,  
<br>
\\[J(a,b,c) = 3(a+bc)\\]
<br>
이 함수를 계산할 수 있는 아래와 같은 절차가 있다고 가정해보자.
\\[\begin{matrix} &u\,=& bc \\\ &v\,=& a+u \\\ &J\,=& 3v \end{matrix} \\]
이 3가지 절차를 `Computation Graph`로 그리면 다음과 같다.  

(그림)

만약 \\(a=5,\;b=3,\;c=2\\)라면 \\(u=6,\;v=11\\)으로 \\(J\\)는 곧 33이 된다.

특정 값에 대한 변수가 있는 경우 (여기선 \\(u, v\\)) 계산 그래프로 보면 쉽게 알 수 있다.  
현재의 계산은 Forward Propagation 선전 계산이다.  
그렇다면 Backword Propagation 역전 계산은 어떨까?  

----
## **<u>[Derivatives with a Computation Graph]</u>**
(그림)

Forward Propagation 계산 값이 적혀진 Computation Graph이다.
미분을 통해서 \\(da,\,db,\,dc\\) 값을 구해보자.
Backward Propagation 계산 절차는 Forward Propagation 계산의 절차의 `정 반대`이기 때문에 \\(J\\)의 \\(v\\)에 대한 미분을 먼저 구해야한다.  

\\(J\\)는 \\(v\\)의 `변화량`에 따라 값이 변화되기 때문에
\\(J = 3v\\)일 때,
\\(v = 11\\)이 되고, \\(v=11.001\\) 이 되면 \\(J=33.003\\)이 된다.  
따라서 \\(dj/dv\\)는 `3`이 된다.  

그 다음 \\(a\\)를 구하기 위해 \\(\frac{dj}{da}\\)를 구해야한다.  
\\(v\\)는 \\(a\\)의 변화량에 따라 값이 변화되기 때문에,  
\\(a = 5 \rightarrow 5.001\\)
\\(v = 11 \rightarrow 11.001\\) 이므로 \\(a\\)의 변화량은 \\(v\\)의 변화량을 `1배` 증가시키기 때문에 \\(\frac{dv}{da}=1\\)이며,
\\(j = 33 \rightarrow 33.003\\) 이므로 \\(a\\)의 변화량은 \\(j\\)의 변화량을 `3배` 증가시키게 된다.  
따라서 \\(\frac{dj}{da}=3\\) 이 되는 것이다.

\\(a\\)가 \\(v\\)에 영향을 주어 J까지 영향을 주는 것, Derivatives에서는 이런 상황을 `chain rule(연쇄 법칙)`이라고 정의한다. 
이를 한 문장으로 \\(a\\)값 변화가 \\(v\\)의 변화량 \\(x\\) \\(v\\)값 변화가 \\(j\\)의 변화량 이며 아래와 같은 공식이 된다.  

실제 미분항들을 표기시 \\(d_{var}\\)라고 정의한다. \\(d_{var}\\)는 \\(var\\)값 변화시 최종 결과값 \\(J\\)의 변화량이며, \\(\frac{dj}{dvar}\\)을 의미한다.  
따라서 \\(\frac{dj}{da}\\) 는 \\(da\\). \\(\frac{dj}{dv}\\)는 \\(dv\\)이다.
<details>
<summary><font size='1'>수학표기법</font></summary>
<div markdown='1'>
\\(var\\)  : variable, 변수이름
</div>
</details>

이와 같은 방법으로 \\(du,\,db,\,dc\\)를 구할 수 있다.

-----
## **<u>[Logistic Regression Gradient Descent]</u>**
Logisitic Regression에서 Gradient Descent를 적용하기 위해 미분시 방법이다.

이전에 Logistic Regression을 통해서 다음과 같은 식을 보았다.  
(블로그)
\\(x1,\,x2\\) 두가지의 feature만 존재한다고 가정했을때,  
Computation Graph는 아래와 같이 \\(z,\,\hat{y},\,\mathscr{L}\\)을 Front Propagation 절차로 계산할 것이다.

Gradient Descent하기 위해 Back Propagation 절차로 계산하려면  Loss 함수 \\(\mathscr{L}(a,y)\\)를 \\(a\\)에 대해서 미분한 값 \\(da\\)를 구해야 한다.  
<br>
\\[da = \frac{d\mathscr{L}(a,y)}{da} = -\frac{y}{a} + \frac{1-y}{1-a} \\]
다음 \\(dz\\)를 구하고  
<br>
\\[\begin{matrix}dz &=& \frac{dL}{dz} \\\ &=& a\,-\,y \\\ &=& \frac{dL}{da}\frac{da}{da} \end{matrix}\\]

[dL / dz = a - y 가 되는 이유](#--참고-dlay--dz--a---y-로-도출되는-이유)  

<br>
마지막 단계에서는 \\(w\\)와 \\(b\\)에 대한 변화량을 게산해야 한다.  
\\(dw_{1}\\) 즉 \\(\frac{dl}{dw_{1}}\\) 와 \\(dw_{2}\\), \\(db\\)를 구하면 다음과 같다.  
\\(dw_{1}\,=\,x_{1}dz\quad dw_{2}\,=\,x_{2}dz\quad db=dz\;\\)이다.
위 공식들을 사용해서 w와 b는 다음과 같이 업데이트가 된다.  
\\[\begin{matrix}w1\,&:=&\,w_{2}-\alpha dw_{1} \\\ w1\,&:=&\,w_{2}-\alpha dw_{2} \\\ b\,&:=&b-\alpha db\end{matrix} \\]

-------------
## **<u>[Gradient Desent of m example]</u>**
모든 example에 대해서 Gradient Desent를 적용해야한다. 따라서 \\(^{i}\\) 를 추가해서 다음과 같이 수식을 정리하게 된다. 그리고 각각의 training example에 대해 \\(dw_{1}^{(i)},\;dw_{2}^{(i)},\;db^{(i)}\\) 를 구할 수 있다.  
<br>
\\[J(w,b)=\frac{1}{m}\sum_{i=1}^{m}\mathscr{L}(\hat{y}^{(i)},y^{(i)})\\]
<br>
위 Cost function을 \\(dw_{1}\\)으로 미분하면 다음과 같다.  
<br>  
\\[\frac{\partial}{\partial w_{1}}J(w,b)=\frac{m}{1}\sum_{i=1}^{m}\underbrace{\frac{\partial}{\partial w_{1}}\mathscr{L}(\hat{a}^{(i)},\hat{y}^{(i)})}_ {dw_{1}^{(i)}}\\]  
<br>
각 Example의 \\(dw_{1}\\)을 구하고 평균치를 구하면, Gradient Descent에 바로 적용이 가능하다.  
Gradient Descent를 코드(와 비슷하게)로 구현하면 아래와 같다.  

~~~python
J = 0, dw1 = 0, dw2 = 0, db = 0
for i = 1 to m :
    z^(i) = w^Tx^(i) + b
    a^(i) = sigma(z^(i))
    J += -[y^(i)log yhat^(i) + (1-y^(i))log(1-yhat^(i))]
    dz^(i) = a^(i)(1-a^(i))
    dw_1 += x_1^(i)(1-a^(i))
    dw_2 += x_2^(i)dz^(i)
    db += dz^(i)
J = J/m, dw_1 = dw_1/m, dw_2 = dw_2m, db = db/m
~~~

<details>
<summary><font size='1'>어려우면 확인..</font></summary>
<div markdown='1'>
(수식)
</div>
</details>
<br>
현재는 feature가 2개이기지만, 앞으로 feature 개수가 많아지면 그 만큼 계산을 해주어야 한다.  
그리고 계산된 미분값들을 사용해 \\(w,b\\)가 업데이트 된다.

딥러닝에서는 코드에 for 문이 있을 경우 비효율이 증가하기 때문에, 대규모 빅데이터 학습시 vectorization, 벡터화를 이용해 for문을 제거한다.  
<!-- Vectorization는 다음 장에서 알아보자. -->

----
### **<u>[ + 참고: dL(a,y) / dz = a - y 로 도출되는 이유]</u>**
계산을 수식을 확인해보면,  
\\(\frac{d\mathscr{L}(a,y)}{dz} = a-y\\) 수식을 볼 수 있다.  
왜 이렇게 되는지 수식으로 알아보자. ~~사실 몰라도..뭐..~~  

\\[dz = \frac{d\mathscr{L}}{dz}=\frac{d\mathscr{L}(a,y)}{dz}=\frac{d\mathscr{L}(a,y)}{da}\times\frac{da}{dz}\\]

\\(\begin{align}\tag{1} \frac{d\mathscr{L}}{da}&=& \mathscr{L}(a,y) \\\ &=&-(y\times\log(a)+(1-y)\log(1-a) \\\ &=& -y\times\frac{1}{a}-(1-y)\times\frac{1}{1-a}\times-1 \\\ &=& -\frac{y}{a} +\frac{1-y}{1-a} \\\ &=& \frac{-y(1-a)}{a(1-a)}+\frac{a(1-y)}{a(1-a)} \\\ &=&\frac{-y+ay+a-ay}{a(1-a)} \\\ &=& \frac{a-y}{a(1-a)} \end{align}\\)

\\[\tag{2} \frac{da}{dz} = \frac{d}{dz}\underbrace{\sigma(z)}_{a} = \sigma(z) \times (1-\sigma(z)) = a(1-a) \\]

\\[\tag{3} \frac{d\mathscr{L}}{dz} = \frac{d\mathscr{L}}{da}\times\frac{da}{dz} = \frac{a-y}{a(1-a)}\times a(1-a) = a-y\\]


```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```