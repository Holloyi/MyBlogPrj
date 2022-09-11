---
title: hexo搭建个人博客
tags: [Hexo,Nodejs,Git,建站]
categories: 建站
date: 2022-09-10
description: 记录Hexo搭建个人博客步骤及遇到的问题
top_img: https://i.loli.net/2020/01/20/BdaA59flE4bMoCr.jpg
cover: https://i.loli.net/2020/01/20/BdaA59flE4bMoCr.jpg
aside: true
---

## 环境准备

> 时间: 2022-09-09
>
> 系统环境:win7 win10 win11
>
> NodeJs: Nodejs12.0及以上
>
> Git: 2.37.3 最新版
>
> Hexo: 20220909最新版

1. 安装NodeJs

​	直接到官网上下载安装即可https://nodejs.org/en/download/

	+  Node.js (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
	+  Node.js 自带npm(npm是nodejs包管理工具)

2. Git

   1. 官网下载[Git 安装包](https://git-scm.com/)
   2. Git配置
      1. 配置用户名`git config --global user.name "yourname"`
      2. 配置邮箱`git config --global user.email "youremail"`
      3. 生成密钥`ssh-keygen -t rsa -C "youremail"`
      4. 配置公钥:复制id_ras.pub文件内容到github中添加密钥
      5. github创建token用于身份认证

3. Hexo

   npm下载hexo `npm install -g hexo-cli`

4. 检查是否成功

   ```
   node -v
   git version
   hexo -v
   ```

   

## Hexo搭建本地博客

1. cmd cd项目文件夹中
2. 执行 hexo init myblog
3. cd 到myblog目录下
4. 执行npm install 安包
5. 执行hexo命令 `hexo g`编译
6. 执行hexo命令 `hexo s`本地运行
7. 此时本地博客已成功运行  浏览器访问即可
8. 

## Github上建站访问

1. 新建github仓库

仓库名称限制了为你的：用户名+.github.io

1. 在项目下

```
npm install hexo-deployer-git --save
```

\3. 修改hexo配置文件指定仓库路径

- - 打开_config.yml文件
  - 配置deploy

```
deploy:
  type: git
  repo: https://github.com/Holloyi/Holloyi.github.io.git
  branch: main
```

4.推送站点到github

```
hexo d
```



## 主题配置(以butterfly为例)

1. 在项目的themes文件夹下面通过git clone下载主题文件
2. 在_config.yml文件中配置主题名称
3. ....

具体参见butterfly官方文档