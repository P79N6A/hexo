---
title: Live App 页面布局
date: 2015-05-28 21:12:59
tags: [live app]
category: [front-end, css]
---

## 一些知识

### 屏幕宽高比

- 主流安卓 720p 手机 720/1280=0.5625
- 主流安卓 1080p 手机 1080/1920=0.5625
- 主流安卓 1440p 手机 1440/2560=0.5625
- iPhone5 640/1136≈0.56
- iPhone6 750/1334≈0.56
- iPhone6P 1242/2208≈0.56 (实际运行分辨 1080p)

[查看更多](http://www.gameui.cn/cc)

### iPhone 的状态栏(信号电量栏)高度:40px

### iPhone 微信的返回栏高度 88px

- 微信浏览器可视高度 - iphone5 1136-40-88=1008px - iphone4 960-40-88=832px

### 关于 dppx

#### dpr(Device Pixel Ratio 设备像素比)

上面所说的 px 是设备像素(Device Pixels),对于我们在 web 开发中接触到的是 css 像素(CSS Pixel),retina 屏幕出现以后,设备像素和 css 像素不再是 1:1 的关系.各厂家和平台通常会通过一个比值 dpr 将分辨率转换为一个较为便于开发的像素.打个比方说,iPhone5 的设备像素是 640x1136,它的 dpr 是 2,所以在 web 页面的 css 计算中需要将 640x1136 除以 2,按 320x568 计算

#### dppx: Number of dots per px unit. (每像素包含点的数量)

dppx 在数值上等于 dpr

![](http://stariveer.qiniudn.com/blog/150528/dpr_scr.jpg)

[查看更多设备的 dppx](http://dpi.lv)

#### dpi

题外话,dpi 是设备分辨率(Device Pixels)和设备物理尺寸(单位:英寸)之间的比值,跟我们 web 前端开发没有一毛钱关系,我们不要理它.

---

<span style="color:red">此分隔线以下所有内容均指 css 像素,不再讨论设备像素<span>

## 极端宽高比

- iPhone4 在微信浏览器中 320x416
- iphone5 在 safari 桌面快捷方式中(无地址栏) 320x548

![](http://ww4.sinaimg.cn/large/456d4a33gw1esj8u2evdnj202802w3y9.jpg)
![](http://ww1.sinaimg.cn/large/456d4a33gw1esj8vf3i01j202803t3y9.jpg)

## 一些案例

### 有道云笔记 乱入学霸の世界

[链接](http://note.youdao.com/xuebagame/)

- 布局方式:流式布局
- 向下兼容:主体部分高度不变

![416](http://stariveer.qiniudn.com/blog/150528/app_1_416.png)
![528](http://stariveer.qiniudn.com/blog/150528/app_1_528.png)

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no">
```

```javascript
if (client_height < 540 && client_height > 500) {
  $('body').addClass('hehe_screen')
}
if (client_height < 420) {
  $('body').addClass('very_low_screen')
} else if (client_height < 500) {
  $('body').addClass('low_screen')
}
```

```css
.very_low_screen .q_0_container {
  margin-top: -150px;
}
```

### 淘宝网|万能时装屋

[链接](http://tbnewwave.cdnpe.com/)

- 纯图片素材,无文字,无表单
- 布局方式:采用百分比绝对定位
- 向下兼容:尽量保持主要区域可见.可以看见对于高度极端不足的 iphone4 屏幕实际上是舍弃了(东西点不到)
- 整个页面未写 height 属性,所有`background-image`容器均使用`padding-bottom`撑出高度

![416](http://stariveer.qiniudn.com/blog/150528/app_2_416.png)
![528](http://stariveer.qiniudn.com/blog/150528/app_2_528.png)

```html
<meta name="viewport" content="initial-scale=1.0, maximum-scale=1.0">
```

```css
html,
body {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
```

```css
.sprue {
  position: absolute;
  left: 18.06%;
  top: 0.2%;
  width: 82.28%;
  padding-bottom: 156.25%;
  background-size: cover;
}
```

### (淘宝)男人爱车 没玩没了

[链接](http://www.uwin.cc/taobao/20150408/index.html)

- 纯图片
- 固定宽度 640
- 定位:按像素绝对定位
- 向下兼容:主要内容都在画面上半部分,下面的截掉了就截掉了无所谓

```html
<meta name="viewport" content="width=640, user-scalable=no, target-densitydpi=device-dpi">
```

![416](http://stariveer.qiniudn.com/blog/150528/app_3_416.jpeg)
![528](http://stariveer.qiniudn.com/blog/150528/app_3_528.jpeg)

### (京东)京东 618 全民红包摇摇摇

[链接](http://wqs.jd.com/promote/CH62/2015/618party/?PTAG=17053.1.1)

- 图片+文字
- rem
- 向下兼容: 超出部分有内容则出滚动条,除此之外也是放任截掉

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
```

![416](http://stariveer.qiniudn.com/blog/150528/app_4_416_1.jpeg)
![528](http://stariveer.qiniudn.com/blog/150528/app_4_528_1.jpeg)

![416](http://stariveer.qiniudn.com/blog/150528/app_4_416_2.jpeg)
![528](http://stariveer.qiniudn.com/blog/150528/app_4_528_2.jpeg)

### 京东微信购物礼包

[链接](http://wqs.jd.com/promote/2015/sns_sale/index.html?PTAG=17053.1.1)

- 高度不固定
- 流式布局
- rem

计算`<html>`标签 font-size 的算法

```js
!(function() {
  var cw = document.documentElement.clientWidth || document.body.clientWidth,
    zoom = cw / 320
  if (cw > 640) zoom = 2
  document.write(
    '<style id="htmlzoom">html{font-size:' + zoom * 50 + 'px;}</style>'
  )
  window.addEventListener('resize', function() {
    ;(cw = document.documentElement.clientWidth || document.body.clientWidth),
      (zoom = cw / 320)
    if (cw > 640) zoom = 2
    document.getElementById('htmlzoom').innerHTML =
      'html{font-size:' + zoom * 50 + 'px;}'
  })
})()
```

### 京东微信购物 1 周年

[链接](http://wqs.jd.com/promote/CH50/2015/anniversary/index.html?PTAG=17053.5.3#1)

- 绝对定位(像素)
- 向下兼容:缩放

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
```

```css
element.style {
  zoom: 0.693333333333333;
}
```

![416](http://stariveer.qiniudn.com/blog/150528/app_5_416.jpeg)
![528](http://stariveer.qiniudn.com/blog/150528/app_5_528.jpeg)

## 总结

1. `<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">` 强制页面全宽
2. (设计)主要内容尽量放在页面靠上部分,至少兼容 iPhone4s
3. 流式布局用 rem 体验最佳
4. 全图片页面可以考虑所有元素绝对定位
