## 第一次测试|2017.09.30

### 1. 常见Linux命令及用法
  * pwd
    * 输出当前工作目录
  * ls
    * 输出当前工作目录下的文件和文件夹
      * ls -a
        - 输出包括隐藏文件和文件夹
      * ls -l
        - 输出文件和文件夹详细信息
  * cd
    * 切换工作目录
      * cd /
        - 切换至根目录
      * cd ..
        - 切换至上层目录
      * cd .
        - 切换至当前目录
      * cd ~
        - 切换至当前用户家目录
  * rm
    * 删除文件
      * rm -r xxx
        - 删除文件夹
  * mkdir
    * 创建文件夹
  * rmdir
    * 删除文件夹
  * echo
    * 将用户输入的内容输出
    * echo aaa >> a.md
      * 将输出追加至a.md
  * cat
    * 文件拼接输出
      * cat a.md b.md
  * cp
    * 复制
  * touch
    * 创建文件
      * touch aaa
  * mv
    * 移动文件
      * mv a.md ..
        - 将a.md移动至上层文件夹
      * mv a.md b.md
        - 将a.md重命名为b.md
  * 管道符`|`
    * 将前一个命令的输出作为后一个命令的输入
  * grep

### 2. 什么是 html 实体？常见 html 实体有哪些？
  * html中，`<`和`>` 等符号作为html标签的一部分，如果要在页面中输出`<`和`>`，不能直接使用此类字符，因为其可能被作为html标签处理，所以使用html实体来表示此类符号。另外一些不易用键盘输入的字符也可使用html实体进行表示。
  * 书写方式
    * `&name; &#2345; &#xF87A;`
  * 常见的html实体
    * `&lt;`
    * `&gt;`
    * `&amp;`
    * `&nbsp;&nbsp;&nbsp;&nbsp;`
    * `&copy;`
    * `&quote;`
    * `&apos;`

### 3. 计算机为什么使用二进制
  * 使用二进制消除误差
  * 把设备上的物理量理解成两种状态的信号
  * 当设备上的物理量被理解成01信号的时候，这个01信号成为数字信号
  * 设备上直接测得的物理量是模拟信号
  * 真实的世界是模拟的

### 4. 什么是 Unicode？如何表示，有什么作用？最通用的 Unicode 实现是？
  * 把全球所有的符号统一编号，这个编号方式称为unicode--通用字符编码集，每个符号有唯一编码
  * 使用U+一组16进制字符表示，如U+0041表示A，U+0061表示a
  * 实现全球统一的字符编码，避免了不同国家或地区使用相同的字符编码却表示了不同的字字符，在不同国家之间交流文档时，字符乱码的问题
  * 最通用的Unicode实现是UTF-8，是一种变长编码方式

### 5. 什么是 GUI，什么是 CLI，什么是接口/界面？现实生活中有哪些例子？
  * GUI
    * 图形用户界面 Graphics User Interfact
    * 以图形和鼠标等方式跟用户进行交互的界面
  * CLI
    * 命令行界面 Command Line Interface
    * 以字符输入命令，以字符形式得到反馈
  * 外部的人与一个系统内部进行交流的一个通道
  * 键盘，仪表盘

### 6. 在什么情况下 html 标签可以不需要闭合？
  * 在根据标准，能够推导出某标签已经结束的情况下，这个标签的结束标签可以省略。

### 7. 什么是费茨定律？它有哪些应用？
  * 到达某个区域中心的难易程度与到其的距离和其目标的大小有关，距离越小，目标越大，越容易达到
  * 如Windows操作系统中，将一些重要的交互元素设计在屏幕的四角，目标大小趋近于无穷大；在移动设备系统中，交互元素都设计的尽量大，便于用户操作
  * StrokeIt
  * 快捷键
  * 滚轮切换
  * win-run

### 8. 为什么英文很重要？
  * 找工作
  * 几乎所有变成环境都是英文的，报错信息也都是英文的，相关编程资料也都是英文的
  * 因为相关技术文档一般均使用英语书写，技术文档译者由于技术水平参差不齐，难以非常精准的还原作者的表达，再者技术文档翻译需要一定时间，一些较新的技术文档短期难以完成翻译。所以尽量阅读原版英语文档。

### 9. 将二进制 10010 数转换为十进制数
  * 18

### 10. 将十六进制数 ABCDEF 转换为十进制数
  * `15*16^0+14*16^1+13*16^2+12*16^3+11*16^4+10*16^5=11259375`

### 11. 列出 HTML 中常见的全局属性
  * class
  * id
  * title
  * tabindex
  * style
  * name
  * data-
  * rola
  * arai-

### 12. 什么是操作系统的 Path？它的作用及应用场景是？
  * PATH 是操作系统全局变量，是一个绝对路径列表
  * 命令行中，或者运行窗口的命令都会按准许在path列表张寻找相应的可执行文件
  * Windows系统可以在其中添加自定义目录将常用快捷 方式添加在此目录中，在使用Windows运行，实现快速启动相关应用

### 13. 什么是文本文件？什么是二进制文件？它们最明显的区别是？
  * 使用一定的字符编码方式，将文本进行存储所生成的文件为文本文件。
  * 任何文件最终都是以二进制方式存储，任意文件都可称为二进制文件。狭义的二进制文件指除文本文件之外的文件。
  * 它们之间最明显的区别是，文本文件可以使用任何文本编辑器直接打开进行编辑。二进制文件需要使用相关的专用软件查阅或编辑。

### 14. 为什么说 html 与数学公式有诸多相似之处？
  * html的嵌套方式和数学公式里括号的嵌套方式完全相同
  * 自相似：拿出一部分后，剩余部分依然合法
  * 它们都是一种严格的树状（递归）结构

### 15. 几种常见图片格式有什么区别和特点？
  * jpg
    * 有损压缩，文件较小，适合存储现实中的图片
  * png
    * 无损压缩，适合存储大面积颜色相同的图片--如截图，支持256级透明色
  * bmp
    * 无损，无压缩，体积大，一个像素使用三个字节存储
  * gif
    * 支持动画，只有256种抽样出来颜色，每个点的颜色只需要一个字节来保存。一般来说色彩暗淡，图片尺寸一般比较小，第一帧为完整图片，随后的每帧只存储了变化的像素点，体积较小。支持两色透明
  * psd
    * PhotoShop专用格式
  * webp
    * 有损压缩，在各方面性能胜过jpg，支持透明色

### 16. 在一些情况下某些非自闭合标签的结束标签可以省略的原因是什么？
  * 可以推导出此标签已经结束

### 17. data-* 属性一般是用来干嘛？
  * 可用来在html标签中存储自定义属性，以保存信息，更符合标准，方便使用JS进行操作

### 18. 用什么方法扩大一个 checkbox 的可点击区域？
  * 将对应的label标签for属性设置为checkbox的id属性值
  * label中嵌套checkbox

### 19. 什么是 MIME Type？请列出以下格式的MIME Type
  * 资源的媒体类型
  * image/jpg,image/svg+html,image/png,image/gif
    * image
  * text/html,text/css,text/javascript
    * text

### 20. 哪些标签可以使用 target 属性？哪些标签可以使用 href 属性？
  * target
    * &lt;a&gt; &lt;area&gt; &lt;form&gt; &lt;base&gt;
  * href
    * &lt;a&gt; &lt;area&gt; &lt;link&gt;

### 21. 什么是 BOM 头？
  * UTF-8 with BOM编码的文件用其标示此文件为UTF-8格式 EFBBBF
  * UTF-16/32 编码的文件中其用来标示编码是高位在前还是低位在前
    * 0xFE 0xFF
    * 0xFF 0xFE

### 22. group 类型的标签有哪些？
  * hgroup
  * optgroup
  * colgroup
  * fieldset

### 23. 什么是 SEO？
  * 搜索引擎优化 Search Engine Optimization

### 24. 分别列出每种常见浏览器的内核名称
  * Chrome
    * blink
  * Safari
    * webkit
  * Firefox
    * Gecko
  * IE
    * trident

### 25. 列表类标签有哪些？分别如何使用？需要注意些什么？
  * ol,ul,li
  * dl,dt,dd
<!--   
  * table
  * caption
    * 表格标题
  * thead
    * 表格头部
    * 即使在文档流中处于tbody标签后面，也会被浏览器渲染至表格头部
    * 打印时会在每页显示表头
    * 多余的th标签会作为tbody处理
  * tbody
    * 表格主体
  * tfoot
    * 表格底部
  * tr
    * 表格行
  * th
    * 表头
  * td
    * 单元格
    * rowspan 属性
      * 设置跨行数
    * colspan 属性
      * 设置跨列数
    * headers 属性
      * 其属性值应为空格分割的相对应的th标签的id属性列表
  * col
    * 抽象出的表格列
  * colgroup
    * 存放col标签
 -->

### 26. 为什么查文档一般不推荐 w3school？
  * w3school的文档标准老旧
  * 商业网站
  * 不经常更新
  * 内容不全
  * 不留官方文档地址

### 27. 为什么不同类型的标签的 fallback 内容要以不同的形式提供？
  * 退化
  * 正常使用时，标签内是否包含内容
  * script
    * 写在noscript标签内
  * iframe
    * 写在标签内
  * canvas
    * 写在标签内
  * frame
    * 写在noframe标签内

### 28. 分别写出在 head 中设定页面编码，设定 icon，引入样式表的标签
  ```html
  <meta charset="utf-8">
  <link rel="icon shortcut" href="https://www.baidu.com/xxx.icon">
  <link rel="stylesheet" href="http://www.jd.com/xxx.css">
  ```

### 29. 什么叫做可访问性，html 中为此做了什么工作？
  * 页面在各种情况下能否正常使用
  * 页面在针对不同人群时，能否使用
  * role/aria-*
  * td[headers] -> td[id]
  * tabindex

### 30. 写出以下几个符号的ascii码：a，A，0，CR，LF，空格，NBSP。
  * a
    * 01100001
  * A
    * 01000001
  * 0
    * 00110000
  * CR
    * 00001101
  * LF
    * 00001010
  * 空格
    * 00100000
  * NBSP
    * 10100000

## 31. 用文字描述如下选择器将选择哪些（个）元素

```html
div, h1 {}                  <!-- 页面中所有的div和h1标签 -->
div[class] [id="abc"] {}    <!-- 页面中具有class属性的div标签的后代中id属性值为abc的标签 -->
div:hover ul li > div {}    <!-- 页面中div处于hover状态时的，其后代中的ul标签的后代中的li标签的子div标签 -->
body :active {}             <!-- body标签的后代中，处于active状态的标签 -->
div:hover::after {}         <!-- 页面中的div元素处于hover状态时，在此div元素的后面插入内容 -->
::selection {}              <!-- 页面中，被用户用鼠标选中的内容，只能修改颜色 -->
:target {}                  <!-- 页面中，其id属性值为URL中#后面的内容的标签 -->
input + ul + p ~ span {}    <!-- 页面中，input标签紧邻的ul标签紧邻的p标签的后面与此p标签处于兄弟关系的所有span标签 -->
```

## 32. 分别写出如下几个选择器的优先级
```html
* * * {}                                <!-- 0 0 0 0 -->
div * span {}                           <!-- 0 0 0 2 -->
div[title] {}                           <!-- 0 0 1 1 -->
fieldset legend + input {}              <!-- 0 0 0 3 -->
#some #thing .not:hover .abc:hover {}   <!-- 0 2 4 0 -->
```

## 33. em,px,rem,vw,vh分别代表多长？
  * em
    * 当前元素所继承的字体字号大小
  * px
    * 一个css像素
  * rem
    * 根元素(html)的字体字号大小
  * vw
    * viewport width 视口宽度的1%，包含滚动条
  * vh
    * viewport height 视口高度的1%，包含滚动条

## 34. 显示器的物理分辨率为1920x1080，操作系统设置的分辨率为1280x720，网页的放大倍数为110%，请计算一个CSS像素对应多少个显示器物理像素（面积与长度）？
  * 长度
    1.65
  * 面积
    2.7725

## 35. 写出如下代码显示在浏览器后每个单词的字号
```html
  <style>
  html {
  font-size: 20px;
  }
  section {
  font-size: 10rem;
  }
  p{
  font-size: 24px;
  }
  span {
  font-size: 150%;
  }
  .sucks {
  font-size: inherit;
  }
  </style>
  <body>
    <section>
    <h2>Brown</h2>
    <p>quick</p>
    <p>jumps <span>over <span>lazy</span> dog</span></p>
    <p class="sucks">sucks</p>
    </section>
  </body>
```
  * Brown
    * 300px
  * quick
    * 24px
  * jumps
    * 24px
  * over
    * 36px
  * lazy
    * 54px
  * dog
    * 36px
  * sucks
    * 200px

## 36. 如何给css添加注释
  * `/* css code */`

## 37. 指出如下css代码中的错误
```html
  p,h1,{                            <!-- 逗号多余 -->
    background-color: rgba:(abc)    <!-- 冒号多余，颜色缺少α通道参数，缺少分号 -->
    font-varient; abc;              <!-- 拼写错误，将冒号误写为分号，属性值书写错误 -->
    colr: #ff048;                   <!-- 属性名拼写错误，16位色彩表示错误 -->
    font: "serif" 25px;             <!-- font属性值顺序错误，字体族书写没有引号 -->
  }
```

## 38. 写出如下结构中div元素的所有后代/祖先/子/父/兄弟元素
```html
  <section>
    <h1><span></span></h1>
    <main>
      <h2></h2>
      <div>
        <ul>
          <li><a href=""><img src="" alt=""></a></li>
        </ul>
      </div>
      <aside>
        <h3></h3>
      </aside>
    </main>
  </section>
```
  * 后代
    * ul,li,a,img
  * 祖先
    * main,section
  * 子
    * li
  * 父
    * main
  * 兄弟
    * h2,aside

## 39. 常见的替换元素有哪些？它们与非替换元素最大的区别什么？
  * input,select,img,iframe,audio,video
  * 不能任意添加后代
  * 替换元素内容或资源需要从外部加载

## 40. 让css在html页面上生效有哪几种方法，分别写出来。
  * 外部文件
  `<link rel="stylesheet" href="http://www.jd.com/xxx.css">`
  * style标签内
```html
  <style>
    html{
      font-size: 20px;
    }
  </style>
```
  * html标签的style属性 `<h2 style="font-size: 30px; color: cyan;">XMA</h2>`

## 41. 如何让页面打印时应用不同的效果？
  * `<style media="print"></style>`
  * `<link rel="stylesheet" href="" media="print">`

## 42. 假设index.html的路径为 http://user.coding.me/task/index.html ，如下引用的a.css和b.css路径分别为？
```html
<!-- index.html的内容 -->
<style>
  @import "../a.css";
</style>
```

```html
/* a.css的内容 */
@import "b.css";
```
  * a.css
    * `http://user.coding.me/a.css`
  * b.css
    * `http://user.coding.me/b.css`

## 43. 写出满足如下条件的选择器
  - 第5个子结点之后，倒数第6个子结点之前的第奇数个li结点
  - 【类名】以“damiao-”开头的元素
  - rel属性中有nofollow这个单词的标签
```css
  li:nth-child(n+5):nth-last-child(n+6):nth-child:(2n+1) {}
  [class^="damiao-"], [class*=" damiao-"] {}
  [rel~="nofollow"]
```

## 44. 链接伪类的几种状态书写的顺序是什么？为什么？
  * a:link {}
  * a:visited {}
  * a:focus {}
  * a:hover {}
  * a:active {}
  * 此顺序符合操作逻辑，由于优先级相同，如果后三种伪类顺序颠倒，如果a:hover {} 位于a:active之后，:hover将在两种状态下均生效；如果a:focus位于a:active之后，:focus将均在两种状态下生效。

## 45. 如下font属性的值哪一个是书写正确的？并叙述font的正确书写格式
  * font: serif 24px;
  * font: serif bold 24px/1.2;
  * font: bold 24px/1.2 serif;
  * 最后一种书写形式正确
  * font: style|variant|weight|size/line-height|family

## 46. vertical-align取middle时元素如何对齐？
  * 应用于行内元素，影响该元素在一行内的垂直摆放
  * em框 -> 内容区 -> 行内框   行间距，行高
  * 与英文字母X的中心对齐
  * baseline
    * 标签内文字的baseline和标签外文字的baseline对齐
  * top
    * 元素顶部与行框顶部对齐
  * text-top
    * 元素顶部与标签外文字顶部对齐
  * bottom
  * text-bottom
  * middle
    * 元素的中间与元素外文字x的中心对齐

## 47. 什么是baseline？
  * 英文书写中四线三格中的第三条线
  * 小写英文字母x的下方

## 48. 请写出实现“红色文字有蓝色下划线”的html与css实现。
  * <span style="text-decoration: underline; color: blue;"><span style="color: red;">xxx</span></span>

## 49. 请写出让访问过的链接字号变成50px的代码

## 50. 中英互翻
  * geek 极客
  * nerd 袋子
  * hacker 骇客
  * edge 边缘，刀锋
  * bleeding/cutting edge 前沿/尖端/可能存在风险的技术
  * HTML 实体 html entity
  * coordinate  坐标
  * polygon 多边形
  * bit 位 binary digit
  * byte 字节
  * alternative 可供替代的事物
  * 属性 attribute property
  * obsolate  废弃
  * 二进制 binary
  * 十进制 decimal
  * 十六进制 hexdecimal
  * octal 八进制
  * deprecate 不推荐
  * loop 循环
  * 行 列 row column
  * horizontal 水平
  * 语义化 semantic
  * 可访问性 accessible accessibility