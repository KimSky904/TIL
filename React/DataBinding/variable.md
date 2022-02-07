# Data Binding
    React는 데이터 바인딩이 매우 간편하다는 큰 강점을 가지고 있다.

## 데이터 바인딩 예시

<br>

`{ 변수명 }`

```js
function App() {

  let text = 'Hello world!';

  return (
    <div className="App">
      <h4> {text} </h4>
    </div>
  );
}

export default App;
```

`{ 함수() }`
```js
function App() {

  function func(){
      return 'Hello World!'
  } 

  return (
    <div className="App">
      <h4> {func()} </h4>
    </div>
  );
}

export default App;
```

` { import된 이미지 }`
```js
import logo from './logo.svg';

function App() {

  return (
    <div className="App">
      <img src={logo}/>
    </div>
  );
}

export default App;

```