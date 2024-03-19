---
layout: single
title:  "Django Project - (2)"
categories: "Coding"
tags: [Python, Djnago]
author_profile: false

---

# Django Project

- Djnago 프로젝트 (인프런 강의 도움)
- 환경변수 설정

## 개발 Settings
- IDE: VScode
- OS: Mac OS M1
- Python: 3.12.2 -> 버전은 개인 취향
- Django: 5.0.3 -> 버전은 개인 취향

# 환경변수 설정
   - 환경변수 중요한 정보나 호출해야 하는 변수를 따로 지정한다.

1. SecertKey 설정
   - Settings에 Secertkey는 중요하므로 숨겨야 한다.
   - django 에서 지원하는 [django-environ](https://django-environ.readthedocs.io/en/latest/index.html) 를 설치한다.
   -  `pip install django-environ`

2. .env 파일 생성
   - 모든 변수에 대한 정보를 저장하는 곳으로 코드 상에 직접적으로 표시 하면 안된다.
   - [.env](https://django-environ.readthedocs.io/en/latest/quickstart.html) 파일을 생성하여 이곳에 정보를 저장한다.
   - ` mkdir -p .env` -> .env가 아니더라도 다른 이름으로 지정해도 된다.
   - 아래의 내용을 저장한다.

```
DEBUG=on
SECRET_KEY={여기에 settings에 있는 SecertKey를 넣는다.}
DATABASE_URL=psql://user:un-githubbedpassword@127.0.0.1:8458/database
SQLITE_URL=sqlite:///my-local-sqlite.db
CACHE_URL=memcache://127.0.0.1:11211,127.0.0.1:11212,127.0.0.1:11213
REDIS_URL=rediscache://127.0.0.1:6379/1?client_class=django_redis.client.DefaultClient&password=ungithubbed-secret
```

3. Settings 수정
   - 이제 SecertKey를 바꾸자
   - 메인 프로젝트 폴더에 settings.py 에서 수정

```
import os
import environ

env = environ.Env(
    DEBUG=(bool, False)
)
...

# BASE_DIR 밑에 위치 시킨다.
environ.Env.read_env(
    env_file=os.path.join(BASE_DIR, '.env')
)
...

...

SECRET_KEY = env('SECRET_KEY')

...
```
 
## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/Django_Project)

[인프런 강의](https://www.inflearn.com/course/%EC%9E%A5%EA%B3%A0-%ED%95%80%ED%84%B0%EB%A0%88%EC%8A%A4%ED%8A%B8/dashboard)

[Django공식페이지](https://www.djangoproject.com/)