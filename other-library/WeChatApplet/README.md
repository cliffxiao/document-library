# 微信小程序
>  **2018-9-13 09:04:41**  
> Recently revised in **22018-10-28 12:03:45**

<br>

## 序
&emsp;应产品所需，用技术去折服他~微信小程序开发，走你！

<br>

## 一、环境准备

### 1.1 下载安装
[---地址---](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html?t=18091218)

<br>

### 1.2 授权登录
[---地址---](https://jingyan.baidu.com/article/4dc408486e25e2c8d946f1b7.html)  
&emsp;按上面地址配置，然后扫码登录进小程序。

<br>

## 二、环境介绍

### 2.1 文件类型

| 文件类型 | 作用 |
| --- | --- |
| .json | JSON 配置文件 |
| .wxml | WXML 模板文件 |
| .wxss | WXSS 样式文件 |
| .js | JS 脚本逻辑文件 |

<br>

### 2.2 .json 文件
1. **app.json**：小程序的全局配置。 [详情](https://developers.weixin.qq.com/miniprogram/dev/framework/config.html)
2. **project.config.json**：工具的个性化配置，例如界面颜色、编译配置等。 [详情](https://developers.weixin.qq.com/miniprogram/dev/devtools/projectconfig.html)
3. **page.json**：页面配置，用来设置页面的整体样式等。 [详情](https://developers.weixin.qq.com/miniprogram/dev/framework/config.html#%E5%85%A8%E5%B1%80%E9%85%8D%E7%BD%AE)

<br>

### 2.3 WXML 模板

&emsp;WXML（WeiXin Markup Language）是框架设计的一套标签语言，结合基础组件、事件系统，可以构建出页面的结构。[详情](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxml/index.html)

<br>

### 2.4 WXSS 样式

&emsp;WXSS(WeiXin Style Sheets)是一套样式语言，用于描述 WXML 的组件样式。[详情](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html)

<br>

### 2.5 事件
1. 事件是视图层到逻辑层的通讯方式。
2. 事件可以将用户的行为反馈到逻辑层进行处理。
3. 事件可以绑定在组件上，当达到触发事件，就会执行逻辑层中对应的事件处理函数。
4. 事件对象可以携带额外信息，如 id, dataset, touches。

<br>

### 2.6 API

&emsp;小程序开发框架提供丰富的微信原生 API，可以方便的调起微信提供的能力，如获取用户信息，本地存储，支付功能等。

### 2.7 审核发布
&emsp;微信公众平台 -> 小程序管理后台 -> 开发管理 -> 开发版本 -> 提交审核

<br>

## 三、友情链接

| 作者 | 链接 |
| --- | --- |
| 小程序官网 | [小程序组件](https://developers.weixin.qq.com/miniprogram/dev/component/) |
|   | [小程序的100坑](./WeChatAppletBug.md) |

<br>

 
