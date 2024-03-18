---
layout: post
title:  "FastAPI 동시성 프로그래밍: 데이터 수집부터 웹 개발까지"


---

# FAST API

## Python를 활용하여 동시성 프로그래밍: 데이터수집부터 웹 개발까지

# FAST API 시작

- 인프런 강의 참조하여 시작

→ 출처: [파이썬 동시성 프로그래밍: 데이터 수집부터 웹 개발까지(with FastAPI)](https://www.inflearn.com/course/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%8F%99%EC%8B%9C%EC%84%B1-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D/dashboard)

- 유튜브 강의로 참조하여 시작
- → 출처 : [FastAPI기초](https://www.youtube.com/watch?v=ooHWO2gP7Qo&list=PLr_ki3_GfpZMTSdQehJRrIwuDGOHh5LvB&index=6)

| 동시성 프로그래밍(한순간에) | 병렬성 프로그래밍 |
| --- | --- |
| - 클라이언트와 서버간 통신 | - 비디오, 오디오 또는 이미지 처리 |
| - 시스템 디스크 파일 읽기/쓰기 | - 컴퓨터 비전 |
| - 데이터베이스 쿼리 작업 | - 머신러닝 |
| - API 사용 | - 딥러닝 |

![image-20240318162828784](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318162828784.png)



왼쪽은 일반적인 파이썬  오른쪽은 동시서 프로그래밍으로 사용하여 시간 차이 구분이 가능

# 배울 목차

## 파이썬 코투틴과 비동기 함수

- I/O바운드 & CPU 바운드, 블로킹
- 동기 VS 비동기
- 파이썬 코루틴의 이해
- 파이선 코루틴 활용

## 파이썬 멀티 스레딩과 멀티 프로세싱

- 컴퓨터 구조와 운영체제 기본
- 동시성 VS 병렬성
- 파이썬 멀티 스레딩
- 파이썬 멀티 프로세싱, GIL

## 동시성 프로그래밍으로 데이터 수집

- 서버와 클라이언트, HTTP, API이해
- 웹 크롤링, 스크래핑과 법적 주의사항
- 동시성 프로그래밍으로 웹 크롤링, 스크래핑 성능 극대화
- 포스트맨 셋업, 네이버, 카아오 오픈 API 사용하기
- 오픈 API를 활용한 이미지 데이터 수집
- 동시성 프로그래밍으로 이미지 다운로더 개발(feat. aiofiles)

## 빅데이터 관리의 핵심 기술 MongoDB 이해와 구축

- MongoDB의 이해
- MongoDB Atlas 구축
- MongoDB 접근 권한 설정 & Compass 셋업
- MongoDB CRUD

## 실전프로젝트 : 콜렉터스 북북이(FastAPI)

- 프로젝트 소개
- 비동기 게이트웨이 ASGI, Uvicorn
- FastAPI Tutorial
- 프로젝트 셋업
- FastAPI + MongoDB
- 책 데이터 수집 클래스 개발
- 서비스 로직 개발
- 프로젝트 마무

## AWS 클라우드 컴퓨팅으로 프로젝트 배포하기

- 다른 사용자가 사용가능 할 수 있게 서버로 배포

# 강좌 GitHub구조 및 파이썬 마인드 맵

GitHub : https://github.com/amamov/teaching-async-python

 

마인드 맵 : [https://async-py.netlify.app/](https://async-py.netlify.app/)

파이썬 코루틴 공식문서 : [https://docs.python.org/ko/3/library/asyncio-task.html](https://docs.python.org/ko/3/library/asyncio-task.html)

출처: [**[파이썬 동시성 프로그래밍 : 데이터 수집부터 웹 개발까지 (feat. FastAPI)](https://www.inflearn.com/course/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%8F%99%EC%8B%9C%EC%84%B1-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D/dashboard)**]

# 개발 세팅

[https://github.com/amamov/teaching-type-python-oop/tree/main/00 첫 시작](https://github.com/amamov/teaching-type-python-oop/tree/main/00%20%EC%B2%AB%20%EC%8B%9C%EC%9E%91)

- python 버전 : 3.10 → 인공지능사관학교 프로젝트를 위해 버전 향상 (기존은 Python 3.7 버전)
- 미니콘다 사용(기업 프로젝트에서 버전관리를 위해 사용)

  

### 미니콘다

- 개별적으로 사용하려는 각 패키지를 설치하지 않아도 된다
- 한번에 150개가 넘는 패키지를 설치할 시간이나 디스크 공간이 없을때
- 파이썬과 conda명령에 빠르게 엑세스하고 나중에 다른 프로그램을 정렬하고 싶을때

## 아나콘다

- 콘다 또는 파이썬 처음 접할때 이용
- python과 150개가 넘는 과학 패키지가 한 번에 자동으로 설치되는 편리하다
- 시간 및 디스크 공간이 필요
- 개별적으로 사용하려는 각 패키지를 설치하고 싶지 않을

![image-20240318163124680](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163124680.png)

![image-20240318163152011](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163152011.png)

가상환경 conda와 비슷하다

conda 터미널이나

VSCode에 접속하여 venv를 설치하고 연결해 준다

→ 만들었는데 이름이 생성이 안되는 경우는 환경변수를 만들어서 지정해준다

Linter: 인터프리터 언어이기때문에 미리 점검해주는 것

→ 명령탈레트 Python: Sel까지 입력

- Python Linter클릭
- 기본은 flak8 : 체크해주는 것

Python 과 PIP 명령어 패키지 확인 

참조:

[https://github.com/amamov/teaching-type-python-oop/tree/main/00 첫 시작](https://github.com/amamov/teaching-type-python-oop/tree/main/00%20%EC%B2%AB%20%EC%8B%9C%EC%9E%91)

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

![image-20240318163216912](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163216912.png)

MariaDB연동

SQLAIchemy - ORM 방식 (관계형 데이터베이스와 SQL를 연결)

Starlette - 

# 클라이언트와 API

![image-20240318163256693](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163256693.png)

웹브라우저 상세보기

![image-20240318163318658](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163318658.png)

HTTP 관련 문서 : [HTTP](https://developer.mozilla.org/ko/docs/Web/HTTP)

API 관련 문서 : [API](https://www.redhat.com/ko/topics/api/what-are-application-programming-interfaces)

# ASGI, UVICORN

ASGI : 

Python와 서버에 연결해 주는 입구 역할, 비동기식으로도 지원 가능하

애플리케이션 프로그램(FastAPI)의 실행 결과를 웹 서버에 전달해주며, 웹 서버는 ASGI로부터 전달 받은 응답 결과를 웹 클라이언트(브라우저)에 전송한다. 

- [ASGI docs](https://asgi.readthedocs.io/en/latest/introduction.html#)
- 서버 게이트웨이 : 서버로 들어가는 입구 역할

Uvicorn :

ASGI의 웹 서버(프로세스 관리자, 실행기)

# FastAPI

![image-20240318163350697](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163350697.png)

현재 내가 있는 파일 경로 지정하여 templates 쉽게 이용하기

![image-20240318163407646](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163407646.png)

Request가 없으면

![image-20240318163524087](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163524087.png)

요청하는 주체에 대한 정보들을 가지고 있는 객체

context는 무조건 request로 반환해야 한다.

실행 시킬때 터미널에서 uvicorn main:app —reload이렇게 했지만 python스크립트 파일로 실행하기

![image-20240318163423487](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163423487.png)

이젠 터미널에서 python server.py만 실행하면 명령어 대신하여 사용 가능하다

![image-20240318163500384](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163500384.png)

외부에 노출하지 않을 변수들을 모아둔 것이다. 

![image-20240318163541815](/Users/chusonghyeon/githublog/chusonghyeon.github.io/images/2024-03-18-FastAPI/image-20240318163541815.png)

serets.json안에 있는 변수를 호출하여 실행한다. 

## Udemy강의(Deployment of Machine Learing Models)

- 시작하기 전
    - AI 모델링과 FastAPI로 API호출하고 React JS로 연동 및 AWS에 배포작업
    - 광주인공지능사관학교에 프로젝트에 필요한 능력
    - CI/CD하는 법 배우기(Docker)
    - AWS 서버 배포
    - 영어자막으로 이해하면서 가기…(ㅜ)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2015.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2016.png)
    
    - Python에서 모델을 배포하는 방법
    - 모델에 적응할 준비가 된 코드
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2017.png)
    
    - 모델을 배포하고 모범사례를 배우려는 데이터 과학자
    - 기계학습을 시작하려는 소프트웨어 개발자
    - Python 프로그래밍 및 기계학습에 대한 지식

- 소개
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2018.png)
    
    - 과정 자료
        - 코드
        - 프레젠테이션
        - 데이터 셋
    - 기계학습에 대해 자세히 알아볼 수 있는 추가 리소스
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2019.png)
    
    - 모델 배포 및 중요한 이유
    - 연구 및 가상환경
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2020.png)
    
    - 기계학습시스템 아키텍처
        - 아키텍처 구성요소
        - 적합한 시스템 아키텍처를 생성하기 위한 과제 및 원칙
        - 다양한 아키택처 접근 방식
    - 재현 가능한 파이프라인 구축
        - 과제 및 이를 완화하는 방법
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2021.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2022.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2023.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2024.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2025.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2026.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2027.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2028.png)
    
    Course Requirements(과정 요구사항)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2029.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2030.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2031.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2032.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2033.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2034.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2035.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2036.png)
    
    Course Materials(과정 자료)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2037.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2038.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2039.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2040.png)
    
    - 머신러닝 자료[https://github.com/trainindata/deploying-machine-learning-models]
    - 프레젠테이션 자료[https://www.dropbox.com/sh/effzx0nmstqcr2e/AAB4sB33hv5jULKj-6cj3XqQa?dl=0]
    - DataSet(주택 가격 - 고급 회귀 기법)[[https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data)]
    - 추가 관련 리소스
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2041.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2042.png)
    
    필요한 기술에 대한 추가 리소스
    1) 관련 기계 학습 및 데이터 과학 기술에 대해 어떻게 더 배울 수 있습니까?
    - [Python 프로그래밍에 대해 자세히 알아볼 수 있는 리소스](https://trainindata.medium.com/discover-the-best-resources-to-learn-python-for-data-science-35b87d38fadf)
    - [R 프로그래밍에 대해 자세히 알아볼 수 있는 리소스](https://trainindata.medium.com/find-out-the-best-resources-to-learn-r-for-data-science-9ff1743b274b)
    - [기계 학습에 대해 자세히 알아볼 수 있는 리소스](https://trainindata.medium.com/find-out-the-best-resources-to-learn-machine-learning-cd560beec2b7)
    - [데이터 과학에 대해 자세히 알아볼 수 있는 리소스](https://trainindata.medium.com/discover-the-best-resources-to-learn-data-science-2978499fc804)
    
    기계 학습은 매우 광범위한 분야이므로 다양한 알고리즘을 폭넓게 이해하려면 여러 과정과 리소스를 방문해야 할 가능성이 높습니다.
    
    2) 기계 학습을 위한 변수 전처리 및 데이터 정리에 대해 자세히 알고 싶습니다. 
    이 과정의 마지막 섹션에서 기능 엔지니어링에 대한 종합 과정에 대한 링크를 찾을 수 있습니다. 한편 다음 기사를 살펴보십시오.
    
    - [기계 학습을 위한 기능 엔지니어링: 포괄적인 개요](https://trainindata.medium.com/feature-engineering-for-machine-learning-a-comprehensive-overview-a7ad04c896f8)
    - [기계 학습을 위한 기능 엔지니어링에 대해 배울 수 있는 최고의 리소스](https://trainindata.medium.com/best-resources-to-learn-feature-engineering-for-machine-learning-6b4af690bae7)
    - [Python을 사용한 기능 엔지니어링 기법의 실용적인 코드 구현](https://towardsdatascience.com/practical-code-implementations-of-feature-engineering-for-machine-learning-with-python-f13b953d4bcd)
    
    3) git에 대해 더 알고 싶은데 어떻게 해야 합니까?
    여기 Udemy에는 시도할 수 있는 높은 등급의 여러 과정이 있습니다.
    
    How to approach rhe course(과정에 접근하는 방법)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2043.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2044.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2045.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2046.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2047.png)
    
- 기계학습 모델의 배포
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2048.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2049.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2050.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2051.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2052.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2053.png)
    
- 기계학습 파이프라인의 배포
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2054.png)
    
    - 기계 학습 모델을 이미징하는 간단한 방법으로 조직은 클라우드의 데이터베이스에 저장하거나 타사의 API에서 검색할 수 있는 일부 데이터를 보유합니다.
    - 그런 다음 이러한 데이터를 공급하여 비즈니스에 유용한 몇 가지 예측을 제공할 수 있는 모델을 구축합니다.
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2055.png)
    
    - 그러나 데이터는 기계 학습 모델을 교육하는 데 사용할 준비가 거의 되어 있지 않습니다.
    - 실제로 데이터는 형식과 품질 측면에서 다양한 특성을 나타내므로 적합하지 않습니다.
    - 예를 들어 데이터 1% 누락된 값과 라이브러리의 일부 튜터링 기계 학습 모델은 데이터 세트의 값 부족을 처리할 수 없습니다.
    - 데이터는 또한 숫자 대신 문자열을 포함할 수 있으며 컴퓨터는 다음을 사용하여 계산을 수행할 수 없습니다.
    - 그래서 우리는 그것들을 데이터의 변수에 대한 숫자로 변환해야 합니다. 일부 분포와 변수의 분포는 모델의 성능에 영향을 미칠 수 있습니다.
    - 데이터는 또한 이상값을 나타낼 수 있고 일부 모델은 이상값의 존재에 민감하므로 이러한 값을 검열하거나 제거하도록 선택과 크기를 조정해야 합니다.
    - 때로는 데이터가 텍스트 형식이므로 이 텍스트에서 정보를 추출할 수 있어야 합니다.
    - 때로는 계산할 수 있는 일종의 입력으로 데이터를 이미지로 가져오고 다시 이 이미지에서 데이터 또는 프레임을 추출할 수 있어야 합니다.
    - 일부 데이터는 트랜잭션일 수 있으며 이 데이터를 집계하여 고객에 대한 보다 간소화된 보기를 가질 수 있습니다.
    - 때로는 데이터가 지리적 위치이고 우리는 이 데이터에서 기능을 추출하기를 원합니다.
    - 때로는 특정 방식으로 처리하거나 집계해야 하는 시계열이 있고 모델에서 바로 사용할 수 없는 날짜 및 시간 변수가 있을 수 있지만 대신
    이러한 데이터를 사용하여 교육하기 전에 많은 변수 변환을 수행해야 합니다
    - 하지만 데이터에서 기능을 추출하거나 기존 기능을 결합하여 새로운 기능을 생성해야 합니다.
    - 따라서 우리는 모델을 교육하는 것에 대해 이야기하는 것이 아니라 모델을 교육하기에 적합하도록 데이터를 전처리하는 것에 대해서도 이야기하고 있습니다.
    - 그리고 때때로 우리는 우리가 사용할 수 있는 모든 기능을 사용하고 싶지 않을 수도 있습니다.
    - 우리는 기능 선택 유형을 포함합니다.
    - 기계 학습 파이프라인에는 원시 데이터에서 예측을 얻을 수 있도록 기계 학습 모델을 교육하는 데 적합한 데이터 형식으로 이동할 수 있는 다양한 단계가 포함되어 있습니다.
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2056.png)
    
    - 기계 학습 모델을 배포할 때 모델 자체를 배포할 뿐만 아니라 전체 파이프라인을 배포해야 합니다.
    - 연구와 생산 환경 모두에서 원시 데이터를 받을 가능성이 높기 때문입니다. 따라서 우리는 모델을 훈련하거나 모델이 훈련되면 접두어를 얻을 수 있는 성숙한 데이터를 생성할 수 있는 파이프라인의 단계가 필요합니다.
    - 머신 러닝 파이프라인의 여러 단계에 대한 자세한 내용은 섹션 4에서 나중에 설명하겠습니다.
    - 나머지 부분에서는 재현 가능한 기계 학습 파이프라인을 구축하는 개념에 중점을 둘 것입니다.

- 연구 및 생산 환경
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2057.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2058.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2059.png)
    
- 재현 가능한 기계학습 파이프라인 구축
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2060.png)
    
    - 기계 학습 모델의 배포는 우리 모델을 프로덕션에서 사용할 수 있도록 만드는 프로세스입니다.
    - 다른 소프트웨어 시스템에 예측을 제공할 수 있는 환경을 개발할 것은 소위 연구 환경에서 수행하는 기계 학습 모델입니다.
    - 이것은 데이터 사이언티스트가 자유를 가질 때 빅 데이터와 접촉하지 않는 고립된 환경입니다.
    - 다양한 모델을 시도하고 연구하고 특정 제품 요구에 대한 솔루션을 찾으려면 일반적인 설정에서 과거 데이터가 있고 이 데이터를 사용하여 기계 학습 모델을 교육합니다.
    - 연구 환경에서 모델의 성능에 만족하면 생산 환경으로 모델을 마이그레이션할 준비가 된 것입니다. 여기서 실 데이터에서 입력을 받고 결정을 내리는 데 사용할 수 있는 예측 결과를 출력할 수 있습니다.
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2061.png)
    
    - 실제로 기계 학습 파이프라인의 배포를 의미할 때 기계 학습 모델의 분산에 대해 자주 이야기합니다.
    - 데이터를 받은 순간부터 예측을 하는 순간까지 일어나야 하는 일련의 단계입니다.
    - 일반적인 기계 학습 파이프라인에는 많은 부분의 기능 변환 단계가 포함됩니다. 아마도 이것은 파이프라인의 가장 큰 부분일 것입니다.
    - 그런 다음 기계 학습를 훈련시키는 단계와 연구 환경에서 전체 파이프라인을 생성하는 예측을 출력하는 단계를 포함하여 전체 파이프라인을 생산 환경에 배포해야 합니다.
    - 우리는 또한 원시 데이터를 입력으로 받을 것이며 이를 해석하고 예측을 반환할 수 있도록 필요한 기능을 만들기 위해 변환해야 합니다.
    - 프로덕션에 파이프라인을 배포할 때
    파이프라인을 재현할 수 있는 방식으로 수행해야 합니다.
    - 연구 환경의 파이프라인과 프로덕션 환경의 파이프라인이 모두 동일한 원시 데이터 입력을 수신합니다. 두 파이프라인이 동일한 보호를 반환해야 합니다. 동일한 데이터 Khamsin 동일한 출력이 두 파이프라인에서 나와야 합니다.
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2062.png)
    
    - 우리가 구축하고 성능을 최적화한 프로젝트의 연구 단계가 비즈니스 가치를 극대화한다고 생각하는 이유는 무엇입니까?
    - 머신 러닝 파이프라인을 위한 머신 러닝 모델을 개발할 때 정확성, 정밀도와 같은 고전적인 메트릭을 활용하여 통계적 관점에서 모델 성능을 테스트한다고 말해야 합니다.
    - 중간 제곱 오차 및 친숙한 기타 메트릭을 기억하십시오. 또한 이러한 매개변수를 비즈니스 가치로 변환하는 메트릭도 평가합니다.
    - 예를 들어, 우리는 우리 모델이 창출할 증가된 수익, 증가된 고객 만족도 또는 우리가 관심 있고 조직에 따라 달라지는 다른 측정을 측정할 수 있습니다.
    - 제가 연구 환경에서 실생활, 즉 환경에 이르기까지 이 관점에서 보여주는 것처럼 이 수익 증가를 이 값으로 변환하는지  확인해야 합니다.

### 잠깐의 Flask

# **7.2b - 플라스크 참고 사항**

**Flask에 대한 빠른 참고 사항**

Flask 마이크로 프레임워크에 대한 자습서는 이 과정의 범위를 벗어납니다. (Flask에 익숙하지 않은 경우) Flask에 대해 무료로 사용할 수 있는 여러 리소스 중 일부를 검색해 보시기 바랍니다. 몇 가지 제안:

- 링크 Python 데코레이터 입문서: https://realpython.com/primer-on-python-decorators/
- 플라스크 시작하기: http://flask.pocoo.org/docs/1.0/quickstart/
- 플라스크 메가 튜토리얼: https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world
- 플라스크 청사진: http://flask.pocoo.org/docs/1.0/blueprints/
- Flask 소스 코드: https://github.com/pallets/flask (매우 읽기 쉽습니다!)
- Flask 웹 개발: Miguel Grinberg *의 Python으로 웹 애플리케이션 개발*

## Udemy강의(FastAPI)

- FastAPI는 가장 빠르게 성장하는 API프레임워크
- swagger UI
- 메서드
    - 메서드 사용법(GET, POST, UPDATE, DELETE)
    - 작업순서가 중요하다
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2063.png)
    
    - 순차적으로 하나씩 매칭되기 때문에 위에 all메서드를 우선적으로 해야 한다
- Enum
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2064.png)
    
    - 변수를 저장하여 전달한 매개변수로 사용
    - class를 이용해서 미리 정의된 값을 지정하여 호출하는 방식
- 쿼리매개변수
    - 기본적으로 경로 다음에 전달하는 매개변수
    - 질문에 의해 경로에서 경로로 구분
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2065.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2066.png)
    
    - 선택적 쿼리 매개변수로 사용가능하다
    - 먼저 입력값을 넣어서 호출하면 된다
    - 아래 사진이 쿼리이다
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2067.png)
    
    - 선택적 클래스 유형을 사용
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2068.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2069.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2070.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2071.png)
    
    - 매개변수를 생성하고 경로에 지정하여 호출하는 방식과 매개변수와 결합하여서 호출하는 법
- 상태표시 코드
    - [HTTP 상태 코드](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2072.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2073.png)
    
    - fastapi안의 패키에 status모듈을 호출해서 오류 메시지 표시 함수 출력
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2074.png)
    
    - 해당 응답에 대한 함수를 표시하여 상황에 맞는 상태코드를 입력
- 태그
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2075.png)
    
    - 단일 파일 내에서 작업을 구조화하고 구성 할 수 있어 분류할 수 있다
    - 문자열 기반으로 작업, 여러 범주를 제공 할 수 있다.
    - 변경 전
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2076.png)
    
    - 변경 후
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2077.png)
    
- 추가작업
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2078.png)
    
    - 간략한 요역
    - 태그를 제공한 방식과 유사하게 제공
    - 자세한 설명을 제공
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2079.png)
    
    - 추가적으로 내부의 상세 정보를 넣을 경우
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2080.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2081.png)
    
    - response 작업
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2082.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2083.png)
    
- 라우터
  
    응용프로그램을 다른 파일과 다른 구성요소로 구조화 하는 방법
    
    하나의 단일 파일에 모든 것을 포함하는 대신 더 많은 논리적 구성 요소로 구조화 한다
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2084.png)
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2085.png)
    
    main.py 수정 - router사용해서 정의
    
    Router라는 폴더 생성해서 blog_get.py파일 생성
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2086.png)
    
    파일 내용 작성 이후 확인
    
    이러면 복잡하게 main에다가 모든 경로 적을 필요 없고 APIRouter를 활용해서 호출 할 수 있다
    
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2087.png)
    
- 파라미터
    - Request body(요청목록)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2088.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2089.png)
        
        - 포스트 매서드에서는 쿼리 매개변수에 있는 모든 정보를 보내지 않는다
        실제로 요청 본문 내에서 더 자세한 정보를 보낸다
        - Pydantic의 기본 모델에서 상속(JSON방식)
        - Json으로 읽고 데이터 유효성 검사
        - 데이터 변환이 된다
        - Json으로 출력으로 얻는다.
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2090.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2091.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2092.png)
        
    - Path and Query parameters(경로 및 쿼리 매개변수)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2093.png)
        
        - Post요청에 작동하는 방식
        - 매개 변수 간에 변환, 데이터 유형을 얻는다
        - 본문 매개변수 : blog, 쿼리매개변수: version
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2094.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2095.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2096.png)
        
    - Parameter metadata(매개변수 메타데이터(데이터에 대한 데이터, 매개변수에 대한 정보))
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2097.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2098.png)
        
        - 메타데이터는 무언가의 정보, 문서에 표시되는 정보
        - API에 엑세스 하는 모든 사람에게 유용
        - 메타데이터를 첨부하는 방법과 매개변수에 다른 유형의 정보를 첨부하는 방법
        - 쿼리 구성으로 기본값을 제공
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%2099.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20100.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20101.png)
        
        - 본문 설명 추가
        - 병칠은 요청에서 전달 할 수 있는 매개변수의 이름
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20102.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20103.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20104.png)
        
        - 매개변수에 플래그를 설정 할 수 있다, 특정 매개변수가 더 이상 사용되지 않음을 나타내는 플래그
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20105.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20106.png)
        
    - Validators(유효성 검사)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20107.png)
        
        - 유효성 검사기는 우리가 매개 변수에 전달하는 데이터 또는 호출하는 소프트웨어를 분명히 확인한다
        - API는 매개변수로 전달 된다
        - 내부에 기본값을 제공(본문, 쿼리 또는 경로와 같은 구문 내부의 기본값)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20108.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20109.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20110.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20111.png)
        
        - 매개변수를 선택상이 아닌 것으로 만들 수 있으며 값을 요구하도록 할 수 있다
            - 세 개의 점으로 사용하는 것(Python의 줄임표 의미)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20112.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20113.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20114.png)
        
        - 똑같은 방식으로 Ellipsis작성하면 같은 방식으로 작동한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20115.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20116.png)
        
        - 최소 길이 유효성 검사(단순히 콘텐츠에 대해 최소한의 길이를 제공하는 매개변수를 요구)
        - 최소길이와 최대 길이를 설정할 수 있고 그 이상으로 넘어가면 error가 걸린다
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20117.png)
            
        - 정규식 유효성 검사(사용자가 설정한 값에 대해 유효성을 검사)
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20118.png)
            
            - regex조건 : a에서z까지 소문자와 공백출력가능, 별표를 제공
    - Multiple values(매개변수에 대해 여러 값을 얻는 방법)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20119.png)
        
        - HTML의 쿼리 매개변수는 여러 값을 받을 수 있으므로 동일한 매개변수가 값이 여러 개인 경우 요청에 여러 번 나타난다
        - 요청에 여러 번 나타나고 이러한 여러 값이 함수에 전달된다
        - 선택적 쿼리 매개변수를 정의하고 예상되는 유형의 목록으로 정의
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20120.png)
            
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20121.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20122.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20123.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20124.png)
        
        - 목록이 표시 된다
        - 쿼리 매개변수 내부에 기본값을 목록으로 제공가능
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20125.png)
            
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20126.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20127.png)
        
    - Number Validators(매개변수에서 받은 다양한 요소 유형의 목록 또는 배열)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20128.png)
        
        - 같은 방식으로 문자열과 숫자에 대한 유효성 검사도 있다
        - gt = 크다(초과)
        - ge = 크거나 같음(이상)
        - lt = 작다(미만)
        - le = 작거나 같다(이하)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20129.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20130.png)
        
        - comment_id 조건→ 유효성 검사를 추가하여 5보다 크고 작거나 최대값 10지정
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20131.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20132.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20133.png)
        
        - 10이 넘어갈 경우 error발생
    - Complex subtypes(복잡한 하위 유형/ 문자열 정수 부울 등)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20134.png)
        
        - 받고자 하는 문자열 목록을 추가 할 수 있다
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20135.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20136.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20137.png)
            
        - 데이터 구조를 바꿀 수 있다(List, set, dict,tuple)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20138.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20139.png)
        
        - 테이블 설정, 사용자 정의 모델 하위 유형
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20140.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20141.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20142.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20143.png)
    
- SQLAlchemy
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20144.png)
    
    - Dependencies quick intro(종속성에 대한 빠른 소개)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20145.png)
        
        - 종속성은 기본적으로 함수가 다른 함수에 종속되도록 하는 방법
        - 필요한 곳으로 기능을 매우 쉽게 가져올 수 있으며 일부 기능은 한 번만 작성하고 여러 곳에서 사용 할 수 있다
        - 앞에는 매개변수이고 뒤에는 기능이다
        - 코드 구현
        - blog_post.py에 작성
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20146.png)
        
        - blog_get.py에 작성
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20147.png)
        
        - 종속키워드 Depends와 post.py에 작성한 함수 호출
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20148.png)
        
        - 필수 매개변수 선언
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20149.png)
        
        - 해당 매개변수를 사용하여 결과에 표시
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20150.png)
        
        - 인증 시스템을 올바르게 호출할때도 이 기능을 사용한다
        - 인증 기능에 의존할 수 있도록 많은 엔드포인트에서 사용자 인증을 요구한다
        - 필요할때마다 해당 기능을 작성하는 많은 코드를 절약할 수 있고 유용하게 사용한다
    - Databases in FastAPI(FastAPI의 데이터 베이스)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20151.png)
        
        - 모든 관계형 데이터베이스에서 작동한다
        - ORM라이브러리 사용(객체 관계형 매핑)
            - 클래스와 개체인 객체 지향코드를 관계형 코드로 변환할 수 있다
        - SQLAlchemy라이브러리 사용
            - 객체와 모든 관계형 사이를 간단히 변환할 수 있다.
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20152.png)
        
        - 데이터 베이스에 사용자를 생성하려는 사용자가 있다
        - FastAPI구조를 가지면서 사용자를 받고 사용자의 요청을 받는다
        - 이름을 지정하기 위해 스키마를 설정한다
        - 3가지의 구조가 필요하다
            - 첫 번째로 사용자 요청
              
                → 사용자가 제공하는 모든 정보가 포함되며 이를 스키마라고 한다.
                
                → 수행할 처리가 끝나면 데이터베이스 사용자가 생긴다
                
            - 두 번째로 기본적으로 수행해야 하는 모든 처리와 함께 여기에 모든 정보를 포함되며 이를 모델이라고 한다
              
                → 모델은 기본적으로 데이터 베이스에 들어간다
                
            - 세 번째로 데이터 유형
              
                → 사용자에게 반환할 데이터베이스의 일부 정보를 추가하려는 정보
        
    - Create databases and tables(데이터베이스 및 테이블 생성)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20153.png)
        
        - SQLAlchemy 설치
            - requirements.txt작성하고 여기에 필요한 패키지를 작성해서 넣는다
            - FastAPI, uvicorn, sqlalchemy
            - 명령어 pip install -r requirements.txt하면 작성했던 패키지가 설치된다.
        - DB폴더 생성 및 database파일 생성 후 코드 복사
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20154.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20155.png)
        
        - DB를 불러오는 함수 작업
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20156.png)
        
        - 모델작업
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20157.png)
        
        DB폴더 안에 models.py를 생성
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20158.png)
        
        - DB안에 database에 Base가져와서 DB사용자를 호출
        - 기본에서 상속되도록 모델 설정
        - sqlalchemy안에 있는 모듈 불려오기
            - Column : 컬럼 설정을 한다
            - sql.sqltypes : sql안에 있는 타입을 설정하기 위한 모듈 불러오기
            - Interger, String : 정수형, 문자형 정의 모듈 불러오기
        - id : 기본 키로 설정하고 인덱스를 참이라고 둔다. 색인이 자동으로 생성된다
        - 나머지도 설정해 준다
        - main.py에 데이터 베이스 엔진을 실행 시켜주는 설정을 한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20159.png)
        
        - DB안에 models와 database에 있는 엔진을 불러온다
            - 여기서 엔진은 데이터베이스에서 정의한 engine이다
        - 다시 실행(uvicorn main:app —reload)시키면 sqlite의 파일로 데이터베이스가 생성된다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20160.png)
        
        - 데이터 베이스 구조를 보기 위해 TablePlus설치 하고 보기
        
        [TablePlus](https://tableplus.com/windows) 다운로드 받기
        
        → 데이터 베이스는sqlite로 설정해서 경로 위치 지정하고 이름 지정해서 불러오기
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20161.png)
        
        → 연결해 주면 보여진다
        
        - DBeaver로 하기
        
        → 예전 했던 실습이 있어서 쉽게 한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20162.png)
        
    - Write data(데이터 작성)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20163.png)
        
        - 데이터베이스 정의하기(완료)
        - 모델 정의하기(완료)
        - 데이터 베이스 만들기(완료)
        - 스키마 정의하기
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20164.png)
        
        → 사용자 기반을 호출
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20165.png)
        
        → pydantic 패키지에 있는 BaseModel호출
        
        → 기본 모델을 설정한다
        
        - ORM작업 수행
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20166.png)
        
        → ORM 기능을 필요하는 db_user를 만든다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20167.png)
        
        → sqlalchemy에 있는 DB세션을 가져온다
        
        → 스키마에 있는 사용자 기반을 가져온다
        
        → DB안에 있는 정의 되어 있는 모델을 가져온다
        
        → 비밀번호 같은 경우 일반적인 텍스트로 저장 할 수 없기때문에 해시로 만들어서 가져온다
        
        - 비밀번호 해시 설정
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20168.png)
        
        → DB안에 hash.py를 만든다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20169.png)
        
        → 해싱을 위한 표준 코드 passlib를 패키지를 다운로드 한다
              —> 터미널을 실행시키고 pip install passlib를 한다
        
        → passlib에 context에서 CryptContext를 불러온다
        
        → 실제로 암호화 하는데 사용되는 것이다
        
        → 구성표는 B스크립트로 하고 더 이상 사용되지 않은 것은 자동으로 설정한다
        
        → Hash를 스크립트로 정의한다
        
        → 문자열 유형의 매개변수로 비밀번호를 사용한다
        
        → 암호 컨텍스트인 해시를 반환한다
        
        → 그리고 비밀번호가 올바른지 여부를 실제로 확인할때 인증을 위해 Verify를 사용한다
        
        → 제공된 것이 올바른지 다시 비밀번호 컨텍스트 점을 확인을 반환한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20167.png)
        
        → 다시 돌아와서 password에 정의했던 hash와 b스크립트를 불러서 비밀번호를 호출한다
        
        → DB에 사용자를 추가하고 커밋을 합니다
        
        → 그리고 refresh로 새로고침을 하는 이유는 데이터베이스 자체가 사용자를 위해 일부 데이터를 생성하기 때문이다
        
        → 사용자를 반환한다
        
        - API작업 수행
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20170.png)
        
        → API기능을 추가하기 위해 user.py를 만든다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20171.png)
        
        → DB세션을 가져오고 FastAPI에 APIRouter로 경로를 지정하여 만들어 준다
        
        → 스키마에 있는 사용자기반의 모델을 가져온다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20172.png)
        
        → 스키마에 기본 모델에서 상속되어 있는 디스플레이라는 클래스를 만든다
        
        → orm_mode는 시스템이 데이터 베이스 데이터를 자동으로 제공하는 형식이며
        한 데이터 유형에서 다른 데이터 유형으로 변환 할 수 없다는 오류가 발생한다
        
        → DB에 있는 DB_user의 정보를 불러온다
        
        → Router로 Post로 생성하는 API를 만든다
        
        → response_model는 사용자에게 표시되는 것을 보여준다(그것은 UserDisplay으로 보여준다)
        
        → 사용자 기반이 될 요청을 만들고 DB세션을 통해 DB를 받아온다
        
        → 그리고 DB_User로 만든것을 반환한다
        
    - 중간 프리뷰
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20173.png)
        
        - 필요한 라이브러리 가져오기(sqlalchemy, passlib, bcrypt)
            - 데이터 베이스 연동, 암호를 해시하고 암호화하는 라이브러리
        - 데이터 베이스를 정의하고 main에다가 호출하기
        - 데이터 베이스 모델 만들기(테이블 정의)
        - 데이터 베이스의 실제 기능 부여
        - 스키마 생성
            - 사용자의 데이터대한 데이터 생성
            - 사용자에 대한 응답 데이터 생성
        - API작업 생성
        - 다음 작업 할 것
        - CRUD 만들기
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20174.png)
        
    - Create and read(생성하고 읽어오기)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20175.png)
        
        - 생성을 위해 요소를 생성하는 방법
            - 해당 데이터 베이스 세션을 사용하여 새 데이터를 추가한 다음 커밋을 확인한다
            - 데이터 베이스에 바로 표시되고 새로 고침하여 모든 정보를 얻을 수 있다
            - 데이터 유형에 제공한다 그러면 필요한 정보를 반환 할 수 있다.
        - 읽는 방법과 해당 데이터를 반환하는 방법
            - 데이터 베이스, 테이블에서 모든 요소를 읽을 것
            - 일부 데이터 기반으로 필터링 한다는 점
            - 쿼리를 수행한다
        - db_user에 모든것을 읽는 함수 생성
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20176.png)
        
        - 다음 API호출을 위해 user.py에 모두 읽을 수 있게 경로를 지정한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20177.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20178.png)
        
        - 리스트 목록을 가져와야 하기 때문에 모듈을 불러와 준다
        - 사용자 디스플레이 목록으로 함수를 만들고 가져온다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20179.png)
        
        - 특정 요소를 원하면 해당 요소에 대해 필터를 호출해야 한다
        - db_user.py에 정의한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20180.png)
        
        - user.py에 필터링 되어 있는 API를 생성한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20181.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20182.png)
        
    - Update and delete(수정하고 삭제하기)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20183.png)
        
        - 수정하기
            - 업데이트할 필드를 제공해야 한다
            - 그런 다음 작업을 데이터 베이스에 커밋하는 것
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20184.png)
            
            - 업데이트 할 내용을 작성해서 request로 호출하는 방식이다
            - user.py에도 update에 대한 API를 작성한다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20185.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20186.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20187.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20188.png)
            
        - 삭제하기
            - 실제요소를 찾아서 삭제하면 된다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20189.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20190.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20191.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20192.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20193.png)
        
    - Relationships(관계)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20194.png)
        
        - 관계를 사용하면 단일 요청으로 여러 테이블에서 요소를 검색 할 수 있다
        - 결합된 여러 요청을 정의하는 방식으로 일종의 결합을 허용
        - 여러 정보 소스에 대한 여러 정보를 단일 출력으로 우리가 보내면 여러 수준의 정보가 생성
        - 그 정보를 되찾을때 우리가 받고자 하는 것은 사용자 이름과 이메일뿐 만아니라 기본적으로 이 사용자 ID에 첨부된 기사인 항목 목록도 있다
        - 왼쪽은 목록이고 오른쪽은 딕셔러니 형식이다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20195.png)
        
        - 모델은 데이터 베이스 또는 테이블 구조임을 명심하자
            - 사용자 측의 응답에 들어갈 항목이다
            - 사용자 ID가 외래키로 사용
            - DB사용자와의 관계를 정의한다
        - 스키마 부분
            - API에 정보를 보내고 API에서 정보를 검색 할때 기본적으로 목록도 검색하는 디스플레이를 만든다
            - 관계르르 정의하고 검색하려는 항목을 정의한다
        - 코드로 구현
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20196.png)
        
        - 모델에서 관계정의를 생성한다
            - 새로운 테이블을 생성하고 관계에 적용한다
            - sqlalchemy패키지를 활용해서 모듈을 불러온다(relationship)
            - 클래스에 외래 키와 정의한 관계를 포함하는 article를 생성한다
        - 스키마 정의한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20197.png)
        
        - Article에 대한 정의를 만들고 또한 사용자 기반으로 보여주기 위해 만든다
        - 기본 모델에서 물려받아서 작성한다
        - 반환하려는 데이터 유형을 추가한다
        - 사용자에게 수신하고 보내는 유형과 다른 것을 기억해야 한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20198.png)
        
        - DB에 새로운 테이터 베이스를 만든다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20199.png)
        
        - Article에 관한 데이터 베이스를 생성하고 DB에 추가하여 커밋시킨다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20200.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20201.png)
        
        - article에 대한 라우터 경로를 지정해서 article를 정의한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20202.png)
        
        - article에 대한 API구현을 한다
        - 실행하기 전에 이미 전에 만들었던 데이터베이스는 삭제하고 다시 실행한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20203.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20204.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20205.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20206.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20207.png)
        
        - article에 추가적으로 데이터를 입력해서 확인해보자
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20208.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20209.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20210.png)
    
- 오류처리 및 맞춤형 응답 등
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20211.png)
    
    - Error handling(오류 처리)
        - 예외와 발생할 수 있는 문제를 관리하는 방법
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20212.png)
        
        - 기본적으로 코드에서 발생할 수 있는 오류를 클라이언트에 알리는 방법
        - 예외처리를 만들어서 코드의 아무 곳에서나 나머지 코드 실행을 중지한다
        - 예외에는 상태코드와 메시지를 포함한다
        - 에러 상태 목록
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20213.png)
            
            - 1 : 상태 코드는 "정보"용입니다. 이들은 직접적으로는 잘 사용되지는 않습니다. 이 상태 코드를 갖는 응답들은 본문을 가질 수 없습니다.
            - 2 : 상태 코드는 "성공적인" 응답을 위해 사용됩니다. 가장 많이 사용되는 유형
                - 200 은 디폴트 상태 코드로, 모든 것이 "성공적임"을 의미합니다.
                - • 다른 예로는 201 "생성됨"이 있습니다. 일반적으로 데이터베이스에 새로운 레코드를 생성한 후 사용합니다.
                - • 단, 204 "내용 없음"은 특별한 경우입니다. 이것은 클라이언트에게 반환할 내용이 없는 경우 사용합니다. 따라서 응답은 본문을 가질 수 없습니다.
            - 3 : 상태 코드는 "리다이렉션"용입니다. 본문을 가질 수 없는 304 "수정되지 않음"을 제외하고, 이 상태 코드를 갖는 응답에는 본문이 있을 수도, 없을 수도 있습니다.
            - 4 : 오류코드, 상태 코드는 "클라이언트 오류" 응답을 위해 사용됩니다. 이것은 아마 가장 많이 사용하게 될 두번째 유형입니다.
                - 일례로 404 는 "찾을 수 없음" 응답을 위해 사용합니다.
                - 일반적인 클라이언트 오류의 경우 400 을 사용할 수 있습니다.
            - 5 : 오류 코드, 상태 코드는 서버 오류에 사용됩니다. 이것들을 직접 사용할 일은 거의 없습니다. 응용 프로그램 코드나 서버의 일부에서 문제가 발생하면 자동으로 이들 상태 코드 중 하나를 반환합니다.
        - 오류 메시지 작성법
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20214.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20215.png)
        
        - 사용자 지정 예외를 제공
        - 고객 예외는 예외에서 상속되어야 하며 예외를 제공해야 한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20216.png)
        
        - 예외처리하기 위해 새로운 py파일 생성
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20217.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20218.png)
        
        - JSON응답을 위해 JSONResponse 호출
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20219.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20220.png)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20221.png)
        
        - 현존하는 예외로 부터 상속받은 코드
        - 핸들러는 실제로 사용자 정의 핸들러를 사용하며 HTTP예뢰를 처리 할 수 있다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20222.png)
        
        - fastapi안에도 HTTPException이 있지만 여기선 예외처리에 관한 응답 처리이기 때문에 위에같이 모듈을 불러와야 한다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20223.png)
        
        - 사용자 정의를 개인화 하는 방법으로 배부를 필터링 하는 것이 좋다
        - 예외를 위해 절대적으로 필요하진 않은 경우에는 사용하지 않는다
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20224.png)
        
        - 주석할 경우에는 Response body에 관련된 에러가 나오게 된다
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20225.png)
            
        - 주석 할 경우 관련된 에러 메시지가 보이지 않는다
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20226.png)
        
    - Custom responses(맞춤형 응답)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20227.png)
        
        - 기본적으로 함수에서 간단히 반환할 수 있다
            - 모델, 데이터베이스 모델, 리스트, 자료형 등
            - 응답을 반환할 때 JSON 표준으로 빠르게 시본 설정하려는 상황
        - 다양한 유형의 응답을 매우 명백하게 반환할 수 있다
        - 사용자 지정 응답의 응답을 사용할 때는 데이터를 얻지 못한다
        - 코드
            - product.py파일 생성해서 그곳에 더미 데이터를 생성
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20228.png)
            
        - 더미데이터를 라우터로 지정하고 Text형식으로 불어올 수 있게 지정한다
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20229.png)
            
        - main에 라우터 경로 설정하고 실행하면 Text형식의 값이 호출된다.
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20230.png)
            
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20231.png)
        
        - 왜 이것을 하는 이유는?
          
            1) 우선 표준 응답에서는 할 수 없는 몇가지 매개변수를 응답에 추가 할 수 있기 때문이다 → (해더, 쿠키, 응답 유형 등을 추가 할 수 있다)
            
            2) 다양한 유형의 응답을 제공 할 수 있다 → 반드시 JSON형식에만 호출하는 것이 아닌 다름 형식으로 출력이 된다
            
            - Plain Text : 그래픽 표현이나 그림 등이 아닌, 읽을 수 있는 자료의 문자열
            만을 대표하는 데이터이다. 양식 정보가 포함된 리치 텍스트, 바이너리 파일과는 구별된다.
            - XML : 웹 사이트, 데이터베이스 및 타사 애플리케이션과 같은 컴퓨터 시스템 간의 정보 교환을 지원
            - HTML : 프로그래밍 언어는 아니고, 우리가 보는 웹페이지가 어떻게 구조화되어 있는지 브라우저로 하여금 알 수 있도록 하는 마크업 언어
            - Files : 파일을 전송
            - Streaming : 주로 소리 (음악)나 동영상 등의 다중매체 파일을 전송하고 재생하는 방식
        - 복잡한 의사 결정 논리가 있을 수 있으므로 응답은 여러 요인에 따라 달라 질 수 있다 - 표준 JSON 응답에는 단순히 포함 할 수 없다
        - 더 나은 문서가 있다
        - 코드
            - HTML로 불러오는 법
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20232.png)
            
            - product.py파일 생성
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20233.png)
            
            - HTML를 응답할 수 있는 패키지 설치
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20234.png)
            
            - 미디어 타입은 text/html로 지정한다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20235.png)
            
            - 만약에 id 입력값이 초과하게 된다면 에러 표시를 띄우게 하고 타입은 Text형식으로 지정한다
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20236.png)
                
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20237.png)
            
        - Text/Html의 옵션을 주어서 응답을 받아보자
            - 코드
            - 두가지 유형의 응답을 제공할 것을 선언한다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20238.png)
            
        - 기존의 응답 창 표준식
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20239.png)
            
        - 응답을 정의해서 내린 형식
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20240.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20241.png)
        
    - Headers(헤더)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20242.png)
        
        - Headers : 요청과 함께 전송되고 응답과 함께 수신되는 정보
        - 함수 정의에 특정 사용자 지정 헤더를 추가하는 방법 또는 실제로 기존 헤더를 원하는 경우
        - 요청에 의해 자동으로 쓰거나 덮어쓰는 헤더 중 하나가 아닌지 확인
            - 기본적으로 함수 정의에서 헤더를 정의한다
            - 변수 및 매개변수 이름에는 대시를 사용할 수 없다
        - 밑줄과 대시 가이를 자동으로 변환한다
        - 특별한 경우에 단순히 헤더 목록을 받을 수 있다
            - 리스트로 선언할 수 있다
            - 리스트에서 얻을 수 있는 값이 달라진다
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20243.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20244.png)
            
            - 필요한 모듈와 패키지를 불어온다
            - Header안에 값을 입력하면 products에 저장한 값이 출력된다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20245.png)
            
            - 개발자 도구 에서도 확인이 가능하다(F12)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20246.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20247.png)
            
            - List로 정의해서 헤더 출력
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20248.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20249.png)
            
            - Add string item으로 헤더 값을 출력할 수 있다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20250.png)
            
            - 개발자 도구로 확인
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20251.png)
            
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20252.png)
        
        - 응답 헤더도 제공
        - 응답을 위해 원하는 만큼 많은 헤더를 첨부 할 수 있다
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20253.png)
            
            - 출력 방식은 동일하며 개발자 도구에서 확인 가능하다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20254.png)
        
    - Cookies(쿠키)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20255.png)
        
        - Cookies : 기본적으로 브라우저에 일부 정보를 저장하는 데 사용한다
          
            → 나중에 저장하고 검색해야 하는 것이 무엇이든 쿠키를 사용 할 수 있다
            
        - 문자열, 리스트, 딕셔너리 및 모델을 수용한다
        - 쿠키를 설정하려면 응답 객체가 필요하고 함수 설정 쿠키가 있다
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20256.png)
            
            - 개발자 도구에서 Application에서 Cookies
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20257.png)
            
        - 다른 호출에서 쿠키를 검색, ‘/withheader’ 에 추가 코드 작성해서 쿠키와 너비 헤더 호출을 사용
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20258.png)
            
            - 쿠키 패키지 불러오기
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20259.png)
            
            - 커스텀한 헤더와 쿠키를 반환한다
            - 실행하면 에러가 발생한다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20260.png)
            
            - 응답 헤더를 설정하지 않았기 때문에 오류가 발생
            - 코드를 수정한다
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20261.png)
                
                - 사용자 지정 헤더에 조건문을 넣어서 실행하게 한다
                
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20262.png)
                
            - 개발자 도구에서 확인
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20263.png)
                
            - 쿠키를 삭제하고 실행하게 되면은 —> Null값이 나온다
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20264.png)
                
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20265.png)
        
    - Form data(양식 데이터)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20266.png)
        
        - 매우간단하고 직관적인 양식데이터는 단순히 HTML을 참조한다
        - 인코딩은 응용 프로그램
        - 기본적으로 URL인코딩을 형성하므로 HTML형식에 고유한 특수 유형의 인코딩
            - 웹 페이지와 상호 작용
            - 양식이 있는 경우 이 유형으로 인코딩되며 이를 관리 할 수 있어야 한다
            - 함수 정의에서 형식으로 선언
        - 양식 데이터를 사용하려면 python-multipart를 설치
            - pip install python-multipart
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20267.png)
            
            - Form 패키지 불러오기
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20268.png)
            
            - POST로 생성하고 Form 양식데이터로 받아와서 추가하여 준다
        - Form : HTML forms(<form></form>)은 데이타를 조금 special하게 encoding해서 보낸다. 이는 JSON과 다르다
        Fast API는 이를 자동으로 변환해주어 적절하게 변수 매칭을 해준다.
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20269.png)
        
        - 양식 유형, 양식 URL 인코딩이 있는 양식 인코딩을 볼 수 있다.
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20270.png)
        
    - CORS(Cross Origin Resource Sharing)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20271.png)
        
        - API에 엑세스 하기 위해 로컬 시스템에서 실제 애플리케이션을 만들려고 시도하는 경우
        - 코스는 기본적으로 크로스 오리진, 리소스 공유를 의미
            - 하나의 로컬 웹 사이트가 로컬 환경에서 실행되는 하나의 웹사이트는 특별히 허용되지 않는 기본적으로 동일한 환경의 동일한 시스템에 있는 리소스에 엑세스 할 수 없다
            - 다른 경로로 기반으로 하는 다른 끝점을 기반으로 동일한 시스템의 리소스에 엑세스한다
        - 미들웨어를 추가하여 사용하면 된다
            - 어떤 오리진이 괜찮은지, 어떤 메서드, 헤더 등을 말할 수 있는 과정 미들웨어를 추가합니다
            - 자격증명도 인증과 관련이 있고 로컬환경에서 인증을 허용하려면 여기에서도 코스 미들웨어를 설정해야 한다
            - 까다로운 두가지 사항이 있다
                - 로컬에서 실행 할 수 있는 애플리케이션과 로컬에서 FastAPI를 설정해야 한다
        - React로 연결해서 미들웨어 실습 진행
            - npx create-react-app test-app 터미널에 입력 react에 관련된 패키지 설치
            - 설치되어 있는 폴더로 이동하여 npm start를 하면 실행이 된다
            - React는 localhost:3000으로 되어 있다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20272.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20273.png)
            
        - React안에 FastAPI경로 지정하기
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20274.png)
            
            - App.js에 들어가면 처음에 봤던 화면의 코드가 나온다
            - 코드 요청에서 복사하여 가져오는 기능을 붙인다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20275.png)
            
            - 해당 요청의 응답이 수신 될때 호출이 된다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20276.png)
            
        - 로컬의 환경이 둘다 다르기 때문에 두개의 경로를 연결해줄 미들웨어를 가져와서 추가한다(FastAPI안에서 실행)
            - main.py에서 실행
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20277.png)
                
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20278.png)
                
                - origins : 지역을 설정을 한다
                  
                    → 지금은 리엑트의 주소로 지정
                    
                    → 전부라면 [”*”]로 표기한다(단, 인증에 대해서 문제가 발생 할 수 있다)
                    
                - app.add_middleware를 추가하며 CORSMiddleware를 추가한다
                - origins, 자격증명, 메소드, 헤더에 대한 정의와 허용을 지정한다
        - 실행 결과
            - 개발자 도구 → Network → all → Response를 열면 FastAPI에 있던 호출 값을 불러온다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20279.png)
    
- 인증
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20280.png)
    
    - Authentication(인증)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20281.png)
        
        - 인증과 일반적인 보안을 살펴보자
        - 복잡한 주제
            - 코드 기반의 많은 부분이 모든 애플리케이션의 보안 부분에 특별히 전용되는 것은 드문일이 아니다
            - FastAPI만 다루는 것이 아니라 애플리케이션을 위한 완벽한 보안 솔루션에 대해 이야기 하는 것
            - FastAPi에서 교장에 대한 명세의 실질적인 구현
        - OAuth2와 사용자이름 및 비밀번호를 인증
            1. 사용자이름과 비밀번호를 만든다.
            2. 인증을 위한 엔드포인트가 있고 사용자에게 토큰을 생성한다
            3. 토큰을 검색하기 위해 두번째 엔드포인트을 호출하면 토큰을 로컬에 저장한다
            4. 토큰이 필요한 모든 보안 요청에 대해 사용하게 된다
            5. 정확히 어떤 요청이 보호되어야 하고 어떤 요청이 공개되어야 하는지는 API에서 정의한다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20282.png)
        
    - Securing an endpoint(앤드포인트 보안)
        - 시스템에서 하나 이상의 메서드 · 엔드포인트를 보호하기 위한 매우 기본적인 기능을 구현
        - 사용자 생성 및 열릴 지점을 갖게 된다.
        - Article를 검색하기 위해 사용자를 생성할 수 있다
        - 코드
            - 새로운 폴더 auth를 생성
            - oauth2.py 생성
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20283.png)
            
            - FastAPI에 있는 보안 패키지를 가져온다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20284.png)
            
            - 매개변수를 구현
            - 스키마를 강조하기 위해 이 게시물을 호출
            - 비밀번호 전달자의 호스트 지정
            - 토큰검색을 위한 엔드포인트 제공
                - 실제로 토큰 URL로 token으로 지정
                - 엔드포인트를 생성하지는 않는다 엔드포인트는 스키마에 대한 토큰을 수신하는데 필요
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20285.png)
            
        - article에 인증 보안을 적용
            - article.py에서 불러오기
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20286.png)
            
            - 코드 작성
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20287.png)
            
            - 코드 실행
            - 오른쪽에 자물쇠 형식으로 보안이 유지되어 있다는 표시
                - 인증되지 않아서 열려 있다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20288.png)
            
            - 실행하면 에러 발생(승인이 되지 않았기 때문)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20289.png)
            
        - 승인하는 방법
            - 위쪽에 Authorize을 클릭
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20290.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20291.png)
            
            - 사용자 이름과 암호가 필요하다
    - Generating access token(엑세스 토큰 생성)
        - JWT 토큰 코드 입력(자료 제공)
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20292.png)
        
        - jose패키지 다운로드
            - JSON웹 토큰에 엑세스 하려면 설치
            - pip install python-jose(터미널에서 실행)
        - 비밀키 생성
            - 비밀키는 기본적으로 생성될 코든에 서명할 수 있는 키
            - 비밀키는 무작위이지만 고유해야 한다
            - 임의의 비밀 키를 생성하는 방법
                - 터미널에서 명령어 입력
                - openssl rand -hex 32
                
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20293.png)
            
        - 토큰 엔드포인트 구현
            - auth 폴더에 authentication.py를 생성
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20294.png)
            
            - API라우터로 경로 지정
            - POST로 4개의 슬래시 토큰이 있다
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20295.png)
                
            
            !중요!
            
            → 엔드포인트가 정확히 동일해야 한다
            
            → 다른 의미로 정의해도 사용 할 수가 없다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20296.png)
            
            → tokenUrl와 POST의 경로가 일치해야한다
            
        - 비밀번호 요청 양식
            - 비밀번호 요청 양식 모듈을 불러온다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20297.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20298.png)
            
            - 기본적으로 여기에 있는 형식이며, FastAPI통해 자동으로 수행한다
        - 전반적인 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20299.png)
            
            - 데이터 베이스에 있는 DB를 가져온다
            - 사용자 이름으로 데이터 베이스에서 사용자를 가져온다
            - 비밀번호는 실제로 Hash되고 있다(전에 작업을 해놔서)
            - DB에쿼리로 모델에 저장된 DBUser에서 사용자 모델에 대해 반환 해서 첫 번째 요소를 가져온다
            - 사용자 확인이 안될경우 HTTP예외 처리를 한다
            - 또한 비밀번호(Hash)도 올바르지 않다면 HTTP예외 처리를 한다
        - 둘다 통과하면 토큰을 생성 할 수 있다
            - access_token를 정의해야 토큰을 생성하고 데이터를 전달한다
            - 인증 타입을 지정한다(bearer)
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20300.png)
                
            - ID와 이름을 반환한다
        - main.py 수정
            - 인증이 정의된 모듈 호출
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20301.png)
            
            - 라우터로 경로 지정
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20302.png)
            
        - 확인하기
            - 사용자 이름과 비밀번호를 생성한다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20303.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20304.png)
            
            - 로그인하기
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20305.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20306.png)
            
            - 이러면 권한을 부여하면 권한을 얻게 된다
        - 엑세스 토큰 제공
            - 승인을 사용하면 엑세스 토큰이 제공된다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20307.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20308.png)
            
        - 권한 부여된 것으로 열어보기
            - 인증이 되었으므로 실제로 테이블을 열고 Article에 대한 데이터베이스를 열 수 있도록 하는 것이다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20309.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20310.png)
        
    - User authentication(사용자 인증)
        - 누락된 핵심 구성 요소 → API에서 토큰을 제공
            - API에 대한 토큰에 대한 사용자
            - 해당 토큰이 유효한 비밀키를 기반으로 유효한지 확인 하기 위해 해당 토큰을 확인
        
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20311.png)
        
        - 첫 번째는 토큰 검증 기능을 구현
            - 전달되는 사용자 자격 증명을 기반으로 해당 토큰을 확인하는 방법
        - 두 번째는 해당 토큰과 관련된 사용자를 검색하고 해당 사용자를 무엇이든 제공
            - 엔드포인트 함수가 호출된다
        - 마지막으로 더 많은 엔드 포인트를 확보
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20312.png)
            
            - JWTError : JWT 에러관련 모듈
            - Depends : 종속성 관련 모듈
            - Session : DB정보의 세션
            - get_db : 저장된 DB 모듈
        - 토큰 확인을 위한 함수를 정의
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20313.png)
            
            - 사용자는 토큰이 연결된 현재 사용자를 검색하는 데 사용한다
            - 그러나 해당 사용자를 수신하거나 해당 사용자를 검색하는 과정에서 토큰도 확인한다
            - 문자열 유형의 토큰이 있다
            - 무엇을 스캔할지에 따라 다르며 사용자를 검색하려면 데이터 베이스가 필요하다
            - 코드에서 오류를 발견하면 발생하는 예외를 정의
              
                → credentials_exception으로 정의했다
                
                → 헤더는 www-인증을 제공한다
                
                → 사용자를 인증할 수 없는 경우 표준 HD 예외로 제공한다
                
            - 페이로드를 정의한다
              
                → JWT로 디코드한 다음 토큰을 전달한다
                
                → 비밀키와 알고리즘을 전달한다
                
                → 토큰에서 사용자 이름을 검색하는 표준방법
                
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20314.png)
                
            - JWT 오류 발생 시
              
                → 오류에 대한 GW가 있다
                
                → 해당 오류가 발생하면 예외, 자격 증명, 예외를 다시 발생시킨다.
                
                → 이 시도를 통과하면 계속해서 사용자를 검색 할 수 있다.
                
            - DB사용자를 가져와서 사용자를 기반으로 사용자를 검색하는 새로운 기능을 제곤해야 한다
              
                → 기본적으로 토큰의 유효성을 검사하고 토큰의 데이터를 기반으로 사용자 이름을 검색한다
                
                → 예외가 없다면 사용자를 반환하는 것이다
                
                → 사용자를 제대로 확보한 후에는 더 이상 토큰에 의존할 필요가 없다
            
        - 토큰 종속성 확인하기
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20315.png)
            
            - 필요한 패키지 불러오기
        - 토큰 대신 정의했던 사용자 유형 기반으로 바뀐다
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20316.png)
            
        - 확인하기
            - 권한 로그인을 한 다음 입력값 작성 후 확인
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20317.png)
            
        - 페이지를 새로고침을 하게 되면 인증 토큰을 잃어 버리게 된다
        - 사용자의 다른 방법에 대해 동일한 권한을 추가
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20318.png)
            
            - 이 코드를 복사하여 다른코드에 넣으면 된다.
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20319.png)
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20320.png)
    
- 파일작업
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20321.png)
    
    - File(파일)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20322.png)
        
        - 파일은 양식 필드와 유사하게 선언
          
            → 양식 필드이자 시스템이다
            
            → 파일을 바이트로 선언하고 기본 파일로 설정한다
            
        - 해당 바이트를 문자열로 변환
        - 특정 개체 파일을 사용하여 파일을 메모리에 저장
        - 코드
            - router폴더에 file.py 생성
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20323.png)
            
            - POST로 파일을 생성하는 함수 실행
            - file은 Bytes로 읽어서 온다
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20324.png)
            
            - main에다가 라우터 지정
        - 실행해서 확인
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20325.png)
            
            - 파일 업로드하면 출력으로 보여줌
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20326.png)
        
    - Upload File(파일 업로드)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20327.png)
        
        - 더 많은 기능을 제공
        - 메모리에 일정 크기까지 저장한 다음 디스크에 저장한다
        - 객체와 같은 파이썬 파일을 제공
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20328.png)
            
            - 업로드를 할 함수 생성하기
            - 경로에는 업로드 할 폴더를 만들어 준다
            - 파이썬 파일인 개체가 있으므로 정보를 저장하는데 사용
            - with open 구문으로 열고 파일을 재 정의한다
    - Making Files statically avaliable(파일을 정적으로 사용)
        - 저장되어 있는 이미지 파일에 HTML으로 표현
          
            → localhost:8000/files/저장했던 이미지파일 : 에러 발생
            
            → 외부의 브라우저에서 정적으로 엑세스를 할 수 없기 때문
            
        - aiofiles
          
            → 엑세스 할 수 있게 라이브러리 다운로드
            
            → 터미널 : pip install aiofiles
            
        - main.py에서 작성
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20329.png)
            
            - 정적파일을 가져올 수 있는 모듈 설치
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20330.png)
            
            - 마운트 기능으로 정의한다
            - 다시 작성해서 올리면 나온다
    - Downloading File(파일 다운로드)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20331.png)
        
        - 파일 엑세스에 대한 더 많은 논리를 제공하여 일부를 수행
            - 단순히 파일 엑세스에 대해 훨씬 더 많은 논리를 제공할 수 있으므로 일부 계산을 수행하고 일부 내부 논리를 수행할 수 있으며 로깅을 수행할 수 있다.
            - 파일 다운로드와 관련되 세트를 가질 수 있다
        - 보안을 제공할 수 있으므로 인증된 사용자만 특정 파일에 엑세스 할 수 있다
        - 단순히 특정 파일에 대한 엔드포인트를 제공하는 경우?
          
            → 해당 파일을 다운로드 할 때 응답을 파일 응답으로 제공
            
            → 클라이언트에 파일을 제공할 수 있다
            
            → 해당 파일의 경로를 반환하면 파일 응답으로 제공된다
            
            → 반환 유형에 개체 파일 응답을 제공하고 다른 모든 응답을 제공
            
        - 코드
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20332.png)
            
            - 파일응답요청 할 모듈 불러오기
            
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20333.png)
            
            - Get 매서드로 불러와서 경로는 파일이 저장되어 있는 곳으로 설정
            - 끝에 확장자 까지 붙혀야 불러와 진다.
- 추가작업
  
    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20334.png)
    
    - Deployment(배포)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20335.png)
        
        - 무료 호스팅으로 레이어 확인
        - 배포 준비
        - [data.sh](http://data.sh)
    - Debugging(디버깅)
        - 디버깅 하는 법
            - 서버는 종료한다.
            - VScode에서 디버깅을 한다(F5를 누르거나 Ctrl + P로 검색란에 Debug을 입력)
            - FastAPI 선택
            - 코드에 왼쪽 숫자 버튼을 누르면 중단점을 실행한다.
                - 이것은 코드가 실행하는 구간을 지정하여 중단하는 기점을 만든다.
                  
                    ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20336.png)
        
    - Testing(테스트)
      
        ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20337.png)
        
        - 소프트웨어 개발에서 가장 중요하고 종종 사용하는 부분
        - 100% 커버리지를 위해 노력하는 것
        - request와 pytest 라이브러리로 쉽게 테스트 하기
            - 라이브러리 다운로드
              
                ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20338.png)
            
        - test 파일 만들기
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20339.png)
            
        - 테스트 하기 `pytest` 명령어 입력
        - 결과확인
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20340.png)
            
        - 전체코드
          
            ```python
            from fastapi.testclient import TestClient
            from main import app
            
            client = TestClient(app)
            
            def test_fet_all_blogs():
                response = client.get("/blog/all")
                assert response.status_code == 200
            
            def test_auth_error():
                response = client.post("/token",
                    data = {"username":"", "password": ""}
                )
                access_token = response.json().get("access_token")
                assert access_token == None
                message = response.json().get("detail")[0].get("msg")
                assert message == "field required"
            
            def test_auth_succes():
                response = client.post("/token",
                    data = {"username":"cat", "password": "cat"}
                )
                access_token = response.json().get("access_token")
                assert access_token
            
            def test_post_article():
                auth = client.post("/token",
                    data = {"username":"cat", "password": "cat"}
                )
                access_token = auth.json().get("access_token")
            
                assert access_token
            
                response = client.post(
                    "/article/",
                    json = {
                        "title": "Test article",
                        "content" : "Test Content",
                        "published": True,
                        "creator_id": 1
                    },
                    headers={
                        "Authorization" : "bearer" + access_token
                    }
                )
            
                assert response.status_code == 200
                assert response.json().get("title") == "Test article"
            ```
        
    - Logging(로깅)
        - 로그파일을 만들어서 API 실행 기록을 남기는 법
        - API에서 일부 로깅을 수행하는 쉬운 방법
        - custom_log 파일 만들기
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20341.png)
            
            ```python
            def log(tag="", message=""):
                with open("log.txt", "w+") as log:
                    log.write(f"{tag}: {message}\n")
            ```
            
        - /router/product 에 product./all 에 log 기록 추가하기
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20342.png)
            
        - 서버 실행 후 확인하기 (log.txt 파일 생성)
          
            ![Untitled](FAST%20API%20a79005080242494b95781e27b48ecb87/Untitled%20343.png)