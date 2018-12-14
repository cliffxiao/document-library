Angular开发手册 - 4 - 路由
===

>  **2018年9月5日17:38:19**  
> Recently revised in **2018-10-28 11:50:10**

## 路由

## 6.1 Route
| 名称           | 简介                                                                                                  | 使用                                                                                                                       |
| -------------- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Routes         | 路由配置，保存着哪个 URL 对应展示哪个组件，以及在哪个 RouterOutlet 中展示组件                         | `import {HomeComponent} from "./home/home.component"; const routes: Routes = [{ path: 'home', component: HomeComponent }]` |
| RouterOutlet   | 在 HTML 中标记路由内容呈现位置的占位符指令                                                            | `<router-putlet></router-putlet>`                                                                                                                          |
| Router         | 负责在运行时执行路由的对象，可以通过调用其 navigate() 和 navigateByUrl() 方法来导航到一个指定的路由。 | `<input type="button" value="商品详情" (click)="toProductDetails()"> -> constructor(private router: Router) {} -> toProductDetails() {this.router.navigate(['/product'])}`                                                                                                                          |
| RouterLink     | 在 HTML 中声明路由导航用的指令                                                                        | `<a [routerLink]="['/product']"商品详情</a>`>                                                                              |
| ActivatedRoute | 当前激活的路由对象，保存着当前路由的信息，如路由地址，路由参数等。                                    | *                                                                                                                          |

<br>

### 6.2 解析图
![图](../../public-repertory/img/js-angular-stock-management-platform-chapter4-1.png)

<br>

### 6.3 传递数据
&emsp;在路由时传递数据的方法有：
1. 在查询参数中传递数据
```
/product?id=1&name=2 => ActivatedRoute.queryParams[id]
```
2. 在路由路径中传递参数
```
{path:/product/:id} => /product/1 => ActivatedRoute.params[id]
```
3. 在路由配置中传递参数
```
{path:/product, component:ProductComponent, data:[{isProd:true}]} => ActivatedRoute.data[0][isProd]
```

<br>

### 6.4 路由+传递数据
```
<a [routerLink]="['/product']" [queryParams]="{id: 1}">
    商品详情
</a>
```

```
<a [routerLink]="['/product', 1]">
    商品详情
</a>
```
<br>

### 6.5 路由重定向
&emsp;在用户访问一个特定的地址时，将其重定向到另一个特定的地址   
&emsp;www.aaa.com => www.aaa.com/home   
&emsp;www.aaa.com/x => www.aaa.com/y
```
{path:'', redirectTo:'/home', pathMatch:'full'}
```

<br>

### 6.6 子路由
```
{
    path: 'home',
    component: HomeComponent,
    children: [
        {
            path: '/xxx',
            component: XxxComponent
        }
        {
            path: '/yyy',
            component: YyyComponent
        }
    ]
}
```

<br>

### 6.7 辅助路由
```
<router-outlet></router-outlet>
<router-outlet name="aux"></router-outlet>

{
    path: 'xxx',
    component: XxxComponent,
    outlet: "aux"
}
{
    path: 'yyy',
    component: YyyComponent,
    outlet: "aux"
}

<a [routerLink] = "['/home', {outlets: {aux: 'xxx'}}]">Xxx</a>
<a [routerLink] = "['/product', {outlets: {aux: 'yyy'}}]">Yyy</a>
```

<br>

### 6.8 辅助路由实现
&emsp;辅助路由案例整体思路
* 在 app 组件的模板上再定义一个插座来显示聊天面板
* 单独开发一个聊天室插件，只显示在新定义的插座上。
* 通过路路由参数控制新电脑是否显示聊天面板。

<br>

 