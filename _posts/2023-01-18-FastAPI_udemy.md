---
layout: single
title:  "Udemy FastAPI 강의"
categories: "Coding"
tags: [Python, FastAPI]
author_profile: false
---

# FastAPI - (8)
   - FastAPI는 가장 빠르게 성장하는 API프레임워크
   - swagger UI
   - Udemy 강의 정리

## 파라미터

### Request body(요청목록)

![image-20240320114900789](/images/2023-01-18-FastAPI_udemy/image-20240320114900789.png)

   - 포스트 매서드에서는 쿼리 매개변수에 있는 모든 정보를 보내지 않는다 실제로 요청 본문 내에서 더 자세한 정보를 보낸다
   - Pydantic의 기본 모델에서 상속(JSON방식)
   - Json으로 읽고 데이터 유효성 검사
   - 데이터 변환이 된다
   - Json으로 출력으로 얻는다.

![image-20240320114926168](/images/2023-01-18-FastAPI_udemy/image-20240320114926168.png)

![image-20240320114944182](/images/2023-01-18-FastAPI_udemy/image-20240320114944182.png)

### Path and Query parameters(경로 및 쿼리 매개변수)

![image-20240320115003333](/images/2023-01-18-FastAPI_udemy/image-20240320115003333.png)

   - Post요청에 작동하는 방식
   - 매개 변수 간에 변환, 데이터 유형을 얻는다
   - 본문 매개변수 : blog, 쿼리매개변수: version

![image-20240320115020170](/images/2023-01-18-FastAPI_udemy/image-20240320115020170.png)

![image-20240320115054482](/images/2023-01-18-FastAPI_udemy/image-20240320115054482.png)

### Parameter metadata(매개변수 메타데이터(데이터에 대한 데이터, 매개변수에 대한 정보))

![image-20240320115127366](/images/2023-01-18-FastAPI_udemy/image-20240320115127366.png)

   - 메타데이터는 무언가의 정보, 문서에 표시되는 정보
   - API에 엑세스 하는 모든 사람에게 유용
   - 메타데이터를 첨부하는 방법과 매개변수에 다른 유형의 정보를 첨부하는 방법
   - 쿼리 구성으로 기본값을 제공

![image-20240320115156752](/images/2023-01-18-FastAPI_udemy/image-20240320115156752.png)

   - 본문 설명 추가
   - 병칠은 요청에서 전달 할 수 있는 매개변수의 이름

![image-20240320115218407](/images/2023-01-18-FastAPI_udemy/image-20240320115218407.png)

   - 매개변수에 플래그를 설정 할 수 있다, 특정 매개변수가 더 이상 사용되지 않음을 나타내는 플래그

![image-20240320115233380](/images/2023-01-18-FastAPI_udemy/image-20240320115233380.png)

### Validators(유효성 검사)

![image-20240320115248419](/images/2023-01-18-FastAPI_udemy/image-20240320115248419.png)

   - 유효성 검사기는 우리가 매개 변수에 전달하는 데이터 또는 호출하는 소프트웨어를 분명히 확인한다
   - API는 매개변수로 전달 된다
   - 내부에 기본값을 제공(본문, 쿼리 또는 경로와 같은 구문 내부의 기본값)

![image-20240320115319320](/images/2023-01-18-FastAPI_udemy/image-20240320115319320.png)

   - 매개변수를 선택상이 아닌 것으로 만들 수 있으며 값을 요구하도록 할 수 있다
   - 세 개의 점으로 사용하는 것(Python의 줄임표 의미)

   ![image-20240320115344883](/images/2023-01-18-FastAPI_udemy/image-20240320115344883.png)

   - 똑같은 방식으로 Ellipsis작성하면 같은 방식으로 작동한다

![image-20240320115404890](/images/2023-01-18-FastAPI_udemy/image-20240320115404890.png)

   - 최소 길이 유효성 검사(단순히 콘텐츠에 대해 최소한의 길이를 제공하는 매개변수를 요구)
   - 최소길이와 최대 길이를 설정할 수 있고 그 이상으로 넘어가면 error가 걸린다

    ![image-20240320115425529](/images/2023-01-18-FastAPI_udemy/image-20240320115425529.png)

   - 정규식 유효성 검사(사용자가 설정한 값에 대해 유효성을 검사)

    ![image-20240320115444506](/images/2023-01-18-FastAPI_udemy/image-20240320115444506.png)

   - regex조건 : a에서z까지 소문자와 공백출력가능, 별표를 제공

### Multiple values(매개변수에 대해 여러 값을 얻는 방법)

![image-20240320115500199](/images/2023-01-18-FastAPI_udemy/image-20240320115500199.png)

   - HTML의 쿼리 매개변수는 여러 값을 받을 수 있으므로 동일한 매개변수가 값이 여러 개인 경우 요청에 여러 번 나타난다

   - 요청에 여러 번 나타나고 이러한 여러 값이 함수에 전달된다

   - 선택적 쿼리 매개변수를 정의하고 예상되는 유형의 목록으로 정의

![image-20240320115547987](/images/2023-01-18-FastAPI_udemy/image-20240320115547987.png)

![image-20240320115612513](/images/2023-01-18-FastAPI_udemy/image-20240320115612513.png)

   - 목록이 표시 된다

   - 쿼리 매개변수 내부에 기본값을 목록으로 제공가능

![image-20240320115633746](/images/2023-01-18-FastAPI_udemy/image-20240320115633746.png)

![image-20240320115652099](/images/2023-01-18-FastAPI_udemy/image-20240320115652099.png)

### Number Validators(매개변수에서 받은 다양한 요소 유형의 목록 또는 배열)

![image-20240320115710942](/images/2023-01-18-FastAPI_udemy/image-20240320115710942.png)

   - 같은 방식으로 문자열과 숫자에 대한 유효성 검사도 있다
   - gt = 크다(초과)
   - ge = 크거나 같음(이상)
   - lt = 작다(미만)
   - le = 작거나 같다(이하)

![image-20240320115731440](/images/2023-01-18-FastAPI_udemy/image-20240320115731440.png)

   - comment_id 조건→ 유효성 검사를 추가하여 5보다 크고 작거나 최대값 10지정

![image-20240320115812325](/images/2023-01-18-FastAPI_udemy/image-20240320115812325.png)

  ![image-20240320115829773](/images/2023-01-18-FastAPI_udemy/image-20240320115829773.png)

  - 10이 넘어갈 경우 error발생

  - Complex subtypes(복잡한 하위 유형/ 문자열 정수 부울 등)

![image-20240320115846660](/images/2023-01-18-FastAPI_udemy/image-20240320115846660.png)

   - 받고자 하는 문자열 목록을 추가 할 수 있다

![image-20240320115900957](/images/2023-01-18-FastAPI_udemy/image-20240320115900957.png)

![image-20240320115918299](/images/2023-01-18-FastAPI_udemy/image-20240320115918299.png)

   - 데이터 구조를 바꿀 수 있다(List, set, dict,tuple)

![image-20240320115935140](/images/2023-01-18-FastAPI_udemy/image-20240320115935140.png)

   - 테이블 설정, 사용자 정의 모델 하위 유형

![image-20240320115952467](/images/2023-01-18-FastAPI_udemy/image-20240320115952467.png)

![image-20240320120019721](/images/2023-01-18-FastAPI_udemy/image-20240320120019721.png)


## Reference
[개인 Code 기록 github](https://github.com/chusonghyeon/FastAPI_Project)

[FastAPI 강의](https://www.udemy.com/course/completefastapi/?couponCode=KEEPLEARNING)

[FastAPI 공식페이지](https://fastapi.tiangolo.com/ko/)