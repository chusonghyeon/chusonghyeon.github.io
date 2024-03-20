---
layout: single
title:  "Udemy FastAPI 강의 - (7)"
categories: "FastAPI"
tags: [Python, FastAPI]
author_profile: false
---

# FastAPI - (7)
   - FastAPI는 가장 빠르게 성장하는 API프레임워크
   - swagger UI
   - Udemy 강의 정리

## 라우터

  - 응용프로그램을 다른 파일과 다른 구성요소로 구조화 하는 방법

  - 하나의 단일 파일에 모든 것을 포함하는 대신 더 많은 논리적 구성 요소로 구조화 한다

  ![image-20240320114652974](/images/2023-01-17-FastAPI_udemy/image-20240320114652974.png)

  [main.py](http://main.py) 수정 - router사용해서 정의

  - Router라는 폴더 생성해서 blog_get.py파일 생성

  ![image-20240320114709207](/images/2023-01-17-FastAPI_udemy/image-20240320114709207.png)

  - 파일 내용 작성 이후 확인

  - 이러면 복잡하게 main에다가 모든 경로 적을 필요 없고 APIRouter를 활용해서 호출 할 수 있다

  ![image-20240320114723783](/images/2023-01-17-FastAPI_udemy/image-20240320114723783.png)


## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/FastAPI_Project)

[FastAPI 강의](https://www.udemy.com/course/completefastapi/?couponCode=KEEPLEARNING)

[FastAPI 공식페이지](https://fastapi.tiangolo.com/ko/)