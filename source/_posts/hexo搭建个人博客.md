---
title: hexo搭建个人博客
tags: [Hexo,Nodejs,Git,建站]
categories: 建站
date: 2022-09-10
update: 2022-09-16
description: 记录Hexo搭建个人博客步骤及遇到的问题
top_img: https://i.loli.net/2020/01/20/BdaA59flE4bMoCr.jpg
cover: https://i.loli.net/2020/01/20/BdaA59flE4bMoCr.jpg
aside: true
---





## 概述

+ Github作为博客仓库，并提供在线访问功能
  + Git版本管理工具，由于将代码提交到github中

+ NodeJs为开发环境
  + NodeJs提供JavaScript语言的运行环境
  + Npm为NodeJs包管理工具，用于在线下载第三方包（hexo包，hexo-deployer包）

+ Hexo为构建博客框架
  + hexo-deployer为hexo构建包，用于把markdown格式的文本编译成html、css、js等网页文件
+ Markdown
  + 一种文本格式，用于编写博客
  + typora markdown编辑器
  + 博文需要使用markdown格式

------

## 环境准备

+ 时间: 2022-09-09

+ 系统环境:win7、win10或win11都可

+ NodeJs: Nodejs12.0及以上

+ Git: 2.37.3 最新版

+ Hexo: 20220909最新版

1. 安装NodeJs

​	直接到官网上下载傻瓜式安装即可https://nodejs.org/en/download/

	+  Node.js (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
	+  Node.js 自带npm(npm是nodejs包管理工具)

2. Git

   1. 官网下载[Git 安装包](https://git-scm.com/)

   2. 傻瓜式安装

   3. Git配置

      鼠标右键在桌面打开`Git Bash`,然后在命令行中依次输入以下指令，每输入一行后按下回车键确定

       ![image-20220916230824851](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916230824851.png)

      1. 配置用户名`git config --global user.name "yourname"`

      2. 配置邮箱`git config --global user.email "youremail"`

      3. 生成密钥`ssh-keygen -t rsa -C "youremail"` 输入后连按4次回车，会在`C:\Users\admin\.ssh`目录下生产密钥文件

          ![image-20220916231357270](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916231357270.png)

      4. 配置公钥:复制id_ras.pub文件内容到github中添加密钥

         ![image-20220916231847660](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916231847660.png)

         ![image-20220916232013168](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232013168.png)

      5. github创建token用于身份认证

         setting---左下角的“Developer settings”-“Generate new token“名字任取，下面的全选，创建即可，创建后将token复制保存，后面会用到

         ![image-20220916232246402](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232246402.png)

          ![image-20220916232321207](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232321207.png)

         

3. Hexo

   在cmd窗口中使用npm安装Hexo开发包

   npm下载hexo `npm install -g hexo-cli`

    ![image-20220916232452814](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232452814.png)

4. 检查是否成功

   在cmd窗口中，输入以下指令，检查nodejs、git、hexo的版本，如果能看到版本号则证明环境安装成功

   ```
   node -v
   git version
   hexo -v
   ```

    ![image-20220916232625925](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232625925.png)

------

## Hexo搭建本地博客

1. 在项目目录下打开cmd窗口

输入cmd按回车

![image-20220916232754277](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232754277.png)

![image-20220916232808853](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232808853.png)

 ![image-20220916232853694](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916232853694.png)

2. 在cmd中执行 hexo init myblog（该指令会初始化项目结构，生成项目相关文档，myblog为项目文件夹名称 可任取）

    ![image-20220916233014904](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233014904.png)![](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233037736.png)

3. cd 到myblog目录下

 ![image-20220916233139774](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233139774.png)

4. 执行npm install 下载相关依赖包

 ![image-20220916233214774](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233214774.png)

4. 执行hexo命令 `hexo g`编译（该指令会将markdown文件编译成html、css、js等web前端文件，用于在浏览器中显示）

 ![](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233311864.png)

5. 执行hexo命令 `hexo s`本地运行

 ![](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233332896.png)

6. 在浏览器中访问http://localhost:4000/

 ![](https://raw.githubusercontent.com/Holloyi/MyGallery/main/badminton/image-20220916233452311.png)

7. 以上本地博客已经搭建完成

------

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