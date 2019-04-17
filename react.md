# 30 days of react

Resource from https://www.fullstackreact.com/30-days-of-react/

## Day 1: What is react?

- web apps, view layer (user interface)
- React 應用程式 (application) 的心臟 :heart: 元件 "composable" ***component***
  - e.g. 按鈕、輸入區域
  - 元件內會有元件（*self-contained*）
- React 不像從前的前端框架，運行於 DOM，而是運行在 virtual DOM 上；開發者不操作瀏覽器的 DOM (`document`)，而是更新存在 memory 中的 virtual DOM，react 再去改動 DOM

## Day 2: What is JSX? ES6?

### `ES`: ECMAScript

- ES5 為第五代 JavaScript，於 2009 發布，所有瀏覽器都能支援，過去看到的 JavaScript 都屬於 ES6
- ES6 為第六代 JavaScript，於 2015 發布，提升了 ES5 的功能，目前仍有部分瀏覽器無法支援
  - 可將程式碼轉 (*transpile*) 成 ES5。讓瀏覽器可以支援
  - 若需要另外的功能，需要 *shim* 或 *polfill*

### JSX: JavaScript eXtension

- React component 使用 `render` 函式指出 component 以 HTML 形式呈現的樣貌
- JSX 會在 runtime 時，被轉成一般的 JavaScript，使得開發者可以像寫 HTML 一樣來寫 JavaScript
- 雖然程式碼會被 JSX 編譯器所轉譯，寫單純的 JavaScript 也是可以的：`React.createElement()`，不過由於 JSX 有易讀性，還是比較鼓勵寫 JSX

### 範例

```javascript
// class extends 為 ES6 語法
class HelloWorld extends React.Component {
  render() {
    return (
      // className 為 React 的屬性語法
      <h1 className='large'>Hello World</h1>
    );
  }
}

/********* translated at runtime *********/

class HelloWorld extends React.Component {
  render() {
    return (
      React.createElement(
        'h1',
        {className: 'large'},
        'Hello World'
      )
    );
  }
}
```

## Day 3: First React Component

- 使用 Bebel 將 ES6 轉譯（transpile）成 ES5，來讓開發者可使用 ES6 撰寫能在所有瀏覽器成功執行的程式

  `<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script></head>`

- 使用 `ReactDOM.render()` 將 React components 呈現在頁面上

  - `ReactDom.render(<要 render 的 app>, <app 位置>)`

  - ```html
    <script type="text/babel">
      var app = <h1>Hello world</h1>
      var mountComponent = document.querySelector('#app');
      ReactDOM.render(app, mountComponent);
    </script>
    ```

- React 所有的 components 都需要至少一個 `render()` 函式來回傳 virtual DOM

- 使用內建的 DOM component 型態如 `<h1 />` 和 `<App/>` 來表示宣告的類別（class）

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Hello world</title>
  <!-- Script tags including React -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.3.1/react.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.3.1/react-dom.min.js"></script>
  <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
  <div id="app"></div>
  <script type="text/babel">
    class App extends React.Component {
      render() {
        return <h1>Hello from our app</h1>
      }
    }
    var mountComponent = document.querySelector('#app');
    ReactDOM.render(<App />, mountComponent);
  </script>
</body>
</html>
```