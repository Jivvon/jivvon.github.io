---
title: [python] 파일명 한번에 바꾸기
tags: python
---

과제를 채점해야 하는데 파일명이 각자의 개성에 맞게 제출하여 일괄 처리가 힘들다.
python을 이용하여 파일명을 한번에 바꿔보자.

`학번_이름_개성만끽추가이름들(심지어 공백도 있음).확장자` 형태로 되어있으므로 이를
`학번_이름.확장자` 로  바꿀 생각이다.

```python
# -*- encoding:utf-8 -*-
import sys
import re
from os import rename, listdir, path

# 현재 위치의 파일 목록
files = listdir()

# 정규식 패턴
filename_p = r"^^[0-9]*_[^0-9a-zA-Z_]*"

for name in files:
    # 파이썬 실행파일명과 맥용 파일은 변경하지 않음
    if sys.argv[0].split("/")[-1] == name or ".DS_Store" == name:
        continue

    filename = re.compile(filename_p) # 파일 이름만 추출
    extention = path.splitext(name)[-1] # 확장자

    filename = filename.match(name).group() # 추출한 파일 이름 문자열로
    new_name = filename + extention # 새로운 파일 전체 이름

    rename(name, new_name)
```