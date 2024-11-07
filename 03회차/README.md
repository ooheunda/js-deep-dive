# 3회차

## 참고

- 자바스크립트의 객체 관리 방식 (146p)
  - [해시테이블](https://mangkyu.tistory.com/102)
  - [V8 엔진의 히든 클래스](https://engineering.linecorp.com/ko/blog/v8-hidden-class)
- [얕은 복사와 깊은 복사](https://www.digitalocean.com/community/tutorials/copying-objects-in-javascript) (150p)
- [유사 배열 객체](https://www.zerocho.com/category/JavaScript/post/5af6f9e707d77a001bb579d2) (141p)

## [퀴즈](https://github.com/ooheunda/js-deep-dive/issues/3)

### 하온

1. 원시 값 변수 재할당 시 변수가 참조하던 메모리 공간의 주소가 변경된다. 이런 특성을 뭐라고 할까요?
    <details>
      <summary>정답 보기</summary>
      <div>불변성</div>
    </details>

2. 문자열은 배열이 아님에도 인덱스로 인한 접근과, for문으로 순회가 가능한데 어떻게 가능할까요?
    <details>
      <summary>정답 보기</summary>
      <div>문자열은 유사 배열 객체이기 때문이다.</div>
    </details>

### 주희

1.  '값에 의한 전달'이라는 용어는 엄격하게 표현하자면 변수에는 값이 전달되는 것이 아니라 `$$$ $$`가 전달되기 때문에, 변수와 같은 식별자는 '값'이 아니라 `$$$ $$`를 기억하고 있는 것이다. 식별자는 어떤 값을 구별해서 식별해낼 수 있어야 하므로 변수와 같은 식별자는 '값'이 아니라 `$$$ $$`를 기억하고 있다. 즉, 식별자는 `$$$ $$`에 붙인 이름이라고 할 수 있다.
    <details>
      <summary>정답 보기</summary>
      <div>메모리 주소</div>
    </details>

2.  프로퍼티 키는 프로퍼티 값에 접근할 수 있는 이름으로서 `***` 역할을 한다. `***` 네이밍 규칙을 따르지 않는 이름에는 반드시 따옴표를 사용해야한다.
    <details>
      <summary>정답 보기</summary>
      <div>식별자</div>
    </details>

3.  원시 값은 변경 불가능한 값이므로 원시 값을 갖는 변수의 값을 변경하려면 `@@@` 외에는 방법이 없다. 하지만, 객체는 변경 가능한 값이다. 따라서 객체를 할당한 변수는 `@@@`없이 객체를 직접 변경할 수 있다. 즉, `@@@` 없이 프로퍼티를 동적으로 추가할 수도 있고, 값을 갱신, 삭제 할 수도 있다.
    <details>
      <summary>정답 보기</summary>
      <div>재할당</div>
    </details>

4. 자바스크립트 엔진은 표현식을 평가할 때 코드 문맥에 부합 하도록 `### ## ##`을 실행한다. 문자열 연결 연산자 표현식을 평가하기 위해 문자열 연결 연산자의 피연산자 중에서 문자열이 타입이 아닌 피연산자를 문자열 타입으로 `### ## ##` 한다.
    <details>
      <summary>정답 보기</summary>
      <div>암묵적 타입 변환</div>
    </details>

5. `&&& &&&`는 두 개의 피연산자가 true로 평가될 때 true를 반환한다. `&&& &&&`는 좌항에서 우항으로 진행된다.
    <details>
      <summary>정답 보기</summary>
      <div>논리곱 연산자</div>
    </details>

### 재연

1. ```javascript
    const a = '' ?? 'false';

    console.log(a);
    ```

   <details>
      <summary>정답 보기</summary>
      <div><code>""</code></div>
    </details>

2. ```javascript
    let person = {
      name: 'lee',
      name: 'kim',
      sayHello: function () {
        console.log(`hello ${this.name}`);
      },
    };
    person.sayHello();
    ```
    <details>
        <summary>정답 보기</summary>
        <div><code>"hello kim"</code></div>
      </details>

3. ```javascript
    var sum = {
      boolean: true,
      string: '',
      infinity: Infinity,
      sum: function () {
        console.log(`${this.boolean + 1 + this.string + this.infinity}`);
      },
    };

    sum.sum();
    ```
    <details>
        <summary>정답 보기</summary>
        <div><code>"2Infinity"</code></div>
      </details>

## 분량

- **09장: 타입 변환과 단축 평가**
  - 9.1 타입 변환이란?
  - 9.2 암묵적 타입 변환
    - 9.2.1 문자열 타입으로 변환
    - 9.2.2 숫자 타입으로 변환
    - 9.2.3 불리언 타입으로 변환
  - 9.3 명시적 타입 변환
    - 9.3.1 문자열 타입으로 변환
    - 9.3.2 숫자 타입으로 변환
    - 9.3.3 불리언 타입으로 변환
  - 9.4 단축 평가
    - 9.4.1 논리 연산자를 사용한 단축 평가
    - 9.4.2 옵셔널 체이닝 연산자
    - 9.4.3 null 병합 연산자
- **10장: 객체 리터럴**
  - 10.1 객체란?
  - 10.2 객체 리터럴에 의한 객체 생성
  - 10.3 프로퍼티
  - 10.4 메서드
  - 10.5 프로퍼티 접근
  - 10.6 프로퍼티 값 갱신
  - 10.7 프로퍼티 동적 생성
  - 10.8 프로퍼티 삭제
  - 10.9 ES6에서 추가된 객체 리터럴의 확장 기능
    - 10.9.1 프로퍼티 축약 표현
    - 10.9.2 계산된 프로퍼티 이름
    - 10.9.3 메서드 축약 표현
- **11장: 원시 값과 객체의 비교**
  - 11.1 원시 값
    - 11.1.1 변경 불가능한 값
    - 11.1.2 문자열과 불변성
    - 11.1.3 값에 의한 전달
  - 11.2 객체
    - 11.2.1 변경 가능한 값
    - 11.2.2 참조에 의한 전달

## 출석부

| 이름 | 출석 | 퀴즈 담당 |
| :--: | :--: | :-------: |
| 다은 |  ✅  |           |
| 하온 |  ✅  |    💣     |
|  린  |  ✅  |           |
| 재연 |  ✅  |    💣     |
| 기돈 |  ✅  |           |
| 주희 |  ✅  |    💣     |
| 세민 |  ✅  |           |
