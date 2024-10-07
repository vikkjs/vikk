<div align="center">
<h1>Vikk</h1>
<img src="https://github.com/vikkjs/vikk/blob/main/.github/vikk.png" alt="vikk" width="192" height="192">

### Nonreactive JS library
[![npm](https://img.shields.io/npm/v/vikk)](https://www.npmjs.com/package/vikk)
[![npm](https://img.shields.io/npm/dm/vikk)](https://www.npmjs.com/package/vikk)
[![npm package minimized gzipped size](https://img.shields.io/bundlejs/size/vikk)](https://www.npmjs.com/package/vikk)
[![GitHub](https://img.shields.io/github/license/vikkjs/vikk)](https://github.com/git/git-scm.com/blob/main/MIT-LICENSE.txt)

</div>

## Getting Started
```bash
npx vikk-app project
```
#### Options
```bash
npx vikk-app # in current folder
npx vikk-app -js # javascript
bunx vikk-bun # using bun
```

## Usage
```jsx  
function App() {
    return <div> Hello from Vikk </div>
}
document.body.append(<App />)
```

#### Attributes
```jsx  
const e = <div style="color: red"> Hello </div>
```

#### Events
```jsx  
const f = (text) => alert(text)
const e = <div onclick={() => f("Hi")}> Click Me </div>
```

#### Arrays
```jsx  
const e = <div> {[1, 2, 3].map(i => <div> {i} </div>)} </div>
```

#### Ternaries
```jsx  
const e = <div> {true ? <div> Hello </div> : null} </div>
```

#### Nested elements
```jsx  
const inner = <div> Hello </div>
const e = <div> {inner} </div>
```

#### Style object
```jsx 
const style = { color: "red" }
const e = <div style={style}> Hello </div>
```

## Components
### Using elements
```jsx
function Component({ state }) {
    return <div> {state.data} </div>
}
function App() {
    const state = { data: "hello" }
    return <div>
        <h1> App </h1>
        <Component state={state} />
    </div>
}
document.body.append(<App />)
```

#### Elements with multiple params
```jsx
function Component({ param1, param2 }) {
    return <div> {param1} {param2} </div>
}
function App() {
    return <div>
        <h1> App </h1>
        <Component param1="hello" param2="world" />
    </div>
}
document.body.append(<App />)
```

#### Elements with children
```jsx
function Component({ state }, children) {
    return <div>
        {state.data}
        {children}
    </div>
}
function App() {
    const state = { data: "hello" }
    return <div>
        <h1> App </h1>
        <Component state={state}>
            <div>child1</div>
            <div>child2</div>
        </Component>
    </div>
}
document.body.append(<App />)
```

### Using function calls
```jsx
function Component(state) {
    return <div> {state.data} </div>
}
function App() {
    const state = { data: "hello" }
    return <div>
        <h1> App </h1>
        {Component(state)}
    </div>
}
document.body.append(App())
```

## Examples
### Todo list
```jsx
function App() {
    const input = <input />
    const list = <ul></ul>
    const add = () => list.prepend(<li> {input.value} </li>)
    const btn = <button onClick={add}> Add </button>
    return <div> {input} {btn} {list} </div>
}
document.body.append(<App />)
```

## Licence
MIT