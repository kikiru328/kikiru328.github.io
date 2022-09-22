---
title : "다시 쓰겠지만 일단 파이썬 클린코드"
excerpt : "파이썬도 못하는데 파이썬 클린코드 ㅋㅋ"

categories : 
    - Devlog
tags : 
    - [Dev, Python, Tip]

toc : true
toc_sticky : true

date : 2022-09-18
last_modified_at : 2022-09-18
---
# *Introduction*

### ***Why?***
파이썬은 가독성이 좋지 않으면 안쓴 것 보다 못하다.  
근데 자신이 쓴 코드가 가동성이 제일 뛰어난다 한들, 남이 어디에 뭐있는지 못 알아보면 가독성이 좋은 코드가 아니다. ~~마치 관물대정리와 같다~~    

</br>

### ***Convention***

그래서 나온게 PEP8, Python Convention이다.  
<span style="color:gray">참조 : </span> [Python PEP8](https://peps.python.org/pep-0008/)  ~~<span style="color:gray">영문이라 보기 싫을수도 있음.</span>~~  

모두가 같은 포맷으로 작성한 코드가 가장 가독성이 좋게 될 것이고, 가독성이 좋으니 이해하기도 편할 것이다.  

하지만 장점이 있으면 단점도 있는 법.  

|장점|단점|   
|:---:|:---:|
가독성| **<span style="color:Yellow">귀찮음</span>**|

하지만 PEP8을 기준으로 클린코드를 작성하는 것이 익숙해지면, 일단 코드를 보여줌에 있어서 **자신감**이 생기고 **인수인계**할 때 편리할 것으로 생각이 된다. ~~물론 Github에 올릴 때도 부끄럽진 않을 것이다~~

</br></br>

<!-- # ***PEP8*** -->
<!-- ## **CODE LAYOUT**
### **Indentation**
> Indentation. 들여쓰기  -->


# ***Tips***
<span style="color:gray">Introduction</span>  
PEP8을 기본으로 작성하면 좋긴한데, Library를 사용하거나, 다른 형식으로 사용했을 때 직관적으로 만드는 경우가 있다.

## *Pathlib*
> `Pathlib`을 사용하면 **연산자**를 사용할 수 있기 떄문에 더욱 직관적으로 경로를 파악하기가 쉽다.  
> 그리고  `/` 을 빼먹어서 에러를 만들 수 없다. ~~만들면 천재~~

</br>

<span style="color:red">NO</span>
~~~python
path = base + f'/{usr}' + f'/{file}'
path = os.path.join(base,file)
~~~
**<span style="color:skyblue">Yes</span>**
~~~python

~~~









