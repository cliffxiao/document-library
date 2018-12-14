# React - 3 - JSX 语法
===

>  **2018年9月5日10:41:19**  
> Recently revised in **2018-10-28 10:54:44**

## 第三章 JSX 语法
&emsp;一般我们在 html 中，我们才会用 \<div\> 这些标签。但是，在 React 中，它通过 js ，使用了 \<div\> 这些标签，而只要 \<div\> 出现在 React 中，我们就将它叫做 JSX 。  
&emsp;在 React 中，使用到了 render() ，一般都涉及到了 JSX 语法：
```
import React, { Component } from 'react';

/**
 * import { Component } from 're act';
 * 
 * 等价于
 * 
 * import React from 'react'
 * const Component = React.Component
 */

class App extends Component {
  // JSX
  render() {
    return (
      <h3>Hello React!</h3>
    );
  }
}

export default App;
```

&emsp;在 JSX 语法中，如果我们要使用自己创建的组件，那么这个组件名称，首字母必须大写：
```
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```
&emsp;在 ReactDOM 渲染的组件上， App 这个组件的首字母就是大写的。

<br>

###  目录
| 章节名 | 导航                                |
| ------ | ----------------------------------- |
| 第一章 | [基础环境搭建](./react-chapter1.md) |
| 第二章 | [组件](./react-chapter2.md)         |
| 第三章 | [JSX 语法](./react-chapter3.md)     |

<br>

 
