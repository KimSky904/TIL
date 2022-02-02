# React 시작하기
    react를 사용하기 위해 vscode, nodejs를 설치해놓아야 한다.
    * nodejs는 최신 버전으로 준비


* nodsjs의 npm툴은 다른 라이브러리를 비교적 쉽게 설치할 수 있도록 지원한다.
* 이 npm툴의 기능을 이용해서 create-react-app라이브러리를 설치한다. 

<br><br>


# 개발환경 설정  
vscode의 terminal에서 
```
npx create-react-app '프로젝트명'
```
를 입력하여 react 개발에 필요한 기본 구성 파일들을 다운받는다.

설치된 하위 폴더의 App.js가 react 개발의 메인 페이지라고 할 수 있다.

<br><br>




# 파일구성
npx를 통해 기본구성 파일을 설치하면
다음과 같은 파일구조가 생성된다.   
<br>

![img](./img/create-file.png)

* node-modules : 모듈 설치파일
* public : static설정된 모든 파일
* src : 모든 소스코드

<br><br>

# React 실행
vscode의 terminal에서 다음을 입력한다.

    npm start  
만약 브라우저가 자동으로 뜨지 않았을 경우
    
    http://localhost:3000

에 접속한다.  
실행결과는 다음과 같다.  

![img](./img/start.png)

<br><br>
