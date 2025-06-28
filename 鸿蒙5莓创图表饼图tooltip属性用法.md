### Hello and welcome back to our special session on HarmonyOS 5 Berry Creative chart components! In this episode, we'll explore the complete usage of the `tooltip` property in combined chart components. This functional module is the core configuration for data visualization interaction—mastering its details will make chart information display more professional. Let's break it down layer by layer starting from the underlying properties:  


### 一、Basic Toggle Property: `show`  
**Function**: Control whether the floating tooltip is displayed.  
**Type**: Boolean  
**Default**: `true`  
**Scenario**: Temporarily disable data interaction tooltips.  

```json
// Example: Disable tooltip
tooltip: {
  show: false
}
```  


### 二、Layout Property: `padding`  
**Function**: Set the spacing between tooltip content and its border.  
**Type**: Number  
**Default**: `10`  
**Scenario**: Increase padding for long tooltip text.  

```json
tooltip: {
  padding: 15  // Increase inner padding
}
```  


### 三、Background Style Group  
#### 3.1 `backgroundColor`  
**Function**: Set the tooltip background color.  
**Type**: Color string  
**Default**: `'rgba(0,0,0,0.7)'`  
**Options**: Supports HEX, RGBA, HSL, etc.  

```json
backgroundColor: '#2C3E50'  // Dark blue background
```  

#### 3.2 `borderWidth` & `borderColor`  
**Function**: Configure border thickness and color.  
**Type**: Number + Color string  
**Default**: `0` / `'rgba(0,0,0,0.7)'`  
**Scenario**: Enhance tooltip borders for clarity.  

```json
borderWidth: 2,
borderColor: '#E74C3C'  // Red border
```  


### 四、Indicator Configuration: `axisPointer`  
#### 4.1 Main Type: `type`  
**Function**: Select indicator type.  
**Type**: String  
**Options**: `'line'` (line indicator) or `'shadow'` (background block)  
**Default**: `'line'`  
**Scenario**: Use `line` for line charts, `shadow` for bar charts.  

#### 4.2 Line Style: `lineStyle`  
- `width`: Line thickness (default `1px`).  
- `type`: Line style (`'solid'` / `'dashed'`).  
- `color`: Line color.  

```json
axisPointer: {
  type: 'line',
  lineStyle: {
    width: 2,
    type: 'dashed',
    color: '#3498DB'
  }
}
```  

#### 4.3 Shadow Style: `shadowStyle`  
**Function**: Background configuration when `type` is `'shadow'`.  
- `color`: Shadow color.  
- `borderWidth`: Shadow border thickness.  
- `borderColor`: Shadow border color.  

```json
axisPointer: {
  type: 'shadow',
  shadowStyle: {
    color: 'rgba(200,200,200,0.3)',
    borderWidth: 1
  }
}
```  


### 五、Text Style: `textStyle`  
**Function**: Control text style within the tooltip.  
**Sub-properties**:  
- `color`: Text color (default `#fff`).  
- `fontWeight`: Font weight (`normal` / `bold`).  
- `fontFamily`: Font family.  
- `fontSize`: Font size.  

```json
textStyle: {
  color: '#F1C40F',  // Golden text
  fontSize: 16,
  fontFamily: 'Microsoft Yahei'
}
```  


### 六、Animation Effect Group  
#### 6.1 `animationCurve`  
**Function**: Define the animation easing for tooltip appearance/disappearance.  
**Type**: String  
**Default**: `'easeOutCubic'`  
**Options**: Standard easing curves like `'linear'`, `'easeInOut'`.  

#### 6.2 `animationFrame`  
**Function**: Animation duration (milliseconds).  
**Type**: Number  
**Default**: `0` (no animation)  
**Scenario**: Smooth transition effects.  

```json
animationCurve: 'easeInOut',
animationFrame: 300  // 300ms animation
```  


### 七、Comprehensive Practical Case  
Suppose we're developing a financial data dashboard:  

```json
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

**This configuration achieves**:  
1. Dark semi-transparent background with gray border  
2. Shadow indicator to reduce background interference  
3. Bold text for improved readability  
4. Elastic entry animation  


### Conclusion  
This wraps up our in-depth guide to the `tooltip` property! Use these attributes like building blocks to freely combine effects. Experiment with different configurations in real projects to make data tooltips both professional and dynamic. See you next time! 🚀
