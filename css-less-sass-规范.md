# css/less/sass 规范

## 变量命名

---

css less sass 都可以使用变量，只是前缀不一样。

比如定义一个颜色的变量，3者对应的语法依次是：

```css
  // css
  --color: red;
```

```less
  // less
  @color: red;
```

```sass
  // sass
  $color: red;
```

变量命名规范

`@{组件}-{属性}-{场景}-{状态}-{大小}-{反色}`

#### 公共变量或者通用变量定义



##### 颜色
 
一个软件的颜色构成大体上分2部分：

- 基色;也就是UI中大概率，大面积出现的颜色。就好比你浏览淘宝，淘宝的颜色是橘黄色居多，那么淘宝的基色就橘黄色；京东和天猫就是大红色；支付宝基色就是蓝色，等等；
- 点缀色;
- 灰阶色;就是不同亮度的黑白灰色；也可以理解为辅助色。

```less

@color-text-base: #333; //默认字体
@color-text-placeholder: #999; //输入框的占位符

````

##### 字体大小

- 字体家族

```less

@font-family-base: -apple-system,"SF UI Text",Roboto,Noto,"Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;

```

- 字体大小

```less

@font-size-base: 

```

- 字体粗细

##### 边框

 - 边框颜色
 - 边框粗细
 - 边框半径


```less
@radius-xs
```

###### 间距

#### 组件变量或者模块变量

## 重新设置浏览器默认样式

## icon解决方案

## 自适应

## 公共样式

#### 布局

#### 工具类

## 参考


[bootstrap 变量定义][1]
[ant-design-mobile 设计变量表及命名规范][2]
[CSS预定义的颜色名列表][3]

[1]:https://github.com/twbs/bootstrap "bootstrap github 地址"
[2]:https://github.com/ant-design/ant-design-mobile/wiki/%E8%AE%BE%E8%AE%A1%E5%8F%98%E9%87%8F%E8%A1%A8%E5%8F%8A%E5%91%BD%E5%90%8D%E8%A7%84%E8%8C%83 "ant-design-mobile 设计变量表及命名规范"
[3]:http://www.w3school.com.cn/cssref/css_colorsfull.asp "CSS 颜色名"
[4]:http://www.w3school.com.cn/cssref/css_colors.asp "css颜色"