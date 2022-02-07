# State?

+ 변수 대신 쓰는 데이터 저장공간
+ useState() 문법을 사용하여 생성

<br><br>

## State 사용하기
---
<br>

`import`
```js
import React, {useState} from 'react';
```

`useState`
```js
useState('안녕하세요');

// 위 구문 작성시 2개의 요소가 있는 배열이 생성된다.
// [a,b]
// a에는 괄호안에 작성한 '안녕하세요'가
// b에는 내용을 수정하기 위한 함수가 생성된다.

```


## 왜 State?
----
    웹이 앱처럼 동작하게 하기 위해서
    변수는 변경되어도 새로고침이 되어야 렌더링하고, 자동 재렌더링이 안됨
    state는 변경되면 HTML이 자동으로 재랜더링 된다.
    => HTML이 새로고침 없이도 내용이 변경됨 
    => 자주 바뀌거나 중요한 데이터는 꼭 state로 사용



## State값 변경하기
---
    let [a,b] = useState(1);
    위에서 useState의 값(a)를 변경하기 위해선 변경함수 b를 사용한다.
    b(변경할 값) 을 실행하면 기존값이 변경할 값으로 '대체'된다.

` 1을 100으로 변경하기`
```js
b(100)
```
`1을 '안녕'으로 변경하기`
```js
b('안녕')
```

`주의`
    
    배열의 형태로 useState를 선언했다면 list[0]의 값만 바꾸는 것은 불가능하다.
```js
let [title,changeTitle] = useState(['강남 맛집','사당 맛집','신림 맛집']);

changeTitle[0]('바뀐 맛집') // X
changeTitle(title[1] = '교대 맛집') // X

```  

    Array, Object 데이터 수정 방법
    일단 변경함수를 써야함
    state는 직접 건들지 않는다.
    -> state에 대해 deep copy를 진행, 값 수정
    변경함수(copy본)