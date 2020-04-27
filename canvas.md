# canvas

### [canvas API](https://www.runoob.com/jsref/dom-obj-canvas.html)

### [canvas 基本教程](http://caibaojian.com/canvas/2.html)

### [canvas 相关类库](https://www.zhihu.com/question/19796641)

## 基本使用方式
```html
<!-- 创建canvas元素 -->
<canvas id="canvas"></canvas>
```

```javascript
// 获取canvas元素
const canvas = document.getElementById('canvas')
// 获取2d绘图上下文
const context = canvas.getContext('2d')
```


## 线条
```javascript
// 移动画笔到某个点
context.moveTo(100, 100)
// 线条绘制到某个点
context.lineTo(200, 200)
// 线条宽度
context.lineWidth = 4
// 设置线条样式，默认值为16进制颜色值
// 可设置 color、gradient、pattern
context.strokeStyle
```

## 绘制
```javascript
// 设置状态后绘制线条
context.srtoke()
```
