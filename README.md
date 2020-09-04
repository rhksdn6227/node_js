# nodejs 공부한 내용 정리

##nodejs란...?
javascript를 사용하여 백엔드를 구현하게 해주는 도구. 비유를 들어 설명을 하면 자바스크립트는 웹브라우저(프론트엔드)에서도 사용되고 nodejs(백엔드)에서도 사용이 된다. 자바스크립트는 말 그대로 언어고 웹브라우저는 병원, nodejs는 식당이다. 같은 언어를 사용하지만 각자 하는 일들이 명확히 다르다. 그리고 프라이팬, 가스레인지와 같은 것들이 식당의 일을 편하게 해주는 도구들이며 이러한 도구들을 모듈이라고 한다(내 생각엔 모듈이 nodejs에서 사용하는 라이브러리 같다).

## nodejs 특징
nodejs는 단일 쓰레드(실제로는 멀티 쓰레드긴 하지만...[링크](http://jeremyko.blogspot.com/2012/12/nodejs.html) 참조) 비동기식 실행을 사용하기 때문에 처리 속도가 빠르고 서버 부하가 적다.
비동기식 실행을 위해 콜백함수가 사용이 되고 콜백함수를 쉽게 만들기 위해 익명함수를 사용한다. 콜백함수란 비동기식 실행에서 A라는 일을 끝내고 B라는 일을 해라라고 했을 때 B가 콜백 함수이다. 그리고 익명함수란 말 그대로 이름이 없는 함수이다. 콜백함수를 쉽게 만들게 해줌. 단 내 생각에 콜백 함수를 한번만 쓰면 익명함수로 만들면 편하지만 여러번 사용한다면 정의해서 쓰는게 편할 것 같다.
