### 1. border,box-shadow,outline有什么区别和异同？
- border会影响元素的布局，box-shadow和outline则不会
- *box-shadow 是沿着border画的，可模糊，可扩散*
- *outline，可能不是矩形，但一定是直角多边形，四个方向上只能是一种样式*

### 2. 写出一个与选择器【.foo.bar】意义和优先级完全相同的选择器
- `[class~="foo"][class~="bar"]`
- `[class*=" foo "],[class^="foo "],[class$=" foo"]`,`[class*=" bar "],[class^="bar "],[class$=" bar"]` 笛卡尔集

### 3. vertical-align取middle时元素如何对齐？
- 行内元素的行内框垂直方向的中间(margin-box垂直方向的中间位置)与父元素内的匿名文本小写字母x的中心对齐

```
- 纯文本，匿名文本
  - 高度就是line-height
  - 基线为x下边缘
  - 永远都是baseline对齐
- 行内非替换元素
  - 高度依然是line-height
  - 基线依然是x下沿
- 替换元素
  - 高度为margin-box
  - 基线是margin-box下缘
- inline-block
  - 高度是margin-box
  - 基线
    - 有内容：最后一行的baseline
    - 无内容：margin-box下缘
```

### 4. 什么是baseline？
- x字母下沿，每个字符在设计时都有一个基线，对齐方式默认时，行内元素按照此基线对齐

### 5. 详述你对盒模型的理解。
- 每个元素在进行布局时，都会在生成一个矩形框，矩形框的中心，是内容区，由内容区向外分别是内边距，边框，外边距。每个元素相对其包含块进行摆放，通过设置这几项值的大小，实现元素的布局。

### 6. 元素的高度写百分比在什么情况下【无效】，为什么？在什么情况下【有效】，有效时是以哪个元素的高度为基准值？
- 在其包含块没有显式的声明其高度，而是依靠其内部的元素确定包含块的高度时，其内部的元素高度值设置为百分比是无效。
- 在其包含块高度与内部元素高度之间没有依赖关系时设置有效，基准值为其包含块的高度。

- *当父元素的高度会被子元素影响时，子元素的高度写百分比无效*
- *包含块：一个元素离其最近的（块级元素/表单元格/行内块级祖先框）的内容边界*

### 7. 字体的italic与obsolete的区别是？
- itialic是字体内部内置的斜体字符
- oblique是用户代理将正常的字符强制渲染为斜体
- 当前字符字体没有内置斜体字符时，itialic与oblique表现实行相同
- obsolete 弃用

### 8. 解释box-sizing可以取哪些值，以及每个值的意义
- border-box:在对元素进行[max/min-]width/height属性设置时，将设置其border-box的大小，即边框最边缘的框的大小，元素的大小计算将加上外边距的大小。
- content-box:在对元素惊醒[max/min-]width/height属性设置时，将设置其content-box的大小，即其内容区的大小，元素的大小计算将加上内边距，边框和外边距。

### 9. 如下结构中，div有两个伪元素，分别标出伪元素的位置，用 <before></before> 表示 ::before ，用 <after></after> 表示 ::after
```html
<div>
    <h1>The article</h1>
    <p>the quick brown fox</p>
</div>
```

```html
<div><before></before>
    <h1>The article</h1>
    <p>the quick brown fox</p>
<after></after></div>
```

### 10. 如何在伪元素中插入换行符？如何让这个换行符在页面中生效？
- pseudo element newline
- [CSS ESCAPES](https://www.w3.org/International/questions/qa-escapes#cssescapes)
```css
:bofore {
  content: "Line Flow\a Carriage Return";
  white-space: pre;
}
```

### 11. 画出如下代码中div及其子元素的渲染结果，并指出p标签中【每个行内元素的，内容区，行内框的范围】，p元素的行框，并指明理论的行框高度。有尺子的可以以1mm为2px来绘制。
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>JS Bin</title>
        <style>
            p {
              font-size: 20px;
              line-height: 120%;
              margin: 30px;
              margin-left: auto;
              margin-right: -20px;
              width: 300px;
              background-color: tan;
            }
            .a {
              display: inline-block;
            } 
            .b {
              font-size: 30px;
              vertical-align: 15px;
            } 
            .c {
              display: inline-block;
              width: 60px;
              height: 60px;
              background-color: pink;
              margin: 8px;
            }

            img {
              box-sizing: border-box;
              width: 50px;
              height: 50px;
              border: 2px solid;
              margin: 4px;
              vertical-align: -20px;
              margin-bottom: -5px;
            }
            div {
              width: 400px;
              border: 1px dotted;
            }
        </style>
    </head>
  <body>
    <div>
      <p>
      <span class="a">foo</span>
      <span class="b">bar</span>
      <span class="c"></span>
      <img src="https://drs">
      </p>
    </div>
  </body>
</html>
```
![img](https://q593377931.coding.me/miao/excrise2-13.png)

- span.a 内容区高度20px，行内框高度24px，基线对齐
- span.b 内容区高度30px，行内框高度36px，基线向上15px对齐
- span.c 行内框高度76px，margin-box底部与baseline对齐
- img 行内框高度49px，baseline向下20px与margin-box底部对齐
- p元素行框高度为96px

### 12. 何为缓动函数（即transition-timing-function）？它有哪些内置值？如何自定义一个缓动函数？
- 定义元素属性发生变化时的变化方式，精确描述了元素属性在变化过程中距离目标的距离和变化的速率
- *0 0 , cubic-bezier(x1,y1) , 1 1*
- linear:线性
- ease
- ease-in
- ease-out
- ease-in-out
- step(5[,start|end])

- transition
  
  Transition 属性用来定义元素在两个状态之间如何过渡,不同的状态可以用伪类来定义,如 `:hover`或`:active`,也可以使用JS来动态的定义.
  - transition-property

    transiation-property属性用来指定transition效应应用的属性的属性名
    - 初始值: all
    - 应用于: 所有元素, ::before和::after伪元素
    - 不继承
    - value
      - none: No properties will transition
      - all: All properties that can have an animated transition will do so.
      - 某个属性值在某状态下会发生变化的属性的属性名
  - transition-duration

    transiton-duration属性用来指定一个以秒或毫秒为单位的数字, 以确定属性变化过程所需的时间.
    - 初始值: 0s
    - 应用于: 所有元素, ::before和::after伪元素
    - 不继承
    - value
      - 以秒或者毫秒为单位的数字 `2s,0.5ms`
  - transition-timing-function

    缓动函数(transition-timing-function)是用来描述被transtion effect影响的CSS属性中间值的是如何被计算出来的. 本质上是让你确定一个加速度曲线, 这样在其属性变化过程中速度会有所不同.
    - 初始值: ease
    - 应用于: 所有元素, ::before和::after伪元素
    - 不继承
    - value
      - `<timing-function>`
        - `<single-transiton-timing-function>`
  - transiton-delay

### 13. 什么是模拟信号？什么是数字信号？它们的区别是？
- 任何信号都是实际存在物理值，当此物理值被直接拿来处理使用时此信号即为模拟信号，当此信号舍弃其误差进行处理是，即为数字信号

### 14. 将如下markdown转换成html
```html
<h2>四季变换</h2>
<p>一年有四季，<br>四季有其对应的节气</p>
<ul>
    <li>
        春
        <ul>
            <li>立春</li>
            <li>惊蛰</li>
            <li>元宵</li>
        </ul>
    </li>
    <li>
        夏
        <ul>
            <li><strong>粗粮</strong>发布会</li>
            <li>菊花发布会</li>
        </ul>
    </li>
    <li>
        秋
        <ul>
            <li>开学了</li>
            <li>军训了</li>
        </ul>
    </li>
    <li>
        冬
        <ul>
            <li>
            下雪了
                <ul>
                    <li>
                        打雪仗了
                    </li>
                </ul>        
            </li>
            <li>来暖气了</li>
            <li>开空调了</li>
        </ul>
    </li>
</ul>
<cite title="">知识就是力量，法国就是培根。</cite title=""><br>
<a href="http://baike.baidu.com/item/%E6%98%A5/6983693">春</a><br>
<img src="https://www.google.com.hk/images/nav_logo242_hr.png" alt="春">
```

### 15. 如下表单提交后将跳转到什么地址
- `https://www.baidu.com/s?a=bb&b=123&b=456&c=a5&select=03`

### 16. 列出input的type有哪些值，以及为各个值时分别需要怎么使用
+ text
  - 输入文本
+ number
+ password
+ radio
  - 单选按钮，同一组内的按钮设置相同的name属性
+ checkbox
  - 多选框
+ date
  - 日期
+ time
  - 时间
+ datetime
+ submit
  - 提交按钮
+ reset
  - 重置
+ color
  - 颜色
+ img
  - sec
  - alt
  - title
+ range
  - min
  - max
  - step
  - 范围
+ file
  - accept
+ url

### 17. 想要让一个文本输入框在页面打开后自动获得光标要怎么办？
- 设置其autofocus属性

### 18. 如何在文本框里放置提示性文字？
- 设置其placeholder属性

### 19. 有坐标点（1，2），（3，4），（3，0），（8，1），画出它的大致Beizer曲线。可查维基百科。

### 20. option标签的主体内容太长影响用户体验，你会如何解决？
- 将完整文字写入option标签的title属性中，option标签内简写
- `<option title="详述xxxxxxxxxxxxxxx">简述</option>`
- 自定义select.js select2.js

### 21. 想要在textarea标签中默认显示一段html代码最安全的做法是什么？
- 使用html实体

### 22. 如何禁用一组输入框？ 如下表格渲染出来后是什么效果？不要直接将代码贴入jsbin中看效果
- 使用disabled属性
- *将这一组标签放进fieldset标签，给fieldset加上disabled属性，一般需要加上lengend标签，并是fieldset内的首个标签*

![img](https://q593377931.coding.me/miao/image/excrise2-table.png)

### 23. 写出如下标签或属性值的英文全称
- html(hyper text markup language)
- div(division)
- p(paragraph)
- a(anchor)
- em(emphasis)
- tr(table row)
- th(table head)
- td(table data)
- col(column)
- ul(unordered list)
- ol(ordered list)
- li(list item)
- dl(description list)
- dt(description term)
- dd(description data)
- pre(preformatted)
- nav(navigation)

- 属性：
- coord(coordinate)
- rect(rectangle)
- poly(polygon)
- href(hyper reference)
- src(source)

### 24. 页面有无doctype声明会有什么区别？
- 以标准模式渲染
- 以怪异模式渲染（quirk）
  - 在IE6下box-sizing会成为border-box

### **25. HTML的aria-*与role属性的作用是？**
- accessible rich internet application 可访问的富互联网应用
  - 可访问性：使产品能被更多的人在更多的情况下使用
  - 富：软件功能强大
- UI组件
  - select
  - checkbox
  - input
  - tab
- `<div aria-xxx="当前元素的特定状态" role="当前的div在模拟什么ui组件"></div>`

### 26. 有一张高为100宽为50的图片，内有一个直径为40的圆，其做为一个200x200的元素的背景图片，background-size为contain和cover时，圆的直径分别为多少？
- contain: 80
- cover: 160

### 27. 什么是CSS Sprite？为什么要使用CSS Sprite？它有哪些优缺点？
- CSS图片精灵
- 将页面中小图标集中存储在一份图片中，配合元素大小，通过设置标签的background-positon属性设置偏移，确定位置。
- 使用css sprite减少网络请求，降低传输过程中的网络流量。缺点就是，如果此图片没有正确传输，将导致整个页面图标不能加载，不好维护（放大），只能是静态图片。

### 28. 如何理解inline-block元素？它有什么需要注意的地方？
- 对其后代元素来说，inline-block元素等同于块级祖先元素（BFC，内部内容认为自己在一个浏览器窗口中布局）
- 对其兄弟元素来说，inline-block元素与行内替换元素类似
- 但在baseline对齐方式上略有差别。inline-block元素内有文本内容时，默认对齐方式为内部文本的baseline与inline-block外部的baseline对齐，内部没有文本时，inline-block的margin-box下边缘与外部baseline对齐。
- inline-block会出发一个块级格式化上下文

### **29. color这个属性有什么需要注意的地方？**
- transparent
- border,shadow,outline 默认值为color属性的设置值
- currentColor在任何时候可以用来引用当前元素的color属性值

### 30. 简述em框，内容区，行内框，行框的构成以及其需要注意的问题
- em框：em框在字体中定义，font-size值确定了em框的高度，快读取决于字体和具体字符
- 内容区(content area)：行内非替换元素的em框组合起来构成内容区，行内替换元素的内容区等于margin-box大小
- 行内框：非替换元素的行内框高度为(line-height - font-size)/2 加至内容区的上下构成行内框，垂直方向的padding,border,margin都不计算在行内框内；替换元素的行内框高度为margin-box值大小
- 行框的高度，为包含该行行内框最高点和行内框最低点的最小框（该行最高的行内框顶部至改行最低的行内框底部）

### 31. 如何确定一个行内框的baseline及其最高点和最低点？
- 匿名文本，x下沿
- 对于行内非替换元素，在通过font-size和line-height值确定了行内框的大小，其baseline位置为其内部匿名文本的baseline位置。
- 对于行内替换元素，其baseline值为元素的margin-box下沿
- 对于inline-block元素
  - 其包含匿名文本时，baseline位置为最后一行文本的baseline位置
  - inline-block为空时，baseline位置为其margin-bottom位置
- 将行内框的baseline与行的baseline对齐之后，根据其vertical-align值确定其相对与行baseline的相对位置确定行内框的baseline位置，进而确定该行内框的最高点和最低点。

- 范围
  - 匿名文本和行内非替换元素
    - 行内框上下沿
  - 替换元素和inline-block
    - margin-box上下沿

### 32. 找出如下代码中的错误
```html
<style>
  div::after：hover {
    opacity: 85%；
    transition: opactiy .3s step(5,end);
  }
  a:visited {
    font-size: 28px;
  }
</style>
<div>
  <a href="jd.com”>京东商场<a>
  <a href="mi.com”>小米网<a>
</div>
```

- :全角
- :hover
- 0.85
- opacity
- ;全角
- a标签的visited伪类不能设置其字体大小
- "全角
- a标签的结束标签书写错误
- href属性值为相对路径
- https://www.a.com/a/b/c/d
  - //jd.com
    - https://jd.com
  - /jd.com
    - https://www.a.com/jd.com
  - jd.com
    - https://www.a.com/a/b/c/jd.com

### 33. 如下内容渲染在【同一行】中，请计算那一行的理论行高
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport"   content="width=device-width">
    <title>JS Bin</title>
    <style>
      div {
        margin: 80px;
        background-color: violet;
      }
      span {
        display: inline-block;
        border: 1px dotted;
        background-color: pink;
      }
      .a {
        vertical-align: -15px;
        width: 30px;
        height: 30px;
      }
      .b {
        margin-top: -50px;
        width: 30px;
        height: 30px;
        vertical-align: top;
      }
      .c {
        margin-bottom: 10px;
        vertical-align: middle;
      }
      .d {
        width: 30px;
        height: 30px;
      }
    </style>
  </head>
  <body>
    <div>
      x<span class="a">foo</span>
      <span class="b">bar</span>
      <span class="c">baz</span>
      <span class="d"></span>
    </div>
  </body>
</html>
```
![img](https://q593377931.coding.me/miao/image/excrise2-33.png)

### 34. 各类行内元素的vertical-align取值为baseline时在不同情况下分别是如何对齐的？
- 非替换元素：内部文本的baseline与行内匿名文本的baseline对齐
- 替换元素：margin-bottom
- inline-block
  - 无内容：margin-bottom
  - 有内容：最后一行的baseline

### 35. 写出创建如下目录结果的命令行脚本（注意：有扩展名的为文件，没有扩展名的为文件夹）。
- mkdir a
- cd a
- touch readme.md
- mkdir foo bar
- cd foo
- mkdir c
- cd ../bar
- touch a.txt b.txt
- mkdir y
- cd y
- touch a.js

### 36. 常见缓动函数有哪些，画出其【典型的】【时间-距离】图像。
- `http://cubic-bezier.com`

### 37. 如何让一个元素可被focus？如何去掉其被focus时的虚框？
- `:focus {outline: none;}`

### 38. CSS中一般为何不使用cm，mm等长度单位？
- 由于页面放大，显示器参数，分辨率设置等因素，绝对长度单位不能被准确渲染

### 39. 把如下公式【等号右边反A左边】转换为通过函数名来表达数学符号的单行纯文本表达式形式
- f(n)=mul(division(pow(-1,n),factorial(add(mul(2,n)+1))),pow(x,add(mul(2,n)+1)))
- sigma(0,∞,f)