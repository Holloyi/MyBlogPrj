---
title: NodeJs学习笔记
tags: [NodeJs,Web,笔记]
categories: 前端
date: 2022-09-01
updated:  2022-09-01
description: 黑马NodeJs学习笔记
top_img: https://static.runoob.com/images/mix/code-wallpaper-6.png
cover: https://static.runoob.com/images/mix/code-wallpaper-6.png
connents: 
aside: true
--- 

## 简介

1. 浏览器如何运行JavaScript代码?

浏览器中有JavaScript运行环境(解析引擎+WebApi包)

1. Node.js是什么

Chrome V8解析引擎 + API包(不包括浏览器特有的API包如DOM、POM、AJax，但有一个Node.js特有的)

1. Node.js可以干嘛?

无需浏览器即可运行JavaScript代码，可使用JavaScript进行后端开发

1. 总结

2. - 浏览器,JavaScript前端运行环境
   - Node.js,JavaScript后端运行环境

### 下载安装

1. 官网下载安装包

2. 1. LTS长期稳定版
   2. Current最新版

3. 傻瓜式安装即可

4. `node -v`查看版本号

------



## FS文件系统模块

### 简介

- fs模块是Node.js官方提供的、用来操作文件的模块

- fs模块提供了一系列方法和属性，满足用户对文件操作的需求

- - fs.readFile()
  - fs.writeFile()

- 导入fs

```
const fs = require('fs')
```

### 读取文件内容

#### 1.基本用法

```
const fs = require('fs');
fs.readFile("./files/test.txt",'utf8',function(err,dataStr){
    console.log(err)
    console.log('--------------')
    console.log(dataStr)
})
```

#### 2.判断是否读取成功

```
//1.导入fs模块
const fs = require('fs');
//2.使用fs.readFile()读取文件
fs.readFile("./files/test.txt","utf8",function(err,result){
    //如果err不为空,说明读取失败
    if(err){
        return console.log('文件读取失败! '+ err.message)
    }else{
        return console.log('文件读取成功,内容是: '+ result)
    }
})
```

### 向文件中写内容

#### 基本用法

```
//1.引入fs模块
const fs = require('fs');

//2.使用fs-writeFile()方法向文件中写入内容
/*
    参数说明
        参数1:文件存放路径
        参数2:要写入的内容
        参数3[可选]:以什么编码写入,默认utf8
        参数4:回调函数
*/

fs.writeFile("./files/test2.txt","Today is 2020-08-08","utf8",function(err){
    //如果文件写入成功,则err=null
    //如果文件写入失败,则err为一个对象
    if(err){//写入失败
        return console.log('文件写入失败! ' + err.message);
    }else{//写入成功
        console.log('文件写入成功!');
    }
})
```

#### 注意

- writeFile()只能创建文件,不能创建路径
- writeFile()会覆盖之前的内容,而不是追加

### 其他

- __dirname 表示当前文件所处的目录

------



## Path路径模块

- path模块是node.js官方提供的、用来处理路径的模块。
-  提供了一系列方法和属性，用来满足对路径的处理需求

例如：

> path.join()方法:将多个路径片段拼接成一个完整路径
> path.basename()方法:从路径中解析出文件名

### path.join()

- 作用:拼接路径

### path.basename()

- 作用:获取路径中的最后一部分,常使用该方法获取路径中的文件名
- 语法

```
/*
    参数说明:
        参数1:path,文件路径
        参数2:ext,可选参数,文件拓展名
*/
path.basename(path[,ext])
```

- 示例

```
const path = require('path');

const fpath = "/a/b/c/index.html";

var fullName = path.basename(fpath);
console.log(fullName);

var nameWithoutExt = path.basename(fpath,".html")
console.log(nameWithoutExt);
```

### path.extname()

- 作用:获取拓展名
- 语法

```
//参数path,路径
path.extname(path)
```

- 示例

```
const path = require('path');

const pathStr = "/a/a/b/1.txt";

const extname = path.extname(pathStr);

console.log(extname);
```

------



## Http模块

### 简介

- http模块是Node.js官方提供的、用来创建web服务器的模块，通过http模块提供的http.createServer（）方法，可以创建一台服务器，对外提供web资源服务
- 导入：require('http')

### 创建最基本的web服务器

1. 导入http模块
2. 创建web服务器实例
3. 为服务器实例绑定request时间,监听客户端的请求
4. 启动服务器

```
//1.导入http模块
const http = require("http");

//2.创建web服务器实例
const server = http.createServer();

//3.为服务器绑定request事件,监听客户端的请求
server.on("request", (req, res) => {
  console.log("server has been visited!");
});

//4.启动服务器
server.listen(80,function(){
    console.log('server running at ...')
})
```

### req请求对象

- 只要服务器收到客户端的请求,就会调用通过server.on()为服务器绑定的request事件处理函数
- 通过req请求对象可以***\*访问与客户端相关的数据和属性,\****示例:

```
const http = require("http");

const server = http.createServer();

//req请求对象 包含了与客户端相关的数据和属性
server.on("request", (req, res) => {
  const url = req.url;
  const method = req.method;
  const str = `Your request url is ${url},and request method is ${method}`;
  console.log(str);
});

server.listen(80, () => {
  console.log("server running at http://127.0.0.1");
});
```

### res响应对象

- res是响应对象,包含与服务器相关的数据和属性
- res.end():向客户端发送指定的内容,并结束这次请求的处理过程

### 解决中文乱码问题

```
const http = require('http');

const server = http.createServer();

server.on('request',(req,res)=>{
    const str = `请求的url地址是${req.url},请求方法是${req.method}`;
    //设置utf-8
    res.setHeader("Content-type","text/html; charset=utf-8");
    res.end(str);
})

server.listen(80,()=>{
    console.log("server running at http://127.0.0.1")
})
```

### 时钟案例web服务器版本

```
//1.导包
const http = require("http");
const fs = require("fs");
const path = require("path");

//2.创建web服务
const server = http.createServer();

//3.开启监听
server.on("request", (req, res) => {
  //1.获取url
  var url = req.url;
  //2.获取文件路径
  const fpath = path.join(__dirname, url);
//   res.setHeader("Content-type", "text/html; charset=utf-8");
  //3.读取文件内容
  fs.readFile(fpath, "utf8", (err, dataStr) => {
    if (err) res.end("404 not found");
    res.end(dataStr);
  });
});

server.listen(80, () => {
  console.log("server running at http://127.0.0.1");
});
```

------



## 模块化

目标

- 模块化的好处
- CommonJs规定了哪些内容
- Node.js中模块的三大分类
- npm管理包
- 规范的包结构
- 模块的加载机制

### 模块化的概念

- 遵守固定的规则,把一个大文件拆成独立并相互依赖的多个小模块

模块化的好处

1. 提高代码的复用性
2. 提高代码的可维护性
3. 可以实现按需加载

### 模块化规范

> 模块化规范就是对代码进行模块化的拆分和组合时,需要遵循的规则

> 例如:
>   \+ 使用什么样的语法格式来引入模块
>   \+ 在模块中使用什么样的语法格式向外暴露成员

> 模块化规范的好处:降低沟通成本,方便各模块间的相互调用

### 模块分类

1. 内置模块(Node.js官方提供的)
2. 自定义模块(用户自定义的.js文件)
3. 第三方模块

### 模块加载

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/HHKAGAYAUQ)

### 模块作用域

> 在自定义模块中定义的变量,方法等成员,只能在当前模块内被访问

> 好处:防止全局变量污染

### 向外共享模块中的成员

1. module对象

> 在每个.js自定义模块中都有一个module对象,存储了和当前模块有关的信息,打印内容如下:

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/7LLAGAYAQU)

1. module.exports对象

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/EDMAGAYAWU)

```
//在一个自定义模块中,默认情况下,module.exports={}

const age = 20;

//向module.exports对象上挂载username属性
module.exports.username = "zs";

//向module.exports对象上挂载sayHello方法
module.exports.sayHello = function () {
  console.log("hello");
};

module.exports.age = age;
```

### 向外界共享成员时的注意点

使用require方法导入时,永远以module.exports指向的对象为准

```
//在一个自定义模块中,默认情况下,module.exports={}

const age = 20;

//向module.exports对象上挂载username属性
module.exports.username = "zs";

//向module.exports对象上挂载sayHello方法
module.exports.sayHello = function () {
  console.log("hello");
};

module.exports.age = age;

module.exports = {
  prop1: "test",
  sayHi() {
    console.log("hi");
  },
};
```

### exports对象

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/33MQGAYAUQ)

exports和module.exports的使用误区

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/NXNQGAYAPY)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/PDNQGAYAP4)

### Node.js中的模块化规范

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/NABAIAYAO4)

------

## Npm与包

### 包

#### 概念

> Node.js中的第三方模块又称为包

#### 来源

> 包是由第三方个人或团队开发出来的(开源)

#### 好处

- - Node.js内置模块仅提供了一些底层的API,导致在基于内置模块进行项目开发时,效率很低
  - 包是基于内置模块封装的,提供了更高级,更方便的api,极大的提高了开发效率
  - 包和内置模块之间的关系,类似于jQuery和浏览器内置API之间的关系

#### 从哪里下载包

- - 从 https://www.npmjs.com/ 网站上搜索自己所需要的包
  - 从 https://registry.npmjs.org/ 服务器上下载自己需要的包

#### 5. 如何下载包

- - 使用包管理工作:Node Package Manager(npm包管理工具)

#### 6. 包的分类

- - 项目包(被安装到项目的node_modules目录中的包)

  - - 开发依赖包(只会在开发阶段用到的包,记录在devDependencies节点的包)
    - 核心依赖包(在开发和项目上线阶段都会用到的包,记录在dependencies节点的包)

  - 全局包(安装在系统用户目录下,路径可通过环境变量更改)

#### 7. 包的结构

1. 1. 包必须以单独的目录存在
   2. 包的顶级目录必须包含package.json文件
   3. package.json中必须包含:name,version,main三个属性,分别表示包名,版本和入口

### 2. Nmp的使用

#### 简介

- - npm在安装node.js时会一同安装
  - npm (node package manager)node包管理工具

#### 常用命令

```
//1.查看npm版本
npm -v

/*
2.安装包  
    1)可一次安装多个包  用空格分割即可
    2)install可简写为 i
*/
npm install 包名1 包名2 ... 包名n

//3.安装开发阶段包
npm install packageName -D

//4.安装全局包
npm install packageName -g

//5.卸载包
npm uninstall packageName

//6.卸载全局包
npm uninstall packageName -g

//7.查看当前下载源
npm config get registry

//8.切换淘宝镜像
npm config set registry=https://registry.npm.taobao.org/
```

#### nrm

简介:nrm工具可以方便的切换镜像源

```
//1.全局安装nrm
npm install nrm -g

//2.查看所有可用镜像源
nrm ls

//3.切换镜像源
nrm use taobao
```

### 3.  开发及发布包

#### 包的功能

- - 格式化时间
  - html特殊字符转换
  - html特殊字符还原

#### 项目结构

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/XJDAMAYAFA)

- - package.json

```
{
    "name": "holloyi-tools",
    "version": "1.0.0",
    "main": "index.js",
    "description": "提供了格式化时间,HTMLEscape等功能",
    "keywords": [
        "holloyi",
        "dateFormat",
        "escape"],
    "license": "ISC"

}
```

- - index.js

```
//这是包的入口文件

const dateFormat = require("./src/dateFormat");
const htmlEscape = require("./src/htmlEscape");

// "..." 展开运算符
module.exports = {
    ...dateFormat,
    ...htmlEscape
};
```

- - dateFormat.js

```
//格式化时间的函数
function dateFormat(dateStr) {
  const date = new Date(dateStr);

  const Y = date.getFullYear();
  const M = padZero(date.getMonth() + 1);
  const D = padZero(date.getDay());
  const HH = padZero(date.getHours());
  const mm = padZero(date.getMinutes());
  const ss = padZero(date.getSeconds());

  return `${Y}-${M}-${D} ${HH}:${mm}:${ss}`;
}

//个位数前面补零的函数
function padZero(n) {
  return n > 9 ? n : "0" + n;
}

module.exports = {
  dateFormat,
};
```

- - htmlEscape.js

```
//转义HTML字符的函数
function htmlEscape(htmlStr) {
  return htmlStr.replace(/<|>|"|&/g, (match) => {
    switch (match) {
      case "<":
        return "%lt;";
      case ">":
        return "%gt;";
      case '"':
        return "&quot;";
      case "&":
        return "&amp;";
    }
  });
}

//还原转移html字符的函数
function htmlUnescape(escapeHtmlStr) {
  return escapeHtmlStr.replace(/%lt;|%gt;|&quot;|&amp;/g, (match) => {
    switch (match) {
      case "%lt;":
        return "<";
      case "%gt;":
        return ">";
      case "&quot;":
        return '"';
      case "&amp;":
        return "&";
    }
  });
}

module.exports = {
  htmlEscape,
  htmlUnescape,
};
```

- - README.md

````
## 安装
```
npm install holloyi-tools
```


## 导入
```js
const holloyi = require("holloyi-tools");
```


## 格式化时间
```js
//调动dateFormat对时间进行格式化
const dateStr = holloyi.dateFormat(new Date());
//结果: 2022-08-04 13:56:03
console.log(dateStr);
```

## 转义html中的特使字符
```js
//带转换的HTML字符
const htmlStr = '<h1 title="test">这是h1标题<span>123&nbsp;</span></h1>';
//调用htmlEscape方法进行转换
const escapeHtml = holloyi.htmlEscape(htmlStr);
//转换的结果:%lt;h1 title=&quot;test&quot;%gt;这是h1标题%lt;span%gt;123&amp;nbsp;%lt;/span%gt;%lt;/h1%gt;
console.log(escapeHtml);
```

## 还原html中的特殊字符
```js
//escapeHtml:待还原的字符   newHtmlStr:还原后的字符
const newHtmlStr = holloyiTools.htmlUnescape(escapeHtml);
//还原的结果:<h1 title="test">这是h1标题<span>123&nbsp;</span></h1>
console.log(newHtmlStr);
```

## 开源协议
ISC
````

#### 发布包

1. 注册npm账号

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/65EQMAYAQU)

1. 在命令行登录

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/BRFAMAYAZA)

1. 发布包

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/D5FAMAYAFA)

------



## 模块的加载机制

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/OBFAMAYA5E)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/PFFAMAYAXE)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/RNFAMAYALU)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/S5FAMAYAUA)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/UBFAMAYA5E)

------

## Express

### 目标

- - 能够使用express.static()快速托管静态资源
  - 能够使用express路由精简项目结构
  - 能够使用常见的express中间件
  - 能够使用express创建API接口
  - 能够在express中启用corss跨域资源共享

### 简介

- - express是基于Node.js平台,快速、开放、极简的web开发框架

  - 专门用来创建web服务器的第三方包

  - 作用，快速构建服务器

  - - 1.Web网站服务器，专门对外提供Web网页资源的服务器
    - 2.API接口服务器，专门对外提供API接口的服务器

### 基本使用

#### 安装

```
npm install express@4.17.1
```

#### 使用步骤

```
//1.导入express
const express = require('express')

//2.创建web服务器
const app = express()

//3.调用app.listen(端口号,回调函数) 启动服务器

app.listen(80,()=>{
    console.log('server running at http://127.0.0.1')
})
```

#### 监听get请求

```
//参数1:客户端请求的url地址
//参数2:请求对应的处理函数
//           req:请求对象
//           res:响应对象
app.get('/user',(req,res=>{
    //处理
})
```

#### 监听post请求

```
app.post('/add/user/',(req,res)=>{
    //处理
})
```

#### 把内容响应给客户端

通过res.send()方法,可以将处理好的内容响应给客户端

```
app.get("/user/list", (req, res) => {
  res.send([
    {name:'张三',age:18},
    {name:'李四',age:24},
  ])
});
```

#### 获取url中携带的参数

通过req.query()方法,可以获取客户端通过***\*查询字符串\****的形式,发送到服务器的参数

```
app.post("/user/add", (req, res) => {
  console.log(req.query);
  res.send(req.query);
});
```

#### 获取url中的动态参数

```
//URL地址中,通过':参数名'的形式,匹配动态参数值
app.get('/user/:id/:age',(req,res)=>{
  //req.params 默认为空对象{}
  //可以获取通过':'动态匹配到的参数值
  console.log(req.params)
  res.send(req.params)
})
```

### 托管静态资源

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/7E2AWAYA6U)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/BE2QWAYAR4)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/CU2QWAYAJA)

### 4. Nodemon第三工具包

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/K43AWAYADE)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/ME3AWAYADA)

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/OA3AWAYARM)

### 5. express路由 

#### 模块化路由

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/DU3QWAYASU)

- - - 创建模块化路由

```
//1.导入express
const express = require("express");
//2.创建路由
const router = express.Router();

//3.挂载路由
router.get("/user/list", (req, res) => {
  res.send("Get user list");
});

router.post("/user/add", (req, res) => {
  res.send("Post user add");
});

//向外暴露路由对象
module.exports = router;
```

- - - 使用模块化路由

```
const express = require("express");
const userRouter = require('./router/router')

const app = express();

app.use(userRouter)
```



#### 为路由模块添加前缀

![img](https://www.kdocs.cn/api/v3/office/copy/dmsxSUUyWDhBWm5Cd3JnTWdQczZUUkVZTCtLaTRvQ2l0eXM1dlFNZG5WSWUvY1ZDNC9rYTh6Rm5aWWpiR0lZbWVhNmQ0Sm1LTlFzcDcwSGs3OU0xVkt5RjZRODh4Rk9HUlN6dml3c1VqaTg4SG5IUGZIOWhMamdONUNuMmpZNVZwZHlSdlEzaDBZUUpENGxDSnZYZkdzRmtsWjFlTkdHL0JKeWRRTlNYb2ppdVFuVFhOUS9FakhmbWF1aFJIOFdiOUdCZVZwOXdHb1k4RWJ3dTNTY1VsazAzTENvQnNLZG5wenROT0lhZ1l1ZVM1KzFCcTQ0cE1nQzQxU1hIa2FJM2s0aGhLSk5sSzFZPQ==/attach/object/MY4AWAYAXU)

### 6. express中间件

### 7. express写接口

#### CROS解决跨域问题



------



## 数据库与身份认证

### 目标

- - 如何配置MySql数据库环境
  - 常用Sql语句
  - 在项目中操作MySql数据库
  - 了解Session的实现原理
  - 了解JWT的实现原理