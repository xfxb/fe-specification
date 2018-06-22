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

#### 公共变量或者通用变量定义

##### 颜色

##### 字体大小

- 字体家族
- 字体颜色
- 字体大小
- 子图粗细

##### 边框

 - 边框颜色
 - 边框粗细
 - 边框半径

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