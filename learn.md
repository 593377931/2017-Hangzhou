# 前端201709 杭州

标签（空格分隔）： 前端

---


* 上课时间
  * 09:00 - 12:00
  * 14:30 - 17:30
  * 18:30 - 23:00
* 坚果云
* 学好英语有什么用  知乎
* CSS 权威指南/The Book of CSS3/Eloquent JS
* 一进制（结绳计数）
* [十年学会编程](https://bitandliteracy.github.io/21-days)
* [花两年时间去面试一个人](http://mindhacks.cn/2011/11/04/how-to-interview-a-person-for-two-years/)
* [来自老程序员的建议](https://flyouting.gitbooks.io/learn-python-the-hard-way-cn/content/learn-python-the-hard-way-Advice_From_An_Old_Programmer.html)
* [如何掌握所有的程序语言](http://www.yinwang.org/blog-cn/2017/07/06/master-pl)



----------



* win-run:
* 环境变量 PATH
  * 是一个路径的列表，每项都是一个绝对路径
* Windows系统常用快捷键https://support.microsoft.com/zh-cn/help/12445/windows-keyboard-shortcuts
* 快捷键 AutoHotKey

* 编辑器中上下行换行 Ctrl+Shift+方向键

* everything（打开快捷键设置）
* StrokeIt（鼠标手势）
    - 软件
    - 手势
    - 发送给对应软件的快捷键

* 菲茨定律

* 浏览器
    * 自主内核浏览器
    * IE -> EDGE / Chrome / Firefox / Safari / Opera
      * Safari -> webkit
      * Chrome webkit 
      * 15年，Opera转用webkit内核
      * Blink
      * Firefox -> gecko
      * trident
      * Edge HTML

* 移动端浏览器
  * 安卓自带浏览器
  * 微信浏览器
  * IOS浏览器

* 兼容性
  * 早些年兼容性出现在CSS中

* 常用编辑器
  * Sublime
  * Atom
  * VSCode

* 图片格式
  * jpg：有损压缩；适合存储现实照片
  * png：无损压缩；适合存储大面积相同色块的图片，不适合用来存储照片；支持透明色（Alpha通道）
  * gif：无损压缩；颜色表；一般来说图片尺寸小；抽样出256种颜色；不存储每张图的所有点，第一帧是一张完整图片只存储变化了的那些点
  * bmp：无压缩，无损;体积大，不适合用在网页中 * 
  * psd：保存了Photoshop在构造这张图片的过程中的所有信息
  * webp：Google发明；有损压缩；各方面胜过jpg；适合在移动端使用；支持透明

* GUI
* CLI
* API

* 技能树
* 基础
  * mingw
  * cgywin
  * promot
  * 将命令的结果输出至文件 >
  * 命令的结果追加至某个文件 >>
  * 管道符：前一个命令的输出结果作为后一个命令的输入 |
* 常用linux命令
  * ls
  * cat:拼接
  * grep：搜索
  * echo
  * cd:change directory
  * cd .. 父文件夹
  * mkdir:创建文件夹
  * rm: 删除
    * rm -r: 删除文件夹和其内容
  * cp: 复制
  * mv：移动
  * time: 命令运行时间
  * date：显示时间和日期
  * cal: 日历
  * ping
  * touch: 创建文件
* ASCII   American Standard Code for Information Interchange
  * A 65
  * a 97
  * 0 48
  *   32
  * 换行 10
  * Enter 13

---


* 再谈二进制 

0000  | 0   |
0001  | 1   |
0010  | 2   |
0011  | 3   |
0100  | 4   |
0101  | 5   |
0110  | 6   |
0111  | 7   |
1000  | 8   |
1001  | 9   |
1010  | A   |
1011  | B   |
1100  | C   |
1101  | D   |
1110  | E   |
1111  | F   |


* Markdown

---

* HTML
  * 正确嵌套 `<div>markdown<i>language</i></div>`
  * 递归(树状)结构
    * 自相似
  * 自闭合标签 `<input />`
  * 语义正确
  * 父元素
  * 子元素
  * 祖先
  * 后代元素
* 代码缩进：两个空格(区别于tab)
* 语义化：用正确的标签描述合适的内容

* 属性
  ```
  <tag attr1="val1" attr="val2"></tag>
  <person age="28" gender="man"></person>
  ```
* 全局(通用)属性
  * title
  * alt 主要用在图片中 alternative 可选项，替补
  * class
    * 属性的值是空格分割的单词列表
* `<!DOCTYPE html>` 文档类型声明

```html
<body>
  <head>
    放置文档的源信息
  </head>
  <body>
    此处内容会直接显示在浏览器窗口中
  </body>
</body>
```


* HTML 实体
    <: &lt; ":&quot; &:&amp; ':&apos; &nbsp; non-breaking-space
* HTML 标签
  * html 
    * 根标签 root element
    * 一个页面只能有一个
    * 没有浏览器也会自动添加
  * head
    * 头部标签,存放与页面相关的"元信息"
      * 页面的编码方式
        `<meta charset='utf-8'>`
      * 页面的标题
        `<title>页面标题</title>`
      * 页面图标
        * 在页面中指定某个图标
          `<link rel="icon" href="http://www.baidu.com">`
        * 浏览器会自动读取网站根目录下的favicon.icon文件
      * 样式表
        `<link rel="stylesheet" href="">`
      * 指定渲染引擎`<meta name="UA-X-Compatable" content="EDGE" />`
      * 指定页面以多宽的尺寸渲染 viewport
    * head里的内容不会显示在页面上
    * 页面中没有head标签时,会自动添加
  * body
    * 想要在页面中被显示的内容存放的位置
    * 如果页面没有body标签或head标签,浏览器会自动添加,并将内容包含在body内
      * 同时,浏览器会将必须放进head标签内的内容放进head标签中,如title标签.
  
  * title
    * 页面标题
    * 仅支持纯文本,不支持标签嵌套
    * 如果不出现在 head 标签中,会被移动至 head 标签
    * 仅第一个 head 标签生效
  
  * base
    * 设置页面a标签的href属性为相对地址时,的参考路径
      ```
      <base href="http://www.baidu.com/" target="_blank"></base>
      ```

      * 相对路径
        * `<a href='a.html'></a>`
        * 相对于当前页面所在的文件夹进行访问
        * 可通过在 head 标签中添加 base 标签修改相对文件夹
      * 绝对路径
        * 按完整路径访问
    * 指定页面相对路径
    * target属性指定页面中所有链接的打开方式
  
  * h1-h6
    * 默认上下留白
    * 传统观点认为页面不能超过一个h1,以实现SEO
      * SEO
        - 关键字
        - 页面被引用的次数
        - 使用https
        - 使html更语义化
    * HTML5 中新增了 hgroup 标签
      当不同级别标题显示在一起时使用此标签
  
  * p
    * 段落

  * a
    * anchor,锚
    * 语义是链接,连接地址写在herf(hyperlink reference)属性中
    * href属性
        - 绝对网址
        - 页面内特定位置跳转`<a href="#pos1"></a>`
        - 其他页的特定位置
        - 电子邮件

          ```
          <a href="mailto:aa@bb.com?title=">Send me an email</a>
          ``` 

        - 电话
        
          ```
          <a herf="tel:18728783872">call me</a>
          ```
        - 空的href属性代表本页面
        - QQ/淘宝
          ```
          tencent://temp-chat?QQ=23451234
          thunder://LKSFSFSffkLJ/
          ```
    * download属性

  * img
    * src属性
    * alt属性
    * width/height 属性
  * span
    * 没有明确语义的标签

  * hr
    * 分割线
  * br
    * 换行
  * font/blink/marquee
    * obsolete 已弃用标签
  * em
    * 语义强调
  * strong
    * 语义上更强调
  * b
    * 视觉上加粗,没有语义强调
  * 可访问性
    * 读屏、不同设备
  * u
    * underline
  * i
    * italic 斜体
    * html5中明确了其语义
      * 由于某些原因需要与普通文本区分开来
    * 默认情况下为斜体
    * 很多框架和库使用i标签来表示图标
  * 注释`<!-- 这是一段注释 -->`
    * 注释是对程序本身的解释,几乎不会对程序造成影响
    * 行注释 `//`
    * 块级注释 `/* */`
  * pre
    * 预定义 preformated
    * width属性:表示每行最多的字符,在html5中弃用
    * 常与code标签配合使用

    ```js
    <pre>
      <code>
        var a = 1;
      </code>
    </pre>
    ```
  * 列表类标签
    * ol,ul
      * 其直接子节点最好是li标签
      * 默认会在美多一层级的标签中缩进
      * 多个同类项重复,就应该使用ol/ul标签
    * dl description list
      * dt
      * dd
      * 一个列表项由一个dt和多个dd组成

  * 表单类标签
    * form
      * action属性
        * 表单提交地址
      * target
        * 设置提交跳转位置,`_blank`
      * method
        * 提交方式
    * 一般来说所有表单类标签都应放进form标签内
    * input
      * type属性
        * text 文本
        * password 密码
        * checkbox 复选框
          * 使用name属性进行分组
        * radio 单选
          * 使用 name 进行分组，每个input设置相应的value属性进行区分
        * file 文件
          - accept 接收文件的格式  `<input type="file" accept=".jpg .png">`  `<input type="file accept=".jpg">`
          - mulitple 选择多个文件 `<input type="file" accept="image/*" multiple>`
        * hidden 隐藏，但是在表单提交时会进行相应提交
        * image `<input type="image" src="">`
          * 默认显示为按钮，按钮内容是一个图片
        * button `<input type="button" value="提交">`
        * submit `<input type="submit">`
        * reset `<input type="reset">`
      * html5新增的type属性
        * number
        * email
        * date
        * time
        * url
        * week
        * month
        * tel
        * range`<input type="range" min="10" max="90" step="5">`
        * color 色板
      * type属性浏览器不能识别时，默认为text属性进行展示
      * value
        * 文本框的默认值
        * button上的文字
      * disabled
        不能输入状态
      * required
      * maxlength
      * minlength
      * placeholder 提示性文字
      * autofocus 页面加载完成后，光标跳转在此input内
      * tabindex
        * 影响按tab键时,光标的跳转顺序
        * 值为-1时,会跳过
      * name
        * 表单提交时，这个域/字段的名字
    * button
      * 没有type属性的button默认为提交
      * 非自闭合标签,可嵌套其他内容,input只能显示纯文字
      * type
        * submit
        * reset
        * button
    * label
      * for 属性绑定对应的控件id属性
      * 将表单控件和相应的文字写进同一个label中
      * 扩大点击区域
    * select
      * 下拉
      * 子元素为option
        * option 可以没有value属性时,其值为option标签内的值
      * multiple 所选
      * 样式很难修改
      * selected
      * hidden
      * disabled
    * optgroup
     * ```html
        <optgroup label="上海">
          <option>浦东</option>
          <option>外滩</option>
        </optgroup>
       ```
    * textarea
      * 多行文本输入框
      * 默认内容写在标签中
      * rows属性
      * cols属性
    * fieldset
      * 将多个表单的输入控件组合在一起
      * 使用 legend 标签可设置此集合名称
      * 设置disabled属性，可不显示整个组合
    * table标签
      * 以前经常用于做布局(页面大区块的排列和摆放)
      * table是方方正正的格子,了解后易于控制
        * 语义很差
        * 可读性差
        * 可维护性差
        * 可访问性
      * 目前基本上只用table来显示数据
      * caption
        * 表格标题
      * thead
        * 表头
        * 即使出现在tbody的后面,也会被渲染至表头前面
        * 多余的thead会被作为tbody处理
        * 打印时，会在每一页的头部显示
      * tbody
        * 表格主体
        * 表格中可有多个连续的tbody
      * tfoot
        * 表格尾部
      * tr
        * 表格行
      * td
        * 单元格
        * td单元格的headers属性应和相应的表头th的id属性相对应
      * th
        * 表头
      * col
        * t抽象出的table列
        * 必须需要紧跟caption标签出现
      * colgroup
        * col组
      * map
        * area
          - shape属性
            * rect 矩形
              * coords "xy,xy"
            * circle 原型
              * coords
            * poly 多边形
              * coords 多个坐标点
      * iframe
        * target attr
          * `_self`
          * `_blank`
          * `_parent`
          * `_top`
          * 自定义
        * name
      * frameset 将整个页面划分
      * frame
  * 不同标签在进行退化时的方式不相同
    * 正常使用时，标签内是空的时，退化内容写在标签内
    * 正常使用是，标签内应有内容，退化内容写在标签外

---
* HTML5新增的一些语义标签
  * article
  * section
  * aside
  * header
  * footer
  * nav
  * main
  * template
* 其他常见标签
  * sub 下标
  * sup 上标
  * noscript
  * code
    - 与pre标签组合使用
  * kbd
  * script
    * 不能在此标签内以任何明文的形式出现`</script>`
  * style
* 多媒体标签
  * video
    ```
    <video src="a.mp4" autoplay loop preload controls>
      <source src="a.m3u8">
      <source src="a.webm">
    </video>
    ```
    * mp4
    * m3u8
      * 包含了分拆了视频文件地址的列表
    * webm
    * flv.js
  * audio 
    * mp3
    * ogg
    * wmv
    * wav
  * object
    * 内嵌任何对象
    * type属性
      * 标明嵌入对象类型的媒体类型
  * canvas
    * 画布
    * width/height
  * progress
    * 进度
    * max
    * value
  * div
  * span
  * Doctype
    * 文档类型声明
    `<!DOCTYPE html>`
    * HTML5 到目前为止，所有前端技术合集
    * 如果不写，IE下会以怪异模式渲染，IE6引入，主要区别是在css盒模型计算方面
  * meta
  * link
    * 引入外部文件 css 图标
  * 语义化
    * 用合适的标签描述合适的内容
    * 方便人与机器理解
    * 有利于SEO
    * 合理使用h，p，列表，表格，div，html5心怎的语义标签
    * 使用合适的嵌套
    * 给元素命名合适的类和ID
* 标签分类
  * 曾经：
    * 行内标签
    * 块级标签
  * 现在

    * role与aria- 属性
      * role 使用其余非语义元素来模拟一些语义标签
      * aria- 描述所模拟的元素的交互状态
    
---

* GIT
  * 版本控制工具 source control manager
  * git config --global user.email "you@example.com"
  * git config --global user.name "Your name"
  * git init 
  * git commit -m "commit massage"
  * git diff
  * git remote add XXX http://.........
  * git push -u XXX 

  ---

## Sublime
* 快捷键
* package control

## Developer Tools




## css
* 没有CSS时，使用html属性来控制样式
* Dont't repet yourself！
* html不能选择各种度量单位，只能选择像素和百分比
* 可精准控制到每个像素
* 精准控制每个元素的摆放
* 更加精细的样式
* 专为UI开发设计
* 样式之间可覆盖，有优先级，还可继承
* 替换元素和非替换元素
  * replaced elements
    * 一般没有后代元素/标签/节点的
    * 内容被其他不在文档里的内容替换了的元素
  * non-replaced elements
    * 内容直接显示在页面中
    * 内容直接出现在标记中
* 元素的显示角色 dispaly role(不是html5中的role属性)
  * 布局上下文
  * 块级元素 block
    * 块级元素会占满父元素的宽度
    * p,div,h1
    * display属性可改变元素的显示角色
  * 行内元素 inline
    * 在一行文字内产生的元素框
    * 
  * css引入
    * 内联style标签
    * link标签引入
      * 可设置在什么情况下生效，media属性设置显示介质，screen和print
    * 任意标签的style属性
    * DOM
    * style标签内可使用@import "a.css" 引入css文件
      * 会形成树状依赖关系
    * 
* CSS规则
  * 选择器 selector
    * 可使用逗号分组
    * `*`选择所有属性
    * 标签选择器
      * ```css
        div {}
        p {}
        div,p{}
        ```
    * 类选择器
      * `.p{}`
      * 大小写敏感
    * ID选择器
      * 几乎不使用ID选择器
    * 属性选择器
      * `img[alt="foo"]`
      * `img[alt^="f"]` 选择img标签属性alt以f开头的标签
      * `img[alt$="f"]` 选择img标签alt属性以f结尾的的标签
      * `img[title*="bar"]`
      选择img标签title属性内包含bar字样的标签
      * `p[like~="orange"]` 选择p标签like属性包含orange单词的标签
      * `[foo|="zh"]` 选择foo属性是zh或以zh-kai头的标签
    * 组合选择器
      * 多个选择器组合起来
  * 规则块 role block
    * 每一条规则 rule
      * 声明
        * 必须是CSS支持的属性
      * 属性值
        * 必须是正确的值
      * 分号是每条规则的结束标志