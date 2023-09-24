## react element

```js
const element1 = <button>text</button>;

const value = "title";
const element2 = (
  <div>
    <h1>{value}</h1>
  </div>
);

const element3 = (
  <div>
    <Square />
  </div>
);
// 会被编译为
// const element3 = _jsx("div", {
//   children: _jsx(Square, {})
// });
```

## react 组件

一个函数，返回 react element

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

```js
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

## 条件渲染

```js
function Hello({ name }) {
  return name && <div>hello {name}</div>;
}
```

## 渲染列表

```js
// const data = [
//   { name: "a", id: 0 },
//   { name: "b", id: 2 },
// ];
function List({ data }) {
  return (
    <ul>
      {data.map((it) => (
        <li key={it.id}>{it.name}</li>
      ))}
    </ul>
  );
}
```
