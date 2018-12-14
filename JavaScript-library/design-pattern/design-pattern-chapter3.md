设计模式手册 - 3 - 工厂模式
===

>  **2018年8月22日11:19:00**  
> Recently revised in **2018-10-28 10:54:44**

## 第三章 工厂模式

### 3.1 使用介绍
* 将 new 操作单独封装。
* 遇到 new 时，就要考虑是否使用工厂模式。
* 举个例子：  

&emsp;你去购买汉堡，只需要跟服务员点餐，做汉堡这些步骤你就不用理会了。然后下一个人去购买汉堡，也是只需要点餐，至于餐厅怎么操作的，就不需要去关心了。在这里，餐厅封装了做汉堡的工作，只需要“接受点餐”、“送餐给顾客”就可以了。

<br>

### 3.2 UML类图及其实现
![图](../../public-repertory/img/js-design-pattern-chapter3-1.png)
```
class Product {
    constructor(name) {
        this.name = name;
    }
    init() {
        alert("init");
    }
    fun1() {
        alert("fun1");
    }
    fun2() {
        alert("fun2");
    }
}

class Creator {
    create(name) {
        return new Product(name);
    }
}

// 测试
let creator = new Creator();
let p = creator.create("p1");
p.init(); // init
p.fun1(); // fun1
```

<br>

### 3.3 使用场景
* jQuery - $("div")
* React.createElement
* vue 异步组件

> jQuery
```
class jQuery {
    constructor(selector) {
        let slice = Array.prototype.slice;
        let dom = slice.call(document.querySelectorAll(selector));
        let len = dom ? dom.length : 0;
        for(let i = 0; i < len; i++) {
            this[i] = dom[i];
        }
        this.length = len;
        this.selector = selector || '';
    }
    append(node) {
        alert("Hello function append!");
    }
    addClass(name) {
        alert("Hello function addClass! "+ name);
    }
    html(data) {
        alert("Hello function html!");
    }
    // 此处省略若干API……
}

window.$ = function(selector) {
    return new jQuery(selector);
}

let p = $("p");
p.addClass(" "); // Hello function addClass!  
```

> React
```
var profile = <div>
    <img src="avatar.png" className="profile" />
    <h3>{[user.firstName, user.lastName].join(' ')}</h3>
</div>

var profile = React.createElement("div", null,
    React.createElement("img", {src: "avatar.png", className: "profile"}),
    React.createElement("h3", null, [user.firstName, user.lastName].join(" "));
);
```
```
class Vnode(tag, attr, children) {
    // ...省略内部代码...
}
React.createElement = function(tag, attrs, children) {
    return new Vnode(tag, attrs, children);
}
```

> Vue
```
Vue.component('async-example', function(resolve, reject) {
    setTimeout(function() {
        resolve({
            template: '<div>I am async!</div>'
        })
    }, 1000)
})
```

<br>

### 3.4 设计原则验证
* 构造函数和创建者分离
* 符合开放封闭原则

<br>

 