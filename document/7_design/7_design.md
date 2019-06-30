# 挣闲钱money 软件设计文档

## 1、技术选型

- 整个项目为web开发，采用前后端分离的设计进行。
### 技术栈
分为三大块：前端(Vue)、后端(NodeJS)、数据库(MongoDB)

- 前端基于 Vuex+axios实现，UI框架使用了[Vant](https://youzan.github.io/vant/)，是一个简洁美观的框架，轻量、可靠的移动端 Vue 组件库。

- 后端选用nodejs，框架采用的是 Koa。一个新的 web 框架，由 Express 幕后的原班人马打造。

- 数据库选用MongoDB，基于分布式文件存储的数据库，旨在为WEB应用提供可扩展的高性能数据存储解决方案。

## 2、架构设计

### 逻辑架构

- 表示层： 
-- 前端作为表示层，提供服务的显示，问卷管理系统、用户管理系统等。

- 业务层： 
-- 后端及为业务层，根据表示层的请求，完成各种操作逻辑，形成各个模块，向系统提供各种不同的功能。

- 数据层： 
-- 采用mongodb为程序提供数据层服务。


### 项目结构

- 前端front-end目录结构：
  
```
├─axios
│  └─interface
├─build
├─config
├─src
│  ├─assets
│  ├─router
│  └─views
│      ├─......
├─static
│      ├─clear-default.css
└─vuex
    └─index.js
    └─modules
        └─about.js
        └─home.js
        └─mine.js
        └─publish.js
```
-- axios-interface：对axios进行二次封装后的一些api
-- assets：部分资源
-- router：路由配置     
-- views：路由页面
-- static：默认格式
-- index.js：主界面样式
-- modules：页面代码

- 后端back-end目录结构：
```
├─app
│  ├─controllers
│  ├─models
│  └─utils
└─routes
│   └─api
├─app.js
├─config.js
├─package.json
├─README.md
```
-- controller：逻辑处理的控制类
-- model：数据结构类的定义
-- util：部分使用的组件
-- router：路由模块
-- config：全局配置文件
-- package：nodejs包信息

## 3、模块划分

### 1. 注册登录的主界面模块

  - 打开web服务后的第一个界面。用户可以在此进行注册、登录。

 ![](http://wx3.sinaimg.cn/mw690/932e8e0cly1g4ibubt6luj209o09ta9w.jpg)

### 2. 子界面管理模块

  - 分为四个子界面模块，分别为参与问卷模块、发布问卷模块、查看问卷模块以及我的信息模块。
  
-- 参与问卷模块

![](http://wx3.sinaimg.cn/mw690/932e8e0cly1g4ibueqhoaj20dg0nlmx1.jpg)

-- 发布问卷模块

![](http://wx1.sinaimg.cn/mw690/932e8e0cly1g4ibu8obe1j20dj0ngglk.jpg)

-- 查看问卷模块

![](http://wx4.sinaimg.cn/mw690/932e8e0cly1g4ibu5dw6kj20dg0nht8y.jpg)

-- 我的信息模块

![](http://wx2.sinaimg.cn/mw690/932e8e0cly1g4ihze2nxlj20dm0nrwed.jpg)


## 4、软件设计技术

### 1. 洋葱模型
在nodejs中广泛使用的一种设计模式，将一个比较复杂的逻辑分解为几个小事件。把前一个函数当做参数传递给后一个函数，实现把多个函数串联后执行复杂逻辑的效果。


### 2. 设计模式
- 采用典型的MVC模式

-- Model为后端model类的设计

-- View为前端页面设计

-- Controller为后端controller类的设计
