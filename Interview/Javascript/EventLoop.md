# 💻 Javascript EventLoop

<br />

## EventLoop란?

- `Event Loop`란, Callback Event Queue에서 하나씩 꺼내서 동작시키는 Loop.
- 자바스크립트는 싱글 스레드 기반 언어이기 때문에, 한번에 하나씩 작업을 진행하고,
- 비동기로 동작하기때문에 단일 스레드임에도 불구하고 동시에 많은 작업을 진행한다.

<br />

## EventLoop 동작 방식

![ajax동작방식](https://miro.medium.com/max/1400/1*pjRSYsfW-D8MCrGh9LS_4Q.png)

<br />

- `Heap` : 메모리 할당이 발생한 곳
  </br>
- `Call Stack` : 실행된 코드의 환경을 저장하는 자료구조, 함수호출시 이곳에 저장
  어떤 함수를 저장하면 스택에 쌓고 또 다른함수를 호출하면 그 다음 스택에 쌓이면서 가장 위에 쌓인 함수를 가장 먼저 처리(LIFO : Last In First Out)
  </br>
- `Web APIs` : 브라우저에서 제공하는 API로 DOM,Ajax,TimeOut 등이있다.
  Call Stack에서 실행된 비동기함수는 Web API를 호출하고,
  Web API는 콜백함수를 Task Queue에 넣는다.
  </br>
- `Callback Queue` : 함수를 저장하는 자료구조,
  Call Stack과 다르게 가장 먼저 들어온 함수를 가장 먼저 처리한다.
  </br>
- `Event Loop` : 이벤트루프는 call stack이 다 비워지면 callback queue에 존재하는 함수를 하나씩 call stack으로 옮기는 역할을 한다.

<br />

### Event Loop 과정

```js
function main() {
  console.log("First");
  setTimeout(function display() {
    console.log("Second");
  }, 0);
  console.log("Third");
}
main();

//	First
//	Third
//      Second
```

<br />

## 참고

https://www.youtube.com/watch?v=8aGhZQkoFbQ
