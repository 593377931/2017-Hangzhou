* sublime 代码片段
* git
* linux
* vim
* 色彩模型
* html标签
* role/aria-*
* box-shadow

* inline-block相邻标签之间空格的处理
  * 手动删除
  * 将父元素的font-size设置为零
  * word-spacing: -5px;
  * 计算出空格的对应的em宽度
* normallize.css
* 打造自己的CSS.reset

* list-style
  * `<'list-style-type'> || <'list-style-position'> || <'list-style-image'>`

* 各属性属性值可设置为百分比时的参照物
  * height: 包含块高度
  * width: Defines the width as a percentage of the containing block's width. 
  * margin：包含块宽度
  * line-height: the font size of the element itself
    * line-height inherit, very funny
      * 父元素的 line-height 值为unitless number 时，子元素继承此 <number> 值与子元素的 font-size 值进行重新计算，确定子元素 line-height 值的大小;
      * 父元素的 line-height 值为 <length> | <percentage> 时，子元素继承根据此数值计算出的父元素的 line-height 值
      * 例如，父元素 font-size 值为20px，子元素的 line-height 的值为40px。
        * 父元素line-height 设置为200% 或 2em，子元素继承的 line-height 值将为40px
        * 父元素的 line-height 值设置为2时，子元素的 line-height 值将为80px。
    * font-size inherit
      * 如父元素的字体大小设置百分比或者em为单位的数字，子元素的实际字体大小为继承的font-size值，与父元素实际字体大小的乘积(会导致处于祖先和后代关系的相同标签，在被同一个选择器选中，并设置相同的百分比或em值时，祖先元素和后代元素的大小不一致，可使用rem单位避免此问题)



* box-shadow

* 行内布局术语
  * 匿名文本 anonymous text
    * 所有未包含在行内元素中的字符串，包括空格
    * 可假设这些匿名文本包含在一个line标记的行内元素中
  * em框（em box | 字符框 | character box）
    * font-size 值确定了em框的大小
    * 实际的字形可能比其em框更高或者更矮
  * 内容区 content area
    * 非替换元素(nonreplaced elements)中，字符em框串起来，构成的框
    * 替换元素(replaced elements)和display:inline-block元素中，为其margin-box
  * 行间距 leading
    * 行间距只应用于非替换元素
    * 值为font-size 与 line-height 值之差，差值分为两半，分别应用与内容区的顶部和底部
  * 行内框 Inline box
    * 非替换元素，等于其line-height
    * 替换元素和display: inline-block，等于其margin-box
  * 行框 Line-box
    * 包含该行中出现的行内框的最高点和最低点的最小框
  * 相关概念
    * 行内元素的内容区类似于块级元素的内容框(content-box)
    * 行内元素背景应用与padding-box
    * 非替换元素的padding border 和 margin 对行内垂直布局没有影响
    * 替换元素的margin和border会影响其行内框高度，进而影响行框高度
    * 行内框在行框中根据其vertical-align属性垂直对齐，可能进而影响包含该元素的行框高度

* background-attachment: fixed

* 布局
  在CSS中，一个盒子可以按章三种布局定位方案进行布局
    1. Normal flow 正常流
      在CSS中，正常流包含：
        1. 块格式化的块级盒子
        2. 行格式化的行级盒子
        3. 相对定位或者粘性定位的块级盒子和行级盒子
    2. Floats 浮动
      在浮动模型中，一个盒子首先依据正常流进行布局，然后从流中拿出进行定位，一般来说是左或者右。内容顺着浮动盒子的一边进行布局。
    3. Absolute positioning 绝对定位
      在绝对定位模型中，一个盒子完全从正常流中移除（对后续的兄弟元素没有影响），相对其包含块指定一个位置。
  被称为流外(out-of-flow)的元素，是浮动、绝对定位或者是根元素。非流外的元素被称为流内(in-flow)的元素。The flow of an element A is the set consisting of A and all in-flow elements whose nearest out-of-flow ancestor is A.
  * 相对定位
    一旦一个盒子被按照正常流或者浮动布局，它将参照这个位置进行偏移。这就称为相对定位。









* 浮动
  * 清除浮动
    * 通过在浮动元素的末尾添加一个空元素，设置clear: both属性，after伪元素其实也是通过在元素的后面生成了内容为一个点的块级元素
  * 闭合浮动
    * 通过设置父元素的 overflow 或者 display:table 属性来闭合浮动。
  * 触发BFC(Block formatting contexts)
    * float设置除了none以外的值
    * overflow除了visible以外的值 (hidden, auto, scroll)
    * diaplay (table-cell, table-caption, inline-block, flow-root(CSS3))
    * position (absolute, fixed)
    * fieldset 元素
  * BFC特性
    * 块级格式化上下文会阻止外边距叠加
    * 块级上下文格式化不会重叠浮动元素
    * 块级格式化上下文通常可以包含浮动
  * 利用浮动做灵活的三列布局

* 绝对定位
  * 静态定位，不定位，常规流
  * 固定定位，相对于视口定位，脱离文档流，基于margin-box定位
    ```css
    div {
      positon: fixed;
      top: 0px;
      right: 
    }
    ```
  * 相对定位，盒模型不变，相对于自身本来的位置，没有脱离流，可以和浮动一起使用

  * 绝对定位
    * position: absolute
    * 脱离文档流
    * 以其margin-box为基准，相对离它最近的定位祖先(position不是默认值)的padding box定位
    * 不能和浮动一起使用
  * sticky
    * 在视口内时，没有定位
    * 不在视口内时，fixed定位
    * 具体生效还取决于在视口的上方还是下方
  * 覆盖顺序
    * 默认情况下按在文档中出现的顺序覆盖
    * 可以使用z-index属性修改，对于常规流中的元素设置无效

* z-index
  * CSS为盒模型布局提供了三种不同的定位方案：
    * 常规流
    * 浮动
    * 绝对定位
  * 绝对定位将元素从常规流中移除，由开发者确定显示位置
  * 通过设置top left bottom right 属性，确定元素在二维平面上的位置，此外CSS允许使用z-index属性以在第三维上放置元素
  * z-index 基础
    * 属性值：auto(自动,默认值) | (整数) | inherit
    * 整数值可以是正负和零
  * 层叠上下文和层叠层
    * 每一个页面都有默认的层叠上下文, 这个层叠上下文的根源是html元素. html标签中的一切都被至于这个默认的层叠上下文的一个层叠层上
    * 当给一个元素赋予除auto外的z-index值时, 就创建以一个新的层叠上下文,其中有着独立于页面上其他层叠上下文和层叠层的层叠层.
  * 层叠次序
    * 在一个层叠上下文中一共可以有7种层叠等级
      1. 背景和边框 -- 形成层叠上下文的元素的背景和边框. 层叠上下文中的最低等级
      2. 负z-index -- 层叠上下文内有着负z-index值的子元素
      3. 块级盒 -- 常规流中非行内非定位子元素
      4. 浮动盒 -- 非定位浮动元素
      5. 行内盒 -- 常规流中行内级别非定位子元素
      6. z-index: 0 -- 定位元素. 这些定位元素形成了新的层叠上下文
      7. 正z-index值 -- 定位元素. 层叠上下文中的最高等级
      ![层叠上下文中的层叠次序](image/stacking-order1.png)
* 垂直居中
  * 表格
  * 绝对定位


* Vendor Perfix 厂商前缀
  * 为了让代码尽量的向前和向后兼容
  * 不提倡区分浏览器
  * -webkit-backgroud-clip: text;
  * -moz-background-clip: text;
  * -o-background-clip: text;
  * background-clip: text;
* IE hack
  * `div {*zoom: 1; +zoom: 1; zoom: 1 \9;}`


*
  * Conceptually, the odd parity test entails drawing a line segment from any point that lies outside the polygon to a point P, that we wish to determine whether it is inside or outside of the polygon. Count the number of edges that the line crosses. If the number of polygon edges crossed is odd, then P lies within the polygon. Similarly, if the number of edges is even, then P lies outside of the polygon. 

* contenteditable 内容可编辑属性
* URI/ URL
* 艺龙
* 伪元素模拟checkbox


# Table Layout
## 表格式化
在开始考虑表单元格边框如何被绘制和表格如何确定大小之前，我们需要探究一下表格组装的基本方式，和表格单元中的元素之间的相互关系。这里提及的表格式化与表布局有着相当大的区别，在前者被解释清楚之后我们才能开始探索后者。
### 表格的视觉安编排
提到的CSS属性：`display`

首先我们需要知道CSS如何定义表格编排。当然，这个知识点看起来有些基础，但是它是理解如何进行最佳表格样式的关键所在。

CSS对表元素和表内元素有着很明显的区分。**CSS中，表内元素生成由内容(content)，内边距(padding)，边框(border)组成的矩形盒子，没有外边距。**因而，不能通过指定表单元格的外边距来确定表单元格之间的隔离(separation)。**遵从CSS规范的浏览器会忽略所有尝试给表内元素添加外边距(margin)的行为，如表单元格，表格行。（caption元素例外，本章稍后讨论）**
#### 表格排布规则
* 每个行盒(row box)包含简单的一行'grid cells'。所有的行盒根据依据他们在文档中出现的顺序从表格顶部至底部填充表格（thead 和 tfoot 行盒例外，它们依次出现在表格的开头和结尾。**表格中包含多个thead和tfoot时，只有首次出现的thead和首次出现的tfoot将出现在表格的开头和结尾，其余的thead和tfoot被作为tbody处理**）。因此，表格包含很多'gird rows' 就像它们是行元素一样。
* 一个行组盒(row group's box)和行盒(row boxs)包含的'grid cells'相同。
* 一个列盒(column box)包含由'grid cells'组成的一个或多个列。所有的列盒依据出现顺序一次排放。在从左至右的语言中，第一个列盒在左边，从右至左的语言中，第一个列盒在右边。
* 一个列组盒(column group's box)包含和列盒相同的'grid cells'。
* 尽管单元格可能跨多行或者多列，CSS并没有对此做出定义。而是由文档语言来定义。每个跨行列的单元格是一个矩形盒子，宽高分别为多个相应的'grid cells'。这个盒子的首行所在的行是这个盒子的父元素。书写系统为从左至右的语言中，单元格必须尽可能的向左，但是不能覆盖其余的单元格，本行源文档中在当前单元格之前出现的单元格，必须在本单元格的左边。书写系统为从右至左的语言中，正好相反。
* 单元格不能跨表格之间或行组之间进行合并。
### 匿名表对象
#### 对象插入规则
### 表标题
CSS属性：`caption-side: top|bottom`
## 表单元格边框
CSS属性：
`border-collapse: separate|collapse|inherit`
`border-spacing: <length> <length>?|`
`enpty-cells: show|hide|inherit`

### 分隔模型表格单元格的边框
### 合并模型表格单元格的边框
#### 合并边框布局
#### 合并边框规则——“最有意思”的边框胜出
有一些严格的规则来确定哪一个边框会在合并中胜出
* 如果某个合并边框的border-style属性为hidden，它会优先覆盖其它合并边框。所有在这个位置的边框都将隐藏。
* 如果某个合并边框的border-style属性为none，它的优先级最低。除非所有的边框border-style值都为none，否则，不会绘制此边框。border-style 属性的默认值为none。
* 如果至少有一个边框不是none，所有边框都不是hidden。更宽的边框胜出。如果多个边框的宽度相同，则会考虑边框的样式。胜出顺序为：double solid dashed dotted ridge outset groove inset
* 如果边框样式和宽度都相同，不同元素之间按照表格层顺序进行合并，相同元素之间取左上元素的边框颜色。

## 表大小
```
表宽度计算的两种方法
table-layout: fixed|auto|inherit
```
在确定表宽度时，由两种不同的方式：固定宽度布局和自动宽度布局。无论宽度算法采用何种方式，表高度都会被自动计算。


# CSS `white-space` property
`white-space`CSS属性用来确定一个元素中的whitespace如何被处理
```
<!-- Keyword value -->
white-space: normal;
white-space: nowrap;
white-space: pre;
white-space: pre-wrap;
white-space: pre-line;

<!-- Global value -->
white-space: inherit;
white-space: initial;
white-space: unset;
```

## Values
* normal
连续的whitespace将被折叠。源代码中的换行符同样作为whitespace处理。行在填充行盒时，会在需要时折断。
* nowrap
连续的whitespace也会被折叠，阻止源代码中的换行。
* pre
连续的whitespace会被保留。行折断仅发生在源代码中的换行负和`<br>`标签处。
* pre-wrap
连续的whitespace保留，在换行符处和`<br>`标签处换行，在需要换行的时候折断
* pre-line
连续的whitespace折叠，在换行符和`<br>`表全处换行，在需要折断时折断。



## viewport
* 100vw=(视觉稿宽度)rem  1rem等于设计稿中的一个像素 
* 最新移动端浏览器：<meta name="viewport" content="width=800">
* 稍老移动端浏览器： html {font-size: calc(100vw / 8)}
  * calc和vw兼容性问题：使用js读取viewport宽度，按需设置html的font-size
* 谷歌浏览器最小字号限制为12px
* 在不需按比例还原视觉稿的场景下，声明width=device-width，页面使用px以流式布局开发，最终结果就是屏幕越大，一屏展示的文字越多

* 如果页面即重布局，又有相当量的文字
  * 完全可以rem跟px一起用
  * 布局用rem，文字字号用px


## 卷帘
max-height



## 递归
递归一定要有结束条件
不是结束条件的分支要把问题往结束条件的方向递推
编写递归函数的时候，把递归函数当成普通该函数，并且认为它已经正确实现
想清递归的功能