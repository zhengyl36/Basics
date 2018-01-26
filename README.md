# Basics

    前端学习过程中最喜欢的两种适配方案

## 方法一: rem布局，动态设置html的font-size

    我们知道rem是根据html设置的font-size计算的，因此我们可以在布局是全部使用rem，再通过动态设置html的font-size值来缩放页面，
    达到适配的效果。
    
    为了方便计算，个人喜欢将fonts-size设置为100px,这样750px * 1334px的设计稿，为7.5rem * 13.34rem
    
    当然，你也可以设置其他font-size值，尽量合理些，因为计算时可能出现一些除不断的情况，会有误差
    
    布局好后，通过js动态计算font-size值
    
```js
//屏幕适应
var html = document.documentElement;
    var k = 750;//设计稿宽度
    html.style.fontSize = html.clientWidth / k * 100 + "px";
```

## 方法二： 固定宽度

    添加头部
```js
 <meta name="viewport" content="width=设计稿宽度, target-densitydpi=device-dpi">
```
    布局时完全按照设计稿布局即可，浏览器会帮我们自动缩放到适配屏幕大小，包括图片字体等。
    
    target-densitydpi=device-dpi 属性用于适配android4.4以下机型，已逐渐不再支持。

## 对比

    两种方法都很很好的适配绝大部分浏览器，方法一适配范围更广些，对于那些不支持缩放的环境（如webview中不开启缩放）也能很好的适应。


