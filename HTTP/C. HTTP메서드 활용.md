# HTTP메서드 활용 
## 클라이언트에서 서버로 데이터 전송 
### 1. 쿼리 파라미터를 통한 데이터 전송 
* GET
* 주로 정렬 필터(검색어 같은 거)  -> 정렬 조건  
### 2. 메시지 바디를 통한 데이터 전송 
* POST, PUT, PATCH 
* 회원 가입, 상품 주문, 리소스 등록, 리소스 변경… 

<br/> 

## 클라이언트 -> 서버 4가지 상황 
### 1. 정적 데이터 조회
#### 쿼리 파라미터 미사용 
- 이미지, 정적 텍스트 문서 
- 조회는 GET을 사용한다. 
- 일반적으로 쿼리 파라미터 없이 단순한 조회가 가능함 

### 2. 동적 데이터 조회
#### 쿼리 파라미터 사용 
- 쿼리 파라미터를 기반으로 데이터 조회 
- 검색, 게시판 정렬 
- 조회 조건을 줄여주는 필터, 정렬 조건 
- 조회는 GET을 사용하며, 쿼리 파라미터를 사용하여 데이터를 전달한다.  (리퀘스트 바디 지원 안하는 경우가 많음) 

### 3. HTML Form 데이터 전송 
#### POST 전송 - 저장 
- 폼 데이터를 쿼리 파라미터와 유사하게 변환시켜 바디에 넣어서 전송 
- Content-Type : application/x-www-form-urlencoded 
#### GET 전송 - 저장 
- 폼 데이터를 쿼리 파라미터에 넣어버림 
- 물론 동일하게 동작하지만 절대 사용하면 안됨
#### multipart/form-data 
- 폼 데이터 중에 파일이 있다면 해당 enctype을 사용해야함 (바이너리 데이터 전송) 
- 웹 브라우저는 여러 타입의 폼 데이터들을 구분할 수 있도록 바운더리를 자동으로 생성

### 4. HTTP API 데이터 전송 
* 서버 to 서버에서 주로 사용 
* 앱 클라이언트에서 전송할 때 사용 
* HTML에서 javascript를 통한 통신에서 사용 (AJAX) -> Vue, React.. 
* POST, PUT, PATCH 모두 활용할 수 있음 -> 메시지 바디를 통해 데이터 전송 
* GET 조회, 쿼리 파라미터로 데이터 전달 
* 요즘은 json을 주로 사용 (사실상 표준) 

<br/>

## 참고 
### HTML Form 전송은 GET, POST만 지원 
