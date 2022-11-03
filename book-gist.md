[https://western-warlock-494.notion.site/717ef2f973144ef28942d836217a9e37](https://www.notion.so/e44c4d3269ec4b828be8b69c95fecf96?p=717ef2f973144ef28942d836217a9e37&pm=c)

# 8월 1일 스터디

생성일: 2022년 8월 1일 오전 2:42

## npm start

- [ ]  Node.js(+npm)와 yarn 설치
- [ ]  Visual Studio Code(+확장 프로그램) 설치
- ESLInt
- Reactjs Code Snippents (charalampos karypidis)
- Prettier-Code formatter
- Korean Language Pack for Visual Studio Code
- [ ]  Git 설치
- [ ]  프로그램 생성

```jsx
# 프로젝트를 생성할 디렉토리로 이동하여 실시
$ yarn create react-app <프로젝트 이름>

# yarn을 사용하지 않을 경우
$ npm init react-app <프로젝트 이름>

# 프로젝트 디렉터리로 이동
$ cd <프로젝트 이름>
$ yarn start

# http://localhost:3000/ 으로 이동
```

- [ ]  src/index.js

```jsx
import logo from './logo.svg';
import './App.css';

function App() { {/* function 키워드로 App이라는 컴포넌트 생성 */}
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

> App이라는 [컴포넌트](http://wiki.hash.kr/index.php/%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8)를 만들어 주는 코드
프로젝트에서 컴포넌트를 렌더링(보여주기)하면 함수에서 반환하고 있는 내용 출력
HTML처럼 보이지만 JSX라고 부름
> 
- [ ]  JSX

> 자바스크립트의 확장 문법 (XML과 비슷하게 생김)
브라우저에서 실행되기 전에 일반 자바스크립트 형태로 변환 (번들링되는 과정에서 바벨을 사용하여)

장점
HTML을 작성하는 것과 비슷함 (친숙함)
= 태그 활용 가능
> 

코드 1

```jsx
function App() {
  return (
    <div>
      <h1>div 태그로 감싸져 있다.</h1>
      <h2>요소 여러개가 부모 요소 하나로 감싸져 있다.</h2>
    </div>
  )
}

export default App;
```

코드 2

```jsx
import { Fragment } from 'react';

function App() 
  return (
    <Fragment>
      <h1>div 태그로 감싸져 있다.</h1>
      <h2>요소 여러개가 부모 요소 하나로 감싸져 있다.</h2>
    </Fragment>
  )
}

export default App;
```

코드 3

```jsx
function App() {
  return (
    <>
      <h1>div 태그로 감싸져 있다.</h1>
      <h2>요소 여러개가 부모 요소 하나로 감싸져 있다.</h2>
    </>
  )
}

export default App;
```

- [ ]  if 문 대신 조건부 연산자 (= 삼항 연산자)

```jsx
function App() {
  const name = '리액트'; {/* 're액트' -> 리액트가 아닙니다. */}
  return (
    <>
      {name === '리액트' ? (
        <h1>리액트입니다.</h1>
      ) : (
        <h2>리액트가 아닙니다.</h2>
      )}
    </>
  )
}

export default App;

//-> 리액트입니다.
```

- [ ]  AND 연산자(&&)를 사용한 조건부 랜더링

```jsx
function App() {
  const name = 're액트';
	// return <div>{name === '리액트' ? <h1>리액트입니다.</h1> : null}</div>;
  return <>{name === '리액트' && <h1>리액트입니다.</h1>}</>
}

export default App;
```

- [ ]  undefined를 렌더링X

```jsx
import './App.css'

function App() {
  const name = undefined;
  return name;
}

export default App;

{/* -> 오류 (안남...?) */}
```

- [ ]  인라인 스타일링
background-color → backgroundColor로 작성

```jsx
function App() {
  const name = '리액트';
  const style = {
    backgroundColor: 'black', {/* background-color를 카멜 표기법으로 작성 */}
    color: 'aqua',
    fontSize: '48px', // font-size
    fontWeight: 'bold', // font-weight
    padding: 16 {/* 단위를 생략하면 px로 지정 */}
  };
  return <div style={style}>{name} </div>;
}

export default App;
```

```jsx
{/* style을 미리 선언 */}

function App() {
  const name = '리액트';
  return (
    <div
      style = {{
        backgroundColor: 'black', {/* background-color를 카멜 표기법으로 작성 */}
        color: 'aqua',
        fontSize: '48px', {/* font-size */}
        fontWeight: 'bold', {/* font-weight */}
        padding: 16 {/* 단위를 생략하면 px로 지정 */}
      }}
    >
      {name}
    </div>
  );
}
export default App;
```

- [ ]  class 대신 className

```jsx
import './App.css'

function App() {
  const name = '리액트';
  return <div className='react'>{name}</div>;
}

export default App;
```

```css
.react {
  background: aqua;
  color: black;
  font-size: 48px;
  font-weight: bold;
  padding: 16px;
}
```

- [ ]  닫아야 하는 태그
- [ ]  주석 처리
{/* */}
- [ ]  확장 프로그램 적용
ESLint: 코드 작성 시 에러 혹은 경고 메시지를 에디터에서 바로 확인
Prettier: 들여쓰기나 빠뜨리거나 틀린 기호들을 고쳐줌

```jsx
{/* 이상한 코드 */}

import "./App.css";

function App() {
  const name = "리액트";
  return (
    <div>
      <div className="react">{
        name
      }</div>
              <h1>들여쓰기가 이상한</h1>
          <h2>코드</h2>
              </div>
  )
}

export default App;
```

# 8월 8일 스터디

생성일: 2022년 8월 7일 오전 12:24

# 다음주까지 5,6,7장 해보기

- 결과물을 공유한다.
- 요일을 바꾸어서 진행한다.

## 3장. 컴포넌트

### 3.1 클래스형 컴포넌트

       85p

```jsx
# App.js - 함수 컴포넌트
import './App.css';

function App() {
	const name = '리액트';
	return <div className="react">{name}</div>;
}

export default App;
```

```jsx
# App.js - 클래스형 컴포넌트
import { Component } from 'react';

class App extends Component {
	render() {
		const name = 'react';
		return <div className="react">{name}</div>;
	}
}

export default App;
```

### 3.2 첫 컴포넌트 생성

- [ ]  src 디렉터리에 MyComponent.js 파일 생성
87p
- [ ]  코드 작성하기
88p

```jsx
# MyComponent.js - 함수 컴포넌트로 작성
const MyComponent = () => {
	return <div>나의 새롭고 멋진 컴포넌트</div>;
};

export default MyComponent;
```

.       91p 모듈 내보내기(export)

```jsx
# MyComponent.js - 맨 아래 코드
export default MyComponent;
```

      91p 모듈 불러오기(import)

```jsx
# App.js
import MyComponent from './MyComponent';

const App = () => {
	return <MyComponent />;
};

export default App;
```

<aside>
💡 두꺼운 글씨로 렌더링x

</aside>

### 3.3 props

- [ ]  jsx 내부에서 props 렌더링
92p
- [ ]  컴포넌트를 사용할 때 props 값 지정하기
92p

```jsx
# App.js
import MyComponent from './MyComponent';

const App = () => {
	return <MyComponent name="React" />;
};

export default App;
```

<aside>
💡 두꺼운 글씨로 렌더링x

</aside>

- [ ]  props 기본값 설정: defaultProps
93p

```jsx
# MyComponent.js
const MyComponent = props => {
	return <div> 안녕하세요. 제 이름은 {props.name}입니다.</div>;
};

MyComponent.defaultProps = {
	name: '기본 이름'
};

export default MyComponent;
```

<aside>
💡 두꺼운 글씨로 렌더링x

</aside>

- [ ]  태그 사이의 내용을 보여 주는 children
94p

```jsx
# App.js
import MyComponent from './MyComponent';

const App = () => {
	return <MyComponent>리액트</MyComponent>;
};

export default App;
```

```jsx
# MyComponent.js
const MyComponent = props => {
	return (
		<div>
			안녕하세요, 제 이름은 {props.name}입니다. <br />
			children 값은 {props.children}
			입니다.
		</div>
	);
};

MyComponent.defaultProps = {
	name: '기본 이름'
};

export default MyComponent;
```

- [ ]  비구조화 할당 문법을 통해 props 내부 값 추출하기
96p

```jsx
# MyComponent.js
const MyComponent = props => {
	const { name, children } = props;
	return (
		<div>
			안녕하세요, 제 이름은 {name}입니다. <br />
			children 값은 {children}
			입니다.
		</div>
	);
};

MyComponent.defaultProps = {
	name: '기본 이름'
};

export default MyComponent;
-> 객체에서 값을 추출하는 문법: 비구조화 할당
```

```jsx
# MyComponent.js
const MyComponent = ({ name, children }) => {
	return (
		<div>
			안녕하세요, 제 이름은 {name}입니다. <br />
			children 값은 {children}
			입니다.
		</div>
	);
};

MyComponent.defaultProps = {
	name: '기본 이름'
};

export default MyComponent;
-> 함수의 파라미터가 객체일 때 (= props 사용 시)
```

- [ ]  propTypes를 통한 props 검증
컴포넌트의 필수 props를 지정하거나 타입을 지정할 떄 propTypes 사용

```jsx
# MyComponent.js
import PropTypes from 'prop-types';

const MyComponent = ({ name, children }) => {
	return (
		<div>
			안녕하세요, 제 이름은 {name}입니다. <br />
			children 값은 {children}
			입니다.
		</div>
	);
};

MyComponent.defaultProps = {
	name: '기본 이름'
};

MyComponent.propTypes = {
	name: PropTypes.string
};

export default MyComponent;
```

```jsx
# App.js
import MyComponent from './MyComponent';

const App = () => {
	return <MyComponent name={3}>리액트</MyComponent>;
};

export default App;
```

<aside>
💡 콘솔에 경고 메시지 출력되는 것이 정상!

</aside>

```jsx
# App.js - 콘솔 경고 반영하여 수정하기
import MyComponent from './MyComponent';

const App = () => {
	return <MyComponent name="React">리액트</MyComponent>;
};

export default App;
```

       100p isRequired를 사용하여 필수 propTypes 설정

                propTypes를 지정하지 않았을 때 경고 메시지를 띄워 주는 작업

                ⇒ propTypes를 지정할 때 뒤에 isRequired를 붙이면 됨.

```jsx
# MyComponent.js
import PropTypes from 'prop-types';

const MyComponent = ({ name, children }) => {
	return (
		<div>
			안녕하세요, 제 이름은 {name}입니다. <br />
			children 값은 {children}
			입니다.
			<br />
			제가 좋아하는 숫자는 {favoriteNumber}입니다.
		</div>
	);
};

MyComponent.defaultProps = {
	name: '기본 이름'
};

MyComponent.propTypes = {
	name: PropTypes.string,
	favoriteNumber: PropTypes.number.isRequired
};

export default MyComponent;
```

<aside>
💡 콘솔에 경고 메시지 출력되는 것이 정상!

</aside>

```jsx
# App.js - 콘솔 경고 반영하여 수정하기
import MyComponent from './MyComponent';

const App = () => {
	return (
		<MyComponent name="React" favoriteNumber={1}>
			리액트
		</MyComponent>
	);
};

export default App;
```

       101p 더 많은 PropTypes 종류

- [ ]  클래스형 컴포넌트에서 props 사용하기
102p 클래스형 컴포넌트로 변환

```jsx
# MyComponents.js
import { Component } from "react";
import PropTypes from "prop-types";

const MyComponent = {
  render() {
    const { name, favoriteNumber, children } = this.props; // 비구조화 할당
    return (
      <div>
        안녕하세요, 제 이름은 {name}입니다. <br />
        children 값은 {children}
        입니다.
        <br />
        제가 좋아하는 숫자는 {favoriteNumber}입니다.
      </div>
    );
  },
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

MyComponent.propTypes = {
  name: PropTypes.string,
  favoriteNumber: PropTypes.number.isRequired,
};

export default MyComponent;
```

       103p defaultProps와 propTypes 설정 시 class 내부에서 지정

```jsx
# MyComponents.js
import { Component } from "react";
import PropTypes from "prop-types";

class MyComponent extends Component {
  static defaultProps = {
    name: "기본 이름",
  };
  static propTypes = {
    name: PropTypes.string,
    favoriteNumber: PropTypes.number.isRequired,
  };
  render() {
    const { name, favoriteNumber, children } = this.props; // 비구조화 할당
    return (
      <div>
        안녕하세요, 제 이름은 {name}입니다. <br />
        children 값은 {children}
        입니다.
        <br />
        제가 좋아하는 숫자는 {favoriteNumber}입니다.
      </div>
    );
  }
}

export default MyComponent;
```

- [ ]  클래스형 컴포넌트의 state
컴포넌트 내부에서 바뀔 수 있는 값을 의미
props는 바꾸려면 부모 컴포넌트에서 바꾸어야 함.
104p

```jsx
# Counter.js
import { Component } from "react";

class Counter extends Component {
	// 컴포넌트에 state를 설정할 때 constructor 메서드 작성 필요: 컴포넌트의 생성자 메서드
  constructor(props) {
    super(props);
    // state의 초깃값 설정하기
    this.state = {
      number: 0,
    };
  }
  render() {
    const { number } = this.state; // state를 조회할 때는 this.state로 조회합니다.
    return (
      <div>
        <h1>{number}</h1>
        <button
          // onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정합니다.
          onClick={() => {
            // this.setState를 사용하여 state에 새로운 값을 넣을 수 있습니다.
            this.setState({ number: number + 1 });
          }}
        >
          +1
        </button>
      </div>
    );
  }
}

export default Counter;
```

       106p

```jsx
# App.js
import Counter from "./Counter";

const App = () => {
  return <Counter />;
};

export default App;
```

       107p state 객체 안에 여러 값이 있을 때

```jsx
# Counter.js
import { Component } from "react";

class Counter extends Component {
  // 컴포넌트에 state를 설정할 때 constructor 메서드 작성 필요: 컴포넌트의 생성자 메서드
  constructor(props) {
    super(props); // 반드시 호출 필요 Component 클래스가 지닌 생성자 함수 호출
    // state의 초깃값 설정하기
    this.state = {
      number: 0,
      fixedNumber: 0,
    };
  }
  render() {
    const { number, fixedNumber } = this.state; // state를 조회할 때는 this.state로 조회합니다.
    return (
      <div>
        <h1>{number}</h1>
        <h2>바뀌지 않는 값: {fixedNumber}</h2>
        <button
          // onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정합니다.
          onClick={() => {
            // this.setState를 사용하여 state에 새로운 값을 넣을 수 있습니다.
            this.setState({ number: number + 1 });
          }}
        >
          +1
        </button>
      </div>
    );
  }
}

export default Counter;
```

       108p state를 constructor에서 꺼내기

```jsx
# Counter.js
import { Component } from "react";

class Counter extends Component {
  state = {
    number: 0,
    fixedNumber: 0,
  };
  render() {
    const { number, fixedNumber } = this.state; // state를 조회할 때는 this.state로 조회합니다.
    return (
      <div>
        <h1>{number}</h1>
        <h2>바뀌지 않는 값: {fixedNumber}</h2>
        <button
          // onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정합니다.
          onClick={() => {
            // this.setState를 사용하여 state에 새로운 값을 넣을 수 있습니다.
            this.setState({ number: number + 1 });
          }}
        >
          +1
        </button>
      </div>
    );
  }
}

export default Counter;
```

       109p this.setState에 객체 대신 함수 인자 전달하기

```jsx
# Counter.js - button onClick
onClick={() => {
  // this.setState를 사용하여 state에 새로운 값을 넣을 수 있습니다.
  this.setState({ number: number + 1 });
  this.setState({ number: this.state.number + 1 });
}}
-> 두 번 작성했지만 1씩 더해진다.

# Counter.js - button
<button
  // onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정합니다.
  onClick={() => {
    this.setState(prevState => {
        return {
            number: prevState.number + 1
        };
    });
    // 위 코드와 아래 코드는 완전히 똑같은 기능을 합니다.
    // 아래 코드는 함수에서 바로 객체를 반환한다는 의미입니다.
    this.setState(prevState => ({
        number: prevState.number + 1
    }));
  }}
>
	+1
</button>
-> 2씩 올라간다.
```

       110p this.setState가 끝난 후 특정 작업 실행하기

```jsx
# Counter.js - button
<button
  // onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정합니다.
  onClick={() => {
    this.setState(
      {
        number: number + 1,
      },
      () => {
        console.log("방금 setState가 호출되었습니다.");
        console.log(this.state);
      }
    );
  }}
>
  +1
</button>
-> 콘솔 내용 출력 "방금 setState가 호출되었습니다. {number: 1, fixedNumber: 0}"
```

- [ ]  함수 컴포넌트에서 useState 사용하기
112p 배열 비구조화 할당

```jsx
# Say.js
import { useState } from "react";

const Say = () => {
  const [message, setMessage] = useState("");
  const onClickEnter = () => setMessage("안녕하세요!");
  const onClickLeave = () => setMessage("안녕히 가세요!");

  return (
    <div>
      <button onClick={onClickEnter}>입장</button>
      <button onClick={onClickLeave}>퇴장</button>
      <h1>{message}</h1>
    </div>
  );
};

export default Say;

# App.js
import Say from "./Say";

const App = () => {
  return <Say />;
};

export default App;
```

       114p 한 컴포넌트에서 useState 여러 번 사용하기

```jsx
# Say.js
import { useState } from "react";

const Say = () => {
  const [message, setMessage] = useState("");
  const onClickEnter = () => setMessage("안녕하세요!");
  const onClickLeave = () => setMessage("안녕히 가세요!");

  const [color, setColor] = useState("black");

  return (
    <div>
      <button onClick={onClickEnter}>입장</button>
      <button onClick={onClickLeave}>퇴장</button>
      <h1 style={{ color }}>{message}</h1>
      <button style={{ color: "red" }} onClick={() => setColor("red")}>
        빨간색
      </button>
      <button style={{ color: "green" }} onClick={() => setColor("green")}>
        초록색
      </button>
      <button style={{ color: "blue" }} onClick={() => setColor("blue")}>
        파란색
      </button>
    </div>
  );
};

export default Say;
```

## 4장. 이벤트 핸들리

```html
# test.html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>JS Bin</title>
  </head>
  <body>
    <button onclick="alert('executed')">Click Me</button>
  </body>
</html>
```

### 4.1 리액트의 이벤트 시스템

- [ ]  이벤트를 사용할 때 주의 사항
1. 이벤트 이름은 카멜 표기법(onclick→onClick)으로 작성합니다.
2. 이벤트에 실행할 자바스크립트 코드를 전달하는 것이 아니라, 함수 형태의 값을 전달합니다.
3. DOM 요소(div, button, input, form, span)에만 이벤트를 설정할 수 있습니다.
- [ ]  이벤트 종류
Clickboard
Composition
Keyboard
Focus
Form
Mouse
Selection
Touch
UI
Wheel
media
Image
Animation
Transition

### 4.2 예제로 이벤트 핸들링 익히기

- [ ]  컴포넌트 생성 및 불러오기
124p 컴포넌트 생성

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
      </div>
    );
  }
}

export default EventPractice;
```

       App.js에서 EventPractice 렌더링

```jsx
# App.js
import EventPractice from "./EventPractice";

const App = () => {
  return <EventPractice />;
};

export default App;
```

- [ ]  onChange 이벤트 핸들링하기
125p onChange 이벤트 설정

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          onChange={(e) => {
            console.log(e);
          }}
        />
      </div>
    );
  }
}

export default EventPractice;
```

```jsx
# EventPractice.js의 onChange 코드 수정
onChange={(e) => {
  console.log(e.target.value);
}}
```

       128p state에 input 값 담기

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  state = {
    message: "",
  };

  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          value={this.state.message}
          onChange={(e) => {
            this.setState({
              message: e.target.value,
            });
          }}
        />
      </div>
    );
  }
}

export default EventPractice;
```

       129p 버튼을 누를 때 comment 값을 공백으로 설정

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  state = {
    message: "",
  };

  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          value={this.state.message}
          onChange={(e) => {
            this.setState({
              message: e.target.value,
            });
          }}
        />
        <button
          onClick={() => {
            alert(this.state.message);
            this.setState({
              message: "",
            });
          }}
        >
          확인
        </button>
      </div>
    );
  }
}

export default EventPractice;
-> alert으로 인해 팝업창에 메시지 박스가 뜬다.
```

- [ ]  임의 메서드 만들기
130p 기본 방식

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  state = {
    message: "",
  };

  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
    this.handleClick = this.handleClick.bind(this);
  }

  handleChange(e) {
    this.setState({
      message: e.target.value,
    });
  }

  handleClick() {
    alert(this.state.message);
    this.setState({
      message: "",
    });
  }

  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          value={this.state.message}
          onChange={this.handleChange}
        />
        <button onClick={this.handleClick}>확인</button>
      </div>
    );
  }
}

export default EventPractice;
```

       132p Property Initializer Syntax를 사용한 메서드 작성

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  state = {
    message: "",
  };

  handleChange = (e) => {
    this.setState({
      message: e.target.value,
    });
  };

  handleClick = () => {
    alert(this.state.message);
    this.setState({
      message: "",
    });
  };

  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          value={this.state.message}
          onChange={this.handleChange}
        />
        <button onClick={this.handleClick}>확인</button>
      </div>
    );
  }
}

export default EventPractice;
```

- [ ]  input 여러 개 다루기
134p

```jsx
# EventPracitce.js
import { Component } from "react";

class EventPractice extends Component {
  state = {
    username: "",
    message: "",
  };

	// 핵심!! 객체 안에 key를 []로 감싸면 안에 넣은 레퍼런스가 가리키는 실제 값이 key 값으로 사용됨
  handleChange = (e) => {
    this.setState({
      [e.target.name]: e.target.value,
    });
  };

  handleClick = () => {
    alert(this.state.username + ": " + this.state.message);
    this.setState({
      username: "",
      message: "",
    });
  };

  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="username"
          placeholder="사용자명"
          value={this.state.username}
          onChange={this.handleChange}
        />
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          value={this.state.message}
          onChange={this.handleChange}
        />
        <button onClick={this.handleClick}>확인</button>
      </div>
    );
  }
}

export default EventPractice;
```

- [ ]  onKeyPress 이벤트 핸들링
136p

```jsx
# EventPractice.js
import { Component } from "react";

class EventPractice extends Component {
  state = {
    username: "",
    message: "",
  };

  handleChange = (e) => {
    this.setState({
      [e.target.name]: e.target.value,
    });
  };

  handleClick = () => {
    alert(this.state.username + ": " + this.state.message);
    this.setState({
      username: "",
      message: "",
    });
  };

  handleKeyPress = (e) => {
    if (e.key === "Enter") {
      this.handleClick();
    }
  };

  render() {
    return (
      <div>
        <h1>이벤트 연습</h1>
        <input
          type="text"
          name="username"
          placeholder="사용자명"
          value={this.state.username}
          onChange={this.handleChange}
        />
        <input
          type="text"
          name="message"
          placeholder="아무거나 입력해 보세요"
          value={this.state.message}
          onChange={this.handleChange}
          onKeyPress={this.handleKeyPress}
        />
        <button onClick={this.handleClick}>확인</button>
      </div>
    );
  }
}

export default EventPractice;
```

### 4.3 함수 컴포넌트로 구현해 보기

       138p

```jsx
# EventPractice.js
import { useState } from "react";

const EventPractice = () => {
  const [username, setUsername] = useState("");
  const [message, setMessage] = useState("");
  const onChangeUsername = (e) => setUsername(e.target.value);
  const onChangeMessage = (e) => setMessage(e.target.value);
  const onClick = () => {
    alert(username + ": " + message);
    setUsername("");
    setMessage("");
  };
  const onKeyPress = (e) => {
    if (e.key === "Enter") {
      onClick();
    }
  };
  return (
    <div>
      <h1>이벤트 연습</h1>
      <input
        type="text"
        name="username"
        placeholder="사용자명"
        value={username}
        onChange={onChangeUsername}
      />
      <input
        type="text"
        name="message"
        placeholder="아무거나 입력해 보세요"
        value={message}
        onChange={onChangeMessage}
        onKeyPress={onKeyPress}
      />
      <button onClick={onClick}>확인</button>
    </div>
  );
};

export default EventPractice;
```

       139p

```jsx
# EventPractice.js
import { useState } from "react";

const EventPractice = () => {
  const [form, setForm] = useState({
    username: "",
    message: "",
  });
  const { username, message } = form;
  const onChange = (e) => {
    const nextForm = {
      ...form, // 기존의 form 내용을 이 자리에 복사한 뒤
      [e.target.name]: e.target.value, // 원하는 값을 덮어 씌우기
    };
    setForm(nextForm);
  };
  const onClick = () => {
    alert(username + ": " + message);
    setForm({
      username: "",
      message: "",
    });
  };
  const onKeyPress = (e) => {
    if (e.key === "Enter") {
      onClick();
    }
  };
  return (
    <div>
      <h1>이벤트 연습</h1>
      <input
        type="text"
        name="username"
        placeholder="사용자명"
        value={username}
        onChange={onChange}
      />
      <input
        type="text"
        name="message"
        placeholder="아무거나 입력해 보세요"
        value={message}
        onChange={onChange}
        onKeyPress={onKeyPress}
      />
      <button onClick={onClick}>확인</button>
    </div>
  );
};

export default EventPractice;
```

# 8월 15일 스터디

생성일: 2022년 8월 8일 오후 3:14

## 5장 ref: DOM에 이름 달기

HTML에서 DOM 요소에 이름을 달 때는 id를 사용

```html
<div id="my-element"></div>
```

id를 달면 CSS 또는 자바스크립트에서 정의한 id의 스타일을 적용

```html
# public/index.html - id가 root인 div 요소 부분
...
<body>
	<div id="root"></div>
</body>
...
```

```jsx
# src/index.js - id가 root인 요소에 리액트 컴포넌트를 렌더링하라는 코드 부분
...
const root = ReactDOM.createRoot(document.getElementById('root'));
```

### 5.1 ref는 어떤 상황에서 사용해야 할까?

      143p

      - DOM을 꼭 직접적으로 건드려야 할 때 ([https://jsbin.com/qawucezuci/edit](https://jsbin.com/qawucezuci/edit))

```html
# 일반 HTML 예제 코드
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Example</title>
  <style>
    .success {
      background-color: lightgreen;
    }

    .failure {
      background-color: lightcoral;
    }
  </style>
  <script>
    function validate() {
      var input = document.getElementById('password');
      input.className='';
      if(input.value==='0000') {
        input.className='success';
      } else {
        input.className='failure';
      }
    }
  </script>
</head>
<body>
  <input type="password" id="password"></input>
  <button onclick="validate()">Validate</button>
</body>
</html>
-> 리액트에서는 DOM에 직접 작업하지 않아도(id를 가진 input클래스를 설정하지 않아도) state로 구현할 수 있다.
```

> **<리액트 컴포넌트에서 state 사용 (실습 진행 흐름)>**
1. ValidationSample 컴포넌트 만들기
2. input에 ref 달기
3. 버튼을 누를 때마다 input에 포커스 주기
> 
- [ ]  예제 컴포넌트 생성
145p

```css
# src/ValidationSample.css
.success {
    background-color: lightgreen;
}

.failure {
    background-color: lightcoral;
}
```

```jsx
# src/ValidationSample.js
import { Component } from 'react';
import './ValidationSample.css'

class ValidationSample extends Component {
    state = {
        password: '',
        clicked: false,
        validated: false
    }

    handleChange = (e) => {
        this.setState({
            password: e.target.value
        });
    }

    handleButtonClick = () => {
        this.setState({
            clicked: true,
            validated: this.state.password === '0000'
        })
    }

    render() {
        return (
            <div>
                <input
                    type="password"
                    value={this.state.password}
                    // onChange 이벤트가 발생하면 handleChange를 호출하여 state의 password 값을 업데이트
                    onChange={this.handleChange}
                    className={this.state.clicked ? (this.state.validated ? 'success' : 'failure') : ''}
                />
                {/* onClick 이벤트가 발생하면 handleButtonClick을 호출하여 clicked 값을 참으로 설정, validated 값을 검증 결과로 설정 */}
                <button onClick={this.handleButtonClick}>검증하기</button>
            </div>
        );
    }
}

export default ValidationSample;
```

- [ ]  App 컴포넌트에서 예제 컴포넌트 렌더링
146p

```jsx
# App.js
import { Component } from "react";
import ValidationSample from "./ValidationSample";

class App extends Component {
  render() {
    return (
      <div>
        <ValidationSample />
      </div>
    );
  }
}

export default App;
```

- [ ]  DOM을 꼭 사용해야 하는 상황 (= state만으로 해결할 수 없는 기능)
- 특정 input에 포커스 주기
- 스크롤 박스 조작
- Canvas 요소에 그림 그리기 등

### 5.2 ref 사용 (DOM에 직접적으로 접근)

- [ ]  콜백 함수를 통한 ref 설정
147p

```jsx
# 콜백 함수 사용 예시
-> ref라는 콜백 함수를 props로 전달
-> 콜백 함수는 ref 값을 파라미터로 전달 받음.
-> 함수 내부에서 파라미터로 받은 ref를 컴포넌트의 멤버 변수로 설정
<input ref={(ref) => {this.input=ref}} />
-> this.input: input 요소의 DOM
```

- [ ]  createRef를 통한 ref 설정
148p

```jsx
# createRef 사용 예시
import { Component } from 'react';

class RefSample extends Component {
	input = React.createRef();

	handleFocus = () => {
		this.input.current.focus();
	}

	render() {
		return (
			<div>
				<input ref={this.input} />
			</div>
		);
	}
}

export default RefSample;
```

- [ ]  적용
149p
150p input에 ref 달기

```jsx
# ValidationSample.js의 input 요소
...
		<input
			ref={(ref) => this.input=ref}
			...
		/>
```

       150p 버튼 onClick 이벤트 코드 수정

```jsx
# ValidationSample.js의 handleButtonClick 메서드
handleButtonClick = () => {
  this.setState({
    clicked: true,
    validated: this.state.password === "0000",
  });
  this.input.focus();
};
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2015%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20ae381ce63cd745dc9789093748e89380/1.mp4)

### 5.3 컴포넌트에 ref 달기

- [ ]  사용법
1. ScrollBox 컴포넌트 만들기
2. 컴포넌트에 ref 달기
3. ref를 이용하여 컴포넌트 내부 메서드 호출하기
- [ ]  컴포넌트 초기 설정
152p

```jsx
# ScrollBox.js
import { Component } from "react";

class ScrollBox extends Component {
  render() {
    const style = {
      border: "1px solid black",
      height: "300px",
      width: "300px",
      overflow: "auto",
      position: "relative",
    };

    const innerStyle = {
      width: "100%",
      height: "650px",
      background: "linear-gradient(white, black)",
    };
    return (
      <div
        style={style}
        ref={(ref) => {
          this.box = ref;
        }}
      >
        <div style={innerStyle} />
      </div>
    );
  }
}

export default ScrollBox;
```

```jsx
# App.js
import { Component } from "react";
import ScrollBox from "./ScrollBox";

class App extends Component {
  render() {
    return (
      <div>
        <ScrollBox />
      </div>
    );
  }
}

export default App;
```

- [ ]  컴포넌트에 메서드 생성
154p
- scrollTop: 세로 스크롤바 위치 (0~350)
- scrollHeight: 스크롤이 있는 박스 안의 div 높이 (650)
- clientHeight: 스크롤이 있는 박스의 높이 (300)

```jsx
# ScrollBox.js
...
class ScrollBox extends Component {
  scrollToBottom = () => {
      const { scrollHeight, clientHeight } = this.box;
      /* 앞 코드에서 비구조화 할당 문법을 사용했습니다.
         다음 코드와 같은 의미입니다.
         const scrollHeight = this.box.scrollHeight;
         const clientHeight = this.box.clientHeight;
      */
     this.box.scrollTop = scrollHeight - clientHeight;
  }
...
```

- [ ]  컴포넌트에 ref 달고 내부 메서드 사용
155p

```jsx
# App.js
import { Component } from "react";
import ScrollBox from "./ScrollBox";

class App extends Component {
  render() {
    return (
      <div>
        <ScrollBox ref={(ref) => (this.ScrollBox = ref)} />
        <button onClick={() => this.ScrollBox.scrollToBottom()}>
          맨 밑으로
        </button>
      </div>
    );
  }
}

export default App;
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2015%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20ae381ce63cd745dc9789093748e89380/1%201.mp4)

## 6장 컴포넌트 반복

```jsx
# src/IterationSample.js
const IterationSample = () => {
    return (
        <ul>
            <li>눈사람</li>
            <li>얼음</li>
            <li>눈</li>
            <li>바람</li>
        </ul>
    );
};

export default IterationSample;
```

### 6.1 자바스크립트 배열의 map() 함수

- [ ]  문법
159p
arr.map(callback, [thisArg])
이 함수의 파라미터
- callback: 새로운 배열의 요소를 생성하는 함수로 파라미터는 다음 세 가지
   - currentValue: 현재 처리하고 있는 요소
   - index: 현재 처리하고 있는 요소의 index 값
   - array: 현재 처리하고 있는 원본 배열
- thisArg(선택 항목): callback 함수 내부에서 사용할 this 레퍼런스
- [ ]  예제
159p

> # 콘솔에 입력
var numbers = [1, 2, 3, 4, 5];

var processed = numbers.map(function(num){
      return num * num;
});

console.log(processed);
→ [1, 4, 9, 16, 25]
> 

```jsx
# 위의 코드 변경
const numbers = [1, 2, 3, 4, 5];
const result = numbers.map(num => num * num);
console.log(result);
```

### 6.2 데이터 배열을 컴포넌트 배열로 변환하기

- [ ]  컴포넌트 수정하기
160p

```jsx
# IterationSample.js
const IterationSample = () => {
  const names = ["눈사람", "얼음", "눈", "바람"];
  const nameList = names.map((name) => <li>{name}</li>);
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```

- [ ]  App 컴포넌트에서 예제 컴포넌트 렌더링
161p

```jsx
# App.js
import { Component } from "react";
import IterationSample from "./IterationSample";

class App extends Component {
  render() {
    return <IterationSample />;
  }
}

export default App;
```

                                       → “key” prop이 없다는 경고 메시지

### 6.3 key

- [ ]  key 설정
162p
데이터가 가진 고윳값을 key 값으로 설정

> const articleList = articles.map(article ⇒ (
          <Article
                    title={article.title}
                    writer={article.writer}
                    key={article.id}
          />
));
> 

       163p

```jsx
# IterationSample.js - const nameList 부분
const nameList = names.map((name, index) => <li key={index}>{name}</li>);
-> 경고 메시지 사라짐.
```

### 6.4 응용

    164p

> **<유동적인 데이터 렌더링>**
1. 초기 상태 설정
2. 데이터 추가 기능 구현
3. 데이터 제거 기능 구현
> 
- [ ]  초기 상태 설정하기
164p

```jsx
# IterationSample.js
import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); // 새로운 항목을 추가할 때 사용할 id

  const namesList = names.map((name) => <li key={name.id}>{name.text}</li>);
  return <ul>{namesList}</ul>;
};

export default IterationSample;
-> 이전과 동일
```

**→ 이렇게 터미널에 경고가 뜨는 것이 정상인가?**

- [ ]  데이터 추가 기능 구현
165p

```jsx
# IterationSample.js
import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); // 새로운 항목을 추가할 때 사용할 id

  const onChange = (e) => setInputText(e.target.value);

  const namesList = names.map((name) => <li key={name.id}>{name.text}</li>);
  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button>추가</button>
      <ul>{namesList}</ul>
    </>
  );
};

export default IterationSample;
```

→ 입력은 받으나 업데이트는 되지 않음

```jsx
# IterationSample.js
import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); // 새로운 항목을 추가할 때 사용할 id

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId, // nextId 값을 id로 설정
      text: inputText,
    });
    setNextId(nextId + 1); // nextId 값에 1을 더해 준다.
    setNames(nextNames); // names 값에 업데이트한다.
    setInputText(""); // inputText를 비운다.
  };

  const namesList = names.map((name) => <li key={name.id}>{name.text}</li>);
  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button onClick={onClick}>추가</button>
      <ul>{namesList}</ul>
    </>
  );
};

export default IterationSample;
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2015%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20ae381ce63cd745dc9789093748e89380/1%202.mp4)

- [ ]  데이터 제거 기능 구현
167p

> const numbers = [1, 2, 3, 4, 5, 6];
const biggerThanThree = numbers.filter(number ⇒ number > 3);
// 결과: [4, 5, 6]
> 

> const numbers = [1, 2, 3, 4, 5, 6];
const withoutThree = numbers.filter(number ⇒ number !== 3);
// 결과: [1, 2, 4, 5, 6]
> 

```jsx
# IterationSample.js
import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); // 새로운 항목을 추가할 때 사용할 id

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId, // nextId 값을 id로 설정
      text: inputText,
    });
    setNextId(nextId + 1); // nextId 값에 1을 더해 준다.
    setNames(nextNames); // names 값에 업데이트한다.
    setInputText(""); // inputText를 비운다.
  };

  const onRemove = (id) => {
    const nextNames = names.filter((name) => name.id !== id);
    setNames(nextNames);
  };

  const namesList = names.map((name) => (
    <li key={name.id} onDoubleClick={() => onRemove(name.id)}>
      {name.text}
    </li>
  ));

  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button onClick={onClick}>추가</button>
      <ul>{namesList}</ul>
    </>
  );
};

export default IterationSample;
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2015%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20ae381ce63cd745dc9789093748e89380/1%203.mp4)

## 7장 컴포넌트의 라이프사이클 메서드

### 7.1 라이프사이클 메서드의 이해

- **라이프사이클 메서드의 종류 (총 9가지)**
    
    Will 접두사가 붙은 메서드는 어떤 작업을 작동하기 전에 실행되는 메서드
    
    Did 접두사가 붙은 메서드는 어떤 작업을 작동한 후에 실행되는 메서드
    
- **라이프사이클 (총 3가지)**
    
    마운트
    
    업데이트
    
    언마운트
    
    [라이프사이클 설명](https://www.notion.so/3ae816af055d4847b853bf2d2f1d3d39)
    

### 7.2 라이프사이클 메서드 살펴보기

- render() 함수
    
    175p
    render() {…} : 컴포넌트 모양새를 정의
    이 메서드 안에서 this.props와 this.state에 접근할 수 있으며, 리액트 요소를 반환
    ! 이벤트 설정이 아닌 곳에서 setState를 사용하면 안돼 !
    
- constructor 메서드
    
    176p
    constructor(props) {…} : 컴포넌트의 생성자 메서드로 컴포넌트를 만들 때 처음으로 실행. 초기 state를 정할 수 있음
    
- getDerivedStateFromProps 메서드
    
    176p
    props로 받아 온 값을 state에 동기화시키는 용도로 사용. 컴포넌트가 마운트될 때와 업데이트될 때 호출
    
    > static getDerivedStateFromProps(nextProps, prevState) {
          if(nextProps.value !== prevState.value) { //조건에 따라 특정 값 동기화
                return { value: nextProps.value };
          }
          return null; // state를 변경할 필요가 없다면 null을 반환
    }
    > 
- componentDidMount 메서드
    
    176p
    componentDidMount() {…}
    컴포넌트를 만들고, 첫 렌더링을 마친 후 실행. 다른 자바스크립트 라이브러리 또는 프레임워크의 함수를 호출하거나 이벤트 등록, setTimeout, setInterval, 네트워크 요청 같은 비동기 작업 처리 가능
    
- shouldComponentUpdate 메서드
    
    176p
    shouldComponentUpdate(nextProps, nextState) {…}
    props 또는 state를 변경했을 때, 리렌더링을 시작할지 여부를 지정하는 메서드. true 혹은 false 값을 반환
    
- getSnapshotBeforeUpdate 메서드
    
    177p
    render에서 만들어진 결과물이 브라우저에 실제로 반영되기 직전에 호출. 반환하는 값은 componentDidUpdate에서 세 번째 파라미터인 snapshot 값으로 전달받을 수 있음. 주로 업데이트 직전의 값을 참조할 일에 사용
    
    > getSnapshotBeforeUpdate(prevProps, prevState) {
          if(prevState.array !== this.state.array) {
                const { scrollTop, scrollHeight } = this.list
                return { scrollTop, scrollHeight };
          }
    }
    > 
- componentDidUpdate 메서드
    
    177p
    componentDidUpdate(prevProps, prevState, snapShot) {…}
    리렌더링을 완료한 후 실행. DOM 관련 처리 가능. prevProps 또는 prevState를 사용하여 컴포넌트가 가졌던 데이터에 접근 가능. getSnapshotBeforeUpdate에서 반환한 값이 있다면 snapshot 값을 전달 받음.
    
- componentWillUnmount 메서드
    
    178p
    componentWillUnmount() {…}
    컴포넌트를 DOM에서 제거할 때 실행. componentDidMount에서 등록한 이벤트, 타이머, 직접 생성한 DOM이 있다면 제거
    
- componentDidCatch 메서드
    
    178p
    컴포넌트 렌더링 도중에 에러가 발생했을 때 애플리케이션이 먹통이 되지 않고 오류 UI를 보여줌
    
    > componentDidCatch(error, info) {
          this.setState({
                error: true
          });
          console.log({ error, info });
    }
    > 

### 7.3 라이프사이클 메서드 사용하기

> **<라이프사이클 메서드 사용>**
1. LifeCycleSample 컴포넌트 만들기
2. App에 렌더링하기
3. 버튼 누르고 콘솔 창 관찰하기
> 
- [ ]  예제 컴포넌트 생성
179p

```jsx
# LifeCycleSample.js
import { Component } from "react";

class LifeCycleSample extends Component {
  state = {
    number: 0,
    color: null,
  };

  myRef = null; // ref를 설정할 부분

  constructor(props) {
    super(props);
    console.log("constructor");
  }

  static getDerivedStateFromProps(nextProps, prevState) {
    console.log("getDerivedStateFromProps");
    if (nextProps.color !== prevState.color) {
      return { color: nextProps.color };
    }
    return null;
  }

  componentDidMount() {
    console.log("componentDidMount");
  }

  shouldComponentUpdate(nextProps, nextState) {
    console.log("shouldComponentUpdate", nextProps, nextState);
    // 숫자의 마지막 자리가 4면 리렌더링하지 않습니다.
    return nextState.number % 10 !== 4;
  }

  componentWillUnmount() {
    console.log("componentWillUnmount");
  }

  handleClick = () => {
    this.setState({
      number: this.state.number + 1,
    });
  };

  getSnapshotBeforeUpdate(prevProps, prevState) {
    console.log("getSnapshotBeforeUpdate");
    if (prevProps.color !== this.props.color) {
      return this.myRef.style.color;
    }
    return null;
  }

  componentDidUpdate(prevProps, prevState, snapshot) {
    console.log("componentDidUpdate", prevProps, prevState);
    if (snapshot) {
      console.log("업데이트되기 직전 색상: ", snapshot);
    }
  }

  render() {
    console.log("render");

    const style = {
      color: this.props.color,
    };

    return (
      <div>
        <h1 style={style} ref={(ref) => (this.myRef = ref)}>
          {this.state.number}
        </h1>
        <p>color: {this.state.color}</p>
        <button onClick={this.handleClick}>더하기</button>
      </div>
    );
  }
}

export default LifeCycleSample;
```

- [ ]  App 컴포넌트에서 예제 컴포넌트 사용
181p

```jsx
# App.js
import { Component } from "react";
import LifeCycleSample from "./LifeCycleSample";

// 랜덤 색상을 생성
function getRandomColor() {
  return "#" + Math.floor(Math.random() * 16777215).toString(16);
}

class App extends Component {
  state = {
    color: "#000000",
  };

  handleClick = () => {
    this.setState({
      color: getRandomColor(),
    });
  };

  render() {
    return (
      <div>
        <button onClick={this.handleClick}>랜덤 색상</button>
        <LifeCycleSample color={this.state.color} />
      </div>
    );
  }
}

export default App;
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2015%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20ae381ce63cd745dc9789093748e89380/1%204.mp4)

- [ ]  에러 잡아내기
184p

```jsx
# LifeCycleSample.js의 render 함수 부분
render(
	return (
      <div>
        {this.props.missing.value}
...
```

<aside>
💡 브라우저가 뜨지는 않지만 오류는 발생

</aside>

       186p

```jsx
# ErrorBoundary.js
import { Component } from "react";

class ErrorBoundary extends Component {
  state = {
    error: false,
  };
  componentDidCatch(error, info) {
    this.setState({
      error: true,
    });
    console.log({ error, info });
  }
  render() {
    if (this.state.error) return <div>에러가 발생했습니다.</div>;
    return this.props.children;
  }
}

export default ErrorBoundary;
```

```jsx
# App.js
import { Component } from "react";
import LifeCycleSample from "./LifeCycleSample";
import ErrorBoundary from "./ErrorBoundary";

// 랜덤 색상을 생성
function getRandomColor() {
  return "#" + Math.floor(Math.random() * 16777215).toString(16);
}

class App extends Component {
  state = {
    color: "#000000",
  };

  handleClick = () => {
    this.setState({
      color: getRandomColor(),
    });
  };

  render() {
    return (
      <div>
        <button onClick={this.handleClick}>랜덤 색상</button>
        <ErrorBoundary>
          <LifeCycleSample color={this.state.color} />
        </ErrorBoundary>
      </div>
    );
  }
}

export default App;
```

# 8월 22일 스터디

생성일: 2022년 8월 15일 오후 3:05

# 8장 ~ 9.2장

## 8장 Hooks

새로운 프로젝트 생성

$ yarn create react-app hooks-tutorial

### 8.1 useState

      190p

```jsx
# Counter.js
import { useState } from 'react';

const Counter = () => {
    const [value, setValue] = useState(0);

    return (
        <div>
            <p>
                현재 카운터 값은 <b>{value}</b>입니다.
            </p>
            <button onClick={() => setValue(value + 1)}>+1</button>
            <button onClick={() => setValue(value - 1)}>-1</button>
        </div>
    );
};

export default Counter;
```

```jsx
# App.js
import Counter from "./Counter";

const App = () => {
  return <Counter />;
};

export default App;
```

- [ ]  useState를 여러 번 사용하기
192p

```jsx
# Info.js
import { useState } from "react";

const Info = () => {
  const [name, setName] = useState("");
  const [nickname, setNickname] = useState("");

  const onChangeName = e => {
    setName(e.target.value);
  };

  const onChangeNickname = e => {
    setNickname(e.target.value);
  };

  return (
    <div>
      <div>
        <input value={name} onChange={onChangeName} />
        <input value={nickname} onChange={onChangeNickname} />
      </div>
      <div>
        <div>
          <b>이름:</b> {name}
        </div>
        <div>
          <b>닉네임:</b> {nickname}
        </div>
      </div>
    </div>
  );
};

export default Info;
```

```jsx
# App.js
import Info from "./Info";

const App = () => {
  return <Info />;
};

export default App;
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2022%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%208965037881eb42c2a6db06730bae206f/1.mp4)

### 8.2 useEffect

      194p

```jsx
# Info.js
import { useState, useEffect } from "react";

const Info = () => {
  const [name, setName] = useState("");
  const [nickname, setNickname] = useState("");
  useEffect(() => {
    console.log("렌더링이 완료되었습니다.");
    console.log({
      name,
      nickname,
    });
  });

  const onChangeName = e => {
    setName(e.target.value);
  };

  const onChangeNickname = e => {
    setNickname(e.target.value);
  };

  return (
    <div>
      <div>
        <input value={name} onChange={onChangeName} />
        <input value={nickname} onChange={onChangeNickname} />
      </div>
      <div>
        <div>
          <b>이름:</b> {name}
        </div>
        <div>
          <b>닉네임:</b> {nickname}
        </div>
      </div>
    </div>
  );
};

export default Info;
-> useEffect를 사용한 코드에 문제가 있는지 감지하기 위해 두 번 실행되어 문장이 두 번 출력
```

- [ ]  마운트될 때만 실행하고 싶을 때
196p

```jsx
# Info.js의 useEffect 부분
useEffect(() => {
  console.log("마운트될 때만 실행됩니다.");
}, []);
```

- [ ]  특정 값이 업데이트될 때만 실행하고 싶을 때
196p
useEffect를 사용할 때, 특정 값이 변경될 때만 호출하는 경우

```jsx
cimponentDidUpdate(prevProps, prevState) {
	if (prevProps.value !== this.props.value) {
		doSomething();
	}
}
```

```jsx
# Info.js에서 useEffect 부분
useEffect(() => {
  console.log(name);
}, [name]);
```

- [ ]  뒷정리하기
198p

```jsx
# Info.js에서 useEffect 부분
useEffect(() => {
  console.log('effect');
  console.log(name);
  return () => {
      console.log('cleanup');
      console.log(name);
  };
}, [name]);
```

```jsx
# App.js 수정
import { useState } from "react";
import Info from "./Info";

const App = () => {
  const [visible, setVisible] = useState(false);
  return (
    <div>
      <button
        onClick={() => {
          setVisible(!visible);
        }}
      >
        {visible ? "숨기기" : "보이기"}
      </button>
      <hr />
      {visible && <Info />}
    </div>
  );
};

export default App;
```

[1.mp4](8%E1%84%8B%E1%85%AF%E1%86%AF%2022%E1%84%8B%E1%85%B5%E1%86%AF%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%208965037881eb42c2a6db06730bae206f/1%201.mp4)

### 8.3 useReducer

      200p

```jsx
# 액션 값을 전달받아 새로운 상태를 반환하는 함수
function reducer(state, action) {
	return { ... }; // 불변성을 지키면서 업데이트한 새로운 상태를 반환합니다.
}
# 액션 값
{
	type: 'INCREMENT',
}
```

- [ ]  카운터 구현하기
201p

```jsx
# Counter.js
import { useReducer } from "react";

function reducer(state, action) {
  // action.type에 따라 다른 작업 수행
  switch (action.type) {
    case "INCREMENT":
      return { value: state.value + 1 };
    case "DECREMENT":
      return { value: state.value - 1 };
    default:
      // 아무것도 해당되지 않을 때 기존 상태 반환
      return state;
  }
}

const Counter = () => {
  const [state, dispatch] = useReducer(reducer, { value: 0 });

  return (
    <div>
      <p>
        현재 카운터 값은 <b>{state.value}</b>입니다.
      </p>
      <button onClick={() => dispatch({ type: "INCREMENT" })}>+1</button>
      <button onClick={() => dispatch({ type: "DECREMENT" })}>-1</button>
    </div>
  );
};

export default Counter;
```

```jsx
# App.js
import Counter from "./Counter";

const App = () => {
  return <Counter />;
};

export default App;
```

- [ ]  인풋 상태 관리하기
202p

```jsx
# Info.js
import { useState, useEffect, useReducer } from "react";

function reducer(state, action) {
  return {
    ...state,
    [action.name]: action.value,
  };
}

const Info = () => {
  const [state, dispatch] = useReducer(reducer, {
    name: "",
    nickname: "",
  });
  const { name, nickname } = state;
  const onChange = e => {
    dispatch(e.target);
  };

  return (
    <div>
      <div>
        <input value={name} onChange={onChange} />
        <input value={nickname} onChange={onChange} />
      </div>
      <div>
        <div>
          <b>이름:</b> {name}
        </div>
        <div>
          <b>닉네임:</b> {nickname}
        </div>
      </div>
    </div>
  );
};

export default Info;
```

### 8.4 useMemo

     204p

```jsx
# Average.js
import { useState } from "react";

const getAverage = numbers => {
  console.log("평균값 계산 중..");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = e => {
    setNumber(e.target.value);
  };
  const onInsert = e => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  };

  return (
    <div>
      <input value={number} onChange={onChange} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값</b> {getAverage(list)}
      </div>
    </div>
  );
};

export default Average;
```

```jsx
# App.js
import Average from "./Average";

const App = () => {
  return <Average />;
};

export default App;
```

     206p

```jsx
# Average.js
import { useState, useMemo } from "react";

const getAverage = numbers => {
  console.log("평균값 계산 중..");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = e => {
    setNumber(e.target.value);
  };
  const onInsert = e => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  };

  const avg = useMemo(() => getAverage(list), [list]);

  return (
    <div>
      <input value={number} onChange={onChange} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b> {avg}
      </div>
    </div>
  );
};

export default Average;
```

### 8.5 useCallback

     208p

```jsx
# Average.js 컴포넌트 렌더링이 자주 발생할 때 최적화
import { useState, useMemo, useCallback } from "react";

const getAverage = numbers => {
  console.log("평균값 계산 중..");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = useCallback(e => {
    setNumber(e.target.value);
  }, []); // 컴포넌트가 처음 렌더링될 때만 함수 생성
  const onInsert = useCallback(() => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  }, [number, list]); // number 혹은 list가 바뀌었을 때만 함수 생성

  const avg = useMemo(() => getAverage(list), [list]);

  return (
    <div>
      <input value={number} onChange={onChange} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b> {avg}
      </div>
    </div>
  );
};

export default Average;
```

### 8.6 useRef

     209p

```jsx
# Average.js - 등록 누르면 다시 인풋으로 포커스
import { useState, useMemo, useCallback, useRef } from "react";

const getAverage = numbers => {
  console.log("평균값 계산 중..");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");
  const inputE1 = useRef(null);

  const onChange = useCallback(e => {
    setNumber(e.target.value);
  }, []); // 컴포넌트가 처음 렌더링될 때만 함수 생성
  const onInsert = useCallback(() => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
    inputE1.current.focus();
  }, [number, list]); // number 혹은 list가 바뀌었을 때만 함수 생성

  const avg = useMemo(() => getAverage(list), [list]);

  return (
    <div>
      <input value={number} onChange={onChange} ref={inputE1} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b> {avg}
      </div>
    </div>
  );
};

export default Average;
```

- [ ]  로컬 변수 사용하기
211p

```jsx
예시 코드 - 컴포넌트 로컬 변수를 사용해야 할 때 useRef 활용
import { Component } from 'react';

class MyComponent extends Component {
	id = 1
	setId = (n) => {
		this.id = n;
	}
	printId = () => {
		console.log(this.id);
	}
	render() {
		return (
			<div>
				MyComponent
			</div>
		);
	}
}

export default MyComponent;

예시 코드 - 함수 컴포넌트로 작성
import {useRef } from 'react';

const RefSample = () => {
	const id = useRef(1);
	const setId = (n) => {
		id.current = n;
	}
	const printId = () => {
		console.log(id.current);
	}
	return (
		<div>
			refsample
		</div>
	);
};

export default RefSample;
```

### 8.7 커스텀 Hooks 만들기

     212p

```jsx
# useInputs.js
import { useReducer } from "react";

function reducer(state, action) {
    return {
        ...state,
        [action.name]: action.value
    };
}

export default function useInputs(initialForm) {
    const [state, dispatch] = useReducer(reducer, initialForm);
    const onChange = e => {
        dispatch(e.target);
    };
    return [state, onChange];
}
```

```jsx
# Info.js
import useInputs from "./useInputs";

const Info = () => {
  const [state, onChange] = useInputs({
    name: '',
    nickname: ''
  });
  const { name, nickname } = state;

  return (
    <div>
      <div>
        <input name="name" value={name} onChange={onChange} />
        <input name="nickname" value={nickname} onChange={onChange} />
      </div>
      <div>
        <div>
          <b>이름:</b> {name}
        </div>
        <div>
          <b>닉네임:</b> {nickname}
        </div>
      </div>
    </div>
  );
};

export default Info;
```

**-> App.js에서 파일 Info.js로 렌더링!!**

## 9장

216p

- 스타일링 방식
    
    일반 CSS: 컴포넌트를 스타일링하는 가장 기본적인 방식
    
    Sass: 자주 사용되는 CSS 전처리기 중 하나, 확장된 CSS 문법으로 CSS 코드를 더욱 쉽게 작성할 수 있도록 함
    
    CSS Module: 스타일을 작성할 때 CSS 클래스가 다른 클래스의 이름과 절대 충돌하지 않도록 파일마다 고유한 이름을 자동으로 생성해 주는 옵션
    
    styled-components: 스타일을 자바스크립트 파일에 내장시키는 방식, 스타일을 작성함과 동시에 스타일이 적용된 컴포넌트를 만들 수 있게 해 줌
    
    1. 프로젝트 준비
    2. 일반 CSS 사용
    3. Sass 사용
    4. CSS module 사용
    5. styled-components 사용

프로젝트 준비

$ yarn create react-app styling-react

또는

$ npm create react-app styling-react

### 9.1 가장 흔한 방식, 일반 CSS

     217p

     App.js와 App.css 확인

     → CSS를 작성할 떄 중요한 점은 CSS 클래스를 중복되지 않게 만드는 것

         1. 이름을 지을 때 규칙을 사용  2. CSS Selector 활용

- [ ]  이름 짓는 규칙
219p
컴포넌트 이름-클래스 형태 : App-header
클래스가 어디에서 어떤 용도로 사용되는지 작성 : .card__title-primary
- [ ]  CSS Selector
219p
.App 안에 들어 있는 .logo에 스타일을 적용할 때
.App .logo {
     animation: App-logo-spin infinite 20s linear;
     height: 40vmin;
}

```jsx
# App.css
.App {
  text-align: center;
}

.App-logo {
  height: 40vmin;
  pointer-events: none;
}

@media (prefers-reduced-motion: no-preference) {
  .App-logo {
    animation: App-logo-spin infinite 20s linear;
  }
}

/*.App 안에 들어 있는 .logo */
.App .logo {
  animation: App-logo-spin infinite 20s linear;
  height: 40vmin;
}

.App-header {
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}

/*.App 안에 들어 있는 header
   header 클래스가 아닌 header 태그 자체에 스타일을 적용하기 떄문에 .이 생략되었습니다.*/
.App header {
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}

.App-link {
  color: #61dafb;
}

/*.App 안에 들어 있는 a 태그*/
.App a {
  color: #61dafb;
}

@keyframes App-logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```

```jsx
# App.js
import { Component } from "react";
import logo from "./logo.svg";
import "./App.css";

class App extends Component {
  render() {
    return (
      <div className="App">
        <header>
          <img src={logo} className="logo" alt="logo" />
          <p>
            Edit <code>src/App.js</code> and save to reload.
          </p>
          <a
            href="https://reactjs.org"
            target="_blank"
            rel="noopener noreferrer"
          >
            Learn React
          </a>
        </header>
      </div>
    );
  }
}

export default App;
```

### 9.2 Sass 사용하기

     221p

     Syntactically Awesome Style Sheets : 문법적으로 매우 멋진 스타일시트

     CSS 전처리기로 복잡한 작업을 단순화, 코드의 가독성을 높여 재활용성

     .scss와 .sass를 지원

```jsx
# .sass
$font-stack: Helvetica, sans-serif
$primary-color: #333

body 
	font: 100% $font-stack
	color: $primary-color
-> 중괄호와 세미콜론을 사용하지 않음
```

```jsx
# .scss
$font-stack: Helvetica, sans-serif
$primary-color: #333;

body {
	font: 100% $font-stack;
	color: $primary-color;
}
-> 중괄호와 세미콜론을 사용
```

<aside>
💡 $ yarn add sass
또는
$ npm add sass 로 라이브러리를 설치

</aside>

     222p

```jsx
# SassComponent.scss
// 변수 사용하기
$red: #fa5252;
$orange: #fd7e14;
$yellow: #fcc419;
$green: #40c057;
$blue: #339af0;
$indigo: #5c7cfa;
$violet: #7950f2;
// 믹스인 만들기(재사용되는 스타일 블록을 함수처럼 사용할 수 있음)
@mixin square($size) {
  $calculated: 32px * $size;
  width: $calculated;
  height: $calculated;
}

.SassComponent {
  display: flex;
  .box {
    // 일반 CSS에서는 .SassComponent .box와 마찬가지
    background: red;
    cursor: pointer;
    transition: all 0.3s ease-in;
    &.red {
      // .red 클래스가 .box와 함께 사용되었을 때
      background: $red;
      @include square(1);
    }
    &.oragne {
      background: $orange;
      @include square(2);
    }
    &.yellow {
      background: $yellow;
      @include square(3);
    }
    &.green {
      background: $green;
      @include square(4);
    }
    &.blue {
      background: $blue;
      @include square(5);
    }
    &.indigo {
      background: $indigo;
      @include square(6);
    }
    &.violet {
      background: $violet;
      @include square(7);
    }
    &:hover {
      // .box에 마우스를 올렸을 때
      background: black;
    }
  }
}
```

```jsx
# SassComponent.js
import "./SassComponent.scss";

const SassComponent = () => {
  return (
    <div className="SassComponent">
      <div className="box red" />
      <div className="box orange" />
      <div className="box yellow" />
      <div className="box green" />
      <div className="box blue" />
      <div className="box indigo" />
      <div className="box violet" />
    </div>
  );
};

export default SassComponent;
```

```jsx
# App.js
import { Component } from "react";
import SassComponent from "./SassComponent";

class App extends Component {
  render() {
    return (
      <div>
        <SassComponent />
      </div>
    );
  }
}

export default App;
```

- [ ]  utils 함수 분리하기
225p

```jsx
# src/styles/utils.scss
// 변수 사용하기
$red: #fa5252;
$orange: #fd7e14;
$yellow: #fcc419;
$green: #40c057;
$blue: #339af0;
$indigo: #5c7cfa;
$violet: #7950f2;

// 믹스인 만들기(재사용되는 스타일 블록을 함수처럼 사용할 수 있음)
@mixin square($size) {
  $calculated: 32px * $size;
  width: $calculated;
  height: $calculated;
}
```

```jsx
# SassComponent.scss
@import "./styles/utils.scss";
.SassComponent {
  display: flex;
  .box {
    // 일반 CSS에서는 .SassComponent .box와 마찬가지
    background: red;
    cursor: pointer;
    transition: all 0.3s ease-in;
    &.red {
      // .red 클래스가 .box와 함께 사용되었을 때
      background: $red;
      @include square(1);
    }
    &.oragne {
      background: $orange;
      @include square(2);
    }
    &.yellow {
      background: $yellow;
      @include square(3);
    }
    &.green {
      background: $green;
      @include square(4);
    }
    &.blue {
      background: $blue;
      @include square(5);
    }
    &.indigo {
      background: $indigo;
      @include square(6);
    }
    &.violet {
      background: $violet;
      @include square(7);
    }
    &:hover {
      // .box에 마우스를 올렸을 때
      background: black;
    }
  }
}
```

- [ ]  sass-loader 설정 커스터마이징
226p
디렉터리를 많이 만들어 구조가 깊어지면 import 문이 길어짐
create-react-app으로 만든 프로젝트는 구조의 복잡도를 낮추기 위해 세부 설정이 숨겨져 있음
커스터마이징하려면 프로젝트 디렉터리에서 yarn eject 명령어로 세부 설정을 꺼내야 함
→ 기본적으로 Git 설정이 되어 있어 yarn eject는 Git에 커밋되지 않은 변화가 있다면 진행 불가
→ 커밋 먼저!!!!!!
$ yarn eject
$ react-scripts eject

<aside>
💡 만약 yarn이 안되면 [이 링크](https://singa-korean.tistory.com/21)를 참고 할 것

</aside>

     수정 후

     SassComponent.scss에서 import문 수정 @import ‘utils.scss’;

     229p

```jsx
# webpack.config.js에서 sass-loader의 옵션에서 additionalData 필드 설정
{
  test: sassRegex,
  exclude: sassModuleRegex,
  use: getStyleLoaders({
    importLoaders: 3,
    sourceMap: isEnvProduction
      ? shouldUseSourceMap
      : isEnvDevelopment,
  }).concat({
    loader: require.resolve("sass-loader"),
    options: {
      sassOptions: {
        includePaths: [paths.appSrc + "/styles"],
      },
      additionalData: "@import 'utils';",
    },
  }), ...
```

- [ ]  node_modules에서 라이브러리 불러오기
230p
@import ‘../../../node_modules/library/styles’;
→ @import ‘~library/styles’;
Sass 라이브러리 두 가지 설치
1. $ yarn add open-color include-media
2. utils.scss에서 라이브러리 불러오기

```jsx
# utils.scss
@import '~include-media/dist/include-media';
@import '~open-color/open-color';
...
```

```jsx
# SassComponent.scss
.SassComponent {
  display: flex;
  background: $oc-gray-2;
  @include media("<768px") {
    background: $oc-gray-9;
  }
...
```

### 9.3 CSS Module

     [파일 이름]_[클래스 이름]__[해시값]

```jsx
# CSSModule.module.css
/*자동으로 고유해질 것이므로 흔히 사용되는 단어를 클래스 이름으로 마음대로 사용 가능*/

.wrapper {
  background: black;
  padding: 1rem;
  color: white;
  font-size: 2rem;
}

/*글로벌 CSS를 작성하고 싶다면*/

:global .something {
  font-weight: 800;
  color: aqua;
}
```

```jsx
# CSSModlue.js
import styles from "./CSSModule.module.css";
const CSSModule = () => {
  return (
    <div className={styles.wrapper}>
      안녕하세요, 저는 <span className="something">CSS Module!</span>
    </div>
  );
};

export default CSSModule;
-> style = CSSModlue_wrapper__1SbdQ
```

```jsx
# App.js
import { Component } from "react";
import CSSModule from "./CSSModule";

class App extends Component {
  render() {
    return (
      <div>
        <CSSModule />
      </div>
    );
  }
}

export default App;
```
     234p

```jsx
# CSSModule.module.css
/*자동으로 고유해질 것이므로 흔히 사용되는 단어를 클래스 이름으로 마음대로 사용 가능*/

.wrapper {
  background: black;
  padding: 1rem;
  color: white;
  font-size: 2rem;
}

.inverted {
  color: black;
  background: white;
  border: 1px solid black;
}

/*글로벌 CSS를 작성하고 싶다면*/

:global .something {
  font-weight: 800;
  color: aqua;
}
```

```jsx
# CSSModlue.js
import styles from "./CSSModule.module.css";
const CSSModule = () => {
  return (
    <div className={`${styles.wrapper} ${styles.inverted}`}>
      안녕하세요, 저는 <span className="something">CSS Module!</span>
    </div>
  );
};

export default CSSModule;
```

<aside>
💡 ` (백틱) 사용 주의!

</aside>

- [ ]  classnames
236p
$ yarn add classnames
    - classnames 간략 사용법
        
        import classNames from ‘classnames’;
        
        classNames(’one’, ‘two’); // = ‘one two’
        classNames(’one’, { two: true }); // = ‘one two’
        classNames(’one’, { two: false }); // = ‘one’
        classNames(’one’, [’two’, ‘three’]); // = ‘one two three’
        
        const myClass = ‘hello’;
        classNames(’one’, myClass, { myCondition: true }); // = ‘one hello myCondition’
        
    
    ```jsx
    예시 코드1
    const MyComponent = ({ highlighted, theme }) => (
    	<div className={classNames('MyComponent', { highlighted }, theme)}>Hello</div>
    );
    
    예시 코드2 - 라이브러리의 도움을 받지 않을 경우
    const MyComponent = ({ highlighted, theme }) => (
    	<div className={`MyComponent ${theme} ${highlighted ? 'highlighted' : ''}`}>
    		Hello
    	</div>
    );
    ```
    
    ```jsx
    # CSSModule 컴포넌트에 classnames의 bind 함수를 적용한 예
    import classNames from 'classnames/bind';
    import styles from './CSSModule.module.css';
    
    const cx = classNames.bind(styles); // 미리 styles에서 클래스를 받아 오도록 설정하고
    
    const CSSModule = () => {
    	return (
    		<div className={cx('wrapper', 'inverted')}>
    			안녕하세요, 저는 <span className="something">CSS Module!</span>
    		</div>
    	);
    );
    
    export default CSSModule;
    ```
    
- [ ]  Sass와 함께 사용
238p

### 9.4 styled-components
