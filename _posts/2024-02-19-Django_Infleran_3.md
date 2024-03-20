---
layout: single
title:  "Django Project - (3)"
categories: "Coding"
tags: [Python, Djnago]
author_profile: false

---

# Django Project

- Djnago 프로젝트 (인프런 강의 도움)
- Tetmplate 구성

## 개발 Settings
- IDE: VScode
- OS: Mac OS M1
- Python: 3.12.2
- Django: 5.0.3


### MTV?

![image-20240319220333271](/images/2024-02-19-Django_Infleran/image-20240319220333271.png)

- Django의 기본 구조이며 M(model)은 DB와 연동하여 데이터 호출(ORM - Object Relational Model)
- T(Template)는 보여주는 페이지(HTML)
- V(view)는 model로 부터 수집하거나 라우팅 규칙으로 url를 호출


# Template
   - MTV 중 Template 구조 작성
   - 템플릿 파일은 주로 HTML, XML, JSON
   - [장고 공식 템플릿](https://docs.djangoproject.com/en/5.0/topics/templates/)
   - Extends/Include를 자주 쓰인다.

## Extends 
   - HTML 파일들은 구역을 지정하여 만든다.

## Include
   - 만들어진 HTML를 불러와서 Template에 붙혀준다.

# Templates 폴더 생성
   1. HTML 파일 만들기
      - 프로젝트 폴더에 새로운 폴더를 만든다.
      `mkdir -p templates`
      - .html 파일 생성

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    Hello World!
</body>
</html>

```

   2. view 수정
      - 현재는 httpresspone로 호출하지만 html파일 호출하기 위해 render 를 사용한다.

```
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.


def helloworld(request):
    return render(request, 'base.html')
```

   3. Templates 폴더 등록
      - 생성한 폴더를 읽을수 있도록 Settings에 등록

```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

```

   4. 결과 

   ![image-20240320152350123](/images/2024-02-19-Django_Infleran_3/image-20240320152350123.png)



## Reference

[개인 Code 기록 github](https://github.com/chusonghyeon/Django_Project)

[인프런 강의](https://www.inflearn.com/course/%EC%9E%A5%EA%B3%A0-%ED%95%80%ED%84%B0%EB%A0%88%EC%8A%A4%ED%8A%B8/dashboard)

[Django공식페이지](https://www.djangoproject.com/)