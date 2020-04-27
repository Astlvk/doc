# Animation

## 基本使用
1. 使用@keyframes定义动画帧
2. 在需要动画效果的元素的样式中通过animation属性使用@keyframes定义的动画帧


### 嵌套的圆圈旋转动画
```html
<!-- 最外容器 -->
<div class="container">
<!-- 第1个圆，center类为flex的水平垂直居中 -->
  <div class="round1 center">
  <!-- 第2个圆 -->
    <div class="round2 center">
    <!-- 第3个圆 -->
      <div class="round3"></div>
    </div>
  </div>
</div>
```

```css
html {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  width: 300px;
  height: 300px;
  position: relative;
}

.round1 {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 1px solid #409EFF;
  position: relative;
  animation: spin 7s infinite linear;
}

.round1::before {
  content: '';
  position: absolute;
  top: -6.5px;
  left: 50%;
  display: block;
  width: 10px;
  height: 10px;
  border-right: 1px solid #909399;
  border-top: 1px solid #909399;
  transform: rotate(45deg);
}

.round2 {
  width: 90%;
  height: 90%;
  position: relative;
  border-radius: 50%;
  border: 1px solid #E6A23C;
  animation: spin-reverse 4s infinite linear;
}

.round2::before {
  content: '';
  position: absolute;
  top: -6.5px;
  left: 50%;
  display: block;
  width: 10px;
  height: 10px;
  border-left: 1px solid #909399;
  border-top: 1px solid #909399;
  transform: rotate(-45deg);
}

.round3 {
  width: 90%;
  height: 90%;
  position: relative;
  border-radius: 50%;
  border: 1px solid rgb(162, 60, 230);
  animation: spin 4.5s infinite linear;
}
.round3::before {
  content: '';
  position: absolute;
  top: -6.5px;
  left: 50%;
  display: block;
  width: 10px;
  height: 10px;
  border-right: 1px solid #909399;
  border-top: 1px solid #909399;
  transform: rotate(45deg);
}

@keyframes spin {
  from {
    transform: rotate(0deg)
  }

  to {
    transform: rotate(360deg)
  }
}

@keyframes gradient {
  from {
    background-color: #409EFF;
  }

  to {
    background-color: #F56C6C;
  }
}

@keyframes spin-reverse {
  from {
    transform: rotate(360deg);
  }

  to {
    transform: rotate(0deg);
  }
}
```