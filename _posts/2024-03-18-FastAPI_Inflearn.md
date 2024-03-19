---
layout: single
title:  "FastAPI 동시성 프로그래밍: 데이터 수집부터 웹 개발까지"
categories: "Coding"
tags: [Python, FastAPI]
author_profile: false
---


# FAST API 시작

| 동시성 프로그래밍(한순간에) | 병렬성 프로그래밍 |
| --- | --- |
| - 클라이언트와 서버간 통신 | - 비디오, 오디오 또는 이미지 처리 |
| - 시스템 디스크 파일 읽기/쓰기 | - 컴퓨터 비전 |
| - 데이터베이스 쿼리 작업 | - 머신러닝 |
| - API 사용 | - 딥러닝 |

![image-20240318192715101](/images/2024-03-18-FastAPI_Inflearn/image-20240318192715101.png)

왼쪽은 일반적인 파이썬  오른쪽은 동시서 프로그래밍으로 사용하여 시간 차이 구분이 가능

## 개발 세팅

- python 버전 : 3.10 → 인공지능사관학교 프로젝트를 위해 버전 향상 (기존은 Python 3.7 버전)
- 미니콘다 사용(기업 프로젝트에서 버전관리를 위해 사용)


### 미니콘다

- 개별적으로 사용하려는 각 패키지를 설치하지 않아도 된다
- 한번에 150개가 넘는 패키지를 설치할 시간이나 디스크 공간이 없을때
- 파이썬과 conda명령에 빠르게 엑세스하고 나중에 다른 프로그램을 정렬하고 싶을때

### 아나콘다

- 콘다 또는 파이썬 처음 접할때 이용
- python과 150개가 넘는 과학 패키지가 한 번에 자동으로 설치되는 편리하다
- 시간 및 디스크 공간이 필요
- 개별적으로 사용하려는 각 패키지를 설치하고 싶지 않을

![image-20240318192805615](/images/2024-03-18-FastAPI_Inflearn/image-20240318192805615.png)

![image-20240318192826413](/images/2024-03-18-FastAPI_Inflearn/image-20240318192826413.png)

가상환경 conda와 비슷하다

conda 터미널이나

VSCode에 접속하여 venv를 설치하고 연결해 준다

→ 만들었는데 이름이 생성이 안되는 경우는 환경변수를 만들어서 지정해준다

Linter: 인터프리터 언어이기때문에 미리 점검해주는 것

→ 명령탈레트 Python: Sel까지 입력

- Python Linter클릭
- 기본은 flak8 : 체크해주는 것

Python 과 PIP 명령어 패키지 확인 

requirements.txt파일 다운로드 하는법

→ pip install -r requirements.txt

# 시작

- pip install fastapi
- pip install uvicorn
- 실행 명령어 unicorn main:app —reload

실행하면 주소값 출력 json형태의 api값 출력

주소값에 /docs를 입력시 기본적인 api창이 나온다.(swagger)

restapi를 json형식으로 보여준다

주소값에 /redoc를 입력시 읽기 권한으로 보여주기 된다.

→ openapi를 보여준다
![image-20240318192855416](/images/2024-03-18-FastAPI_Inflearn/image-20240318192855416.png)

MariaDB연동

SQLAIchemy - ORM 방식 (관계형 데이터베이스와 SQL를 연결)

Starlette - 

## 클라이언트와 API

![image-20240318192923032](/images/2024-03-18-FastAPI_Inflearn/image-20240318192923032.png)

웹브라우저 상세보기

![image-20240318192945621](/images/2024-03-18-FastAPI_Inflearn/image-20240318192945621.png)

HTTP 관련 문서 : [HTTP](https://developer.mozilla.org/ko/docs/Web/HTTP)

API 관련 문서 : [API](https://www.redhat.com/ko/topics/api/what-are-application-programming-interfaces)

## ASGI, UVICORN

ASGI : 

Python와 서버에 연결해 주는 입구 역할, 비동기식으로도 지원 가능하

애플리케이션 프로그램(FastAPI)의 실행 결과를 웹 서버에 전달해주며, 웹 서버는 ASGI로부터 전달 받은 응답 결과를 웹 클라이언트(브라우저)에 전송한다. 

- [ASGI docs](https://asgi.readthedocs.io/en/latest/introduction.html#)
- 서버 게이트웨이 : 서버로 들어가는 입구 역할

Uvicorn :

ASGI의 웹 서버(프로세스 관리자, 실행기)

## FastAPI

![image-20240318193035290](/images/2024-03-18-FastAPI_Inflearn/image-20240318193035290.png)

현재 내가 있는 파일 경로 지정하여 templates 쉽게 이용하기

![image-20240318193102173](/images/2024-03-18-FastAPI_Inflearn/image-20240318193102173.png)

Request가 없으면

![image-20240318193118994](/images/2024-03-18-FastAPI_Inflearn/image-20240318193118994.png)

요청하는 주체에 대한 정보들을 가지고 있는 객체

context는 무조건 request로 반환해야 한다.

실행 시킬때 터미널에서 uvicorn main:app —reload이렇게 했지만 python스크립트 파일로 실행하기

![image-20240318193138971](/images/2024-03-18-FastAPI_Inflearn/image-20240318193138971.png)

이젠 터미널에서 python server.py만 실행하면 명령어 대신하여 사용 가능하다

![image-20240318193156474](/images/2024-03-18-FastAPI_Inflearn/image-20240318193156474.png)

외부에 노출하지 않을 변수들을 모아둔 것이다. 

![image-20240318193216009](/images/2024-03-18-FastAPI_Inflearn/image-20240318193216009.png)

serets.json안에 있는 변수를 호출하여 실행한다. 


# Reference 

[개인 기록 Code github](https://github.com/chusonghyeon/FastAPI_Project/tree/master/Fast_API_MogoDB)

[https://github.com/amamov/teaching-type-python-oop/tree/main/00 첫 시작](https://github.com/amamov/teaching-type-python-oop/tree/main/00%20%EC%B2%AB%20%EC%8B%9C%EC%9E%91)

[파이썬 동시성 프로그래밍 GitHub](https://github.com/amamov/teaching-async-python)
 
[마인드 맵](https://async-py.netlify.app/)

[파이썬 코루틴 공식문서](https://docs.python.org/ko/3/library/asyncio-task.html)

[파이썬 동시성 프로그래밍: 데이터 수집부터 웹 개발까지(with FastAPI)](https://www.inflearn.com/course/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%8F%99%EC%8B%9C%EC%84%B1-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D/dashboard)

[FastAPI기초](https://www.youtube.com/watch?v=ooHWO2gP7Qo&list=PLr_ki3_GfpZMTSdQehJRrIwuDGOHh5LvB&index=6)