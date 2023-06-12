---
title : '[빅분기] 빅데이터분석기사 1장 정리본' 
excerpt : "빅데이터 실기 필기"
categories: 
 - BigData
tags: 
 - [BigData, Test]



toc : true
toc_sticky : true



date : 2022-11-19
last_modified_dat : 2022-11-19
---
<span style='color:gray'>Introduction<br></span>
빅데이터 분석 기사 실기 시험을 앞두고 필기를 정리합니다. 필기시험을 앞둔 분들도 참고하면 좋습니다.<br>
{: .notice}

## **<u>[데이터의 유형]</u>**

| 종류                             | 내용                                                                    |
| :------------------------------- | :---------------------------------------------------------------------- |
| `정량적` 데이터(`정형`데이터)    | 수치로 표현할 수 있는 숫자, 도형, 기호 등의 데이터를 의미.              |
| `정성적` 데이터(`비정형` 데이터) | 언어, 문자 등의 정형화되지 않은 데이터. 많은 비용과 기술적 투자가 필요. |


## **<u>[암묵지와 형식지의 상호작용]</u>**
암묵지가 형식지로 표출되고 연결되면 그 상호작용으로 지식이 형성된다.  

|   분류   |      내용       |
| :------: | :-------------: | :---------------: |
| `암묵지` | 공통화 / 내면화 | 암묵적으로 인정함 |
| `형식지` | 표출화 / 연결화 |  말해야 알아들음  |


## **<u>[⭐️⭐️⭐️ DIKW 피라미드]</u>**
데이터 : 의미 없음  
정보 : 의미 생김  
지식 : 정보를 분류하고 지식으로  
지혜 : 창의적 산물  

## **<u>[데이터베이스의 특징]</u>**
총 4개 : [ 정보 축적 및 전달 / 정보 이용 / 정보 관리 / 정보 기술 발전  / 경제 산업적(인프라) ]  

> `정보의 축적 및 전달`:  
> 기계 가독성 : 대량의 정보를 컴퓨터가 읽음  
> 검색 가능성 : 다양한 방법으로 정보 검색 가능성  
> 원격 조작성 : 원거리에서 온라인으로 가능  
> `정보 이용 측면`:  
> 이용자의 정보 요구에 따라 다양한 정보를 신속하게 획득하고 원하는 정보를 찾을 수 있음  
> `정보 관리 측면`:  
> 정보를 일정한 질서와 구조에 따라 정리, 저장하고 검색 관리할 수 있게 하여 방대한 양의 정보를 체계적으로 축적하고 추가 갱신함  
> `정보 기술 발전 측면`:  
> 데이터 베이스는 정보처리 검색 관리 소프트 웨어, 하드웨어, 네트워크 등을 발전하게 끔 함  
> `경제 산업적 측면`:  
> 다양한 정보를 필요에 따라 신속 제공 이용 할 수 있는 인프라 특성을 보이기 때문.

## **<u>[부문별 사회 기반 구조 데이터 베이스]</u>**
물류 : CVO서비스 / CALS / PORT-MIS(항만운영정보) / KROIS(철도운영정보)  
지리 : GIS(지리정보) / LBS(위치정보) / SIM(공간정보 관리)  
교통 : ITS(지능형교통정보) / 교통정보 / 기초자료 및 통계, 대국민 서비스  
의료 : 의료정보시스템 / PACS   
교육 : 첨단 정보통신기술을 활요한 교육 정보 개발 / 대학 정보화 / NEIS(교육행정정보)  

## **<u>[⭐️⭐️⭐️ 빅데이터 특징]</u>**
`빅데이터 3V`  
크기 (Volume) : 대량의 데이터 증가 발생으로 기존 데이터 수집, 관리 한계  
다양성 (Variety) : 비정형 데이터 발생으로 다양한 데이터 형식 증가  
속도 (Velocity) : 실시간 정보 발생으로 데이터 유입, 처리 속도 요구  

`빅데이터 4V`  
가치 (Value) : 데이터 전체 파악, 패턴 발견의 어려움으로 가치의 중요성 강조  
정확성 (Veracity) : 빅데이터 기반의 예측 분석 결과에 대한 신뢰성이 중요.

## **<u>[⭐️⭐️⭐️ 빅데이터에 거는 기대]</u>**
산업혁명의 석탄, 철 : 세상 전반에 혁명적 변화  
21세기 원유 : 필요한 정보를 제공하여 생산성을 향상시킬 것.  
렌즈 : 산업 발전에 큰 영향을 줄것   
플랫폼 : 공동 활용의 목적으로 구축된 유무형의 구조물. 다양한 서드파티 비즈니스에 활용.

## **<u>[⭐️⭐️⭐️ 빅데이터 변화]</u>**
사전처리 > <span style='color:skyblue'><u>사후처리</u></span>  
표본조사 > <span style='color:skyblue'><u>전수조사</u></span>  
질 > <span style='color:skyblue'><u>양</u></span>  
인과관계 > <span style='color:skyblue'><u>상관관계</u></span>  

## 7가지 빅데이터 활용 기본 테크닉
> `1. 연관규칙 학습`:
> 변인 간에 상관관계 판단   
> `2. 유형분석`:
> 새로운 사건이 속할 범주를 찾음  
> `3. 유전알고리즘`:
> 최적화가 필요한 문제의 해결책을 자연 선택, 돌연변이 등과 같은 메커니즘을 통해 진화  
> `4. 기계학습 == 머신러닝`:
> 학습 데이터로 부터 학습한 알려진 특성을 활용해 <span style='color:skyblue'>예측</span>  
> `5. 회귀분석`:
> 독립변수를 조작하면서 종속변수과의 변인 관계를 파악  
> `6. 감정분석`:
> 특정 주제에 대해 말하거나 글을 쓴 사람의 감정을 분석  
> `7. 소셜 네트워크 분석`:
> 오피니언 리더, 인플루언서를 찾아내고, 고객간 소셜 관계를 파악

## **<u>[빅데이터의 위기 요인과 통제 방안]</u>**
|     위기     |           통제           |
| :----------: | :----------------------: |
|  사생활침해  |       동의 > 책임        |
| 책임원칙훼손 | 결과 기반 책임 원칙 고수 |
|  데이터오용  |    알고리즘 접근 허용    |

## **<u>[데이터 사이언티스트에 요구되는 역량]</u>**
> `하드스킬`:
> 빅데이터에 대한 이론적 지식, 분석 기술에 대한 숙련  
> `소프트스킬`:
> 통찰력있는 분석, 설득력 있는 분석, 다분야 간 협력

## **<u>[가치 패러다임의 변화]</u>**
> `디지털화`:
> 아날로그 > 디지털 변화에 의한 가치 창출 원천  
> `연결`:
> 디지털화된 정보와 대상들이 서로 연결되어 효과적이고 효율적으로 제공되느냐  
> `에이전시`:
> 사물인터넷 연결이 증가하고 복잡  
> 복잡한 연결을 얼마나 효과적이고 신뢰있게
> <u>데이터 사이언스 역량에 따라 좌우</u>

## **<u>[분석 준비도 평가]</u>**
`분석 업무 파악 / ` `분석 인력 및 조직 / ` `분석 기법 / ` `분석 데이터 / ` `분석 문화 / ` `IT인프라`

## **<u>[분석 성숙도 평가]</u>**
1단계 : 분석시작, 환경과 시스템 구축  
2단계 : 분석 결과를 업무에 적용  
3단계 : 전사 차원에서 분석관리, 공유  
4단계 : 분석을 진화시켜 혁신 및 성과 향상에 기여  

## **<u>[⭐️⭐️⭐️ 분석 준비도 및 성숙도 진단 결과 4분면]</u>**  

| 분면종류 | 준비도 | 성숙도 | 내용                                 |
| :------: | :----: | :----: | :----------------------------------- |
|  확산형  |  높음  |  높음  | 지속적 확산 가능 기업                |
|  정착형  |  낮음  |  높음  | 분석기법 제한적 사용, 분석 정착 필요 |
|  도입형  |  높음  |  낮음  | 준비도가 높아 바로 도입 가능         |
|  준비형  |  낮음  |  낮음  | 사전 준비가 필요                     |

<br>
![IMAGE](https://user-images.githubusercontent.com/60537388/220329727-42bf0ba9-dcc2-4516-8db9-1080dfb6ac34.png){: width='20%' height='20%' .align-center} 

<br>  


## **<u>[분석 조직의 유형]</u>**
`DSCoE` 위치가 중요  
집중구조 : DSCoE가 마지막.  
기능구조 : 부서가 다 분석함
분산구조 : 부서가 모두 DSCoE포함. DSCoE 분산

## **<u>[빅데이터 플랫폼 개념도]</u>**

\\[\text{데이터소스} \rightarrow  \underbrace{\text{데이터수집} \rightarrow \text{데이터 저장, 처리, 관리}}_{관리플랫폼} \rightarrow \underbrace{\text{데이터 활용}} _{분석플랫폼} \\]


## **<u>[에코시스템]</u>**
빅데이터는 여러가지 기술 및 프레임워크, 솔루션 등을 이용해 플랫폼을 완성하게 되는데 이를 `에코시스템`라고 한다.

## **<u>[머신러닝 vs 딥러닝]</u>**
머신러닝 : 데이터 분석, 결정을 내리기 위핸 학습한 내용을 적용  
딥러닝 : 인공신경망 분석. 인간의 뇌처럼 학습함.  

## **<u>[미래의 인공지능 활용 분야]</u>**
자율주행, 스마트홈, 메디컬 케어, 인프라, 스마트 농업, 업무 환경 변화

## **<u>[⭐️⭐️⭐️ 마이데이터]</u>**
마이데이터 :  
    `정보의 주체가 개인 정보 권한을 갖고 관리할 수 있게 하자`
    개인정보에 대한 인간 중심의 비전을 향해 나아가는 것을 목표.
    공정하고 지속 가능하며 변영하는 디지털 사회의 조건

개념 :
`자기정보 결정권` + `데이터 경제 활성화`  
`데이터통제 / ` `데이터제공 / ` `데이터활용 / `

## **<u>[빅데이터 분석 기획의 능력 단위 요소]</u>**
도메인 이슈 도출, 분석 목표 수립, 프로젝트 계획, 보유데이터 자산 확인

## **<u>[⭐️⭐️⭐️ 분석 대상과 그 방법에 따른 4가지 분석 요소 (OSID)]</u>**

<u>하향식 접근법</u>  

| 분석대상 | 분석방법 |        요소         |
| :------: | :------: | :-----------------: |
|   안다   |   안다   | 최적화 Optimization |
|   안다   |  모른다  |   솔루션 Solution   |


<u>상향식 접근법</u>  

| 분석대상 | 분석방법 |      요소      |
| :------: | :------: | :------------: |
|  모른다  |   안다   |  통찰 Insight  |
|  모른다  |  모른다  | 발견 Discovery |

## **<u>[⭐️ 5단계 빅데이터 분석 방법론]</u>**
1단게 : 분석기획 > 비즈니스 이해, 프로젝트 정의 및 계획 수립, 프로젝트 위험 계획 수립    
2단계 : 데이터 준비 > 필요 데이터 정의, 데이터 스토어 설계, 데이터 수집 및 정합성 점검  
3단계 : 데이터 분석 > 분석용 데이터 준비, 텍스트 분석, 탐색적 분석, 모델링, 모델 평가 및 검증  
4단계 : 시스템 구현 > 설계 및 구현, 시스템 테스티 및 운영  
5단계 : 평가 및 전개 > 모델 발전 계획 수립, 프로젝트 평가 및 보고

## **<u>[⭐️ 분석과제 발굴 방법론]</u>**
분석 대상 안다 > 하향식 > 문제 탐색 > 문제 정의 > 해결방안 탐색 > 타당성 검토  
분석 대상 모른다 > 상향식 > 지도 비지도 학습 > 프로토 타입

## **<u>[⭐️⭐️ 하향식 분석과제 발굴 방법론]</u>**

|       | 문제 탐색 단계 |       |
| :---: | :------------: | :---: |
|       |   규제와감사   |       |
| 업무  |      제품      | 고객  |
|       |   지원인프라   |       |

> `분석기획 발굴의 범위 확장`:
> 거시적관점, 경쟁자 분석, 시장의 니즈, 역량 분석   
> 외부 참조 모델 기반의 문제 탐색  
> 분석 유스케이스

## **<u>[⭐️⭐️⭐️ 상향식 분석 과제 발굴 방법론]</u>**
> `지도학습`:
> 머신러닝, 의사결정트리, 인공신경망 모형  
> `비지도학습`:
> 장바구니분석, 군집분석, 주성분 분석, 다차원 척도  
> `프로토타입`:
> 시행착오 해결법

![image](https://user-images.githubusercontent.com/60537388/204082496-5c9cb835-81fc-4b71-a42a-a1a499dfa474.png){: width="20%" height="20%"}
>시급성우선 : 3421  
>난이도우선 : 3124


## **<u>[⭐️⭐️⭐️데이터 유형에 따른 데이터 수집 방법]</u>**  

| 데이터 |           종류            |       수집        |
| :----: | :-----------------------: | :---------------: |
|  정형  |           DBMS            |        ETL        |
| 반정형 |     HTML,XML,JSON 등      |   웹크롤링,API    |
| 비정형 | 소셜데이터,문서,이미지 등 | 웹크롤링,스트리밍 |

## **<u>[⭐️⭐️⭐️ 데이터 축소 및 차원 축소]</u>**

> `데이터 축소` :
> 같은 정보량을 가지면서 데이터의 크기를 줄이는 방법. 분석의 효율성을 높이기 위해 필요한 변환 과정.  
> `차원축소` :
> 데이터의 잡음을 제거. 데이터셋을 다루기 쉽게 함. 관계없거나 중복되는 속성을 제거하는 작업으로 최소 집합을 찾아냄  
> `데이터 압축`:
> 데이터 인코딩, 변환과정을 이용해 축소. 무손실압축기법 이라고 하며 BMP포맷있음. 손실압축기법은 JPEG포맷

## **<u>[스타스키마]</u>**
> `장점` :
> 복잡도가 낮아 이해 쉬움. 조인 테이블 적음  
> `단점` :
> 차원 테이블들의 비정규화로 데이터 중복 발생, 상대적으로 데이터 적재에 시간 많이 소요.


## **<u>[스노우플레이크 스타스키마]</u>**
> `장점` :
> 데이터 중복 제거되면서 데이터 적재시 소요시간 빠름  
> `단점` :
> 복잡성 증가 > 조인 테이블 개수 증가. 쿼리 난이도 증가

## **<u>[⭐️⭐️⭐️ ETL 프로세스]</u>**
데이터 원천으로 데이터를 <span style='color:skyblue'><u>추출(Extraction)</u></span>, <span style='color:skyblue'><u>변환(Transform)</u></span>, <span style='color:skyblue'><u>적재(Load)</u></span>하는 작업이다.

<font size='1'><span style='color:gray'>데이터의 원천으로 부터 데이터를 추출 및 변환하여 운영 데이터 스토어, 데이터 웨어하우스, 데이터 마트에 데이터를 적재</span></font>

## **<u>[ETL vs CDC]</u>**
ETL : 정해진 시점  
CDC : 실시간 혹은 준 실시간

## **<u>[ODS 프로세스]</u>**
데이터에 추가 작업을 하기 위해 다양한 원천 데이터로부터 데이터를 추출 통합한 데이터 베이스   
Operatinal Data Store

## **<u>[⭐️⭐️⭐️ 데이터 웨어하우스 vs 데이터 레이크]</u>**
> `데이터 웨어하우스` :
> 표준화된 SQL, 정제된 데이터, 저장 처리에 비용 높음, 빠르고 간편, 접근성 제한적, 안전, 동시성과 통합성  
> `데이터 레이크` :
> SQL유사 시스템 (HBase, NoSQL), Spark, Map Skyblueuce, YARN, Presto로 액세스, Raw데이터, 저렴한 비용 처리  
> 접근성 매우 높음, 자유로움, 도구 및 저장용량 확장성 좋음, `스트리밍`, `빅데이터 분석 솔루션과 연동 편리`


## **<u>[⭐️⭐️⭐️ 하둡]</u>** 
 
내용이 꽤 어렵지만, 알고 모르는거에 점수 차이가 크다.<br>
{: .notice--primary}  

하둡은 하나의 좋은 컴퓨터를 이용하여 데이터를 처리하는 대신, 적당한 성능의 범용 컴퓨터 여러대를 클러스터화여 데이터를 처리하는 것을 목표로 하는 것을 의미한다. 즉, `하둡은 큰 크기의 데이터를 여러대의 컴퓨터에서 병렬로 동시에 처리하여 처리 속도를 높이는 것을 목적으로 하는 분산처리 오픈소스 프레임워크`.
> `장점` : 
> 오픈소스, 장비 추가에 용이, 일부 장비의 장애시에도 전체에 영향이 미미,  
> 저렴하고 비용대비 빠르게 데이터 처리, 오프라인 배치 프로세싱에 최적화  
> `단점` :
> HDFS에 저장된 데이터를 변경할 수 없음. 실시간 데이터 분석과 같이 신속하게 처리해야 하는 작업에는 부적합  

### **<u>[⭐️⭐️⭐️ 수집 및 연결 프레임워크]</u>**
#### **<u>[스쿱 Sqoop]</u>**
> 하둡과 데이터베이스 간 <span style='color:skyblue'><u>데이터 이동을 간편하게</u></span>  
> 하둡에서 데이터를 가져오거나 올릴 때 사용  
> 하둡에서 제공하는 데이터베이스 연결용 <span style='color:skyblue'><u>맵 인풋 포매터</u></span>를 사용

#### **<u>[플럼 Flume]</u>**
> <span style='color:skyblue'><u>반정형데이터(로그 데이터)수집</u></span>  
> <span style='color:skyblue'><u>비정형데이터 수집</u></span>  
> 대용량 로그 데이터를 안정성, 가용성을 바탕으로 효율적 수집  
> 다양한 소스로부터 데이터를 수집, `다양한 방식`으로 데이터를 전송 
> <span style='color:skyblue'><u>최근 국내의 빅데이터 솔루션에서 수집 부분 채택</u></span>

#### **<u>[카프카 Kafka]</u>**
> 데이터 <span style='color:skyblue'><u>스트림 실시간 관리</u></span>를 위한 `스트리밍` 플랫폼  
> <span style='color:skyblue'><u>발행 / 구독</u></span>모델로 구성  
> 메세지를 파일에 저장
> 다수의 카프카 서버에서 메세지 분산 처리  

#### **<u>[스크라이브 Scribe]</u>**
> <span style='color:skyblue'><u>반정형데이터(로그 데이터)수집</u></span>  
> <span style='color:skyblue'><u>비정형데이터 수집</u></span>  
> `실시간 스트리밍 로그 수집`  
> <span style='color:skyblue'><u>페이스북</u></span>자체 Scaling 작업

#### **<u>[척와 Chuckwa]</u>**
> <span style='color:skyblue'><u>반정형데이터(로그 데이터)수집</u></span>   
> 하둡의 `서브 프로젝트`로 분산 서버에서 로그데이터를 `수집, 저장, 분석`하기 위한 솔루션  
> 수집된 로그 파일을 <span style='color:skyblue'><u>HDFS</u></span>에 저장
> 지나치게 하둡에 의존

#### **<u>[스톰 Storm]</u>**
> <span style='color:skyblue'><u>실시간 스트리밍</u></span>처리 `서버이자 프레임워크`  
> 장애 대응 능력이 뛰어남  
> 장애 노드에 대해서는 복구 처리를 자동으로

#### **<u>[아브로 Avro]</u>**
> 데이터 직렬화 프레임워크  
> `특정 언어에 종속 x`  
> 스키마를 보통 `JSON`으로 작성하여 바이너리 형태로 인코딩

#### **<u>[웹 크롤링]</u>**
> `Python` :
> Scrapy  
> `JAVA` :
> Nutch, Crawler4j  

### **<u>[⭐️⭐️⭐️분석 및 관리 프레임워크]</u>**
#### **<u>[하이브 Hive]</u>**
> 사용자가 SQL로 쿼리를 작성하면 <span style='color:skyblue'><u>자동으로 맵리듀스 작업으로 변경</u></span>  
> 기존에 사용하던 `RDBMS`와 아주 유사한 환경의 분석 플랫폼  
> <span style='color:skyblue'><u>자바 기반으로 널리 활용</u></span>  

#### **<u>[피그 Pig]</u>**
> <span style='color:skyblue'><u>PIG Latin</u></span>언어 사용  
> 쉬운 프로그래밍  
> 최적화와 효율 굿

#### **<u>[임팔라 Impala]</u>**
> `HDFS`와 직접 통신  
> `하이브 쿼리 언어 HiveQL`사용  
> <span style='color:skyblue'><u>C++</u></span>기반 실행엔진 -> 속도 빠름  

#### **<u>[스파크 Spark SQL]</u>**
> 데이터프레임으로 변환, 분석작업 용이  
> 구조화된 데이터셋을 가지고 효율적으로 다룰 수 있음  
> JSON, Parquet, ORC, JDBC, 하이브 호환테이블, 스파크 전용 테이블  

#### **<u>[타조 Tajo]</u>**
> <span style='color:skyblue'><u>고려대</u></span>  
> 하둡 기반의 대용량 데이터를 SQL 형태의 명령을 통해 분산 분석 작업을 진행  
> 하이브랑 비슷. `ETL`, `Low-Latency` 지원  
> 자동 최적화 지원  

#### **<u>[머하웃 Mahout]</u>**
> 분산처리 가능, 확장성을 가짐 <span style='color:skyblue'><u>머신러닝용 라이브러리</u></span>  
> 비슷한 특성을 가진 데이터를 `분류, 정의`하는 <span style='color:skyblue'><u>작업 및 협업 필터링 수행</u></span>

#### **<u>[프레스토 Presto]</u>**
> <span style='color:skyblue'><u>Hive보다 빠른 SQL</u></span>  
> <span style='color:skyblue'><u>자바</u></span>로 만들어짐. 메모리 처리와 데이터 구조 기술을 적절히 혼합  
> HDFS와 HBase와 같은 데이터 저장소 외에 뉴스피드 백엔드 속 <span style='color:skyblue'><u>스토리지</u></span>와 쉽게 연결  
> <span style='color:skyblue'><u>페이스북</u></span>은 프레스토를 여러 지역에서 운영

### **<u>[⭐️⭐️⭐️관리 프레임워크]</u>**
#### **<u>[주키퍼 ZooKeeper]</u>**
> 분산 시스템간의 정보 공유 및 <span style='color:skyblue'><u>상태 체크, 동기화</u></span>처리 프레임워크  
> `코디네이션` 서비스 시스템  
> 분산 큐, 분산 로크 등 다양한 기능

#### **<u>[우지 Oozie]</u>**
> 하둡의 `워크플로`관리  
> 일정한 시간이 경과하거나 <span style='color:skyblue'><u>주기적으로 반복해서 실행</u></span>되는 잡을 관리  
> 맵리듀스 잡, 피그 잡 등 시작과 완료, 실행 중 <span style='color:skyblue'><u>에러 등의 이벤트 콜백</u></span>

#### **<u>[휴 Hue]</u>**
> Hue는 <span style='color:skyblue'><u>코어 하둡, 스파크 하둡</u></span>에서 사용 가능한 컴포넌트  
> 하둡 클러스터와 함께 사용되는 <span style='color:skyblue'><u>웹 기반 사용자 인터페이스</u></span>  
> 다른 하둡과 함께 그룹화되어 Hive작업 및 스파크 잡 실행

#### **<u>[에어플로우 Airflow]</u>**
> 데이터 워크플로 관리 도구  
> <span style='color:skyblue'><u>Airbnb</u></span>개발. 현재는 아파치 <span style='color:skyblue'><u>Python</u></span>을 기반으로 코드 작성  
> HDFS와 같이 여러대의 노드가 동작해야 하는 환경에 대해서도 지원  
> <span style='color:skyblue'><u>웹 UI 기반 강력함</u></span>  

#### **<u>[암바리 Ambari]</u>**
> 손쉬움 웹 UI, REST API 사용 제공  
> <span style='color:skyblue'><u>LINUX</u></span>기반 

#### **<u>[H카탈로그 HCatalog]</u>**
> <span style='color:skyblue'><u>테이블 뷰</u></span>제공  
> Pig, Hive (데이터 처리도구)간의 테이블, 저장공간 관리 계층 제