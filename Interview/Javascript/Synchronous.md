### 동기 (Synchronous)와 비동기(Asynchronous)

- 동기는 말 그대로 동시에 일어난다는 뜻.
- 동기 방식은 서버에서 요청을 보냈을 때 응답이 돌아와야 다음 동작을 수행할 수 있다.
  - 즉 A작업이 모두 진행 될때까지 B작업은 대기
- 비동기 방식은 반대로 요청을 보냈을 때 응답 상태와 상관없이 다음 동작을 수행 할 수 있다.

  - 즉 A작업이 시작하면 동시에 B작업이 실행된다. A작업은 결과값이 나오는대로 출력
    <br />

  ![동작방식](https://velog.velcdn.com/images%2Fdaybreak%2Fpost%2F1be2c518-3360-4354-beff-678bc4e13fef%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-07-09%2016.21.39.png)
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
