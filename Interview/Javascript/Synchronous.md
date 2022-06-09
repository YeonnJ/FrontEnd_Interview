# 동기 (Synchronous)와 비동기(Asynchronous)

- 동기는 말 그대로 동시에 일어난다는 뜻.
- 동기 방식은 서버에서 요청을 보냈을 때 응답이 돌아와야 다음 동작을 수행할 수 있다.
  - 즉 A작업이 모두 진행 될때까지 B작업은 대기
- 비동기 방식은 반대로 요청을 보냈을 때 응답 상태와 상관없이 다음 동작을 수행 할 수 있다.

  - 즉 A작업이 시작하면 동시에 B작업이 실행된다. A작업은 결과값이 나오는대로 출력
    <br />

  ![동작방식](https://t1.daumcdn.net/cfile/tistory/99B27B3B5BC7D69604)
  </br>

### 동기

```js
function func1() {
  console.log("첫번째 펑션!");
  func2();
}

function func2() {
  console.log("두번째 펑션!");
  func3();
}

function func3() {
  console.log("세번째 펑션");
}

func1();
// 출력값은 아래와 같다.
// 첫번째 펑션!
// 두번째 펑션!
// 세번째 펑션! 을 띄우게 된다.
```

<br />

### 비동기

```js
function func1() {
  console.log("func1");
  func2();
}

function func2() {
  setTimeout(function () {
    console.log("func2");
  }, 0);
  func3();
}

function func3() {
  console.log("func3");
}
func1();
/*
실행결과
func1
func3
func2
*/
```

<br />
