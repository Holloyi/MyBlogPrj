---
title: Vue2学习笔记
tags: [Vue2,Web,框架,笔记]
categories: 前端
date: 2022-09-10
updated:  2022-09-10
description: 黑马Vue2学习笔记
top_img: https://static.runoob.com/images/mix/code-wallpaper-22.jpg
cover: https://static.runoob.com/images/mix/code-wallpaper-22.jpg
connents: 
aside: true
---

## 前端工程化与webpack

### 前端工程化

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/KCOCCAYA3E)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/OGOCCAYAHY)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/P6OCCAYATM)

### webpack基本使用

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/V6OCCAYATM)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/Z6OCCAYBKY)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/4COCCAYAKU)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/7GOCCAYAIY)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/BGOSCAYACY)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/DCOSCAYAWY)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/E2OSCAYAMY)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/G2OSCAYAQY)

------

## 六大指令

### 简介

- - 指令(directives)是vue为开发者提供的模板语法,用于辅助开发者渲染页面的基本结构

  - vue中的指令***\*按用途\****可以分为以下6类:

  - 1. 内容渲染指令
    2. 属性绑定指令
    3. 事件绑定指令
    4. 双向绑定指令
    5. 条件渲染指令
    6. 列表渲染指令

### 内容渲染指令

- - v-text

v-text会覆盖原内容

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/52PCCAYBF4)

- - `{{}}`

插值表达式,最常用,可写js表达式进行简单处理

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/AWPSCAYAUQ)

- - v-html

用于渲染html文本

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/GSPSCAYA3M)

### 属性绑定指令

- - v-bind

作用:动态的为元素的属性绑定属性值

例:

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/PKPSCAYACY)

- - 简写  ":"

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/TCPSCAYAMU)

- - 属性绑定指令中可写js表达式,进行简单处理

### 事件绑定指令

- - v-on

  - - 作用:为dom元素绑定事件监听
    - 语法:

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/DWQCCAYAPM)

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/F6QCCAYARM)

- - 简写 "@"
  - 事件参数对象

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/O6QCCAYAH4)

- - $event

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/TGQCCAYARE)

- - 事件修饰符

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/XOQCCAYAQY)

- - 按键修饰符

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/4OQCCAYAKE)

### 双向数据绑定

- - v-model
  - 作用:绑定表单元素,实现双向数据绑定
  - 修饰符

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/MSQSCAYAFY)

### 条件渲染指令

- - v-if and v-show

  - - 作用: 控制dom元素的显示与隐藏

    - 区别

    - - 1.实现方式不同

      - - v-if 指令会动态地创建或移除 DOM 元素，从而控制元素在页面上的显示与隐藏；
        - v-show 指令会动态为元素添加或移除 style="display: none;" 样式，从而控制元素的显示与隐藏；

      - 2.性能销毁不同

      - - v-if 有更高的切换开销,如果在运行时条件很少改变，则使用 v-if 较好
        - v-show 有更高的初始渲染开销,如果需要非常频繁地切换，则使用 v-show 较好

  - v-else

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/MCRCCAYAFE)

- - v-else-if

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/PGRCCAYAHY)

### 列表渲染指令

- - v-for

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/E6RSCAYATM)

- - v-for中的索引

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/J6RSCAYATM)

- - 使用key维护列表的状态

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/NCRSCAYAH4)

- - key的注意事项

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/Q2RSCAYAGY)

------

## 过滤器、侦听器、计算属性

## 组件

## 生命周期

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/DMICGAYAAU)

## 组件间数据传输

### 父传子

- - - 父传子,通过***\*自定义属性\****实现,具体步骤如下

    - 1. 在子组件中定义props(自定义属性)
      2. 父组件使用子组件时,通过子组件的自定义属性传值
      3. 示例如下

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/UMICGAYAUM)

### 子传父

- - - 子传父,通过***\*自定义事件\****实现,具体步骤如下

    - 1. 在子组建中通过$emit('事件名',参数...)触发事件
      2. 在父组件中通过 @事件名='函数名'监听事件,并在函数中作处理
      3. 示例如下

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/O4JCGAYAAY)

### 任意传值

- - - 在vue2.0中,通过***\*EventBus\****实现任意传值
    - 步骤

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/GUJSGAYAYE)



- - - 示例

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/DAJSGAYAYE)

## Ref引用

- - 作用:辅助开发者在不依赖jQuery的情况下,获取DOM元素或组件的引用
  - this.$nextTick(cb)方法

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/UQJSGAYASE)

## 动态组件、插槽、自定义指令

## 路由

### 前端路由

#### SPA与前端路由

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/GD4SSAYBRA)

#### 前端路由

​      Hash地址与组件之间的对应关系

#### 前端路由的工作方式

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/O34SSAYA3I)

#### 手撸前端路由

1. 1. 1. 通过  标签，结合 comName 动态渲染组件。示例代码如下：

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/6P4SSAYAUM)

1. 1. 1. 在 App.vue 组件中，为  链接添加对应的 hash 值

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/A35CSAYAUM)

1. 1. 1. 在 created 生命周期函数中，监听浏览器地址栏中 hash 地址的变化，动态切换要展示的组件的名称：

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/CX5CSAYAJ4)

### vue-router的基本使用

#### vue-router简介

vue-router 是 vue.js 官方给出的路由解决方案。它只能结合 vue 项目进行使用，能够轻松的管理 SPA 项目 中组件的切换

#### vue-router安装和配置

1. 1. 1. 安装vue-router包
      2. 创建src/router/index.js

```
//导入Vue和VueRouter
import Vue from 'vue'
import VueRouter from 'vue-router'

//Vue使用VueRouter插件
Vue.use(VueRouter)

//创建router对象
const router = new VueRouter({
  //配置路由规则
  routes: [
    { path: '/', redirect: '/login' },
    {
      path: '/login',
      component: Login
    },
    {
      path: '/home',
      component: Home,
      children: [
        { path: 'users', component: Users },
        { path: 'userinfo/:id', component: UserDetail, props: true }
      ]
    }
  ]
})

//全局前置守卫
router.beforeEach((to, from, next) => {
  const pathArr = ['/home', '/home/users', '/home/rights']
  if (pathArr.indexOf(to.path) !== -1) {
    const token = localStorage.getItem('token')
    if (token) {
      next()
    } else {
      next('/login')
    }
  } else {
    next()
  }
})

//向外暴露router对象
export default router
```

1. 1. 1. 在main.js文件中导入并挂载路由模块

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/EL5SSAYA2U)

1. 1. 1. 声明路由连接和占位符

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/ND5SSAYAJ4)

### vue-router的常见用法

1. 路由重定向

2. 嵌套路由(子路由)

3. 声明式子路由连接和子路由占位符

4. 动态路由

5. 1. 动态路由
   2. $route.params
   3. props

6. 声明式导航 编程式导航

7. 路由守卫

### 后台管理案例

------

## 其他

### Vue中"@"的使用

- - "@"代表这src目录
  - 使用"@"代替"./"  "../" 更加清晰
  - 实现原理,别名配置

### Vue的特性

- - 数据驱动视图
  - 双向数据绑定
  - Vue-MVVM模式

### Vue的指令

#### 1.分类

![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/HDXBQAYAZI)

#### 2.内容指令

内容渲染指令用来辅助开发者渲染 DOM 元素的文本内容

- - - v-text    会覆盖
    - `{{}}`         占位符,里面可写简单js
    - v-html   针对于html文本

#### 3.属性指令

- - - v-bind:属性名    为元素的属性动态绑定值
    - 简写    :

#### 4.事件指令

- - - v-on:click v:on:input

    - 简写:@click   @input

    - 事件参数对象

    - 事件修饰符

    - - prevent,阻止跳转
      - stop,阻止事件穿透,冒泡

    - 按键修饰符

#### 5.双向绑定指令

- - - v-model

#### 6.条件指令

- - - v-if
    - v-else
    - v-else-if

#### 7.列表指令

- - - v-for























![img](https://www.kdocs.cn/api/v3/office/copy/T0pBeFNINXRwOTdzWkxBZEo5TjZ1ZFJwY215aUxoL3FXWE1oeEYyWEIxRUpqOEdNcDQrSnFWMWRWekZkQnFLLzcvUWxqdFRLZVlUTGdoMWVMSGVXS1FOSUk4K3VvMkxQSVpYazNuWXd1U0Y2dkU2Y05nN0NuM3pYV3hEUmphVGtGZWxoUkx6V0tNSUc2V2xiM290OGFyZTQwYy9Qa0R6M3Bid0g1YjBVWW5CQVorOURlMXhDM2N0MUZwakthM1U0dTJjdmJUK2R6amdZMEVwMWkrRGRrRGdWR050bHhycXpHQ0ZyYjdLNkk4QXBTazNOKzludjRvM3lhWkt3SmlPWlhNUWpubFJqaFA4PQ==/attach/object/4BCBWAYARE)









------



### VSCode插件

#### path-autocomplete

- - - 作用:路径补全
    - 配置:在settings.json文件中添加如下配置

```
   //path-autocomplte插件设置
    //1.导入文件时是否携带拓展名
    "path-autocomplete.extensionOnImport": true,
    //2.配置@的路径提示
    "path-autocomplete.pathMappings": {
        "@": "${folder}/src"
    }
```







#### prettier

```
/*  prettier的配置 */
    "prettier.printWidth": 100, // 超过最大值换行
    "prettier.tabWidth": 4, // 缩进字节数
    "prettier.useTabs": false, // 缩进不使用tab，使用空格
    "prettier.semi": true, // 句尾添加分号
    "prettier.singleQuote": true, // 使用单引号代替双引号
    "prettier.proseWrap": "preserve", // 默认值。因为使用了一些折行敏感型的渲染器（如GitHub comment）而按照markdown文本样式进行折行
    "prettier.arrowParens": "avoid", //  (x) => {} 箭头函数参数只有一个时是否要有小括号。avoid：省略括号
    "prettier.bracketSpacing": true, // 在对象，数组括号与文字之间加空格 "{ foo: bar }"
    "prettier.disableLanguages": ["vue"], // 不格式化vue文件，vue文件的格式化单独设置
    "prettier.endOfLine": "auto", // 结尾是 \n \r \n\r auto
    "prettier.eslintIntegration": false, //不让prettier使用eslint的代码格式进行校验
    "prettier.htmlWhitespaceSensitivity": "ignore",
    "prettier.ignorePath": ".prettierignore", // 不使用prettier格式化的文件填写在项目的.prettierignore文件中
    "prettier.jsxBracketSameLine": false, // 在jsx中把'>' 是否单独放一行
    "prettier.jsxSingleQuote": false, // 在jsx中使用单引号代替双引号
    "prettier.parser": "babylon", // 格式化的解析器，默认是babylon
    "prettier.requireConfig": false, // Require a 'prettierconfig' to format prettier
    "prettier.stylelintIntegration": false, //不让prettier使用stylelint的代码格式进行校验
    "prettier.trailingComma": "es5", // 在对象或数组最后一个元素后面是否加逗号（在ES5中加尾逗号）
    "prettier.tslintIntegration": false // 不让prettier使用tslint的代码格式进行校验
```