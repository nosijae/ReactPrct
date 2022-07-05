# React JS

## 바닐라 JS / React JS

리엑트 JS는 UI를 interactive하게 해준다.

### 바닐라 JS

우리가 버튼을 만들어 뭔가를 하려면 Javascript는 굉장히 할 게 많다.
html로 만들고, Id를 주고, 이를 Javascript에 가져오기 위해, querySelector 같은 것을 사용하고,
function을 만들어 Eventlistener에 넣어줘야 한다.

> **_ Button Counter 만들기 _**

1. html 만들기
2. javascript에서 가져온다.
3. event listner 만들기
4. 데이터를 업데이트 ( html 업데이트도 함께 해야 함 )

이 과정에서 React JS로 개선할 수 있는 것이 많다.

### React JS 설치

script src를 직접 넣어줄 수 있는 방법이 있따.
react, react-dom을 import를 해주면 된다.

```html
<script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js"></script>
```

### React JS Component 형성

HTML 코드를 사용하지 않고, 자바스크립트만으로 버튼을 만든다.

이를 위해서는 React-dom이 필요하다.
React JS는 엔진이다.
interactive 한 UI를 가능하게 한다.

react-dom 은 React element를 HTML에 두는 역할을 한다.

ReactDOM.render("보여줄 요소", "보여줄 위치") => user에게 보여준다.

```html
<!DOCTYPE html>
<html>
  <body>
    <div id="root"></div>
  </body>
  <script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js"></script>
  <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js"></script>

  <script>
    const root = document.getElementById("root");
    // 코드를 만들면서 span의 id도 Property로 지정해줄 수 있다. 또한 argument도 넘겨줄 수 있다.
    const span = React.createElement(
      "span",
      { id: "sexy-span", style: { color: "red" } },
      "Hello I'm a Span"
    );
    ReactDOM.render(span, root);
  </script>
</html>
```

실제로 이렇게 작성하지는 않는다.
React JS는 javascript에서 시작해서, HtmlDl ehlsek.

react js가 필요한 element를 업데이트한다.
react js는 유저에게 보여질 내용을 컨트롤하기도 쉽다.

react js에게 업데이트해야 하는 Html을 업데이트하라 한다.

#### javascript를 이용해 Element를 생성하고, react js가 그것을 html로 번역

렌더링을 통해 화면에 보여주는 방식이다.
변수로 생성하고 -> 위치를 정해 rendering 한다.

```html
<!DOCTYPE html>
<html>
  <body>
    <div id="root"></div>
  </body>
  <script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js"></script>
  <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js"></script>

  <script>
    const root = document.getElementById("root");
    // 코드를 만들면서 span의 id도 Property로 지정해줄 수 있다. 또한 argument도 넘겨줄 수 있다.
    const span = React.createElement(
      "span",
      { id: "sexy-span", style: { color: "red" } },
      "Hello I'm a Span"
    );
    const btn = React.createElement("button", null, "Click me");
    const container = React.createElement("div", null, [span, btn]);
    ReactDOM.render(container, root);
  </script>
</html>
```

### 이벤트 리스너

react에서 이벤트 리스너를 추가하는 방법은 매우 간단하다 .

propert를 넣는 부분에 정의를 해주면 된다 .

```html
<!DOCTYPE html>
<html>
  <body>
    <div id="root"></div>
  </body>
  <script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js"></script>
  <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js"></script>

  <script>
    const root = document.getElementById("root");
    // 코드를 만들면서 span의 id도 Property로 지정해줄 수 있다. 또한 argument도 넘겨줄 수 있다.
    const span = React.createElement(
      "h3",
      {
        onMouseEnter: () => console.log("Mouse Enter"),
      },
      "Hello I'm a Span"
    );
    const btn = React.createElement(
      "button",
      {
        onClick: () => console.log("i'm Clicked"),
      },
      "Click me"
    );
    const container = React.createElement("div", null, [span, btn]);
    ReactDOM.render(container, root);
  </script>
</html>
```

addEventlistener 대신 이와같이 Property에 이벤트 리스너를 둘 수 있다는 것이다.

# 더 쉬운 방법

React JS가 Element를 생성하고, Event Listener를 더하는 것을 도와준다.
React JS는 Interactive power를 가지고 있다.

React element들을 가져다가 Html로 바꾸기 위해 react dom도 Import 했다.

```html
<!DOCTYPE html>
<html>
  <body>
    <div id="root"></div>
  </body>
  <script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js"></script>
  <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js"></script>

  <script>
    const root = document.getElementById("root");
    // 코드를 만들면서 span의 id도 Property로 지정해줄 수 있다. 또한 argument도 넘겨줄 수 있다.
    const span = React.createElement(
      "h3",
      {
        onMouseEnter: () => console.log("Mouse Enter"),
      },
      "Hello I'm a Span"
    );
    const btn = React.createElement(
      "button",
      {
        onClick: () => console.log("i'm Clicked"),
      },
      "Click me"
    );
    const container = React.createElement("div", null, [span, btn]);
    ReactDOM.render(container, root);
  </script>
</html>
```

1. body에 root라는 id를 가진 Div를 생성했다.
   -> 이 비어있는 div는 reactDOM이 react element들을 가져다놓을 곳이다.
2. root div를 가져와서, ReactDOM.render를 통해, Root div안에서 react element들을 보여줬다.

props에서 id, class명을 만들고, style도 주고, event listner도 했다.
react 팀은 element에 event listener를 두는 것을 중요시 했다.
addEventListner 대신 property 부분에 직접 element에 적용해줬다.

reactDOM은 React element를 가져다가 HTML로 바꾸는 역할을 한다.
