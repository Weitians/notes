## &lt;head&gt;&lt;/head&gt; 内标签: 
##### **&lt;link/&gt; : 放在&lt;head&gt;内，用于链接样式表，引入样式文件。**

	• rel：当前文档与被链接文档的类型。
	• type：规定被链接文档的类型。
	• href：被链接文档的地址。
	• media：被链接的文档显示在什么设备上。

`设置地址栏图片方法：1.favicon.ico 放置在网站根目录，2.放在head内，使用link标签引入。 `

##### **&lt;base/&gt; : 定义页面中所有链接的默认地址或默认目标。**

	• href：定义页面中所有相对默认链接地址。
	• target：定义默认打开链接方式。_blank(在新窗口在打开）；

##### &lt;meta/&gt; : 提供页面相关的元信息，定义与文档相关的名称/值。

	• http-equiv: 把content属性关联到HTTP头部。
		- content-type：规定文档的字符编码；例：<meta http-equiv="content-type" content="text/html" charset="UTF-8">
		- refresh：定义文档自动刷新的时间；例：<meta http-equiv="refrsh" content="5">
		- X-UA-Compatible:针对IE浏览器优先使用什么模式渲染页面。例：<meta http-equiv=X-UA-Compatible" content="IE=Edge，chorm=1">

	• name： 把content属性关联到一个名称。
		- description：描述 ；例：<meta name="description" content="网站对外内容简短描述">
		- Keywords：关键词；例：<meta name="keywords" content="关键词内容">
		- renderer：设置浏览器渲染内核；例：<meta name="renderer" content="webkit">
		- viewport：指定客户是否可以缩放页面；例：<meta name="viewpoort" content="width=device-width" , initial-scale=1 ,  miximum-scale=1>
	• scheme： 定义用于翻译content的属性值的格式。

##### <script></script> : 可放在&lt;head&gt;里也可放在&lt;body&gt;里，用于定义客户端和引入外部脚步。

	• 必填属性：type；指定脚本类型（text/javascript>; 例：<script type="text/javascript"> alert("hello");</script>
	• 选填属性：
		- src；外部脚本文件的URL；
		- defer；是否对脚本执行进行延缓，直到页面加载完成，值与属性同名；
		- async；异步执行脚本（仅对外部脚本有效）值与属性同名；

##### <style></style> : 放在&lt;head&gt;内，定义样式信息；

	• 必填属性：type；指定样式表类型（text/css）；例： <style type="text/css">p{color: green}</style>
	• 选填属性：media；为样式表规定媒介类型；
		- screen；计算机屏幕（默认值）；
		- print；打印预览模式/打印页；
		- handheld；手持设备；
		- all；所有设备；
   
## &lt;body&gt;&lt;/body&gt; 内标签：
##### &lt;h1&gt; ~ &lt;h6 &gt; : 定义标题、文档的重点内容 &lt;h1&gt;最大，&lt;h6&gt;最小，常用&lt;h1&gt;~&lt;h3&gt;

 ><body>
    <h1>我</h1>
    <h2>是</h2>
    <h3>你</h3>
    <h4>爸</h4>
    <h5>爸</h5>
    <h6>哦</h6>
</body>

##### &lt;p&gt;&lt;/p&gt; : 定义段落，可放其他标签；

    <p>可以放任何内容，包括其他标签</p>

##### &ltbr&gt; : 换行符，可以加在标签之间，也可加在文本之间；

##### &lt;div&gt;&lt;/div&gt; : 定义文档中的一个分区（块）；

##### &lt;span&gt;&lt;/span&gt; : 定义文档中的行内部分元素；

><body>
    <h1>再次强调!! 我是你爸爸!!</h1>
    <div>今天超市<span style="color: red">大减价</span>,快去给林北买榴莲!</div>
</body>

| 块级（block） |内联（inline) |
| :--- | :----: | 
| ①总是在新行上开始；②高度，行高以及外边距和内边距都可控制；③宽度缺省是它的容器的100%，除非设定一个宽度；④它可以容纳内联元素和其他块元素。  |①和其他元素都在一行上；②高，行高及外边距和内边距不可改变；③宽度就是它的文字或图片的宽度，不可改变；④内联元素只能容纳文本或者其他内联元素。  | 
|div:分隔区块
section:文档节
nav:导航
header:页眉
article:文章
aside:文章侧栏
footer:页脚
details:元素的细节
summary:details元素可见的标题
dialog:对话框窗口
h1,h2,h3,h4,h5,h6:标题
p:段落
ul:无序列表
ol:有序列表
dir:目录列表
li:项目
dl:列表
dt:列表项目
dd:项目描述
menu:命令的菜单,列表
menuitem:菜单项目
command:命令按钮
form:表单
fieldset:围绕元素的边框(可用于表单内元素分组)
legend:在边框上的标题
select:选择列表(内联元素)
optgroup:组合选择列表选项
option:选择列表选项(也可做datalist选项)
datalist:下拉列表(id要与input中list属性值绑定)
table:表格
caption:表格标题
thead:组合表头内容(th)
tbody:组合主体内容(td)
tfoot:组合表注内容(td)
tr:表格行
th:表头单元格
td:表格单元
col:表格列属性;(空标签)
colgroup:表格格式化列组;
iframe:内联框架
figure:媒介内容分组
figcaption:figure标题
map:图像映射
area:图像区域
canvas:图形容器(脚本来绘制图形)
video:视频
source:媒介源
track:文本轨道
audio:声音内容
br:换行(空标签)
hr:水平分割线(空标签)
pre:格式文本
blockquote:块引用
address:文档联系信息
center:居中文本(不赞成使用)
spacer:在水平和垂直方向插入空间(空元素) 
 | span:内联容器
abbr:缩写
em:强调
strong:粗体强调
mark:突出显示的文本
b:粗体
i:斜体
bdi:文本方向
bdo:文字方向
big:大字体
small:小字体
sup:上标
sub:下标
del:被删除的文本
strike:删除线
s:删除线
ins:被插入的文本
u:下划线
nobr:禁止换行
wbr:单词换行时机(空标签)
tt:打字机文本
kbd:键盘文本
time:日期/时间
cite:引用
q:短引用("")
font:字体设定(不常用)
acronym:缩写(html5不支持)
dfn:字段(不常用)
a:锚点
img:图片
embed:内嵌(空标签)
label:input标记(点击文本触发控件)
input:输入框
button:按钮
keygen:生成秘钥(空标签)
textarea:多行文本输入框
output:输出结果
ruby:中文注音
rt:注音
rp:浏览器不支持ruby元素显示的内容
progress:进度条
meter:度量
var:定义变量
code:计算机代码文本
samp:计算机代码样本
select:下拉列表
| 

》》》内联元素用于块级元素内，不能表示完整的区块，只是区块内的一小部分 》》》

<a></a>:定义一个超链接；

	• 必选属性：href；链接到目标网站；
	• 选填属性：
		- target:打开链接的方式，默认当前页打开；
		- title:链接的标题；
	
	<body>
	    <a href="https://www.baidu.com">百度一下</a>
	    <a href="https://www.baidu.com" target="_blank" title="baidu">百度一下</a>
	</body>
	
<img/>:在网页中嵌入图片；

	• 必填属性:
		- src:图片的 url；
		- alt：图片无法显示时，显示文本信息；
	• 选填属性：
		- width：图片宽度；
		- height：图片高度；

<ul></ul>:无序列表，<li>为其列表项；

<body>
    <ul>
        <li>我</li>
        <li>是</li>
        <li>你</li>
        <li>爸</li>
        <li>爸</li>
    </ul>
</body>

<ol></ol>:有序列表，<li>为其列表项；

<body>
    <ol>
        <li>我</li>
        <li>是</li>
        <li>你</li>
        <li>爸</li>
        <li>爸</li>
    </ol>
</body>

<table></table>:表格标签，<th>为表头、<tr>为行、<td>为列，每一行必须相同列数；

<body>
    <table border="1">
        <tr>
            <th>姓名</th>
            <th>年龄</th>
            <th>性别</th>
        </tr>
        <tr>
            <td>小王</td>
            <td>2岁</td>
            <td>男</td>
        </tr>
        <tr>
            <td>小于</td>
            <td>5岁</td>
            <td>女</td>
        </tr>
        <tr>
            <td>小张</td>
            <td>4岁</td>
            <td>男</td>
        </tr>
    </table>
</body>





