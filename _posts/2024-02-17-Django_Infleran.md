---
layout: single
title:  "Django Project"
categories: "Coding"
tags: [Python, Djnago]
author_profile: false
---

# Django Project

- Djnago 프로젝트 (인프런 강의 도움)
- 프로젝트 설정과 앱 만들기

## 개발 과정

### Settings
- IDE: VScode
- OS: Mac OS M1
- Python: 3.12.2 -> 버전은 개인 취향
- Django: 5.0.3 -> 버전은 개인 취향

1. Mac OS M1 환경에서 생성
   - `python mkdir -p {새로운 장고 프로젝트 폴더 생성}s`

2. Python 가상환경(.venv)
   - `python -m venv {설정할 가상환경 이름}`
   
3. 가상환경 실행
   - `source {설정한 가상환경이름}/bin/activate`
   
4. Django 설치
   - `python install django`

### DJango 설정 

1. Django admin 설정
   - `django-admin startproject {설정할 프로젝트 이름} .`

   - Django 프로젝트 구조
```
{설정한 프로젝트 폴더}
├───manage.py
└───{설정한 프로젝트 이름}
    ├─── settings.py
    ├─── assgi.py
    ├─── urls.py
    ├─── wsgi.py
    └─── __init__.py
```

2. Settings 변경
   - `cd {설정란 프로젝트 이름}`
   - `vi settings`

```
LANGUAGE_CODE = 'ko-kr'
TIME_ZONE = 'Asia/Seoul'
```

3. 실행
   - `cd ..` -> 상위 폴더로 이동
   - `python manage.py runserver` -> 8000포트로 해서 사이트가 열린다.
   -  접속: (http://localhost:8000/)


4. 장고 로컬 화면
![image-20240319144413659](/images/2024-02-17-Django_Infleran/image-20240319144413659.png)


# App만들기
- 프로젝트에 필요한 app 생성


## 새로운 App 폴더 만들기
1. App 생성
   - 프로젝트 폴더에서 실행
   - `python manage.py startapp {생성할 폴더 이름}`
   - 기존 프로젝트 위에 새로운 App 폴더가 생긴다.

```
App 구조
{설정한 App 폴더}
├─── admin.py
├─── app.py
├─── model.py
├─── test.py
├─── urls.py
└─── view.py
```

2. Settings에 등록
   - App를 사용하기 위해 등록해 준다.
   - INSTALLED_APPS 리스트 안에 생성하였던 App 를 넣어준다.

3. Hello world 페이지 생성
   - App 폴더에 view.py 에서 Hello World 만들기

```
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.

def helloworld(request):
    return HttpResponse('Hello world!')
```

4. 메인 프로젝트에 urls 수정하여 App urls 등록
```
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('{app폴더 이름}/', include('{app 폴더 이름}.urls')),
]
```

5. App폴더에도 url를 만든다
   - urls 생성하여 메인에서 바로 호출 할 수 있게끔 한다.
```
from django.urls import path
from {app폴더이름}.views import helloworld

app_name = '{url 이름}'

urlpatterns = [
    path('hello_world/', helloworld, name='hello_world'),
]
```

6. 재기동 
   - `python manage.py runserver`
   - 주소창에서 localhost:8000/{url 이름}/hello_world 를 하면 'Hello world!'가 나온다.
​ 

## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/Django_Project)
[인프런 강의](https://www.inflearn.com/course/%EC%9E%A5%EA%B3%A0-%ED%95%80%ED%84%B0%EB%A0%88%EC%8A%A4%ED%8A%B8/dashboard)
[Django공식페이지](https://www.djangoproject.com/)