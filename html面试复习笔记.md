### 简述Chome盒子模型与IE盒子模型的区别
---
每个元素在页面中占位大小 = content + padding + margin + border

* Chrome盒模型内容大小等于content大小；

* IE盒模型内容大小等于content + padding + border的总和。

### html5新特性
* (1)Canvas绘图
* (2)SVG绘图
* (3)地理定位
* (4)Web Worker
* web worker 是运行在后台的 JS，独立于其他脚本，不会影响页面的性能。
* (5)Web Storage
1. Cookie技术 （ 兼容性好,数据不能超4kb,操作复杂）
2. 兼容性差,数据8MB,操作简单）sessionStorage
3. localStorage
* Web Socket
WebSocket协议是基于TCP的一种新的网络协议。它实现了浏览器与服务器全双工(full-duplex)通信——允许服务器主动发送信息给客户端
---
### position有哪些属性？
1. position:relative; _(相对定位)_
2. position:absolute; _(绝对定位)_
3. positin:fixed;_(固定定位)_
4. position:static; _(默认定位)_
5. position:sticky;_(粘性定位)_
6. position: inherit 规定应该从父元素继承 position 属性的值
7. position: initial 设置该属性为默认值
#### 前端单位
##### **rem**：
rem是全部的长度都相对于根元素`<html>`元素。通常做法是给html元素设置一个字体大小，然后其他元素的长度单位就为rem。
##### **em：**
元素用em的话是相对于该元素的font-size
##### **vw/vh**
全称是 Viewport Width 和 Viewport Height，视窗的宽度和高度，相当于 屏幕宽度和高度的 1%，不过，处理宽度的时候%单位更合适，处理高度的 话 vh 单位更好。在手机端的时候用这个部分绝对定位地方用这个单位比较好一点，容易在不同屏幕的情况下使用，vh相当于把屏幕高度分为一百份，一个vh就是一份
##### px；
px像素（Pixel）。相对长度单位。像素px是相对于显示器屏幕分辨率而言的。
一般电脑的分辨率有{1920 * 1024}等不同的分辨率，1920 * 1024 前者是屏幕宽度总共有1920个像素,后者则是高度为1024个像素，这是我们前端常用的单位之一，现阶段很多测量工具都支持该单位，非常的好用,用过都说好
>  注意：对于中文网页需要使用 `<meta charset="utf-8"> `声明编码，否则会出现乱码。有些浏览器(如 360 浏览器)会设置 GBK 为默认编码，则你需要设置为` <meta charset="gbk">。`
---
#### XHTML和HTML的区别
1. 文档顶部doctype声明不同，xhtml的doctype顶部声明中明确规定了xhtml DTD的写法；
2. html元素必须正确嵌套，不能乱；
3. 属性必须是小写的；
4. 属性值必须加引号；
5. 标签必须有结束，单标签也应该用  “/” 来结束掉；
##### 在实际当中我们一般很少用到用table  iframe这两个元素
  因为浏览器页面渲染的时候是从上至下的，而table 和 iframe 这两种元素会改变这样渲染规则，他们是要等待自己元素内的内容加载完才整体渲染。用户体验会很不友好。
  