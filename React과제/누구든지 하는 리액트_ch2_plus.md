> 🎧 20.03.06 <br>
> 🧩 인프런 - 누구든지 하는 리액트: 초심자를 위한 react 핵심 강좌 ([https://www.inflearn.com/course/react-velopert](https://www.inflearn.com/course/react-velopert))

# Ch 2 plus. 컴포넌트 파일 파헤치기

<br>

## hello-project 프로젝트를 열고 구성 이해하기

리액트를 사용하며 웹 어플리케이션에서 사용하는 유저 인터페이스를 재사용 가능한 컴포넌트로 분리해 작성. 프로젝트의 유지보수성을 우수하게 함.<br>
이 컴포넌트에 해당하는 코드가 src 폴더 속 **App.js**<br>
```
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}

export default App;
```

<br>
하나씩 나눠 코드를 이해해보기
<br>

```
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';
```
import : 무엇을 불러오기<br>
우리가 webpack을 사용하기에 가능한 작업으로, 나중에 프로젝트를 빌드하게 됐을 때 파일 확장자에 따라 다른 작업을 하게 됨<br>

```
class App extends Component {
  ...
}
```
컴포넌트를 만드는 방법 2가지 : 클래스를 통해 / 함수를 통해 <br>
위는 클래스를 통해 컴포넌트를 만든 경우 <br>

```
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
```
return 내부에 html과 같이 생긴 코드는 JSX<br>
클래스형태로 만들어진 컴포넌트에는 render 함수가 반드시 존재해야 하며, 그 내부에서 JSX를 return 해줘야 함<br>
JSX가 무엇인지는 3챕터에서..<br>
```
export default App;
```
마지막으로 작성한 컴포넌트를 다른 곳에서 불러와 사용 가능하도록 내보내기 해줌<br>
이는 index.js 파일 속<br>
```
import App from './App';
```
를 통해 export한 App.js가 import를 통해 연결됐음을 볼 수 있음<br>
