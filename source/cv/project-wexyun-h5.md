---
title: 云金融平台 H5 端（refactor）
date: 2018-09-03 16:31:43
---

> [返回简历首页](/cv)

## 本人职责

前端架构 & 组件库开发 & 关键代码编写 & code rereview

## 项目起止时间

2018/01 ~ 至今

### 项目描述

- 此项目为金融产品交易平台重构，包含交易/充值/提现/订单管理等功能 （[详情](/cv/project.html)）
- UI 库基于开源组件库 [vant](https://youzan.github.io/vant/#/zh-CN/intro)（MIT），根据项目需求二次开发
- 技术栈：
  - typescript/es6
  - webpack/vue.js/vue-router/vuex
  - http 库：axios，自行封装 api.js 处理后端返回的状态码，采用 mock.js 进行接口模拟
  - 表单同步验证：vuelidate
  - 数据可视化：echarts
  - css 后处理：postcss
  - css 规范：BEM

#### 项目地址

N/A（内部项目，暂未部署到外网）

### 像素级还原设计稿:

![](http://stariveer.qiniudn.com/projects/20180132/%E6%88%AA%E5%9B%BE.png)

### 脚手架说明

项目组采用统一的 eslint 配置和 js/css/vue/html format 工具:

![](http://stariveer.qiniudn.com/projects/20180132/104544.png)

<hr>

src 主要目录说明:

![](http://stariveer.qiniudn.com/projects/20180132/105049.png)

<hr>

postcss 变量:

![](http://stariveer.qiniudn.com/projects/20180132/105246.png)

<hr>

icon 库,使用时仅需采用约定的 class:

![](http://stariveer.qiniudn.com/projects/20180132/105324.png)

### 预定义公共组件(与业务流程无关):

![](http://stariveer.qiniudn.com/projects/20180132/1520849954126.jpg)

## 魔鬼在细节:

### 使用 rem 实现等比缩放

![](http://stariveer.qiniudn.com/projects/20180132/2018-03-14%2018_25_32.gif)

### 表单所有必填项不为空时提交按钮才可以点击 & input 获取焦点时显示清空按钮 &输入手机号自动处理为 3-4-4 格式

![](http://stariveer.qiniudn.com/projects/20180132/2018-03-14%2018_38_13.gif)
