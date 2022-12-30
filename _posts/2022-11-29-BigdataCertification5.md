---
title : '[Certification] 빅데이터 실기 Kaggle' 
excerpt : "빅데이터 실기 공부"
categories: 
 - Certification
tags: 
 - [Certification, BigData, ML, DL, Study]



toc : true
toc_sticky : true



date : 2022-11-29
last_modified_dat : 2022-11-29
---
# 실기 문제
<font size='2'><span style='color:gray'>Introduction  </span></font>  
---
<font size='1'><span style='color:gray'>실기문제는 kaggle 에 있는 [🔗 빅데이터 캐글](https://www.kaggle.com/datasets/agileteam/bigdatacertificationkr) 에 있는 내용을 사용할 예정이다.</span></font>

### 빅데이터 실기 문제 문제 및 해설

1. <font size='2'>[T1-1]  
    문제 : 데이터에서 IQR을 활용해 Fare 컬럼의 이상치를 찾고, 이상치 데이터의 여성 수를 구하시오.</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    ```python
    # 데이터 파일 읽기 예제
    import pandas as pd
    a = pd.read_csv("./titanic_train.csv")
    # 사용자 코딩
    q1 = a['Fare'].quantile(.25)
    q3 = a['Fare'].quantile(.75)
    IQR = q3-q1
    low_out, high_out = (q1-(1.5*IQR), q3+(1.5*IQR))
    low_outlier = a[a['Fare']<low_out]
    high_outlier = a[a['Fare']>high_out]

    # 답안 제출 예시
    # print(평균변수값)
    print(len(high_outlier[high_outlier['Sex']=='female']))
    ```

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    IQR 이 문제에 나오면 `.quantile()`을 생각하자.
    </div>
    </details>
    </div>
    </details>

2. <font size='2'>[T1-2]  
    문제 : 주어진 데이터에서 이상치(소수점 나이)를 찾고 올림, 내림 버림(절사)했을 때 3가지 모두 이상치 'age' 평균을 구한 다음 모두 더하여 출력하시오.</font>
    <details>
    <summary><font size='2'><span style='color:gray'>정답</span></font></summary>
    <div markdown='1'>

    ```python
    # 데이터 파일 읽기 예제
    import pandas as pd
    df = pd.read_csv("./basic1.csv")
    # 사용자 코딩
    import numpy as np
    age = df[(df['age'] - np.floor(df['age'])) != 0]
    ceil = np.ceil(age['age']).mean()
    floor = np.floor(age['age']).mean()
    trunc = np.trunc(age['age']).mean()

    # print(평균변수값)
    print(ceil + floor + trunc)
    ```

    <details>
    <summary><font size='2'><span style='color:gray'>해설</span></font></summary>
    <div markdown='1'>

    np.ceil : 올림 / np.floor : 내림 / np.trunc : 버림(절사)
    </div>
    </details>
    </div>
    </details>

    