# 1회차

## 참고

- `var` 와 `let`, `const` 키워드 간 호이스팅 차이점
  - [let과 const도 호이스팅이 될까? TDZ란?](https://taenami.tistory.com/87)
  - [TDZ(Temporal Dead Zone) 더 알아보기](https://ui.toast.com/weekly-pick/ko_20191014)
- [**Google Chrome Web development docs**](https://developers.google.com/focus/web-development?hl=ko)
- [Garbage Collection](<https://ko.wikipedia.org/wiki/%EC%93%B0%EB%A0%88%EA%B8%B0_%EC%88%98%EC%A7%91_(%EC%BB%B4%ED%93%A8%ED%84%B0_%EA%B3%BC%ED%95%99)>)
- [실행 컨텍스트란?](https://velog.io/@kados22/FE-%EA%B8%B0%EC%88%A0-%EB%A9%B4%EC%A0%91-%EC%8B%A4%ED%96%89-%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8%EA%B0%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94)
- [CBD(Component-Based Development) 방법론](https://ko.wikipedia.org/wiki/%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8_%EA%B8%B0%EB%B0%98_%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4_%EA%B3%B5%ED%95%99)
- [Web API](https://developer.mozilla.org/ko/docs/Web/API) vs [Node API](https://nodejs.org/api/n-api.html)
- [ES6 지원 브라우저 표](https://compat-table.github.io/compat-table/es6/)

## [퀴즈](https://github.com/ooheunda/how-to-enjoy/issues/1)

### 재연

<ol>
  <li>개발자 도구에 변수 선언문을 작성했을때, undefined 값을 반환하는 이유
    <details>
    <summary>정답 보기</summary>
      변수를 선언하는 것으로는 값을 반환하지 않기 때문에
    </details>
  </li>

  <li>변수의 값이 재할당 될때 해당 60의 값은 어떤 식으로 메모리 공간에 저장되나?
    <details>
    <summary>정답 보기</summary>
      메모리 공간에 이미 할당된 값이 삭제되는게 아닌, 60을 다른 메모리 공간에 저장하고, 해당 변수에 60에 대한 주소값이 할당된다.
    </details>
  </li>

  <li>변수를 선언하고 값을 할당하지 않았을 때, 해당 변수에 의해 확보된 메모리 공간은 비어있는가?
    <details>
    <summary>정답 보기</summary>
      자바스크립트 엔진에 의해 undefined 값이 할당된다.
    </details>
  </li>
</ol>

### 린

<ol>
  <li>프로그램을 구성하는 기본 단위이자 최소 실행 단위를 뭐라고 부르는지?
    <details>
      <summary>정답 보기</summary>
      문(statement)
    </details>
  </li>

  <li>표현식인 문과 표현식이 아닌 문을 간단히 구별하는 방법은?
    <details>
      <summary>정답 보기</summary>
      변수에 할당해보기.
    </details>
  </li>

  <li>변수의 선언은 런타임을 기준으로 전, 중, 후 언제 실행되나?
    <details>
      <summary>정답 보기</summary>
      런타임 전
    </details>
  </li>

  <li>식별자가 등록되는 곳은 어디인가?
    <details>
      <summary>정답 보기</summary>
      실행 컨텍스트
    </details>
  </li>
</ol>

### 다은

<ol>
  <li>
    <pre><code>
console.log(quiz1); //(1)

quiz1 = 120;
var quiz1 = 300;

console.log(quiz1); //(2)
</code></pre>

<details>
<summary>정답 보기</summary>
<b>(1) undefined</b> <br>
var 키워드로 선언된 변수는 런타임 전 호이스팅되어 코드상에서 변수 선언문이 밑에 있어도 자바스크립트 엔진은 그 변수를 이미 알고 있다. <br>
<b>(2) 300</b> <br>
마지막으로 할당된 300이 출력된다.
</details>
  </li>

  <li>
    <pre><code>
console.log(quiz2); //(1)

quiz2 = 100; //(2)
let quiz2;

console.log(quiz2); //(3)
</code></pre>

<details>
<summary>정답 보기</summary>
<b>(1) reference error: 'quiz2' is not defined</b> <br>
quiz2 변수가 정의되지 않았다는 에러를 반환한다. 이는 quiz2가 let 키워드로 선언되었기 때문인데, 선언과 초기화가 동시에 이뤄지는 var 키워드와 다르게 let, const 키워드는 호이스팅시 선언만 되기 때문이다. <br>
<b>(2) reference error: cannot access 'quiz2' before initialization</b> <br>
위와 같은 이유로, 좀 더 명확한 에러 메세지이다. 호이스팅시 선언만 되고 초기화가 되지 않았기 때문에 이런 에러가 뜬다. <br>
<b>(3) undefined</b> <br>
에러를 배제하고 생각했을 때 (3)에는 undefined가 출력될 것이다. 저 로그문 위의 마지막 문이 quiz2 선언문이기 때문에, 저 시점에서 quiz2는 초기화되고 자동으로 undefined가 할당된다.
</details>
  </li>
</ol>

## 분량

- **01장: 프로그래밍**
  - 1.1 프로그래밍이란?
  - 1.2 프로그래밍 언어
  - 1.3 구문과 의미
- **02장: 자바스크립트란?**
  - 2.1 자바스크립트의 탄생
  - 2.2 자바스크립트의 표준화
  - 2.3 자바스크립트 성장의 역사
    - 2.3.1 Ajax
    - 2.3.2 jQuery
    - 2.3.3 V8 자바스크립트 엔진
    - 2.3.4 Node.js
    - 2.3.5 SPA 프레임워크
  - 2.4 자바스크립트와 ECMAScript
  - 2.5 자바스크립트의 특징
  - 2.6 ES6 브라우저 지원 현황
- **03장: 자바스크립트 개발 환경과 실행 방법**
  - 3.1 자바스크립트 실행 환경
  - 3.2 웹 브라우저
    - 3.2.1 개발자 도구
    - 3.2.2 콘솔
    - 3.2.3 브라우저에서 자바스크립트 실행
    - 3.2.4 디버깅
  - 3.3 Node.js
    - 3.3.1 Node.js와 npm 소개
    - 3.3.2 Node.js 설치
    - 3.3.3 Node.js REPL
  - 3.4 비주얼 스튜디오 코드
    - 3.4.1 비주얼 스튜디오 코드 설치
    - 3.4.2 내장 터미널
    - 3.4.3 Code Runner 확장 플러그인
    - 3.4.4 Live Server 확장 플러그인
- **04장: 변수**
  - 4.1 변수란 무엇인가? 왜 필요한가?
  - 4.2 식별자
  - 4.3 변수 선언
  - 4.4 변수 선언의 실행 시점과 변수 호이스팅
  - 4.5 값의 할당
  - 4.6 값의 재할당
  - 4.7 식별자 네이밍 규칙
- **05장: 표현식과 문**
  - 5.1 값
  - 5.2 리터럴
  - 5.3 표현식
  - 5.4 문
  - 5.5 세미콜론과 세미콜론 자동 삽입 기능
  - 5.6 표현식인 문과 표현식이 아닌 문

## 출석부

|    이름     | 출석 | 퀴즈 담당 |
| :---------: | :--: | :-------: |
|    다은     |  ✅  |    💣     |
|    하온     |  ✅  |           |
|     린      |  ✅  |    💣     |
|    재연     |  ✅  |    💣     |
|    기돈     |  ✅  |           |
|    주희     |  ✅  |           |
| 참관 세민님 |  💗  |           |
