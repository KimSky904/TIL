# Component
    App.js의 JSX태그의 양을 줄일 수 있는 React의 문법

`생성하기`
1. 원하는 HTML코드를 함수의 return문 안에 작성한다.
2. 함수 네이밍은 자유
3. 원하는 곳에 생성한 함수를 '태그'처럼 사용한다.


`예시`
```js

function App() {

  return (
      <Custom></Custom>
      //또는 <Custom/>
  );

  function Custom(){
    return (
      <div className='modal'>
        <h2>제목</h2>
        <p>날짜</p>
        <p>상세내용</p>
      </div>
    );
  }
}
```


`주의점`

    이름의 첫문자는 대문자를 사용한다.
    return문 내부의 최상위 HTML태그는 하나만 존재해야 한다.


`Component `

반복적으로 출현하는 HTML덩어리들
자주바뀌는 UI
다른 페이지

`단점`   
state를 사용한 데이터 바인딩이 복잡해짐
-> 상위 component에서 생성한 state를 쓰기 위해선 props문법을 이용해야함
