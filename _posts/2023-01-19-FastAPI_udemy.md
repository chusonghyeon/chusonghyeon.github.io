---
layout: single
title:  "Udemy FastAPI 강의 - (9)"
categories: "Coding"
tags: [Python, FastAPI]
author_profile: false
---

# FastAPI - (9)
   - FastAPI는 가장 빠르게 성장하는 API프레임워크
   - swagger UI
   - Udemy 강의 정리

## SQLAlchemy

![image-20240320120904630](/images/2023-01-19-FastAPI_udemy/image-20240320120904630.png)

### Dependencies quick intro(종속성에 대한 빠른 소개)

![image-20240320120919232](/images/2023-01-19-FastAPI_udemy/image-20240320120919232.png)

  - 종속성은 기본적으로 함수가 다른 함수에 종속되도록 하는 방법
  - 필요한 곳으로 기능을 매우 쉽게 가져올 수 있으며 일부 기능은 한 번만 작성하고 여러 곳에서 사용 할 수 있다
  - 앞에는 매개변수이고 뒤에는 기능이다
  - 코드 구현
  - blog_post.py에 작성

![image-20240320120935898](/images/2023-01-19-FastAPI_udemy/image-20240320120935898.png)

   - blog_get.py에 작성

![image-20240320120951523](/images/2023-01-19-FastAPI_udemy/image-20240320120951523.png)

   - 종속키워드 Depends와 post.py에 작성한 함수 호출

![image-20240320121010553](/images/2023-01-19-FastAPI_udemy/image-20240320121010553.png)

   - 필수 매개변수 선언

![image-20240320121026524](/images/2023-01-19-FastAPI_udemy/image-20240320121026524.png)

   - 해당 매개변수를 사용하여 결과에 표시

![image-20240320121052723](/images/2023-01-19-FastAPI_udemy/image-20240320121052723.png)

   - 인증 시스템을 올바르게 호출할때도 이 기능을 사용한다
   - 인증 기능에 의존할 수 있도록 많은 엔드포인트에서 사용자 인증을 요구한다
   - 필요할때마다 해당 기능을 작성하는 많은 코드를 절약할 수 있고 유용하게 사용한다

### Databases in FastAPI(FastAPI의 데이터 베이스)

![image-20240320121109763](/images/2023-01-19-FastAPI_udemy/image-20240320121109763.png)

  - 모든 관계형 데이터베이스에서 작동한다
  - ORM라이브러리 사용(객체 관계형 매핑)
    - 클래스와 개체인 객체 지향코드를 관계형 코드로 변환할 수 있다
  - SQLAlchemy라이브러리 사용
    - 객체와 모든 관계형 사이를 간단히 변환할 수 있다.

![image-20240320121124605](/images/2023-01-19-FastAPI_udemy/image-20240320121124605.png)

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

### Create databases and tables(데이터베이스 및 테이블 생성)

![image-20240320121142620](/images/2023-01-19-FastAPI_udemy/image-20240320121142620.png)

   - SQLAlchemy 설치
     - requirements.txt작성하고 여기에 필요한 패키지를 작성해서 넣는다
     - FastAPI, uvicorn, sqlalchemy
     - 명령어 pip install -r requirements.txt하면 작성했던 패키지가 설치된다.
   - DB폴더 생성 및 database파일 생성 후 코드 복사

![image-20240320121206422](/images/2023-01-19-FastAPI_udemy/image-20240320121206422.png)

   - DB를 불러오는 함수 작업

![image-20240320121225132](/images/2023-01-19-FastAPI_udemy/image-20240320121225132.png)

   - 모델작업

![image-20240320121241450](/images/2023-01-19-FastAPI_udemy/image-20240320121241450.png)

  - DB폴더 안에 models.py를 생성

![image-20240320121256408](/images/2023-01-19-FastAPI_udemy/image-20240320121256408.png)

  - DB안에 database에 Base가져와서 DB사용자를 호출
  - 기본에서 상속되도록 모델 설정
  - sqlalchemy안에 있는 모듈 불려오기
    - Column : 컬럼 설정을 한다
    - sql.sqltypes : sql안에 있는 타입을 설정하기 위한 모듈 불러오기
    - Interger, String : 정수형, 문자형 정의 모듈 불러오기
    - id : 기본 키로 설정하고 인덱스를 참이라고 둔다. 색인이 자동으로 생성된다
    - 나머지도 설정해 준다
    - main.py에 데이터 베이스 엔진을 실행 시켜주는 설정을 한다

![image-20240320121312491](/images/2023-01-19-FastAPI_udemy/image-20240320121312491.png)

  - DB안에 models와 database에 있는 엔진을 불러온다
    - 여기서 엔진은 데이터베이스에서 정의한 engine이다
  - 다시 실행(uvicorn main:app —reload)시키면 sqlite의 파일로 데이터베이스가 생성된다

![image-20240320121329292](/images/2023-01-19-FastAPI_udemy/image-20240320121329292.png)

  - 데이터 베이스 구조를 보기 위해 TablePlus설치 하고 보기

  - [TablePlus](https://tableplus.com/windows) 다운로드 받기
   → 데이터 베이스는sqlite로 설정해서 경로 위치 지정하고 이름 지정해서 불러오기

![image-20240320121349645](/images/2023-01-19-FastAPI_udemy/image-20240320121349645.png)
   → 연결해 주면 보여진다

  - DBeaver로 하기 → 예전 했던 실습이 있어서 쉽게 한다

![image-20240320121407469](/images/2023-01-19-FastAPI_udemy/image-20240320121407469.png)

  - Write data(데이터 작성)

![image-20240320121423500](/images/2023-01-19-FastAPI_udemy/image-20240320121423500.png)

  - 데이터베이스 정의하기(완료)
  - 모델 정의하기(완료)
  - 데이터 베이스 만들기(완료)
  - 스키마 정의하기

![image-20240320121439160](/images/2023-01-19-FastAPI_udemy/image-20240320121439160.png) → 사용자 기반을 호출
![image-20240320121454455](/images/2023-01-19-FastAPI_udemy/image-20240320121454455.png) → pydantic 패키지에 있는 BaseModel호출

   → 기본 모델을 설정한다

   - ORM작업 수행

![image-20240320121508821](/images/2023-01-19-FastAPI_udemy/image-20240320121508821.png)

   → ORM 기능을 필요하는 db_user를 만든다

![image-20240320121524529](/images/2023-01-19-FastAPI_udemy/image-20240320121524529.png)

   → sqlalchemy에 있는 DB세션을 가져온다

   → 스키마에 있는 사용자 기반을 가져온다

   → DB안에 있는 정의 되어 있는 모델을 가져온다

   → 비밀번호 같은 경우 일반적인 텍스트로 저장 할 수 없기때문에 해시로 만들어서 가져온다

  - 비밀번호 해시 설정

![image-20240320121540239](/images/2023-01-19-FastAPI_udemy/image-20240320121540239.png)

   → DB안에 hash.py를 만든다

![image-20240320121555112](/images/2023-01-19-FastAPI_udemy/image-20240320121555112.png)

   → 해싱을 위한 표준 코드 passlib를 패키지를 다운로드 한다 —> 터미널을 실행시키고 pip install passlib를 한다

   → passlib에 context에서 CryptContext를 불러온다

   → 실제로 암호화 하는데 사용되는 것이다

   → 구성표는 B스크립트로 하고 더 이상 사용되지 않은 것은 자동으로 설정한다

   → Hash를 스크립트로 정의한다

   → 문자열 유형의 매개변수로 비밀번호를 사용한다

   → 암호 컨텍스트인 해시를 반환한다

   → 그리고 비밀번호가 올바른지 여부를 실제로 확인할때 인증을 위해 Verify를 사용한다

   → 제공된 것이 올바른지 다시 비밀번호 컨텍스트 점을 확인을 반환한다

![image-20240320121611056](/images/2023-01-19-FastAPI_udemy/image-20240320121611056.png)

   → 다시 돌아와서 password에 정의했던 hash와 b스크립트를 불러서 비밀번호를 호출한다

   → DB에 사용자를 추가하고 커밋을 합니다

   → 그리고 refresh로 새로고침을 하는 이유는 데이터베이스 자체가 사용자를 위해 일부 데이터를 생성하기 때문이다

   → 사용자를 반환한다

  - API작업 수행

![image-20240320121625337](/images/2023-01-19-FastAPI_udemy/image-20240320121625337.png)

   → API기능을 추가하기 위해 user.py를 만든다

![image-20240320121642374](/images/2023-01-19-FastAPI_udemy/image-20240320121642374.png)

   → DB세션을 가져오고 FastAPI에 APIRouter로 경로를 지정하여 만들어 준다

   → 스키마에 있는 사용자기반의 모델을 가져온다

![image-20240320121656478](/images/2023-01-19-FastAPI_udemy/image-20240320121656478.png)

   → 스키마에 기본 모델에서 상속되어 있는 디스플레이라는 클래스를 만든다

   → orm_mode는 시스템이 데이터 베이스 데이터를 자동으로 제공하는 형식이며 한 데이터 유형에서 다른 데이터 유형으로 변환 할 수 없다는 오류가 발생한다

   → DB에 있는 DB_user의 정보를 불러온다

   → Router로 Post로 생성하는 API를 만든다

   → response_model는 사용자에게 표시되는 것을 보여준다(그것은 UserDisplay으로 보여준다)

   → 사용자 기반이 될 요청을 만들고 DB세션을 통해 DB를 받아온다

   → 그리고 DB_User로 만든것을 반환한다

  - 중간 프리뷰

![image-20240320121712421](/images/2023-01-19-FastAPI_udemy/image-20240320121712421.png)

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

![image-20240320121728752](/images/2023-01-19-FastAPI_udemy/image-20240320121728752.png)

### Create and read(생성하고 읽어오기)

![image-20240320121743856](/images/2023-01-19-FastAPI_udemy/image-20240320121743856.png)

   - 생성을 위해 요소를 생성하는 방법
     - 해당 데이터 베이스 세션을 사용하여 새 데이터를 추가한 다음 커밋을 확인한다
     - 데이터 베이스에 바로 표시되고 새로 고침하여 모든 정보를 얻을 수 있다
     - 데이터 유형에 제공한다 그러면 필요한 정보를 반환 할 수 있다.
   - 읽는 방법과 해당 데이터를 반환하는 방법
     - 데이터 베이스, 테이블에서 모든 요소를 읽을 것
     - 일부 데이터 기반으로 필터링 한다는 점
     - 쿼리를 수행한다
   - db_user에 모든것을 읽는 함수 생성

![image-20240320121803285](/images/2023-01-19-FastAPI_udemy/image-20240320121803285.png)

   - 다음 API호출을 위해 user.py에 모두 읽을 수 있게 경로를 지정한다

![image-20240320121818781](/images/2023-01-19-FastAPI_udemy/image-20240320121818781.png)

   - 리스트 목록을 가져와야 하기 때문에 모듈을 불러와 준다
   - 사용자 디스플레이 목록으로 함수를 만들고 가져온다

![image-20240320121832957](/images/2023-01-19-FastAPI_udemy/image-20240320121832957.png)

   - 특정 요소를 원하면 해당 요소에 대해 필터를 호출해야 한다
   - db_user.py에 정의한다

![image-20240320121847545](/images/2023-01-19-FastAPI_udemy/image-20240320121847545.png)

   - user.py에 필터링 되어 있는 API를 생성한다

![image-20240320121907790](/images/2023-01-19-FastAPI_udemy/image-20240320121907790.png)

### Update and delete(수정하고 삭제하기)

![image-20240320121927120](/images/2023-01-19-FastAPI_udemy/image-20240320121927120.png)

   - 수정하기
     - 업데이트할 필드를 제공해야 한다
     - 그런 다음 작업을 데이터 베이스에 커밋하는 것

![image-20240320121957715](/images/2023-01-19-FastAPI_udemy/image-20240320121957715.png)

   - 업데이트 할 내용을 작성해서 request로 호출하는 방식이다
   - user.py에도 update에 대한 API를 작성한다

![image-20240320122047904](/images/2023-01-19-FastAPI_udemy/image-20240320122047904.png)

   - 삭제하기
     - 실제요소를 찾아서 삭제하면 된다

![image-20240320122148628](/images/2023-01-19-FastAPI_udemy/image-20240320122148628.png)

### Relationships(관계)

![image-20240320122203748](/images/2023-01-19-FastAPI_udemy/image-20240320122203748.png)

   - 관계를 사용하면 단일 요청으로 여러 테이블에서 요소를 검색 할 수 있다
   - 결합된 여러 요청을 정의하는 방식으로 일종의 결합을 허용
   - 여러 정보 소스에 대한 여러 정보를 단일 출력으로 우리가 보내면 여러 수준의 정보가 생성
   - 그 정보를 되찾을때 우리가 받고자 하는 것은 사용자 이름과 이메일뿐 만아니라 기본적으로 이 사용자 ID에 첨부된 기사인 항목 목록도 있다
   - 왼쪽은 목록이고 오른쪽은 딕셔러니 형식이다

![image-20240320122220210](/images/2023-01-19-FastAPI_udemy/image-20240320122220210.png)

   - 모델은 데이터 베이스 또는 테이블 구조임을 명심하자
     - 사용자 측의 응답에 들어갈 항목이다
     - 사용자 ID가 외래키로 사용
     - DB사용자와의 관계를 정의한다
   - 스키마 부분
     - API에 정보를 보내고 API에서 정보를 검색 할때 기본적으로 목록도 검색하는 디스플레이를 만든다
     - 관계르르 정의하고 검색하려는 항목을 정의한다
   - 코드로 구현

![image-20240320122244097](/images/2023-01-19-FastAPI_udemy/image-20240320122244097.png)

   - 모델에서 관계정의를 생성한다
     - 새로운 테이블을 생성하고 관계에 적용한다
     - sqlalchemy패키지를 활용해서 모듈을 불러온다(relationship)
     - 클래스에 외래 키와 정의한 관계를 포함하는 article를 생성한다
   - 스키마 정의한다

![image-20240320122304574](/images/2023-01-19-FastAPI_udemy/image-20240320122304574.png)

   - Article에 대한 정의를 만들고 또한 사용자 기반으로 보여주기 위해 만든다
   - 기본 모델에서 물려받아서 작성한다
   - 반환하려는 데이터 유형을 추가한다
   - 사용자에게 수신하고 보내는 유형과 다른 것을 기억해야 한다

![image-20240320122320672](/images/2023-01-19-FastAPI_udemy/image-20240320122320672.png)

   - DB에 새로운 테이터 베이스를 만든다

![image-20240320122334852](/images/2023-01-19-FastAPI_udemy/image-20240320122334852.png)

   - Article에 관한 데이터 베이스를 생성하고 DB에 추가하여 커밋시킨다

![image-20240320122352675](/images/2023-01-19-FastAPI_udemy/image-20240320122352675.png)

![image-20240320122409552](/images/2023-01-19-FastAPI_udemy/image-20240320122409552.png)

   - article에 대한 라우터 경로를 지정해서 article를 정의한다

![image-20240320122426220](/images/2023-01-19-FastAPI_udemy/image-20240320122426220.png)

   - article에 대한 API구현을 한다
   - 실행하기 전에 이미 전에 만들었던 데이터베이스는 삭제하고 다시 실행한다

![image-20240320122445393](/images/2023-01-19-FastAPI_udemy/image-20240320122445393.png)

![image-20240320122512233](/images/2023-01-19-FastAPI_udemy/image-20240320122512233.png)

   - article에 추가적으로 데이터를 입력해서 확인해보자

![image-20240320122540644](/images/2023-01-19-FastAPI_udemy/image-20240320122540644.png)


## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/FastAPI_Project)

[FastAPI 강의](https://www.udemy.com/course/completefastapi/?couponCode=KEEPLEARNING)

[FastAPI 공식페이지](https://fastapi.tiangolo.com/ko/)