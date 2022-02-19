# React(JSX) 스타일 적용
    HTML 태그에 사용하는 <p style="-">의 형태는 사용할 수 없다.


주의할 점   
+ 모든 속성명은 camelCase 작명관습을 따른다.
+ Object 자료형으로 주어야 한다.
+ return문 내부의 최상위 태그는 하나만 존재해야한다.

<br><br>

`<태그 style={ {object 자료형} }`
```js

function App() {

  let text = 'Hello world!';

  return (
    <div className="App">
      <h4 style={ { color:'blue',fontSize:'30px'}}> {text} </h4>
    </div>
  );
}

```

style도 데이터 바인딩으로 적용할 수 있다.
```js

function App() {

  let text = 'Hello world!';
  let styles = { color:'blue',fontSize:'30px'};
  return (
    <div className="App">
      <h4 style={ styles }> {text} </h4>
    </div>
  );
}

```