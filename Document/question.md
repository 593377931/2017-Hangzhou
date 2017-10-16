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