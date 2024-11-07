# 2회차

## 참고

- 라인 피드와 캐리지 리턴 (63p)
  - 다은) 패키지를 통해 생성된 파일을 커밋인가 푸시할 때 에러 메세지에서 많이 봤었던 키워드입니당. (ex 프리즈마 초기화 했을때 생기는 파일들)
- [전위/후위 연산자 연산 이해](https://velog.io/@sweetpumpkin/%EC%A0%84%EC%9C%84-%ED%9B%84%EC%9C%84-%EC%97%B0%EC%82%B0%EC%9E%90-%EC%97%B0%EC%82%B0-%EC%9D%B4%ED%95%B4) (76p)
- [레이블문](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/label) (104p)
- [배정밀도 64비트 부동소수점](https://hbsowo58.tistory.com/460)
- [심볼 테이블](https://ko.wikipedia.org/wiki/%EC%8B%AC%EB%B3%BC_%ED%85%8C%EC%9D%B4%EB%B8%94)
- [Object.is](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/is)
- [이스케이프 시퀀스](https://learn.microsoft.com/ko-kr/cpp/c-language/escape-sequences)

## [퀴즈](https://github.com/ooheunda/js-deep-dive/issues/2)

### 하온

<ol>
  <li>
    <pre><code>
let num = 10;
let result;
result = num++ * 2;
</code></pre>
    <details>
      <summary>정답 보기</summary>
      <b>result = 20</b> <br />
      <b>num = 11</b>
    </details>
  </li>

  <li>
    우선 순위 먼저 인것을 나열하기
    <div>ㄱ. () ㄴ. ** ㄷ. /</div>
    <details>
      <summary>정답 보기</summary>
      <b>ㄱ → ㄴ → ㄷ</b>
    </details>
  </li>

  <li>
    <pre><code>
let num = 10;
let result = ++num * 3 ** 2;
console.log(result, num); 
</code></pre>
    <details>
      <summary>정답 보기</summary>
      <b>result = 99</b> <br />
      <b>num = 11</b>
    </details>
  </li>

  <li>
    while문의 조건식에 truthy(1, true)한 값을 넣으면 어떻게 될까??
    <details>
      <summary>정답 보기</summary>
      무한 실행!!! 루프!!!!!!
    </details>
  </li>

  <li>
    <pre><code>
for (let i = 0; i < 10; i++) {
  if (i % 2 === 0) {
    continue;
  }
  console.log(i); 
}
</code></pre>
    <details>
      <summary>정답 보기</summary>
      1, 3, 5, 7, 9
    </details>
  </li>

  <li>
    <pre><code>
for (let i = 0; i < 10; i++) {
  if (i % 2 === 0) {
    break;
  }
  console.log(i); 
}
</code></pre>
    <details>
      <summary>정답 보기</summary>
      출력값 X
    </details>
  </li>
</ol>

### 기돈

<ol>
  <li>
    데이터 타입이 필요한 이유? (3가지)
    <details>
      <summary>정답 보기</summary>
      <div>1. 메모리 할당: 타입에 따라 메모리가 할당되는 크기가 다름</div>
      <div>2. 변수 참조: 변수 참조 시, 읽어올 메모리의 단위를 결정</div>
      <div>3. 메모리에서 받아온 2진수를 어떻게 해석해야 하는지 결정</div>
    </details>
  </li>

  <li>
    <pre><code>
let x = 1;
x++ + 1 = ??; // 1)
x = ??; // 2)
</code></pre>
    <pre><code>
let x = 1;
++x + 1 = ??; // 3)
x = ??; // 4)
</code></pre>
    <details>
      <summary>정답 보기</summary>
      <div>1) 2</div>
      <div>2) 2</div>
      <div>3) 3</div>
      <div>4) 2</div>
    </details>
  </li>

  <li>
    템플릿 리터럴
    <pre><code>
function person(staticData, ...dynamicData) {
  console.log(staticData); // 1)
  console.log(dynamicData); // 2)
}

let name = "jack", age = 30
person`안녕하세요 ${name}입니다. 나이는 ${age}입니다.`;
</code></pre>

<details>
<summary>정답 보기</summary>
<div>1) [‘안녕하세요 ‘, ‘입니다. 나이는 ‘, ‘입니다.’]</div>
<div>2) [‘jack’, 30]</div>
</details>

  </li>
</ol>

### 주희

<ol>
  <li>혼자 다른 것 찾기
  <pre><code>
  var x = "hello";
  var y = hello;
  var y = 'hello';
  var y = hello;
  </code></pre>
  <details>
  <summary>정답 보기</summary>
  2번.
  1, 3, 4번은 문자열로 인식한다. 작은따옴표, 큰따옴표, 백틱이 없는 문자열은 식별자로 인식되어 ReferenceError로 hello를 찾을 수 없다고 뜬다.
  </details>
  </li>

  <li>
  var 키워드로 선언한 변수는 암묵적으로 <code>##</code>로 초기화 된다. 따라서, 변수를 참조했을 때 <code>##</code>가 반환된다면, 이를 통해 우리는 참조한 변수가 선언 이후 값이 할당된 적이 없는, 초기화되지 않은 변수라는 것을 간파 할 수 있다. <br>
  ES6에서 추가된 타입으로, 변경 불가능한 원시 타입의 값이다. <code>%%</code>값은 다른 값과 중복 되지 않는 유일무이한 값이다. 따라서 주로 이름이 충돌할 위험이 없는 객체의 유일한 프로퍼티 키를 만들기 위해 사용한다. <br>
  ECMAScript 사양에서 <code>OO</code>는 선언한다. 라고 표현하고, <code>**</code>는 정의한다. 라고 표현 합니다. <br>
  변수에 <code>++</code>을 할당하는 것은 변수가 이전에 참조 하던 값을 더이상 참조하지 않겠다는 의미다. 함수가 유효한 값을 반환할 수 없는 경우 명시적으로 <code>++</code>을 반환 하기도 한다.
  <details>
  <summary>정답 보기</summary>
  ##: undefined <br>
  %%: 심볼 <br>
  OO: 변수 <br>
  **: 함수 <br>
  ++: null
  </details>
  </li>

  <li>
  일반적으로 코드는 위에서 아래 방향으로 순차적으로 실행 된다. <code>**문</code>을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있다. <br>
  조건문은 주어진 조건식의 평가 결과에 따라 코드 블록(블록문)의 실행을 결정 한다. 조건식은 <code>@@@</code> 값으로 평가 될 수 있는 표현식이다. <br>
  <code>##문</code>은 주어진 조건식의 평가 결과가 참이면 코드 블록을 계속해서 반복 실행한다. <code>%%문</code>은 반복 횟수가 명확할 때 주로 사용하고 <code>##문</code>은 반복 횟수가 불명확할 때 주로 사용한다. <br>
  문의 끝에는 <code>$$</code>를 붙이는 것이 일반적입니다. 하지만 블록문은 언제나 문의 종료를 의미하는 자체 종결성을 갖기 때문에 블록문 끝에는 <code>$$</code>을 붙이지 않는다는 것을 주의하십셔 !
  <details>
  <summary>정답 보기</summary>
  **문: 제어문 <br>
  @@@: 불리언 <br>
  ##문: while문 <br>
  %%문: for문 <br>
  $$: 세미콜론
  </details>
  </li>

  <li> continue문과 break문의 차이점
    <details>
  <summary>정답 보기</summary>
  continue문은 반복문의 코드 블록 실행을 현 시점에서 중단하고, 반복문의 증감식으로 실행 흐름을 이동시킨다. break문은 실행중인 반복문의 코드블록을 탈출한다.
  </details>
  </li>

## 분량

- **06장: 데이터 타입**
  - 6.1 숫자 타입
  - 6.2 문자열 타입
  - 6.3 템플릿 리터럴
    - 6.3.1 멀티라인 문자열
    - 6.3.2 표현식 삽입
  - 6.4 불리언 타입
  - 6.5 undefined 타입
  - 6.6 null 타입
  - 6.7 심벌 타입
  - 6.8 객체 타입
  - 6.9 데이터 타입의 필요성
    - 6.9.1 데이터 타입에 의한 메모리 공간의 확보와 참조
    - 6.9.2 데이터 타입에 의한 값의 해석
  - 6.10 동적 타이핑
    - 6.10.1 동적 타입 언어와 정적 타입 언어
    - 6.10.2 동적 타입 언어와 변수
- **07장: 연산자**
  - 7.1 산술 연산자
    - 7.1.1 이항 산술 연산자
    - 7.1.2 단항 산술 연산자
    - 7.1.3 문자열 연결 연산자
  - 7.2 할당 연산자
  - 7.3 비교 연산자
    - 7.3.1 동등/일치 비교 연산자
    - 7.3.2 대소 관계 비교 연산자
  - 7.4 삼항 조건 연산자
  - 7.5 논리 연산자
  - 7.6 쉼표 연산자
  - 7.7 그룹 연산자
  - 7.8 typeof 연산자
  - 7.9 지수 연산자
  - 7.10 그 외의 연산자
  - 7.11 연산자의 부수 효과
  - 7.12 연산자 우선순위
  - 7.13 연산자 결합 순서
- **08장: 제어문**
  - 8.1 블록문
  - 8.2 조건문
    - 8.2.1 if...else 문
    - 8.2.2 switch 문
  - 8.3 반복문
    - 8.3.1 for 문
    - 8.3.2 while 문
    - 8.3.3 do...while 문
  - 8.4 break 문
  - 8.5 continue 문

## 출석부

| 이름 | 출석 | 퀴즈 담당 |
| :--: | :--: | :-------: |
| 다은 |  ✅  |           |
| 하온 |  ✅  |    💣     |
|  린  |  ✅  |           |
| 재연 |  ✅  |           |
| 기돈 |  ✅  |    💣     |
| 주희 |  ✅  |    💣     |
