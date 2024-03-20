---
layout: single
title:  "Udemy FastAPI 강의"
categories: "Coding"
tags: [Python, FastAPI]
author_profile: false
---

# FastAPI - (12)
   - FastAPI는 가장 빠르게 성장하는 API프레임워크
   - swagger UI
   - Udemy 강의 정리

## 추가작업

![image-20240320123304640](/images/2023-01-27-FastAPI_udemy/image-20240320123304640.png)

### Deployment(배포)

   ![image-20240320123250045](/images/2023-01-27-FastAPI_udemy/image-20240320123250045.png)

   - 무료 호스팅으로 레이어 확인
   - 배포 준비
   - [data.sh](http://data.sh)

### Debugging(디버깅)

   - 디버깅 하는 법

   - 서버는 종료한다.

   - VScode에서 디버깅을 한다(F5를 누르거나 Ctrl + P로 검색란에 Debug을 입력)

   - FastAPI 선택

   - 코드에 왼쪽 숫자 버튼을 누르면 중단점을 실행한다.

      - 이것은 코드가 실행하는 구간을 지정하여 중단하는 기점을 만든다.

      ![image-20240320123233377](/images/2023-01-27-FastAPI_udemy/image-20240320123233377.png)

### Testing(테스트)

![image-20240320123217686](/images/2023-01-27-FastAPI_udemy/image-20240320123217686.png)

   - 소프트웨어 개발에서 가장 중요하고 종종 사용하는 부분

   - 100% 커버리지를 위해 노력하는 것

   - request와 pytest 라이브러리로 쉽게 테스트 하기

      - 라이브러리 다운로드
      `pip install requests pytest`

      - test 파일 만들기

      ![image-20240320123123095](/images/2023-01-27-FastAPI_udemy/image-20240320123123095.png)

   - 테스트 하기 `pytest` 명령어 입력

   - 결과확인

   ![image-20240320123106851](/images/2023-01-27-FastAPI_udemy/image-20240320123106851.png)

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

### Logging(로깅)

   - 로그파일을 만들어서 API 실행 기록을 남기는 법

   - API에서 일부 로깅을 수행하는 쉬운 방법

   - custom_log.py 파일 만들기

      ```python
      def log(tag="", message=""):
          with open("log.txt", "w+") as log:
              log.write(f"{tag}: {message}\\n")
      ```

   - /router/product 에 product./all 에 log 기록 추가하기

   ![image-20240320123015576](/images/2023-01-27-FastAPI_udemy/image-20240320123015576.png)

   - 서버 실행 후 확인하기 (log.txt 파일 생성)

   ![image-20240320123000933](/images/2023-01-27-FastAPI_udemy/image-20240320123000933.png)

## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/FastAPI_Project)

[FastAPI 강의](https://www.udemy.com/course/completefastapi/?couponCode=KEEPLEARNING)

[FastAPI 공식페이지](https://fastapi.tiangolo.com/ko/)