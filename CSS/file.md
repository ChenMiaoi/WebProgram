# CSS  

---  

## CSS语法规范

- CSS由两个主要的部分构成：选择器以及一条或多条声明
```css
h1 {
    color: red;
    font-size: 25px;
}
```

### CSS代码风格

- 使用展开型
```css
h1 {
    color: red;
    font-size: 25px;
}
```

- 代码全部采用小写(特殊字符除外)
- 在属性值的前面，冒号的后面保留一个空格
- 在选择器(标签)和大括号中间保留一个空格


## CSS基础选择器

> 选择器就是根据不同需求把不同的标签选出来这就是选择器的作用

### 选择器分类

- 选择器分为基础选择器和复合选择器
  - 基础选择器是由单个选择器构成的
  - 基础选择器包括：标签选择器、类选择器、id选择器和通配符选择器

#### 标签选择器

```css
标签名 {
    属性: 属性值;
}
```

> 标签选择器会将同类标签全部选择出来  
> 但是会导致不能差异化设置

#### 类选择器

> 能够差异化的选择不同的标签

```css
.类名 {
    属性: 属性值;
}

<div class='类名'></div>
```

- 类选择器使用“.”进行标识， 后面紧跟类名
- 可以理解为给这个标签起个名字
- 长名称或者词组可以使用横线来命名
- 不要使用纯数字和中文

##### 多类名

```css
<div class="red font20"></div>
```

- 在class标签中写入多个类名
- 多个类名中间必须用空格分开


#### id选择器

> id选择器可以为标有特定id的HTML元素指定特定的样式  
> HTML元素以id属性来设置id选择器，CSS中id选择器以#来定义

```css
#id名 {
  属性: 属性值;
}
```

- ==id选择器仅能使用一次==  
- id选择器就相当于人的身份证号码，永远是唯一的，不得重复

#### 通配符选择器

> 在CSS页面中，通配符选择器使用*定义，它表示选取页面中所有元素

```css
* {
  属性: 属性值;
}
```
- 通配符选择器不需要调用，自动给所有元素添加样式
- 特殊情况才使用，后面讲解使用场景
```css
* {
  margin: 0;
  padding: 0;
}
```

## CSS字体属性

> CSS font属性用于定义字体系列、大小、粗细和文字样式

### 字体系列

> CSS 使用font-family属性定义文本的字体系列
```css
p {
  font-family: "Noto Sans Mono CJK SC";
}

div {
  font-family: Dialog, "Fira Code", "Fira Code";
}
```

### 字体大小

```css
p {
  font-size: 20px;
}
```

- px(像素)大小是网页中最常用的单位
- 谷歌浏览器默认为16px

### 字体粗细

```css
p {
  font-weight: normal;
}
```

- 参数
  - normal：正常的字体，相当于number=400
  - bold：粗体
  - bolder：特粗体
  - lighter：细体
  - number： 从100～900

### 文字样式

```css
p {
  font-style: normal;
}
```

| 参数 | 作用 | 
| --- | --- | 
| normal | 默认值，浏览器的默认样式 | 
| italic | 斜体 | 

- 但是平时我们很少给文字加斜体，通常给斜体标签改为不倾斜 字体

### 字体复合属性

```css
body {
  font: font-style font-weight font-size/line-height font-family;
}
```

- 使用font属性时，必须按上面的语法格式顺序书写，**不能颠倒顺序**， 并且各个属性之间以空格隔开
- 不需要设置的属性可以省略(取默认值)， 但是**必须保留font-size和font-family属性，否则font失效

## CSS文本属性

> CSS Text(文本)属性可定义文本的外观，比如颜色、对齐、装饰、缩进行间距等

### 文本颜色

```css
div {
  color: red;
}
```

| 表示 | 属性值 | 
| --- | --- | 
| 预定义的颜色值 | red、green、blue等 | 
| 十六进制 | #FF0000、#FF6600等 | 
| RGB代码 | rgb(255, 0, 0)或rgb(100%, 0%, 0%) | 

### 对齐文本

```css
div {
  text-align: center;
}
```

| 解释 | 属性值 | 
| --- | --- | 
| left | 左对齐(默认值) | 
| center | 居中对齐 | 
| right | 右对齐 | 

### 装饰文本

> 给文本添加下划线、删除线、上划线等 

```css
div {
  text-decoration: underline;
}
```

| 属性值 | 解释 | 
| --- | --- | 
| none | 默认， 没有任何装饰 | 
| underline | 下划线，链接a自带下划线 | 
| overline | 上划线，几乎不使用 | 
| line-through | 删除线 | 

### 文本缩进 

> 用来指定文本的首行缩进

```css
div {
  text-indent: 2em;
}
```

- 在该属性中可以使用em单位，em是一个相对单位，就是当前元素1个文字的大小

### 行间距

```css
p {
  line-height: 26px;
}
```

## CSS的引入方式

### 内部样式表

> 就是写到html内部，是将所有的CSS代码抽取出来，单独放到一个style标签中

```html
<style>
  div {
    color: red;
  }
</style>
```

- style标签理论上可以放在任何地方，但是一般约定放在head标签中
- 可以方便控制当前整个页面中元素样式设置
- 代码结构清晰，但是没有完全分离

### 行内样式表

> 是在元素标签内部的style属性中设定CSS样式，适合简单修改

```html
<div style="color: red; font-size: 12px">xxxx</div>
```

### 外部样式表

> 适合样式比较多的情况，将样式单独写入CSS文件中，之后再把CSS引入到html页面中使用

- 通过link标签引入文件
```html
<link rel="stylesheet" href="css文件路径">
```
| 属性 | 作用 | 
| --- | --- | 
| rel | 定义当前文档和被链接文档之间的关系，stylesheel表示是一个样式标文件 | 
| href | url | 

## emmet语法

> 前身是Zen coding,用来缩写，可以提高编写速度

### 快速生成HTLM结构语法

1. 生成标签直接输入标签名按tab键
2. 如果想要生成多个标签，加上*号，比如div\*
3. 如果有父子关系的标签，可以用>，比如ul>li
4. 如果是兄弟关系的标签，可以用+，比如div+p
5. 如果生成带有类名或者id名字的，直接写.demo或者#two tab一下
6. 如果生成的div类名是有顺序的，可以用自增符号$
7. 如果想要在生成的标签内部写内容可以用{}表示