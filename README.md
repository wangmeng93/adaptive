# adaptive
H5端自适应

###使用方法：
```javascript
在页面head写入以下代码，设置html的fontsize:
<script src="js/adaptive.js"></script>  // 无论iphone还是安卓手机，都能精确还原1px
<script>
    // 设计图宽度
    window['adaptive'].desinWidth = 750;
    // body 字体大小
    window['adaptive'].baseFont = 18;
    /*
    // 显示最大宽度 可选
    window['adaptive'].maxWidth = 480;
    // rem值改变后执行方法 可选
    window['adaptive'].setRemCallback = function () {
        alert(1)
    }
    */
    // 初始化
    window['adaptive'].init();
</script>
```
在css中设置相应样式即可： 设计图的1px对应0.01rem,设计图的24px对应0.24rem,就是如此简单！
```css
.main-info {
    height: 0.88rem;
    padding-bottom: 0.24rem;
}
.fund-info {
    position: relative;
    font-weight: normal;
    padding: 0.2rem 0;
    padding-right: 1.7rem;
    padding-left: 0.23rem;
    font-size: 0.32rem;
    line-height: 1;
}
```
字体也推荐使用rem
##最大宽度，解决平板或手机横屏时体验不佳的问题
```javascript
window['adaptive'].maxWidth = 480; // 设置最大宽度，默认540px
```
需要css配合使用，添加如下代码：
```css
body {
    max-width: 6.4rem; // 设计图宽度为640px时为6.4rem ,750时为7.5rem ，以此类推
    margin: 0 auto;
}
body * {
    max-width: 6.4rem; // 设计图宽度为640px时为6.4rem ,750时为7.5rem ，以此类推
}
```
## window['adaptive'].remToPx 方法，将rem值转换为px   
```javascript
// 将1rem转换为像素值
window['adaptive'].remToPx(1) 
```
