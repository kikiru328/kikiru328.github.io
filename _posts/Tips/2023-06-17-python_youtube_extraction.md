---
title : "Python를 이용한 Youtube 음원 추출 코드"
excerpt : "Python Youtube"

categories: 
 - Tips
tags:  
 - [Python, Youtube, Extraction]


toc : true
toc_sticky : true



date : 2023-06-17 
last_modified_dat : 2023-06-17
---
<div class='notice--info' markdown='1'>
Youtube 영상에서 음원을 추출하는 방법을 알아보자
</div>

<div class='notice--danger' markdown='1'>
Youtube 영상 다운로드 자체는 불법이 아니다.  
하지만 다운받은 영상 혹은 컨텐츠를 `상업적`으로 이용하면 불법이니  
꼭 숙지하고 사용하기 바란다.
</div>

```python
import os
import pandas as pd
import pytube
from tqdm import tqdm
import argparse

class Extractor:
    def __init__(self, excel_path, save_path):
        self.excel_path = excel_path 
        self.save_path = save_path
        
    def read_excel_file(self):
        return pd.read_excel(self.excel_path)
        
    def extract(self, link):
        try:
            yt = pytube.YouTube(link)
            file_path = yt.streams.filter(only_audio=True).first().download()
            return file_path
        except Exception as e:
            print(e)
            return None
        
    def change_extension(self, file_path):
        try:
            new_file_path = file_path.replace('.mp4', '.mp3')
            os.rename(file_path, new_file_path)
            print(new_file_path)
            return new_file_path
        except Exception as e:
                print(e)
                return None
        
def main():
    parser=argparse.ArgumentParser()
    parser.add_argument('--excel_path', type=str)
    parser.add_argument('--save_path', type=str)
    args=parser.parse_args()
    
    extractor = Extractor(args.excel_path, args.save_path)
    df = extractor.read_excel_file()
    
    for ind, link in enumerate(tqdm(df['link'], total=len(df))):
        file_path = extractor.extract(link)
        new_file_path = extractor.change_extension(file_path)
        df.loc[ind, 'save_path'] = new_file_path
    
    df.to_excel(args.excel_path, index=False)

if __name__ == '__main__':
    main()
```

```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```
