# 30 days of react

Resource from https://www.fullstackreact.com/30-days-of-react/

## Day 1: What is react?

- web apps, view layer (user interface)
- React 應用程式的心臟 :heart: 元件 "composable" ***component***
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
