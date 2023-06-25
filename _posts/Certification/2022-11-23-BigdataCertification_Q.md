---
title : '[빅분기] 빅데이터 실기 단답형 문제 모음' 
excerpt : "빅데이터 실기 공부"
categories: 
 - BigData
tags: 
 - [BigData, Test]



toc : true
toc_sticky : true



date : 2022-11-23
last_modified_dat : 2022-11-23
---
# 필기 1장 고놈의 하둡
<font size='2'><span style='color:gray'>Introduction  </span></font>  
---
<font size='1'><span style='color:gray'>14일 남았다. 필기는 문제 풀이를 위주로 공부를 하고, 실기는 Kaggle 문제를 풀면서 진행해보자.</span></font>
<font size='1'><span style='color:gray'>가지고 있는 필기 문제는 총 444개이므로 매일 40문제를 풀고 복습하면 될 것 같다.</span></font>

### 단답형 문제 
<font size='1'> 단답형 문제를 이론 공부처럼 하게 되면 남은 기간으로서는 어려울 것 같다.  </font>

<details>
<summary>빅데이터 실기 내 단답형 문제는?</summary>
<div markdown='1'>

> `주관식 단답형`으로 `10문제`가 출제된다. 각 점수는 3점으로 최대 5개 이상을 맞춰야 한다.  
~~하지만 너무 어려운건 어쩔 수 없다.~~
</div>
</details>

<br/>

<font size='3'><span style='color:red'>와 큰일났다.</span></font>
<font size='1'><span style='color:gray'> [ 2 / 40 ] 이러다간 정말로 떨어지고 말거야</span></font>

#### 단답형 문제와 설명

1. <font size='2'>수집 대상 데이터를 추출, 가공(변환, 정제)하여 데이터 웨어하우스 및 데이터 마트에 저장하는 기술은?</font>

    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **ETL**
    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    문제에서 힌트를 찾을 수 있다.  
    "수집 대상 데이터를 <span style='color:red'><u>추출, 가공(변환, 정제)</u></span>하여 데이터 웨어하우스 및 데이터마트에 <span style='color:red'><u>저장</u></span>하는 기술"

    즉, **<font size='3'>ETL</font>** (Extract Transform Load). 말 그대로 다.
    </div>
    </details>
    </div>
    </details>

2. <font size='2'>사용자의 의사 결정에 도움을 주기 위하여, 기간 시스템의 데이터 베이스에 축적된 데이터를 공통 형식으로 변환해서 관리하는 데이터베이스는 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **데이터웨어하우스**
    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>
    
    힌트는 <span style='color:red'><u>사용자의 의사 결정</u></span>, 그리고 <span style='color:red'><u>기간 시스템</u></span>, <span style='color:red'><u>데이터베이스</u></span>이다.

    데이터 웨어하우스는 여러 소스에서 가져온 구조화된 데이터와 반구조화된 데이터를 분석하고 보고하는데 쓰인다.
    데이터 웨어하우스는 임시 분석과 커스텀 보고서 생성에 적합하다.
    데이터 웨어하우스는 <u>현재 데이터와 과거 데이터를 모두 한 곳에</u> 저장할 수 있으며, <u>시간 흐름</u>에 따른 장기간의 데이터 동향을 확인 할 수 있도록 설계 되어 있다.

    따라서 데이터 웨어하우스는 비즈니스 인텔레전스 (BI)의 주요한 구성이다.

    </div>
    </details>
    </div>
    </details>

3. <font size='2'>서버, 클라이언트 방식으로 로컬 또는 원경의 수집 대상 시스템과 1:1로 파일과 디렉터리를 동기화하는 응용 프로그램 활용 기술은?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **Rsync**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    서버, 클라이언트는 `linux`도 많이 사용하는데, 그 중 서버환경에서 많이 쓰이는 말이 바로 <span style='color:red'><u>Rsync</u></span>이다.
    
    서버, 클라이언트에서 가장 중요한게 무엇일까? 생각해보면 '동기화'가 떠오를 것인데, 이때 사용하는 것이 바로 <span style='color:red'><u>Rsync</u></span>이다.
    **Rsync** (Remote Synchronization). 즉, `원격 동기화`라는 말이다

    </div>
    </details>
    </div>
    </details>

4. <font size='2'>여러 이벤트 소스로부터 발생한 이벤트를 실시간으로 추출하여 대응되는 액션을 수행하는 처리기술. 이 것을 통해 실시간 상황에서 의미있는 이벤트를 파악하고 가능한 빨리 대응할 수 있는 것은?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **Cep**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    문제에 힌트가 있다.
    <span style='color:red'><u>실시간</u></span>으로 추출하여 <span style='color:red'><u>수행하는 처리기술</u></span>
    
    **CEP** (Complex Event Processing). 즉, "실시간으로 발생하는 이벤트 처리에 대한 결과값을 수집하고 처리하는 기술"을 의미한다.

    </div>
    </details>
    </div>
    </details>

5. <font size='2'>커넥터(Connector)를 사용하여 관계형 데이터베이스(RDBS)와 하둡(Hadoop)간 데이터를 수집하고 전송하는 기술은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **스쿱(Sqoop)**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    관계형 데이터베이스와 하둡간 데이터를 <span style='color:red'><u>커넥터 : 스쿱</u></span>을 이용해 퍼 나른다고 이해하자.
    스쿱의 모양은 일정하니, 데이터도 일정해야 푸기 좋다.
    따라서 스쿱은 `정형 데이터`수집에 활용된다.
    전송, 수집 등 모든 적재 과정이 `자동화, 병렬`처리 방식을 따른다.
    </div>
    </details>
    </div>
    </details>

6. <font size='2'>대량의 자료를 처리할 수 있는 대형 컴퓨터 클러스터에서 동작하고 분산 응용 프로그램을 지원하는 오픈 소스 자바 소프트웨어 프레임워크는 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **하둡 (Hadoop)**
    <font size='1'><span style='color:gray'>내답 : 오라클.. 아니다 이사람아..</span></font>
    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>하둡</u></span>은 대용량의 데이터를 적은 비용으로 더 <span style='color:red'><u>빠르게 분석할 수 있는 플랫폼</u></span>이다.
    <span style='color:red'><u>하둡</u></span>은 여러대의 컴퓨터로 데이터를 분석하고 저장하는 병렬 처리 방식을 따른다.
    </div>
    </details>
    </div>
    </details>

7. <font size='2'>웹 사이트를 크롤링 하여 구조화 된 데이터를 수집하는 파이썬 기반의 애플리케이션 프레임워크로서 데이터마이닝, 정보처리, 이력 기록 같은 다양한 애플리케이션에 사용되는 비정형 데이터 수집 기술은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **Scrapy**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    문제를 제대로 읽어보면 힌트가 있다.
    <span style='color:red'><u>파이썬 기반의 애플리케이션 프레임워크</u></span>.
    python으로 크롤링을 하게 만든 프레임워크는 대표적으로 <span style='color:red'><u>Scrapy</u></span>이다.
    </div>
    </details>
    </div>
    </details>
    
8. <font size='2'>대규모로 저장된 데이터 안에서 체계적으로 자동적으로 통계적 규칙이나 패턴을 찾아내는 기법은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **데이터 마이닝**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>데이터 마이닝</u></span>은 말그대로 채굴. 대량의 데이터를 분석해서 규칙이나 패턴을 찾는 것.
    `데이터사이언스`는 수학과 통계학, 프로그래밍을 활용해서 비즈니스에 도움되는 정보를 추출한다.
    </details>
    </div>
    </details>

9. <font size='2'>대용량 실시간 로그 처리를 위해 기존 메시징 시스템과 유사하게 레코드스트림을 발행(Publish), 구독(Subscribe)하는 방식의 분산 스트리밍 플랫폼 기술은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **아파치 카프카**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    대용량, 대규모 데이터를 빠르게 처리하도록 <span style='color:red'><u>분산 메시징 플랫폼</u></span>이 바로 <span style='color:red'><u>아파치 카프카</u></span>이다.
    즉, <span style='color:red'><u>카프카</u></span>는 "어플리케이션간에 메세지를 교환하기 위해 사용되는 메세징 시스템". `실시간 로그 처리가 필요하다`  

    작가중에 `카프카`라고 있다. (변신이라는 책을 지은 작가다.) 이 책을 읽어보면, 자신이 벌레로 변신하는 과정을 시간 순서에 맞게 설명을 하는데, 위와 동일한 내용을 갖는다.
    </details>
    </div>
    </details>

10. <font size='2'>다수의 수집 대상 서버로부터 실시간 데이터를 수집하여 분산 시스템에 데이터를 저장하는 대용량 실시간 로그 수집 기술은?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **스크라이브 (Scribe)**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>실시간 데이터를 수집</u></span> == <span style='color:red'><u>스크라이브 (Scribe)</u></span>  
    `Sqoop`과의 차이는 Sqoop은 정형데이터, Scribe는 비정형데이터를 수집한다.  
    | 수집시스템 |   데이터종류 |
    | :--------: | -----------: |
    |   Sqoop    |   정형데이터 |
    |   Scribe   | 비정형데이터 |


    </details>
    </div>
    </details>

11. <font size='2'>대규모 분산 시스템 모니터링을 위해 에이전트로 컬렉터 구성을 통해 데이터를 수집하고, 수집된 데이터를 하둡 파일 시스템(HDFS)에 저장하는 기능을 제공하는 데이터 수집 기술은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **척와 (Chukwa)**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>대규모 분산 시스템</u></span>이 척와의 가장 큰 특징이다.
    "대규모 분산 시스템. 모니터링을 위한 기술이다. 에이전트-컬랙터의 관계를 보인다. <span style='color:red'><u>HDFS에 저장하고 실시간 분석을 한다.</u></span>
    </div>
    </details>
    </div>
    </details>

12. <font size='2'>스키마 구조 형태를 가지지 않고 고정된 필드에 저장되지 않는 데이터로 SNS 데이터나 오디오/이미지/비디오 데이터가 속하는 유형은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **비정형데이터**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    정형화 되지 않아 스키마 구조 형태를 가지지 않는다.
    </div>
    </details>
    </div>
    </details>

13. <font size='2'>스키마 구조 형태를 가지고 메타데이터를 포함하며, 값과 형식에서 일관성을 가지지 않는 데이터는 무엇인가? (XML, HTML과 같은 웹 데이터가 Noded 형태의 구조를 가진다)</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **반정형데이터**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    구조형태를 가지지만 값과 형식에 일관성이 없는 것이 반정형데이터이다.
    </div>
    </details>
    </div>
    </details>

14. <font size='2'>W3C에서 개발된, SGML(Standard Generalized Markup Language)문서 형식을 가진, 다른 특수한 목적을 갖는 마크업 언어를 만드는 데 사용하는 다목적 마크업 언어는 무엇인지 쓰시오</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **XML**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>XML</u></span>은 **다목적 마크업 언어 (SGML)** 형식을 갖는다. 데이터 표현을 위해 **태그**가 사용되어 사용자 정의가 가능하다. 즉, <span style='color:red'><u>HTML 한계</u></span>를 극복하기 위해 만들어졌다.
    
    </div>
    </details>
    </div>
    </details>

15. <font size='2'>빅데이터 수집 시스템에서 수집 대상이 되는 데이터를 저장 형태 관점에서 분류했을 때 센서데이터, HTTP 트랜잭션, 알람 등과 같이 네트워크를 통해서 실시간으로 전송되는 데이터와 유형은 무엇인가</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **파일데이터 / 데이터베이스 데이터 / 콘텐츠 데이터 / 스트림 데이터**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    문제안에 답이있다.  
    <span style='color:red'><u>실시간으로 전송되는 데이터</u></span> 바로 **Stream data**이다.
    </div>
    </details>
    </div>
    </details>

16. <font size='2'>데이터 베이스에서 자료의 구조, 자료의 표현방법, 자료간의 관계를 형식 언어로 정의한 구조를 무엇이라고 하는가</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **스키마**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>스키마</u></span>는 데이터 베이스의 구조와 제약 조건에 관한 전반적인 명세를 기술한 메타데이터의 집단이다. 데이터의 개체, 속성, 관계 및 데이터 조작시 데이터 값들이 갖는 제약 조건 등에 관해 정의된다.  
    *사용자의 관점에 의해 외부 스키마, 개념 스키마, 내부 스키마로 나뉜다.*
    </div>
    </details>
    </div>
    </details>

17. <font size='2'>데이터에 관한 구조화된 데이터로, 다른 데이터를 실행해주는 데이터는 무엇인가</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **메타데이터**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    데이터에 대한 내용, 데이터를 실행해주는 또다른 데이터를 <span style='color:red'><u>메타데이터</u></span>라고 한다.
    </div>
    </details>
    </div>
    </details>

18. <font size='2'>데이터로부터 잡음을 제거하기 위해 데이터 추세에 벗어나는 값들을 변환하는 기법으로 데이터 집합에 존재하는 잡음으로 인해 거칠게 분포된 데이터를 매끄럽게 만들기 위해 구간화, 군집화 등의 기법을 적용하는 데이터 변환 기술은 무엇인가</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **평활화**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    데이터 변환 기술 중 하나로, 평활화는 <span style='color:red'><u>잡음제거, 추세에서 벗어나는 값 변환</u></span>을 하는 것을 의미한다.
    </div>
    </details>
    </div>
    </details>

19. <font size='2'>(   )는 데이터를 정해진 구간 내에 들도록 하는 기법으로 최단 근접 분류와 군집화와 같은 거리 측정등을 위해 특히 유용하다</font>
    <details>   
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **정규화** 
    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>정규화 ( Normalization )</u></span>는 정해진 구간내에 데이터 분포를 보는 방법이다. 
    </div>
    </details>
    </div>
    </details>

20. <font size='2'>데이터 비식별화 처리 기법 중 은폐화 방법이라고도 하며, 명확한 값을 숨기기 위하여 데이터의 평균값으로 변환하는 방식으로 랜덤 올림방법, 범위방법, 세분 정보 제한 방법 제어올림 방법의 세부 기술을 가지고 있는 기법은?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **범주화 (Categorization)**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    데이터가 포함되어 있는 <span style='color:red'><u>범위</u></span>로 변환하여 데이터를 비식별화 시킨다.
    </div>
    </details>
    </div>
    </details>

21. <font size='2'>(   )기법은 개안 식별 정보에 대하여 전체 또는 부분적으로 대체값, (공백, *, 노이즈 등)으로 변환하는 기법이다. 또한 완전 비식별화가 가능하며 원시 데이터의 구조에 대한 변형이 적다</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **데이터 마스킹**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    데이터 마스킹이란 민감한 데이터의 보호를 하려고 하는 기법이다.
    </div>
    </details>
    </div>
    </details>


22. <font size='2'>프라이버시 보호모델에서 주어진 데이터 집합에서 함께 비식별되는 레코드들은(동질집합에서)적어도 1개의 서로 다른 민감한 정보를 가져와 하는 프라이버시 모델은 무엇인가</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **L-다양성**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    주어진 데이터 집합에서 합께 비식별되는 레코드드 (동질집합에서) 적어도 "L"개의 서로 다른 민감한 정보를 가져야하는 성질을 의미한다.
    <span style='color:red'><u>K-익명성</u></span>에 대한 두 가지 공격, 즉 동질성 공격 및 배경지식에 의한 공격을 방어하기 위한 모델을 의미한다.
    </div>
    </details>
    </div>
    </details>

23. <font size='2'>(     )는 개인이 자신의 정보를 관리, 통제할 뿐만 아니라 이러한 정보를 신용이나 자산관리 등에 능동적으로 활용하는 일련의 과정을 의미한다. 개인은 데이터 주권인 자기 정보 결정권으로 개인 데이터의 활용과 관리에 대한 통제권을 개인이 가진다는 것이 핵심 원리이다</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **마이데이터**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    이건 문제가 답이다. 외우자.
    </div>
    </details>
    </div>
    </details>

24. <font size='2'>전통적인 RDBMS와 다른 DBMS를 지칭하기 위한 용어로 데이터 저장에 고정된 테이블 스키마가 필용하지 않고 조인(JOIN)연산을 사용할 수 없으며, 수평적으로 확장이 가능한 DBMS이다</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **비관계형 데이터베이스**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    NoSQL. <span style='color:red'><u>JOIN</u></span>연산이 불가능하다는 단점이 있다.
    </div>
    </details>
    </div>
    </details>

25. <font size='2'>NoSQL 제품 중 하둡 분산 파일 시스템(HDFS)을 기반으로 구현된 컬럼 기반의 분산 데이터베이스로 비관계형이며 SQL을 지원하지 않는 특성이 있고, 관계형 데이터베이스(RDMBS)와 달리 수평적으로 확장성이 있는 큰 테이블에 적합한 제품은 무엇인가?</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    **HBase**

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    <span style='color:red'><u>Hbase</u></span>는 하둡에 있는 확장성이 뛰어난 `분산 빅 데이터` 이다.  
    하둡 분산 파일 시스템 (HDFS)위에서 실행되는 버전이 지정된 <u>비관계형 오픈 소스 데이터베이스</u>이다. 또한 RDBMS와 달리 수평적(Horizontal)으로 확장성이 있어 큰 테이블에 적합하다.

    </div>
    </details>
    </div>
    </details>    


```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```