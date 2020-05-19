✅ this
* ** 기본적으로 해당 함수를 `호출한 객체`를 가리킨다. (환경에 따라 다르지만)
* `new` 함수로 생성된 객체의 경우, `생성된 인스턴스`가 this
* (명시적, `암시적` 바인딩 모두 `new`를 사용하면 `오버라이딩`된다.)
* 호출 객체가 체이닝되어있을 경우, 가장 하위(`직접 호출한`) 객체를 가리킨다.
* (명시적, 암시적) `바인딩`, `new`로 호출을 제외한 나머지 경우는 `전역객체`('`strict`' 모드일 경우는 `undefined`)를 가리킨다.

<hr />

* `화살표 함수`의 경우 `상위 스코프`의 this와 같다.
  ```javascript
  function test() {
    this.a = 1;
    return () => {
      console.log(this.a);
    }
  }

  test()(); // 1

  function test2() {
    this.a = 1;
    setTimeout(() => {
      console.log(this.a);
    });
  }

  test2(); // 1
  ```