✅ HOC(Higher-Order Components)

* 많은 함수들이 `life cycle에 종속`될 수 밖에 없다. -> `재사용`이 힘듦
* 위 문제를 해결하기 위해 HOC로 컴포넌트를 역할에 따라 분리
  * Inner 컴포넌트: class 컴포넌트로 state와 주요 로직을 가짐(재사용이 가능한 부분만 가지는)
  * Wrapper 컴포넌트: functional 컴포넌트로 state와 무관한 로직(주로 UI와 관련된)을 가짐
  > Wrapper로 Inner를 감싸 역할을 분리
* 하지만, HOC와 같은 패턴을 사용해도..  
  * `Wrapper 컴포넌트가 늘어남`에 따라 DOM이 깊어지고
  * 컴포넌트늘 간에 `전달하는 상태(props)들도 많아진다.`
* 추가로, `this의 어려움`, 코드의 길이가 길다는 문제점도 있다.

<hr />

* hook을 사용함으로써 코드의 양 자체도 줄고, 로직이 단순해지며
* 컴포넌트가 class -> 단순 함수로 바뀌기 때문에 재활용 자체가 용이해진다.