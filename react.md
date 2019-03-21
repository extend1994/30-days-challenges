# 30 days of react

Resource from https://www.fullstackreact.com/30-days-of-react/

## Day 1: What is react?

- web apps, view layer (user interface)
- React 應用程式的心臟 :heart: 元件 "composable" ***component***
  - e.g. 按鈕、輸入區域
  - 元件內會有元件（*self-contained*）
- React 不像從前的前端框架，運行於 DOM，而是運行在 virtual DOM 上；開發者不操作瀏覽器的 DOM (`document`)，而是更新存在 memory 中的 virtual DOM，react 再去改動 DOM
