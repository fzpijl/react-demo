## react element

```js
const element1 = <button>text</button>;

const element2 = (
  <div>
    <h1>title</h1>
  </div>
);

const element3 = (
  <div>
    <Square />
  </div>
);
```

## react 组件

一个函数，返回 UI

```js
function Square() {
  return <button className="square">X</button>;
}

// 返回值
_jsx("button", {
  className: "square",
  children: "X",
});
```

## 添加交互

```js
function Square() {
  function handleClick() {
    console.log("clicked");
  }
  return <button onClick={handleClick}>X</button>;
}
```

## 向组件传递 props

```javascript
function Square({ value }) {
  return <button>{value}</button>;
}

// 使用组件
const ele = <Square value="x">
```

## 组件的状态

```js
function Square() {
  const [value, setValue] = useState("X");
  function clickHandler() {
    setValue("O");
  }
  return <button onClick={clickHandler}>{value}</button>;
}
```
