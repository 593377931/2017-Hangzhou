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
      ![层叠上下文中的层叠次序](image/image/stacking-order1.png)