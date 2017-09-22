# 前端201709 杭州

标签（空格分隔）： 前端

---

## 9.19
* 上课时间
  * 09:00 - 12:00
  * 14:30 - 17:30
  * 18:30 - 23:00
* 坚果云
* 学好英语有什么用  知乎
* CSS 权威指南/The Book of CSS3/Eloquent JS
* 一进制（结绳计数）


----------

## 9.20

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
	*	安卓自带浏览器
	*	微信浏览器
	*	IOS浏览器

* 兼容性
	*	早些年兼容性出现在CSS中

* 常用编辑器
	*	Sublime
	*	Atom
	*	VSCode

* 图片格式
	* jpg：有损压缩；适合存储现实照片
	* png：无损压缩；适合存储大面积相同色块的图片，不适合用来存储照片；支持透明色（Alpha通道）
	* gif：无损压缩；颜色表；一般来说图片尺寸小；抽样出256种颜色；不存储每张图的所有点，第一帧是一张完整图片只存储变化了的那些点
	* bmp：无压缩，无损;体积大，不适合用在网页中	* 
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
* ASCII		American Standard Code for Information Interchange
	* A 65
	* a 97
	* 0 48
	*   32
	* 换行 10
	* Enter 13

---

## 9.21
* 再谈二进制 

0000	|	0   |
0001	|	1   |
0010	|	2   |
0011	|	3   |
0100	|	4   |
0101	|	5   |
0110	|	6   |
0111	|	7   |
1000	|	8   |
1001	|	9   |
1010	|	A   |
1011	|	B   |
1100	|	C   |
1101	|	D   |
1110	|	E   |
1111	|	F   |


* [十年学会编程](https://bitandliteracy.github.io/21-days)
* [花两年时间去面试一个人](http://mindhacks.cn/2011/11/04/how-to-interview-a-person-for-two-years/)
* [来自老程序员的建议](https://flyouting.gitbooks.io/learn-python-the-hard-way-cn/content/learn-python-the-hard-way-Advice_From_An_Old_Programmer.html)
* [如何掌握所有的程序语言](http://www.yinwang.org/blog-cn/2017/07/06/master-pl)


* Markdown
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

---

## 9.22

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
		* 
		* href属性
				- 电子邮件

					```
					<a href="mailto:aa@bb.com?title=">Send me an email</a>
					```	

				- 电话
				
					```
					<a herf="tel:18728783872">call me</a>
					```

	* hr
		* 分割线
	* br
		* 换行
	* font/blink/marquee
		* obsolete 已弃用
	* em
		* 强调
	* strong
		* 强调
	* b
		* 视觉上加粗,没有语义强调
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


* GIT
	* 版本控制工具 source control manager
	* git init 
	* 