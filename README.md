# 20-11-27] 1. Vue, Node, mongoDB 로그인하기 (JWT 사용)

## 1. Node
## 2. mongoDB
## 3. JWT (Json Web Token)


### Node.js란?
웹애플리케이션을 개발할 때 JavaScript를 사용하게 되는데, 모든 브라우저는 JavaScript 코드를 해석하기 위해 JavaScript Engine을 내장하고 있다. (Chrome은 V8, Firefox는 SpiderMonkey, Safari는 Webkit 등) Node.js는 Chrome의 V8엔진을 이용하여 브라우저에서 JavaScript를 해석하듯이 서버에서 JavaScript를 동작할 수 있도록 하는 환경(플랫폼)이다.

### Node에서의 npm
npm은 Node Package Manager의 약자로 node.js에서 사용하는 모듈들을 패키지(package.json)로 만들어 npm을 통하여 관리하고 배포하고 있다. (python의 pip/java의 Jpm)

### mongoDB란?
NoSQL 데이터베이스. NoSQL이란 Not Only SQL의 약자로서 기존의 RDBMS(관계형 데이터베이스)의 한계를 극복하기 위한 새로운 형태의 데이터베이스. (관리툴 : Robo 3T 사용)

NoSQL의 장점
1) 불필요한 Join의 최소화
2) 유연성있는 서버 구조 제공
3) 비정형 데이터 구조로 설계비용 감소
4) Read/Write가 빠르며 빅데이터 처리가 가능
5) 저렴한 비용으로 분산처리 및 병렬처리 가능

### JWT란?
Json Web Token. 클라이언트에서 특정 주소(대부분 로그인 api 주소)를 호출하면 서버에서 그 정보를 지정된 KEY로 암호화를 해서 클라이언트에 전달. 암호화를 할 때 민감한 정보(비밀번호 등)는 넣지 않는다. (참고 https://jwt.io/, https://velog.io/@dnjscksdn98/JWT-JSON-Web-Token-%EC%86%8C%EA%B0%9C-%EB%B0%8F-%EA%B5%AC%EC%A1%B0)

### JWT 저장 방법
- 쿠키 : 시간이 있는 데이터이고, 쿠키의 만료시간을 정해줄 수 있음. 웹토큰 저장하는 방식중 하나임 ex) 팝업창 기간
- 로컬스토리지 : 한번 저장되면 삭제하기 전까지 유지됨. 정보 유지용.
- 세션스토리지 : 한 세션만 유지하며, 브라우져를 끄면 끊어진다. 은행 등 보안이 중요한 곳에 사용함. 도메인별, port별로 스토리지 저장된다.
 
로컬스토리지를 이용하여 토큰 정보를 저장.<br>(조회-localStorage.getItem(키);/등록-localStorage.setItem('token', 토큰);/삭제-localStorage.clear();)
