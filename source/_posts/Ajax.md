---
title: Ajax学习笔记
tags: [Ajax,Web,笔记]
categories: 前端
date: 2022-08-15
updated:  2022-08-15
description: 黑马Ajax学习笔记
top_img: https://static.runoob.com/images/mix/code-wallpaper-18.png
cover: https://static.runoob.com/images/mix/code-wallpaper-18.png
connents: 
aside: true
---

# 服务器的基本概念与初始Ajax

## 1.目标

- - 服务器相关概念
  - 客户端和服务器通信过程
  - 数据是一种资源
  - Ajax概念及应用场景
  - 使用jQuery中的Ajax函数请求数据
  - 接口和接口文档的概念

## 2.什么是Ajax

- - Ajax全称 asynchronous JavaScript And XML(异步JavaScript和XML)
  - 通俗理解：在网页中利用XMLHttpRequest对象和服务器进行数据交互的方式
  - 作用：实现网页和服务器之间的数据交互
  - Ajax的典型应用场景

与后端进行数据交互的场景

- - - 动态检测用户名是否被占用
    - 动态加载搜索提示列表
    - table分页
    - 数据增删改查等

## 3.jQuery中的Ajax

### 1.背景

浏览器提供的XMLHttpRrequest用法复杂,jQuery对XMLHttpRequest进行了封装,提供了更加方便的用法,极大的降低了Ajax的使用难度

### 2.jQuery发起Ajax请求

- - $.get()
  - $.post()
  - $.ajax()

### 3.$.get()

#### 1.作用

- - - 发起get请求,从服务器请求资源

#### 2.语法

```
$.get(url,[data],[callback])
```

| 参数名   | 参数类型 | 是否必选 | 说明                 |
| -------- | -------- | -------- | -------------------- |
| url      | string   | 是       | 要请求的资源地址     |
| data     | object   | 否       | 请求参数             |
| callback | function | 否       | 请求成功时的回调函数 |

#### 3.$.get()发起不带参数请求

> 使用 $.get() 函数发起不带参数的请求时，直接提供请求的 URL 地址和请求成功之后的回调函数即可，示例代码如下：

```
$.get('http://www.liulongbin.top:3006/api/getbooks', function(res) {
    console.log(res) // 这里的 res 是服务器返回的数据
})
```

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/Q4SBCAYARU)

#### 4.$get()发起带参数请求

```
$.get('http://www.liulongbin.top:3006/api/getbooks', { id: 1 }, function(res) {
    console.log(res)
})
```

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/YYSBCAYAK4)

### 4.$.post()

#### 1.作用

发起post请求,向服务器提交信息

#### 2.语法

```
$.post(url,[data],[callback])
```

| 参数名   | 参数类型 | 是否必选 | 说明                     |
| -------- | -------- | -------- | ------------------------ |
| url      | string   | 是       | 提交数据的地址           |
| data     | object   | 否       | 要提交的数据             |
| callback | function | 否       | 数据提交成功时的回调函数 |

#### 3.$.post()向服务器提交数据

```
$.post(
   'http://www.liulongbin.top:3006/api/addbook', // 请求的URL地址
   { bookname: '水浒传', author: '施耐庵', publisher: '上海图书出版社' }, // 提交的数据
   function(res) { // 回调函数
      console.log(res)
   }
)
```

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/WUSRCAYB2A)

### 5.$.ajax()

#### 1.功能

发起post或get请求

#### 2.语法

```
$.ajax({
   type: '', // 请求的方式，例如 GET 或 POST
   url: '',  // 请求的 URL 地址
   data: { },// 这次请求要携带的数据
   success: function(res) { } // 请求成功之后的回调函数
})
```

#### 3.$.ajax()发起get请求

```
$.ajax({
   type: 'GET', // 请求的方式
   url: 'http://www.liulongbin.top:3006/api/getbooks',  // 请求的 URL 地址
   data: { id: 1 },// 这次请求要携带的数据
   success: function(res) { // 请求成功之后的回调函数
       console.log(res)
   }
})
```

#### 4.$.ajax()发起post请求

```
$.ajax({
   type: 'POST', // 请求的方式
   url: 'http://www.liulongbin.top:3006/api/addbook',  // 请求的 URL 地址
   data: { // 要提交给服务器的数据
      bookname: '水浒传',
      author: '施耐庵',
      publisher: '上海图书出版社'
    },
   success: function(res) { // 请求成功之后的回调函数
       console.log(res)
   }
})
```





## 4.接口

### 接口的概念

使用 Ajax 请求数据时，被请求的 URL 地址，就叫做数据接口（简称接口）。同时，每个接口必须有请求方式。

例如：

http://www.liulongbin.top:3006/api/getbooks  获取图书列表的接口(GET请求)

http://www.liulongbin.top:3006/api/addbook   添加图书的接口（POST请求）

### 分析接口的请求过程

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/XQTBCAYAUY)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/X4TBCAYA7Q)

### 接口测试工具

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/3MTBCAYA2A)

### 接口文档

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/QATRCAYAYM)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/QITRCAYBEE)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/QUTRCAYADY)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/RATRCAYAYM)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/RMTRCAYATQ)

## 5.案例1-图书管理系统

1. 使用的库和插件

2. - css库:bootstrap.css
   - js库:jquery.js
   - vscode插件:Bootstrap3 Snippets

3. 主要功能

实现对图书的增删改查功能

1. 用到的技术

2. - ajax

发起网络请求,从服务器获取数据,提交数据到服务器

- - jquery

简化ajax网络请求操作

- - bootstrap3

ui库,快速构建统一风格ui

- - 后端

express,快速构建短,平,快的后台服务器,实现对图书表的增删改查,并与前端进行数据交互



![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/JIUBCAYA24)

## 6.案例2-聊天机器人

------



# form表单与模板引擎

## *目标

- - form表单常用属性
  - 阻止表单的默认提交行为
  - 使用jQuery快速获取表单数据
  - 如何安装和使用模板引擎
  - 模板引擎的实现原理

## 1.Form表单的基本使用

### 1.什么是表单

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/YMVREAYA2A)

### 2.表单的组成部分

- - 表单标签
  - 表单域

表单域：包含了文本框、密码框、隐藏域、多行文本框、复选框、单选框、下拉选择框和文件上传框等。

- - 表单按钮

```
<form>
    <input type="text" name="email_or_mobile" />
    <input type="password" name="password" />
    <input type="checkbox" name="remember_me" checked />
    <button type="submit">提交</button>
</form>
```

### 3.表单属性

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/IAWBEAYADY)

#### 1.action

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/S4WBEAYAZM)

#### 2.target

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/VYWBEAYA24)

#### 3.method

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/XYWBEAYAK4)

#### 4.enctype

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/Y4WBEAYAYU)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/2IWBEAYA2Q)

### 4.表单的同步提交及缺点

#### 1.什么是表单的同步提交

> 通过点击 submit 按钮，触发表单提交的操作，从而使页面跳转到 action URL 的行为，叫做表单的同步提交。

#### 2.表单同步提交的缺点

- - - <form>表单同步提交后，整个页面会发生跳转，跳转到 action URL 所指向的地址，用户体验很差。
    - <form>表单同步提交后，页面之前的状态和数据会丢失。

#### 3.如何解决表单同步提交的缺点

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/OEWREAYAPY)



## 2.通过Ajax提交表单数据

### 1.监听表单提交事件

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/6MWREAYBZM)

### 2.阻止表单默认提交行为

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/DMXBEAYBYM)

### 3.获取表单中的数据

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/HIXBEAYARU)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/KUXBEAYAYI)



## 3.案例-评价列表

### 1.ui

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/EI2REAYAZM)

### 2.功能

1. 1. 1. 获取服务器评论列表并在页面显示
      2. 提交评论到后台并实时刷新

### 3.主要技术

1. 1. 1. ajax提交表单数据
      2. ajax网络请求
      3. bootstrap3
      4. ......

## 4.模板引擎的基本概念

### 1.渲染UI结构时遇到的问题

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/YSBREAYA7Q)

### 2.什么是模板引擎

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/3SBREAYA2Q)

### 3.优点

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/6CBREAYA2Q)

## 5.art-template模板引擎

### 1.简介

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/DGCBEAYAYM)

### 2. 安装

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/FWCBEAYAZI)

### 3.使用步骤

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/I6CBEAYA7Q)

### 4.art-template语法

#### 1.标准语法

art-template 提供了 `{{ }}` 这种语法格式，在 `{{ }}` 内可以进行变量输出，或循环数组等操作，这种 `{{ }}` 语法在 art-template 中被称为标准语法。

#### 2.输出

在 `{{ }}` 语法中，可以进行变量的输出、对象属性的输出、三元表达式输出、逻辑或输出、加减乘除等表达式输出。

```js
{{value}}
{{obj.key}}
{{obj['key']}}
{{a ? b : c}}
{{a || b}}
{{a + b}}
```

#### 3.原文输出(html输出)

如果要输出的 value 值中，包含了 HTML 标签结构，则需要使用原文输出语法，才能保证 HTML 标签被正常渲染。 

```js
{{@ value }}
```

- - - 4.条件输出

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/AOCREAYBRU)

#### 5.循环输出

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/ESCREAYA2Q)

#### 6.属性过滤器(可定义函数对属性值进行处理)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/JGCREAYATQ)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/KWCREAYA6E)

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/MCCREAYAGY)



## 6.案例-使用art-template实现新闻列表

### 1.效果

![img](https://www.kdocs.cn/api/v3/office/copy/ZlQ4RUYzSEpocVZpbnhGRC9JckVXNGNPMmFVeHVzY2tOMVVHcmtOMnQwZlI3VWVWcHIzSURyd0F0MlZ2WlNWQTdCRDBFZkpnUmFRYkU5NkxhTDY0d1dXOXhYU285dFhTeEt4NDRPaG5ROU1ETS9BdnkyeEh4L1hhWWd5TGR5LytiUCtWcUxNSkk4Z2FoTng4bnM3TTB3OXk2YjBwRkM0aWVEd1ZyNGcwblJTTEg4emlsS0t1WFAzRnVmdDZmbGpCTWxzMUNTTnZKUjk4MXFNeHZzSUhzcytFOGgzaXhsLzRpOW5aYktLcll0UmVDczZmZVVpVHphKzZXcG5Va1pJRDY1Y2pGcWlBR3ZRPQ==/attach/object/WGCREAYAZM)



### 主要功能

- - - 1.查询服务器新闻数据在界面上显示

### 3.主要技术

- - - 1.html css js分离
    - 2.art-template模板引擎
    - 3.ajax网络请求

## 7.模板引起实现原理

- - 1.正则表达式
  - 2.字符串替换



------

# 3.Ajax进阶

## *目标

- - 学会如何使用XMLHttpRequest发起Ajax请求
  - 学会如何封装自己的Ajax函数
  - 掌握XMLHttpRequest Level2中的新特性
  - 掌握jQuery中如何实现文件上传与loading效果
  - 掌握axios发起Ajax请求的方法

## 1.XMLHttpRequest基本使用

### 1.1什么是XMLHttpRequest

- - - XMLHttpRequest(简称xhr)是浏览器提供的JavaScript对象
    - 可以请求服务器数据资源

## 2.axios基本使用

axios是专门用于网络请求的库,基于promise