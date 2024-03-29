---
title : '[빅분기] 빅데이터분석기사 2장 정리본' 
excerpt : "빅데이터 실기 필기"
categories: 
 - BigData
tags: 
 - [BigData, Test]



toc : true
toc_sticky : true



date : 2022-11-20
last_modified_dat : 2022-11-20
---
<span style='color:gray'>Introduction<br></span>
빅데이터 분석 기사 실기 시험을 앞두고 필기를 정리합니다. 필기시험을 앞둔 분들도 참고하면 좋습니다.<br>
{: .notice}

## **<u>[⭐️⭐️⭐️ 데이터 전처리]</u>**
데이터 분석을 위한 `필수과정`으로 데이터를 정제한 뒤, 가공, 통합, 정리 변환을 통해 데이터 분석 변수를 처리하는 등의 작업으로 <span style='color:skyblue'><u>데이터 분석 결과의 신뢰도를 높이기 위한 과정</u></span>

## **<u>[데이터 정제]</u>**
> `정제` :
> 결측값, 잡음, 이상값 등 데이터 오류의 분석 작업 `전`에 처리  
> `결측값` :
> 분석 대상에서 제외 또는 보완 처리  
> `이상값` :
> 삭제, 대체, 스케일링, 정규화 등  

## **<u>[데이터 결측값]</u>**
> <b>`유형`</b>  
> `비무작위` :
> 결측값에 영향 미침  
> `무작위` :
> 연관은 있음. 결과에 영향 없음  
> `완전 무작위` :
> 연관도 없고 완전히 무관  
>  
> <b>`방법`</b>  
> `평균대체` :
> 대푯값으로 대체  
> `단순확률대체` :
> 단순확률값으로 대체  
> `보삽법` :
> 비슷한 시기, 다른 해의 데이터를 참고한 평균값으로  
> `평가치 추정` :
> 맥락적 행렬식 자료를 고려하여 원래의 값 추정  
> `다중 대치` :
> 결측치 추정을 통해 완성한 데이터셋 이용  
> `완전 정보 최대 우도법` :
> 최대우도 바탕으로 가중평균 구성  

## **<u>[데이터 이상값]</u>**

|          종류           | 내용                            |
| :---------------------: | :------------------------------ |
|          분산           | 정규분포 95.7% 외의 값          |
|        우도함수         | 우도확률 값 외의 값             |
| 근접이웃기반 이상치탐지 | 정상값 거리와 거리가 먼 값      |
|        밀도기반         | 상대적 밀도 값이 먼 값          |
|          군집           | 특정 군집에 속하지 않은 값      |
|      사분위수(IQR)      | 양쪽 말단 1.5분위수 벗어나는 값 |


## **<u>[변수선택]</u>**
종속 변수에 영향을 미칠 독립변수를 선택하는 과정을 의미.  
`머신러닝 알고리즘 학습속도 향상` `모델 해석 용이` `모델 정확도 향상` `과적합 감소, 성능 향상`

## **<u>[단계적 변수 선택 방법]</u>**
> `전진선택법` :
> 가장 많은 영향을 줄 것 같은 변수부터 추가 (AIC작은 놈)  
> `후진제거법` :
> 가장 적은 영향을 줄 것 같은 변수부터 제거 (AIC 큰 놈)  
> `단계적 방법` :
> 전진선택법, 후진제거법 둘다 사용해서 AIC 낮아지는 모델 완성

## **<u>[⭐️⭐️⭐️ 차원 축소]</u>**
변수의 수 증가로 차원이 커지면서 모델링 안좋아짐. <span style='color:skyblue'><u>차원의 저주</u></span>  
공간은 증가하는데 비해 데이터 수의 변화가 없을 경우 불필요한게 많으니 차원 축소 필요  
> `PCA 주성분분석` :
> 변수간 `상관관계`파악하고 `선형 연관성이 없는 저차원`으로 축소  
> `LDA 선형판별분석` :
> 지도학습을 통해 데이터 결정경계를 만들어 데이터 분류.  
> 다변량 정규분포를 따르는 데이터 분포. 파라미터는 평균과 공분산이어야 함.   
> `t-SNE t-분포 확률적 임베딩`:
> 고차원의 데이터 거리를 `보존`, 그 관계를 저차원으로 축소  
> 하나의 점을 선택하여 다른 점들 간의 거리를 측정한 뒤 이를 T분포 그래프에 표현  
> `SVD 특잇값 분해`:
> 행렬의 크기와 모양에 상관없이 적용할 수 있는 방법  

## **<u>[변수 변환]</u>**
범주형 데이터 변환 : 범주형 변수를 숫자로 변환  
연속 > 범주 : 연속형 데이터를 범주형으로  
비정형 데이터 변환 : 단어의 빈도수 등을 이용해 정형화  
더미 변수화 : 어떤 특징의 존재 여부를 1 또는 0  
스케일링 : <span style='color:skyblue'><u>최소-최대 표준화, 정규화</u></span>

## **<u>[클래스 불균형]</u>**
`여러 클래스 중 데이터 양에 큰 차이가 있는 경우 클래스 불균형이 있다고 함`
과소 표집 : 소수 클래스의 데이터 수 만큼 감소. <span style='color:skyblue'><u>데이터 손실 우려</u></span>  
과대 표집 : 다수 클래스의 데이터 수 만큼 증가. <span style='color:skyblue'><u>과접합 문제 발생 가능</u></span>  
`SMOTE` : `주변값을 기준으로 소수 클래스의 데이터 수를 증가하여 다수 클래스의 수와 동일하게 한다.`

## **<u>[EDA]</u>**
탐색적 데이터 분석 : 데이터를 이해하고 의미있는 관계를 찾아내기 위한 행동 등등 `그냥 데이터 분석하면서 시각화까지 하면 EDA`  
`저항성 강조` `잔차 계산` `변수의 재표현` `그래프를 통한 현시성`

## **<u>[데이터 탐색 개요]</u>**
데이터 파악 : 분석 대상이 되는 데이터에 대한 기술한 설명서 확인   

<u>탐색</u>  
조회 : 일부 관측치 조회, 개별 관측치 관찰  
구조 확인 : 데이터의 차원, 변수명, 변수 타입, 상위 관측치 등을 확인하여 데이터 구조를 간결하게 확인  
요약 : 데이터셋의 통계 요약량을 확인  
관계 맺기 : 현실의 데이터는 각각의 용도, 목적, 종류에 따라 각기 다른 테이블에 저장. `JOIN` 구문을 통한 병합  

## **<u>[JOIN 종류]</u>**
내부조인 : 교집합  
왼쪽 외부 조인 : 왼쪽 집합  
오른쪽 외부 조인 : 오른쪽 집합  
완전 외부 조인 : 왼 오른쪽 다  

## **<u>[상관분석과 상관계수  ]</u>**
> `상관분석` :
> 두 변수 사이에 선형적 관계를 가지고 있는지 분석하는 통계적 분석  
> `상관계수` :
> 두 변수의 선형 관계 정도를 나타내는 척도. <span style='color:skyblue'><u>피어슨 상관계수</u></span>

## **<u>[피어슨 vs 스피어만]</u>**
피어슨 : 연속형 변수 / 모수 검정  
스피어만 : `이산형, 순서형` / 비모수 검정  

## **<u>[기초통계량 추출 및 이해]</u>**
중심경향치 : 단일 값으로 전체 데이터를 대표할 수 있게 중앙에 위치한 데이터.  
> `평균` :
> 주어진 모든 데이터의 값을 더해 총합을 구하고 이를 데이터의 개수로 나눈 것  
> `중앙값` :
> 주어진 데이터의 값들을 오름차순 정렬했을 때 중간에 있는 값.  
> `최빈값` :
> 주어진 데이터 중에서 가장 많이 나오는 값

산포도 : 데이터의 흩어진 정도를 설명하는 통계치  
> `범위` :
> 최댓값 - 최솟값  
> `사분위수 범위` :
> IQR = Q3-Q1  
> `분산` :
> 편차를 제곱으로 총합하여 평균 낸 값  
> `표준편차` :
> 분산 값에 제곱근을 씌운 값  

왜도 : 데이터 분포의 비대칭성을 나타내는 지표 
> `왜도 > 0 ` :
> 오른쪽으로 꼬리가 김 (왼쪽에 데이터가 많음)  
> 최빈값 < 중앙값 < 평균  
> `왜도 < 0 ` :
> 왼쪽으로 꼬리가 김 (오른쪽에 데이터가 많음)  
> 평균 < 중앙값 < 최빈값  

첨도 : 데이터들이 분포의 중심에 어느정도 몰려있는가  
> `첨도 < 3` :
> 정규분포보다 완만한 분포  
> `첨도 == 3` :
> 정규분포와 유사한 분포  
> `첨도 > 3` :
> 정규분포보다 뾰족한 분포  

## **<u>[시각적 데이터 탐색]</u>**
히스토그램 : 연속형 변수 데이터의 도수 분포를 보여줌  
막대그래프 : 범주의 빈도를 직사각형 막대로 나타냄  
줄기-잎 그림 : 데이터의 처음 몇 자리수를 줄기, 나머지는 잎으로 그림  
상자그림 : 다섯 숫자 요약을 그린 그래프, `아웃라이어`처리에 유용

## **<u>[공간분석과 GIS]</u>**
공간분석 : 사람들이 관심을 가지는 공간 데이터를 `시각화`하여 인사이트를 얻는 분석 기법  
지리정보시스템 (GIS) : 지리 공간적으로 참조 가능한 모든 형태의 정보를 효율적으로 수집, 저장, 처리, 관리, 분석할 수 있게 설계된 컴퓨터의 하드웨어와 소프트웨어 및 지리적 자료, 인적 자원의 통합체.  
(GIS 구성요소 : `컴퓨터 시스템 / ` `GIS 소프트웨어 / ` `인력 / ` `데이터 / ` `인프라 `)

## **<u>[일변량 vs 이변량 vs 다변량]</u>**

|  분석종류  | 내용                                                                                                                                                  |
| :--------: | :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 일변량분석 | <span style='color:skyblue'><u> 가장 간단한 형태의 분석. </u></span>1개의 변수를 대상으로 패턴을 찾는 것이 목표. 평균, 중앙값, 최빈값, 분산 등을 조사 |
| 이변량분석 | 2개의 변수를 이용한 분석을 수행하며 두 변수 간의 관계를 주로 분석                                                                                     |
| 다변량분석 | 3개의 변수를 이용한 복잡한 형태의 분석, <span style='color:skyblue'><u>차원을 축소하건나 유사성, 근접성을 기준으로 분류함</u></span>                  |

## **<u>[다변량 분석]</u>**
상관분석 : 산점도 행렬을 그려 교차하는 변수 간의 관계를 보여주는 `산점도와 상관계수`를 파악  
다차원 척도법 : 객체 사이의 유사성 수준을 2차원 또는 3차원 공간에 점으로 시각화하는 분석기법 `유클리드 거리`를 주로 사용.  
(계량적 MDS : 유클리드 거리를 주로 활용해 데이터 간의 실제거리를 근접도로 이용하는 `전통적인 다차원 척도법`)  
(비계량적 MDS : `순서 정보`를 근접도로 이용하는 다차원 척도법)  
주성분 분석 : 데이터의 분포를 잘 설명함과 동시에 정보의 손실을 최소화하게 고차원의 데이터를 저차원으로 변환  
선형판별분석 : 어떤 그룹에 속할지를 판별하는 판별분석 기법으로 `다변량 데이터`에 판별 함수를 적용. `데이터의 클래스`분리를 최적으로 수행할 수 있게 데이터 축소.  

## **<u>[텍스트 마이닝]</u>**
텍스트 마이닝 : 다양한 문서 자료 내 비정형 텍스트 데이터에 자연어 처리 기술 및 문서 처리 기술을 활용해 `인사이트를 도출`하는 기술이다.  
자연어 처리 : 인간이 사용하는 언어(자연어)를 컴퓨터가 처리하고 분석할 수 있게 하는 작업이다. (NLP)
> `텍스트 마이닝 응용 분야` :
> 문야 요약, 문서분류, 문서 군집화, 특성 추출  
> `텍스트 마이닝 용어` :
> 코퍼스 : 분석 작업의 대상이 되는 대량의 텍스트 문서를 모아놓은 집합  
> 토큰화 : 구조화되어 있지 않은 문서를 단어 (토큰)으로 나누는 과정  
> 불용어 : 분석 프로세스에 있어 기여하는 바가 없는 단어  
> 어간 추출 : 단어 내 접사를 제거하고 다넝에서 의미를 담고 있는 어간을 분리하는 것  
> 표제어 추출 : 어간추출 + 품사까지 고려  
> 품사 태깅 : 문서 내 각 단어에 해당하는 품사로 태깅  
> 형태소 분석 : 단위 형태소를 분리한 후에 변형이 일어난 형태소의 원형 복구, 분리된 단어 형태소들로 부터 규칙에 맞는 연속된 형태소들을 구하는 과정  
> N-그램 : 연속된 N개의 단어 혹은 형태소 집합  
> 단어문서행렬 : 문서별로 나타난 단어의 빈도를 행렬 형태로 나타낸 것  
> TF-IDF : 특징 추출의 기법. 문서 내 특정 단어의 빈도와 문서 빈도의 역수를 곱한 값  
> 워드 클라우드 : 문서에 사용된 단어로 구성된 구름 의미지  (출현 빈도와 중요성을 효과적으로 표현)  
> 토픽 모델링 : 대량의 문서 집합에 존재하는 추사적인 토핑(주제)을 추출하는 통계적 모델링  
> 잠재 디리클레 할당 : 가장 대표적으로 사용되고 있는 토픽 모델링 기법으로 데이터의 차원을 축소하는데 용이.  
> bag-of-word : 단어의 순서는 토픽과 상관이 없으며 단어의 빈도만이 중요하다는 개념  

## **<u>[소셜 네트워크 분석]</u>**
소셜 네트워크 서비스 내 개인과 집단 간의 관계 및 상호작용을 모델링해 그것의 위상구조와 특성을 계량적으로 분석하고 시각화하는 방법론  

> `소셜 네트워크 분석방법론` :  
> 집합론적 방법 : 객체와 관계를 집합 관계쌍으로 표현  
> 그래프 방법 : 노드와 링크로 표현  
> 행렬 방법 : 행렬의 행과 열에 객체를 대칭적으로 배치하면서 행렬의 i,j 사이의 관계가 있고 없음을 1,0으로 표현  

> `네트워크 구조를 파악하기 위한 요소 - 중심성` :  
> 전체 네트워크에서 한 개체가 중심에 위치하는 정도를 표현하는 지표  
> 연결 정도 중심성 : 한 노드에 직접 연결된 다른 노드들의 수의 합으로 중심성을 측정  
> 근접 중심성 : 각 노드 간의 거리를 근거로 중심성을 측정  
> 매개 중심성 : 네트워크 내에서 중계자 역할의 정도로 중심성을 측정  
> 위세 중심성 : 연결된 노드의 중요성에 가중치를 두어 노드의 중심성을 측정  

> `네트워크 노드` :  
> 밀도 : 네트워크 내에 존재하는 노드 간의 연결 정도의 수준  
> 집중도 : 네트워크 전체가 한 중심을 집중되는 정도  
> 연결정도 : 노드에 연결된 관계의 수  
> 포괄성 : 한 네트워크 내 연결되지 않은 노드들의 수를 뺀 연결된 노드들의 비율. 포괄성이 높을수록 관계가 많다고 해석  

## **<u>[기술 통계와 추론 통계]</u>**
기술통계 : 수집한 데이터를 요약, 묘사, 설명  
추론통계 : 수집한 데이터를 바탕으로 모수에 대하여 추론 또는 예측  

## **<u>[확률 표본 추출 ]</u>**
`단순 무작위 표본` : 표본을 균등 한 확률로 추출  
체계 표본 추출 : `시간, 순서, 공간의 동일한 구간에서 무작위`로 하나 추출, k번째 간격마다  
`층화` 표본 추출 : `여러 개의 층`으로 나눈 후 각 층에서 표본을 단순 무작위로 추출  
`군집` 표본 추출 : `하나의 군집`을 추출하여 일부 또는 전체를 조사  

## **<u>[비확률 표본 추출의]</u>**
편의 표본 추출 : 편리성에 기준을 두고 추출  
`판단` 표본 추출 : `주관적 판단으로 필요 대상`만 추출  
`누적` 표본 추출 : `사전에 알고 있는` 대상을 조사  
`할당` 표본 추출 : `그룹화`하여 그룹별로 필요한 대상만 추출  

## **<u>[확률분포]</u>**
확률 변수의 분포 형태를 그래프로 표현  
`확률 질량` 함수 : 이산확률분포의 확퓰분포를 나타낸 함수  
`누적분포` 함수 : 시작점을 음의 무한대로 동일한 특수 구간을 사용하는 함수  
확률 밀도 함수 : 임의의 지점의 밀도를 함수로 나타냄 (히스토그램 면적)

## **<u>[이산확률분포]</u>**
이항분포 : 여러번의 베르누이 시행후 성공횟수를 확률변수로. 복원추출
다항분포 : 각각의 경우가 나올 수 있는 횟수 집합의 분포  
초기화 분포 : 비복원 추출  
`포아송` 분포 : `주어진 시간`, 영역에서 어떤 사건의 발생 횟수

## **<u>[연속확률분포]</u>**
정규분포 : 평균값 중앙으로 좌우 대칭인 종 모양의 분포  
감마분포 : 특정 수의 사건이 발생할 때까지 시간에 관한 분포  
베타분포 : 베타함수를 이용한 분포  
t분포 : t=0에 대해 좌우 대칭을 이루는 종 모양의 분포, 자유도가 클수록 표준 정규 분포에 근사  
카이제곱분포 : 정규 분포를 제곱 혹은 제곱한 것을 더해 나타낸 분포, 자유도가 커질수록 종 모양의 정규 분포에 근사  
F분포 : 두 데이터셋의 분산에 대한 분포  

## **<u>[표본 분포]</u>**
표본 분포 개념 : 무수히 많은 표본의 평균값 혹은 표준편차에 대한 분포  
<span style='color:skyblue'><u> 중심극한정리</u></span> : 불규칙한 형태의 모집단에서 표본 크기가 n인 표본을 여러 번 반복 추출하여 정규 분포의 형태를 이루는 그래프로 변환.  
> <span style='color:skyblue'><u>표본 수가 작아도 모집단 통계량을 추정할 수 있다.</u></span>

## **<u>[점추정]</u>**
추정 : 통계량을 통해 모집단의 모수를 추측  
점추정 : 모집단의 모수를 단일 값으로  
추정량 : 모수를 추정하는 통계량  
추정치 : 계산된 추정량의 값  

## **<u>[좋은 추정량]</u>**
`불편`성 : `추정량의 기대값이 모수의 실제값과 같거나 가까울수록`  더 좋은 추정량 (non bias)  
`효율`성 : 모든 불편 추정량 중에서 `분산이 작을수록` 더 좋은 추정량  
`일치`성 : 표본의 `크기를 크게 할수록 추정량은 모수에 가까워`짐  
`충분`성 : 모수에 대한 정보를 많이 제공할 수록 더 좋은 추정량 <font size='1'>(~~존x당연한소리~~)</font>

## **<u>[구간추정]</u>**
구간추정 : 모수가 포함될 것으로 기대되는 구간을 추정 (신뢰성 정도를 포함)  
신뢰구간 : 구간추정을 통해 얻은 구간 (신뢰 하한.상한)  
신뢰수준 : n번 표본을 추출해서 구한 N개의 신뢰구간 중 모수를 포함하는 신뢰구간 비율  
오차율 : 오차율 a는 신뢰구간에 모수가 포함되지 않을 확률  
성질 : `수준은 높게 구간은 좁게` , `수준이 높이면 구간이 넓음 = 구간추정이 어려움` , `n이 클수록 구간이 좁아짐`

## **<u>[가설검정용어]</u>**
통계적 가설검정 : 모집단의 특성에 대한 주장 또는 가설을 세우고 표본에서 얻은 정보를 이용해 가설이 옳은지를 판정하는 과정  
귀무가설 : 기각시키고자 하는 어떤 가설  
대립가설 : 새로운 아이디어 혹은 가설로 귀무가설을 기각함으로서 채택되는 가설  
검정통계량 : 표본 통계량으로 결론을 내릴 때 사용되는 판단 기준  
유의수준 : 귀무가설이 참인데도 이를 잘못 기각하는 오류를 범할 확률의 최대 허용 한계. (1%, 5%..)  
기각역 : 귀무가설이 기가하게 될 영역  
채택역 : 귀무가설을 기각할 수 없는 영역  
임계값 : 기각역의 경계값  
유의확률 : 귀무가설을 지지하는 정도, p-value


## **<u>[가설검정 오류]</u>**

|       | 귀무 참  | 귀무 거짓 |
| :---: | :------: | :-------: |
| 기각  | 1종오류  | 옳은결정  |
| 채택  | 옳은결정 |  2종오류  |

1종오류 : `귀무가설이 참`인데 기각  
2종오류 : `귀무가설이 거짓`인데 채택  


## **<u>[t검정]</u>**
단일표본 t 검정 : 모집단의 평균값을 특정 값과 비교하는 경우  
독립표본 t 검정 : 서로 독립적인 두 그룹의 평균 차이가 0인지 알아보는 검정  
대응표본 t 검정 : 동일한 대상에 대해 두 가지 관측치가 있는 경우 비교하여 차이가 있는지 검정  

```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```