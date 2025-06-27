大家好，欢迎回来鸿蒙5莓创图表组件的专场，我们这一期来讲解组合图组件中tooltip属性的完整用法。这个功能模块是数据可视化交互的核心配置，掌握它的细节能让图表信息展示更专业。下面我们从底层属性开始逐层拆解：

* * *

### 一、基础开关属性 show

作用：控制是否显示浮动提示层 类型：布尔值（Boolean） 默认值：true 场景：需要临时关闭数据交互提示时使用

```
// 关闭提示层示例
tooltip: {
  show: false
}
```

* * *

### 二、布局属性 padding

作用：设置提示框内容与边框的间距 类型：数值（Number） 默认值：10 场景：当提示文字过长需要增加边距时

```
tooltip: {
  padding: 15  // 增大内边距
}
```

* * *

### 三、背景样式组

#### 3.1 backgroundColor

作用：设置提示层背景颜色 类型：颜色字符串（String） 默认值：'rgba(0,0,0,0.7)' 可选值：支持HEX/RGBA/HSL等格式

```
backgroundColor: '#2C3E50'  // 深蓝色背景
```

#### 3.2 borderWidth & borderColor

作用：边框粗细和颜色配置 类型：数值 + 颜色字符串 默认值：0 / 'rgba(0,0,0,0.7)' 场景：需要强化提示框边界时

```
borderWidth: 2,
borderColor: '#E74C3C'  // 红色边框
```

* * *

### 四、指示器配置 axisPointer

#### 4.1 主类型 type

作用：选择指示线类型 类型：字符串（String） 可选值：'line'（直线）或 'shadow'（背景块） 默认：'line' 场景：折线图适合用line，柱状图适合用shadow

#### 4.2 线样式 lineStyle

-   width：线宽（默认1px）
-   type：线型（'solid'实线 / 'dashed'虚线）
-   color：线条颜色

```
axisPointer: {
  type: 'line',
  lineStyle: {
    width: 2,
    type: 'dashed',
    color: '#3498DB'
  }
}
```

#### 4.3 阴影样式 shadowStyle

作用：当type为shadow时的背景配置

-   color：阴影颜色
-   borderWidth：阴影边框
-   borderColor：阴影边色

```
axisPointer: {
  type: 'shadow',
  shadowStyle: {
    color: 'rgba(200,200,200,0.3)',
    borderWidth: 1
  }
}
```

* * *

### 五、文字样式 textStyle

作用：控制提示框内文字样式 子属性：

-   color：文字颜色（默认#fff）
-   fontWeight：字重（normal/bold）
-   fontFamily：字体类型
-   fontSize：字号

```
textStyle: {
  color: '#F1C40F',  // 金色文字
  fontSize: 16,
  fontFamily: 'Microsoft Yahei'
}
```

* * *

### 六、动画效果组

#### 6.1 animationCurve

作用：定义提示框出现/消失的动画曲线 类型：字符串 默认：'easeOutCubic' 可选值：'linear'、'easeInOut'等标准动画曲线

#### 6.2 animationFrame

作用：动画持续时间（单位：毫秒） 类型：数值 默认：0（无动画） 场景：需要丝滑过渡效果时

```
animationCurve: 'easeInOut',
animationFrame: 300  // 300ms动画
```

* * *

### 七、综合实战案例

假设我们要开发一个金融数据看板：

```
tooltip: {
  show: true,
  padding: 12,
  backgroundColor: 'rgba(40,40,40,0.9)',
  borderWidth: 1,
  borderColor: '#7F8C8D',
  axisPointer: {
    type: 'shadow',
    shadowStyle: {
      color: 'rgba(200,200,200,0.2)'
    }
  },
  textStyle: {
    color: '#ECF0F1',
    fontSize: 14,
    fontWeight: 'bold'
  },
  animationCurve: 'easeOutBack',
  animationFrame: 200
}
```

这个配置实现了：

1.  深色半透明背景配合灰色边框
1.  阴影指示器弱化背景干扰
1.  加粗文字提升可读性
1.  带弹性的入场动画

* * *

好，这期讲到这里就结束了，希望大家通过这篇深度解析，能像搭积木一样自由组合tooltip的各种属性。在实际项目中多尝试不同配置的组合效果，让数据提示层既保持专业度又不失灵动感。我们下期再见！