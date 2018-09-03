title: "关于 css position:fixed 和 transform 的一点研究"
date: 2014-09-02 13:52:05
tags: [css,fixed,transform]
categories: [front-end,css]

---

先摘抄 w3school 对`position:fixed`和`transform:translate()`的定义:

> `position:fixed`
> 生成绝对定位的元素，相对于浏览器窗口进行定位。
> 元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

> `transform`
> transform 属性向元素应用 2D 或 3D 转换。该属性允许我们对元素进行旋转、缩放、移动或倾斜。

理论上来说 style 为`position:fixed`的元素,不管他的父、子、兄弟元素如何变化,他的位置相对于屏幕可视区域的位置都是不会变化的.但是在实际操作中却发现并非如此,如下是一个简单的 demo:

#### DEMO:

<iframe src="http://sandbox.runjs.cn/show/acnggx22" frameborder="0" style="width: 500px;height: 500px;">
</iframe>
查看源码 on [runjs.cn](http://runjs.cn/code/acnggx22)

#### Dom 结构如下:

```html
<!DOCTYPE html>
<html>
    <body>
        <div id="wrap">
            <div id="fixed">
            </div>
        </div>
    </body>
</html>
```

#### 样式:

```css
#wrap {
  width: 300px;
  height: 300px;
}
#wrap.transformed {
  transform: rotate(15deg) translate(12px, 20px);
}
#fixed {
  position: fixed;
  width: 100px;
  height: 100px;
  bottom: 0;
  right: 0;
}
```

#### 两个按钮:

作用分别是给`#wrap`添加和去除`transform`属性.

```javascript
$('#addtBtn').on('click', function() {
  $('#wrap').addClass('transformed')
})

$('#removeBtn').on('click', function() {
  $('#wrap').removeClass('transformed')
})
```

很容易发现,当设置为`position: fixed`的元素的父元素有`transform`属性时,子元素不再**"相对于浏览器窗口进行定位"**,而是变为相对于有`transform`属性的父元素定位,以 w3c 给出的定义来看,这应该是一个 bug.

---

### 小结:

`transform`作为 css3 的主要属性,他的**值**其实更像是一个个**方法**.打个比方来说,如果说 css2 的属性都是"静态"的属性,浏览器在渲染页面的时候,css 渲染引擎是先将这些静态的样式渲染出来,再来计算 css3 的那些"方法".也就是说,`transform`属性是后产生作用.反映出的现象就是`transform`优先更高,甚至高于`position: fixed`.

以上是我的一点粗陋的推想,请斧正,谢谢.
