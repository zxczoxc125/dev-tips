✅ 이벤트 루프(싱글 스레드, but 동시성 지원)

* ** `싱글 스레드` 기반인 자바스크립트가 `동시성`을 지원하는 방식
* ** `ECMAScript 공식 명세`에는 `이벤트 루프가 없다.`
  * (간단한 설명과 함께 `HTML5, node`의 이벤트 루프 명세에 대한 `링크만 제공`)
    * ** `자바스크립트 엔진 자체`는 Call Stack, Heap으로 구성된 `동기적인 모델`
    * `실행되는 각 환경`에서 이벤트루프 포함 기타 다른 것들을 제공해준다.
      * `브라우저`
        ![browser](/resources/browser.png)
        * HTML5 공식 명세: https://www.w3.org/TR/2011/WD-html5-20110525/webappapis.html#event-loops
      * `node`
        ![node](/resources/node.jpg)
        * node 공식 명세: https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/

<hr />

* ** `콜 스택이 비어있다면`, 태스크 큐의 `첫번째 callback`을 콜 스택에 쌓는다.
* 태스크 큐의 작업이 콜 스택으로 넘어갈 때, 콜 스택에 다른 작업이 들어온다면 해당 작업은 다시 태스크 큐로 넘어간다.
* `마이크로 태스크 큐`
  ![microtask](/resources/microtask.gif)
  * 일반 태스크 큐보다 `더 높은 우선순위`를 가지고 있기 때문에 아래와 같은 출력 결과를 보인다.
    ```js
    setTimeout(function() {
      console.log('A');
    }, 0);
    Promise.resolve().then(function() {
      console.log('B');
    }).then(function() {
      console.log('C');
    });

    // B
    // C
    // A
    ```

* (참고) 
  * https://www.youtube.com/watch?v=8aGhZQkoFbQ
  * 위 개발자의 이벤트 루프 시각화 App--> http://latentflip.com/loupe/