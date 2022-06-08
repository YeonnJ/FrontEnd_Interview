![restful동작방식](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbj5EFT%2Fbtq1V2X4UsZ%2FCUz5fdV92fUIkveEEJNPYk%2Fimg.png)
</br>

### GET방식

- GET방식의 특징으로는 대표적으로 URL에 Parameter를 붙여서 전송한다는 것
  <br />

```js
http://khj93.tistory.com/test_api?param1=value1&param2=value2
```

<br />

### POST방식

- POST 방식의 특징으로는 대표적으로 GET 방식과는 달리 body영역에 데이터를 실어 보낸다는 점
- Body에 데이터를 실어 보내기 때문에 데이터 전송양에 길이 제한이 없으며 대용량 데이터를 보내는데 적합
- 는 Body영역 데이터 타입을 Header Content-Type에 명시
  <br />

```js
1. application/x-www-form-urlencoded
2. text/plain
3. multipart/form-data
```

- POST 방식으로 데이터를 보낼때는 위와 같이 컨텐츠 타입을 꼭 명시
- 명시해주지 않으면 GET 타입으로 세팅
