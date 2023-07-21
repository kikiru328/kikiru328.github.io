---
title : "Python Multiprocess를 이용한 DataFrame 전처리 코드"
excerpt : "Python Multiprocess"

categories:  
 - Tips
tags: 
 - [Python, DataFrame, Preprocessing]

  
toc : true
toc_sticky : true



date : 2023-06-16
last_modified_dat : 2023-06-16
---
<div class='notice--info' markdown='1'>
전처리 코드가 너무 느려서 Multiprocess를 이용해 속도를 높여보자
</div>

가끔 pandas에서 전처리를 할때 DataFrame rows가 너무 많은 경우가 있다.  
그런데 For문에 if문에 조건을 걸어서 전처리를 하다보면 너무 느려서 기본 5~6시간 걸릴 경우가 있다.  
이럴때 Multiprocess를 이용하면 속도를 높일 수 있다.  

```python
# set up
import time
import os
import numpy as np
import pandas as pds
from multiprocessing import Pool
from tqdm import tqdm
from warnings import filterwarnings
filterwarnings('ignore')  


def multiprocessing_initializer():
    ...
    # if initialize is needed, do it here

def function(x,y):
    ...
    # function to apply to each chunk
    # return list or array anything you want.
    # the DataFrame will be concatenated automatically in work_func below
    # Argument x anything you preprocess

def work_func(data, y) -> pd.DataFrame:
    ...
    # function to apply to each chunk
    # it will be applied in parallel
    # the data is splitted dataframe by the number of cores
    # return dataframe after parallel process
    """Sample Code
    tqdm.pandas()
    data['new'] = data.apply(lambda x: function1(x))
    data['new2'] = data['new'].progress_apply(lambda x: function2(x,y))
    return data
    """
    
def work_func_wrapper(args):
    ...
    # if the work_func needs more than one argument, use this wrapper
    # args is tuple of arguments
    """Sample Code
    x, y = args
    return work_fun(x, y)
    """

def parallel_dataframe(df, num_cores, y):
    ...
    # df: dataframe to apply work_func(not splitted)
    # df_split: splitted dataframe by the number of cores
    # num_cores: number of cores to use
    # pool : multiprocessing pool which is used to apply work_func
    # result : list of dataframe after parallel process
    """Sample Code
    df_split = np.array_split(df, num_cores)
    pool = Pool(num_cores, initializer=multiprocessing_initializer)
    result = list(tqdm(pool.imap(work_func_wrapper, [(d, y) for d in df_split]), total=len(df_split)))
    
    # for save by pool
    for i, df in enumerate(tqdm(result)):
        df.to_pickle(f'./result_{i}.pkl')
        print(f'saved : ./result_{i}.pkl')
    
    pool.close()
    pool.join()
    return df
    """

def main(stopwords):
    ...
    # import dataframe and apply parallel process
    """Sample Code
    start = time.time()
    print('start')
    df = pd.read_pickle(path)
    num_cores = 8 
    result = parallel_dataframe(df, work_func, num_cores, y)
    result.to_pickle(f'./result.pkl')
    print("time :", time.time() - start)
    """
    
if __name__ == '__main__':
    ...
    # run file
    # import args (y)
    """Sample Code
    y = pd.read_pickle(path)
    main(y)
    """
```

데이터 프레임을 num_cores 로 잘라서 전처리를 하는 것이다 보니,  
평균값 대체나 중앙값 대체 같은 전처리는 적합하지 않다.  

하지만 단순 replace나, text 전처리 등 시간이 오래 걸리는 경우를 거의 10배 이상 단축시키는 놀라움을 보인다.  
 
<div class='notice--info' markdown='1'>
다음에는 mutlithreading을 사용해보고 올려보도록 해야겠다.
</div>

```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```
