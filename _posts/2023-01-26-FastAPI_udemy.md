---
layout: single
title:  "Udemy FastAPI 강의"
categories: "Coding"
tags: [Python, FastAPI]
author_profile: false
---

# FastAPI - (11)
   - FastAPI는 가장 빠르게 성장하는 API프레임워크
   - swagger UI
   - Udemy 강의 정리

## 파일작업

![image-20240320123722414](/images/2023-01-26-FastAPI_udemy/image-20240320123722414.png)

### File(파일)

![image-20240320123707522](/images/2023-01-26-FastAPI_udemy/image-20240320123707522.png)
 
   - 파일은 양식 필드와 유사하게 선언
     → 양식 필드이자 시스템이다

     → 파일을 바이트로 선언하고 기본 파일로 설정한다

   - 해당 바이트를 문자열로 변환

   - 특정 개체 파일을 사용하여 파일을 메모리에 저장

   - 코드

   - router폴더에 [file.py](http://file.py) 생성

  ![image-20240320123651141](/images/2023-01-26-FastAPI_udemy/image-20240320123651141.png)

   - POST로 파일을 생성하는 함수 실행
   - file은 Bytes로 읽어서 온다

   ![image-20240320123636576](/images/2023-01-26-FastAPI_udemy/image-20240320123636576.png)

   - main에다가 라우터 지정

   - 실행해서 확인

   ![image-20240320123618221](/images/2023-01-26-FastAPI_udemy/image-20240320123618221.png)

   - 파일 업로드하면 출력으로 보여줌

   ![image-20240320123603561](/images/2023-01-26-FastAPI_udemy/image-20240320123603561.png)

### Upload File(파일 업로드)

![image-20240320123545746](/images/2023-01-26-FastAPI_udemy/image-20240320123545746.png)

   - 더 많은 기능을 제공

   - 메모리에 일정 크기까지 저장한 다음 디스크에 저장한다

   - 객체와 같은 파이썬 파일을 제공

   - 코드
     ![image-20240320123530867](/images/2023-01-26-FastAPI_udemy/image-20240320123530867.png)

   - 업로드를 할 함수 생성하기
   - 경로에는 업로드 할 폴더를 만들어 준다
   - 파이썬 파일인 개체가 있으므로 정보를 저장하는데 사용
   - with open 구문으로 열고 파일을 재 정의한다

### Making Files statically avaliable(파일을 정적으로 사용)

   - 저장되어 있는 이미지 파일에 HTML으로 표현
      → localhost:8000/files/저장했던 이미지파일 : 에러 발생
      → 외부의 브라우저에서 정적으로 엑세스를 할 수 없기 때문
   - aiofiles
      → 엑세스 할 수 있게 라이브러리 다운로드
      → 터미널 : pip install aiofiles

   - main.py에서 작성
   ![image-20240320123515321](/images/2023-01-26-FastAPI_udemy/image-20240320123515321.png)

   - 정적파일을 가져올 수 있는 모듈 설치
   ![image-20240320123501819](/images/2023-01-26-FastAPI_udemy/image-20240320123501819.png)

   - 마운트 기능으로 정의한다
   - 다시 작성해서 올리면 나온다

### Downloading File(파일 다운로드)

![image-20240320123446184](/images/2023-01-26-FastAPI_udemy/image-20240320123446184.png)

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
   ![image-20240320123429691](/images/2023-01-26-FastAPI_udemy/image-20240320123429691.png)

   - 파일응답요청 할 모듈 불러오기
   ![image-20240320123415636](/images/2023-01-26-FastAPI_udemy/image-20240320123415636.png)

   - Get 매서드로 불러와서 경로는 파일이 저장되어 있는 곳으로 설정
   - 끝에 확장자 까지 붙혀야 불러와 진다.


## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/FastAPI_Project)

[FastAPI 강의](https://www.udemy.com/course/completefastapi/?couponCode=KEEPLEARNING)

[FastAPI 공식페이지](https://fastapi.tiangolo.com/ko/)