# nodejs 공부한 내용 정리

## nodejs란...?
javascript를 사용하여 백엔드를 구현하게 해주는 도구. 비유를 들어 설명을 하면 자바스크립트는 웹브라우저(프론트엔드)에서도 사용되고 nodejs(백엔드)에서도 사용이 된다. 자바스크립트는 말 그대로 언어고 웹브라우저는 병원, nodejs는 식당이다. 같은 언어를 사용하지만 각자 하는 일들이 명확히 다르다. 그리고 프라이팬, 가스레인지와 같은 것들이 식당의 일을 편하게 해주는 도구들이며 이러한 도구들을 모듈이라고 한다(내 생각엔 모듈이 nodejs에서 사용하는 라이브러리 같다).

## 핵심 키워드 
먼저 핵심 키워드들을 정리하고 시작하고자 한다.
### 1. 구글 V8 자바스크립트 엔진
### 2. 고성능 네트워크 서버
### 3. 단일 쓰레드 이벤트 루프 기반
### 4. 비동기 I/O 처리(non-blocking I/O)
### 5. 방대한 모듈 제공(npm) (노드 패키지 매니저)

## nodejs 특징
nodejs는 단일 쓰레드(실제로는 멀티 쓰레드긴 하지만...[링크](http://jeremyko.blogspot.com/2012/12/nodejs.html) 참조) 비동기식 실행을 사용하기 때문에 처리 속도가 빠르고 서버 부하가 적다.
비동기식 실행을 위해 콜백함수가 사용이 되고 콜백함수를 쉽게 만들기 위해 익명함수를 사용한다. 콜백함수란 비동기식 실행에서 A라는 일을 끝내고 B라는 일을 해라라고 했을 때 B가 콜백 함수이다. 그리고 익명함수란 말 그대로 이름이 없는 함수이다. 콜백함수를 쉽게 만들게 해줌. 단 내 생각에 콜백 함수를 한번만 쓰면 익명함수로 만들면 편하지만 여러번 사용한다면 정의해서 쓰는게 편할 것 같다.

## 쓰레드 기반 동기방식과 단일쓰레드 이벤트 루프 기반 비동기방식의 차이
### 쓰레드 기반 동기방식 
하나의 쓰레드가 request를 받으면 처리 다하고 응답 보냄. 처리 다하기 전에 request가 또 들어오면 새로운 쓰레드가 업무를 처리함.
동시 request가 많은 경우 많은 쓰레드가 필요하게 되어 서버 과부하.

### 단일 쓰레드 이벤트 루프 기반 비동기방식
request를 받는 하나의 쓰레드가 request를 받아 할 일을 넘겨주고 본인은 또 request 받을 준비를 한다. 요청한 작업이 끝나면 이벤트를 받아 응답을 보낸다.
참고로 req,res를 처리하는 쓰레드가 단일 쓰레드이고 뒷단에 일하는 워커들은 멀티쓰레드이다.
동시 request가 오더라도 처리 될 때 까지 기다리지 않고 바로 넘기기에 서버 부하가 적다.

## nodejs 장점
### 1. 일단 언어가 자바스크립트라 백엔드 용 언어를 따로 안배워도 됨.
### 2. 개발이 빠르고 쉬움. 그리고 가벼움.
### 3. 단일 쓰레드 비동기방식이라 서버에 무리가 적다.
### 4. 방대한 npm 모듈들 사용 가능.
### 간단한 로직, 대용량 request 처리, 빠른 응답시간 요구하는 웹서비스에 어울림.

## nodejs 단점
### 1. 서버단 로직이 복잡하면 콜백함수의 늪에 빠질 수 있음.
### 2. 하나의 작업 자체가 오래 걸리는 웹서비스에는 안어울림.
### 3. 코드가 수행되어야 에러가 있는지 알 수 있어 테스트를 꼼꼼히 해줘야 함.
