---
layout: single
title:  "Django Project"
categories: "Coding"
tags: [Python, Djnago]
author_profile: false
---

# Django Project

- Djnago 프로젝트 (인프런 강의 도움)
- MTV(Model, Template, View)

## 개발 과정

- Setting
- IDE: VScode
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

## 설정 변경

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


​     
​     





## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/Django_Project)
[Django공식페이지](https://www.djangoproject.com/)