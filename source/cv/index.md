---
title: 何星-个人简历
date: 2018-09-03 16:31:43
---

## 项目经验:

### 云金融平台 PC 端（refactor）

<div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/demo-pc.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/demo-pc1.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/demo-pc2.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/demo-pc3.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/demo-pc4.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/uikit/uikit4.png)</div>

#### 本人职责

前端架构 & 组件库开发 & 关键代码编写 & code rereview

#### 项目起止时间

2016/12 ~ 至今

#### 项目描述

- 此项目为金融产品交易平台重构，包含交易/充值/提现/订单管理等功能
- 立项阶段本人力推放弃支持 IE8，得以将技术栈从 gulp/jquery/requirejs 转向 webpack/vue.js，极大提升开发效率
- 基于[Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript/blob/master/README.md)、[Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css/blob/master/README.md)制定团队代码规范，并在项目中使用统一 eslint 配置，有效提升团队代码质量
- 制定团队 IDE（vscode）/插件配置指南，实现团队代码风格一致化
- 采用 git 工作流（gitflow），实现前端项目生命周期规范化
- 参考[Contributing to AngularJS](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md)制定团队 git commit 规范，[详见](/pic/cv/git-commit-rules.png)
- 基于开源 UI 组件库[uikit](http://www.getuikit.net/)(MIT)二次开发基础组件库，实现**开箱即用**，详见[wex-uikit](/cv/wex-uikit.html)
- 脚手架基于 vue cli 2.x，修改打包流程 spa => multi pages，并加入配置项，实现静态资源服务器 domain 配置化。解决了开发->联调->测试->上线各阶段部署需重复打包的问题，打包发布效率成倍提升。
- 技术栈：
  - typescript/es6
  - webpack/vue.js/vue-router/vuex
  - http 库：axios，自行封装 api.js 处理后端返回的状态码，采用 mock.js 进行接口模拟
  - 表单同步验证：vuelidate
  - 数据可视化：echarts
  - css 后处理：postcss

#### 项目地址

[https://demo.wexyun.com/](https://demo.wexyun.com/)（使用桌面浏览器打开）

---

### 云金融平台 H5 端（refactor）

![](/pic/cv/wap2.1.png)
<div style="vertical-align:top; display: inline-block;width: 66.666%">![](http://stariveer.qiniudn.com/projects/20180132/2018-03-14%2018_25_32.gif)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](http://stariveer.qiniudn.com/projects/20180132/2018-03-14%2018_38_13.gif)</div>

#### 本人职责

前端架构 & 组件库开发 & 关键代码编写 & code rereview

#### 项目起止时间

2018/01 ~ 至今

#### 项目描述

- 此项目为金融产品交易平台重构，包含交易/充值/提现/订单管理等功能 （[详情](/cv/project.html)）
- UI 库采用开源 UI 组件库 [vant](https://youzan.github.io/vant/#/zh-CN/intro)（MIT）
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

---

### 云金融商户管理平台

<div style="vertical-align:top; display: inline-block;width: 50%">![](/pic/cv/admin1.png)</div><div style="vertical-align:top; display: inline-block;width: 50%">![](/pic/cv/admin2.png)</div>

#### 本人职责

救火 & 关键代码编写

#### 项目起止时间

2016/07 ~ 2017/04

#### 项目描述

- 此项目为商户管理后台，包含交易/信贷/融资/运营/下载/运营等所有配置
- 此项目 owner 为其他团队，本人参与此项目是作为救火队员（cry 笑），并帮助其优化工作流和项目结构
- 技术栈：
  - es6
  - webpack/vue.js/vue-router/vuex/vue-resource
  - 表单同步验证：async-validator
  - 数据可视化：echarts
  - css 预处理：sass
  - css 规范：BEM
  - - lodash/vue-baidu-map/wangeditor etc...

#### 项目地址

N/A（内网项目）

---

### 云金融平台 H5 端

<div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/wap-2.0.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/wap-2.0-a.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/wap-2.0-b.png)</div>

#### 本人职责

前端架构 & 项目骨架代码编码

#### 项目起止时间

2016/07 ~ 2016/12

#### 项目描述

- 此项目为金融产品交易平台 H5 webapp 版，包含交易/充值/提现/订单管理等功能
- 此项目为了实现不同商户可共享前端组件，采取了 require.js + vue.js 的技术方案，后因不同商户间需求差异过大，无法很好抽象，未能很好实施
- 技术栈：
  - 工作流：gulp
  - mvvm framwork：vue.js
  - ui 库：light7
  - 自适应方案：rem
  - 使用 pdf.js 解析 pdf 格式文件

#### 项目地址

[https://demo.wexyun.com/](https://demo.wexyun.com/)（使用 mobile 浏览器打开）

---

### 云金融平台 PC 端（legacy）

<div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/xlubank.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/xlubank-3.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/xlubank-4.png)</div>

#### 本人职责

主导脚手架重构，前后端分离，代码优化等

#### 项目起止时间

2015/10 ~ 2016/05

#### 项目描述

- 此项目为金融产品交易平台，包含交易/充值/提现/订单管理等功能
- 此项目为前同事 legacy 项目，需兼容 IE8，接手时前后端未分离，本人力推并主导前端实现全站 restful 接口化
- 技术栈：
  - 工作流：grunt + shell => gulp，**打包时间缩短 60%**，本人**独自**完成重构
  - html+css 由于历史原因未组件化，本人着手将其拆分，抽象，加入 sass 预编译，形成组件
  - js 框架：jquery
  - 数据可视化框架：echarts
  - 模板引擎：nunjucks => swig.js
  - js 组件化：require.js
- 打包流程加入 trick：通过 velocity 模板变量实现静态资源服务器域名后端配置，解决了开发->联调->测试->上线各阶段部署需重复打包的问题

#### 项目地址

[https://www.xlubank.com/](https://www.xlubank.com/)

---

### 企业魔方

<div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/qiyemofang.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/qiyemofang1.png)</div><div style="vertical-align:top; display: inline-block;width: 33.333%">![](/pic/cv/qiyemofang2.png)</div>

#### 本人职责

**独立完成**前端从选型到编码的所有工作任务

#### 项目起止时间

2015/10 ~ 2016/04

#### 项目描述

- 此项目为企业内部管理 H5 Webapp，包含存钱罐、圈子、工资单、通知、消息系统、个人设置等模块
- 技术栈：
  - 工作流：gulp，使用 gulp-file-include 解决 dev html 复用，使用 gulp-rev + gulp-rev-collector 解决静态资源缓存问题
  - css 预编译：sass
  - 模板引擎：swig.js
  - js zepto
  - js 组件化：require.js
  - ui 框架：YO
  - 其他：选择 rem 为自适应解决方案，使用 iconfont
- 在本人强烈要求下，公司前端版本管理 **svn => git**

#### 项目地址

[https://m.cubepart.com](https://m.cubepart.com)

---

## side project

### 云金融前端手册

![](/pic/cv/doc.jpg)

#### 本人职责

制定前端规范，编写入职培训手册，介绍 wiki/jira/jenkis/gitlab 等系统

#### 项目起止时间

2016/10 ~ 至今

#### 项目描述

- 使用 gitbook 搭建

#### 项目地址

[云金融前端开发手册](/frontend-doc/)（已 remove 敏感信息，仅作为何星个人展示）
