node.js Server_Programming
===

<a href="https://myengineering.tistory.com/"><img src="https://img.shields.io/badge/blog-myengineering-red.svg" /></a>
<a href="#"><img src="https://img.shields.io/github/last-commit/manduMY/Server_Programming.svg?style=flat" /></a>
<a href="#"><img src="https://img.shields.io/github/languages/top/manduMY/Server_Programming.svg?colorB=yellow&style=flat" /></a>
<a href="#"><img src="https://img.shields.io/badge/license-MIT-green.svg" /></a>

서버 프로그래밍 프로젝트

- 핵심 목표: 서버 프로그래밍을 해보자
- Keyword: node.js, javascript, Jquery, Ajax, Ejs Templete, bootstrap, Multur 모듈, Express 서버, 미들웨어, Box Slider, LightBox, Open API, FlexSlider, Parsing, 크롤링, MongoDB, 반응형 웹, Server-Side, Client-Side
- 주제: 각종 공모전 컨텐츠들을 한눈에 볼 수 있도록 제공하는 웹 서비스
- 내용: 공모전 정보와 입상 후 포트폴리오 양식 지원, 공모전을 준비하는 사람들이 정보를 쉽게 얻고 자기계발 향상을 위한 서비스 제공
- 개발 기간: 2019.07 ~ 2019.08

> Readme 작성중...

<br/>

샘플 화면
---
개발 환경이 윈도우이기 때문에 윈도우 운영체제에서 실행 하였습니다.

| 메인 화면 |
|:----------------------------------------:|
|<img src="markdown/img/main_view.png" width=1000 />|

| 지난 공모전 | 진행중인 공모전 |
|:----------------------------------------:|:-----------------------------------------:|
|<img src="markdown/img/lastcontest_view.png" width=500 />|<img src="markdown/img/ongoingcontenst_view.png" width=500 />|

| 포트폴리오 다운로드 | 포트폴리오 공유 |
|:----------------------------------------:|:-----------------------------------------:|
|<img src="markdown/img/portfoliodownload_view.png" width=500 />|<img src="markdown/img/portfolioshare_view.png" width=500 />|

<br/>

전체 사이트맵
---
<img src="markdown/img/sitemap.png" width=1000 >

<br/>

주요 기술 요소
---

| 메인 화면 |
|:----------------------------------------:|
|<img src="markdown/img/mainpage_function.png" width=1000 />|

| 로그인 및 회원가입 | 메인페이지 기능 |
|:----------------------------------------:|:-----------------------------------------:|
|<img src="markdown/img/signinandsignup_function.png" width=500 />|<img src="markdown/img/mainpage_function.png" width=500 />|

| 포트폴리오 다운로드 | 포트폴리오 공유 |
|:----------------------------------------:|:-----------------------------------------:|
|<img src="markdown/img/portfoliodownload_view.png" width=500 />|<img src="markdown/img/portfolioshare_view.png" width=500 />|

<br/>

개발 중점 사항
---
<img src="markdown/img/Development_Focus.png" width=1000 >

<br/>

개발 과정
---

1. HTML과 javascript로 기본적인 기능이 있는 웹페이지 구성
2. node.js 모듈 설치 및 app.js 구축
3. Open API 적용(날씨 정보)
4. MongoDB 연동 및 DataBase와Collection 생성
5. 회원가입과 로그인 기능 구현(MongoDB)
6. ejs 템플릿 엔진 적용
7. 공모전 정보 Parsing(MongoDB)
8. multur 모듈을 통한 파일 업로드 구현
9. 파일 다운로드 기능 구현
10. lightBox, BoxSlider, flexSlider 적용을 통한 깔끔한 뷰 구성

<br/>

한눈에 보는 전체 시스템 구조도
---
<img src="markdown/img/Overall_System_Structure.png" width=1000 >

<hr/>

<img src="markdown/img/ClassUML.png" width=1000 />
<img src="markdown/img/ClassUML2.png" width=1000 />
<img src="markdown/img/ClassUML3.png" width=1000 />

- Client: 
  - 이 클라이언트의 쓰레드는 while문으로 동작한다.
  - 모든 요청은 'PCController'를 거치며 View에서의 모든 Event 처리를 여기서 처리한다.
  - 클라이언트 프로그램이 실행될 때 하나의 소켓이 생성되며 port를 통해 서버와 연결된다.
  - Server와 데이터를 주고받을 때 gson 라이브러리를 통해 JSON 형식인 메세지 객체를 통해 주고받는다.
  - Server가 Client에게 메세지를 보내면 Client의 쓰레드에서 정보를 확인하여 실시간으로 정보를 뿌려준다.
  - 프로그램을 실행할 경우 즉, 로그인할 때마다 생성되는 Client 프로그램은 각각의 쓰레드가 하나씩 존재한다.
  - 서로 다른 클라이언트들은 각각 고객정보 DAO와 주문정보 DAO 객체를 참조할 수 있다. (고객 정보는 예를들어 로그인여부, 주문 정보는 주문 시 데이터베이스에 접근해야 하기 때문이다.)
  - 보여줄 화면객체를 찾았다면 cardLayout을 통해 유저에게 화면을 보여준다.
  - 모든 컨트롤러와 서비스, 뷰는 싱글톤으로 구성되어 있다.
  - 서버에 들어오는 모든 메세지를 BufferedReader로 읽어들인다.
  - 프로그램을 종료시킬 때 스레드를 stop하는 것이 아닌 status라는 bool값을 false로 두어 스레드가 동작중인 while 문에서 자연스럽게 빠져나와 종료되도록 한다.

<br/>
<br/>

- Server:
  - 이 서버의 쓰레드는 while문으로 동작한다.
  - 서버는 실행과 동시에 ServerSocket과 그냥 Socket을 하나씩만 만들어 서버에 들어오는 모든 요청을 받는다.
  - 서버는 열려있는 클라이언트의 쓰레드들을 ArrayList에 저장하여 필요할 때 특정 클라이언트의 쓰레드에 접근할 수 있다.
  - 각각의 개별적인 쓰레드(각 클라이언트들)에서 서로 다른 클라이언트에 접근하기 위해서는 Server에 메세지를 보내고 Server에서 해당 클라이언트를 찾아 해당 클라이언트의 쓰레드에 메세지를 보내서 Event를 처리하였다.
  - 서버에는 주문 정보 DAO와 DTO 둘 다 참조할 수 있다. (클라이언트에서 요청이 들어오면 주문 정보 database를 처리하고 주문 목록에 대한 정보를 알아내기 위해서이다.)
  - 서버에 들어오는 모든 메세지를 BufferedReader로 읽어들인다.
  - 클라이언트와 똑같이 프로그램을 종료시킬 때 스레드를 stop하는 것이 아닌 status라는 bool값을 false로 두어 스레드가 동작중인 while 문에서 자연스럽게 빠져나와 종료되도록 한다.
  - 제네릭 종류(리스트, 해쉬맵, 벡터 등)들은 JSON으로 변환하여 메세지를 보내지 못한다.(JSON으로 변환할 때 제네릭을 잃어버린다고 한다. 그래서 데이터는 정상적으로 보내지지만 get으로 선택해서 데이터를 쓸 수 없었다.)
  - 상품관리 창의 로그인 여부, 상품 삽입/삭제/수정/검색(CRUD), 음식 주문 여부는 데이터베이스에서 저장된다.

<br/>

어떻게 실행하나요?
---
- [MongoDB 설정하기](markdown/index/MongoDB.md)
  - MongoDB Community Or MongoDB Compass 버전 둘중 하나를 운영체제에 맞게 설치합니다.
  - 환경변수 설정하기 ([내컴퓨터] 우클릭 -> [고급시스템설정] -> [환경변수])
  - MongoDB와 프로젝트를 연결해주자 (이 프로젝트의 app.js 파일에 databaseURL이 적혀있다. 'mongodb://localhost:27017/test'를 복사하고 MongoDB를 키면 databaseURL을 적으라고 한다. 복사한걸 붙여주자.)
  - DataBase를 만들어 주어야 한다. 이 프로젝트에서는 test라는 이름으로 DataBase를 사용하고 있으므로 프로젝트 파일을 수정하기 귀찮다면 DataBase 이름을 test로 지어주자.
  - test라는 DataBase에 Create Collection을 눌러서 info2, infos, users를 생성해준다.



- 로컬 환경에서 실행하기
  - 로컬 환경이므로 Chrome이나 Internet Explorer를 킬때 localhost:3000를 주소창에 쳐야 들어가집니다.
  
***
##### ※ 프로그램 실행 순서 ※ 
  
-> 몽고DB Comunity 버전 설치, node.js 설치, 몽고 DB

-> cmd 창을 실행

맺으며
---
- 앞으로 사용시간과 잔여시간 기능을 추가할 계획입니다!!!

참고 자료 출처
---
https://mongoosejs.com/docs/documents.html - MongoDB 참고 사이트
https://www.jqueryscript.net/popular/ - Jquery Plugin 참고 사이트
https://www.w3schools.com/ - HTML, CSS, javascript, JQuerty 사용법 참고 사이트
http://www.weather.go.kr/weather/lifenindustry/sevice_rss.jsp – 날씨 API Parsing 사이트
https://www.thinkcontest.com/ - 공모전 정보 Parsing 사이트

License
---
This is released under the MIT license. See [LICENSE](LICENSE) for details.
