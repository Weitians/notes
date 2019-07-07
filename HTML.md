### &lt;head&gt;&lt;/head&gt; 内标签: 
***
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
	• 选填属性：
		- media；为样式表规定媒介类型；
		- screen；计算机屏幕（默认值）；
		- print；打印预览模式/打印页；
		- handheld；手持设备；
		- all；所有设备；
   
### &lt;body&gt;&lt;/body&gt; 内标签：
***
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

##### &lt;br&gt; : 换行符，可以加在标签之间，也可加在文本之间；

##### &lt;div&gt;&lt;/div&gt; : 定义文档中的一个分区（块）；

##### &lt;span&gt;&lt;/span&gt; : 定义文档中的行内部分元素；

><body>
    <h1>再次强调!! 我是你爸爸!!</h1>
    <div>今天超市<span style="color: red">大减价</span>,快去给林北买榴莲!</div>
</body>

##### &lt;a&gt;&lt;/a&gt; : 定义一个超链接；

	• 必选属性：href；链接到目标网站；
	• 选填属性：
		- target:打开链接的方式，默认当前页打开；
		- title:链接的标题；
	
	<body>
	    <a href="https://www.baidu.com">百度一下</a>
	    <a href="https://www.baidu.com" target="_blank" title="baidu">百度一下</a>
	</body>
	
##### &lt;img/&gt; : 在网页中嵌入图片；

	• 必填属性:
		- src:图片的 url；
		- alt：图片无法显示时，显示文本信息；
	• 选填属性：
		- width：图片宽度；
		- height：图片高度；

##### &lt;ul&gt;&lt;/ul&gt; : 无序列表，&lt;li&gt;为其列表项；

<body>
    <ul>
        <li>我</li>
        <li>是</li>
        <li>你</li>
        <li>爸</li>
        <li>爸</li>
    </ul>
</body>

##### &lt;ol&gt;&lt;/ol&gt;:  有序列表，&lt;li&gt;为其列表项；

<body>
    <ol>
        <li>我</li>
        <li>是</li>
        <li>你</li>
        <li>爸</li>
        <li>爸</li>
    </ol>
</body>

##### &lt;table&gt;&lt;/table&gt; : 表格标签，&lt;th&gt;为表头、&lt;tr&gt;为行、&lt;td&gt;为列，每一行必须相同列数；

<body>
    <table border="0">
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

`colspan:用于横向合并 、rowspan：用于纵向合并，可用在<th><td> `

##### &lt;form&gt;&lt;/form&gt; : 表单标签，用于网页中提交信息；

	• 重要属性：
		- action：表单提交到何处；
		- method：提交表单的方法，get or lost；
		
	• <form>文本输入框；
		- type：文本类型,值为text；
		- name：定义名称；
		- value：输入框输入值；
		- placeholder：提示用户信息；
		- readonly：input输入值为只读，该属性值也为readonly；
		- disabled：input元素被禁用，该属性值也为disabled；
		
><body>
   <form action=“” method=“get”>
       <input type="text" name="user_name" value="" readonly="readonly" disabled="disabled" placeholder="请输入用户名">
    </form>
</body>

	• <form>单选框；
		- type：单选按钮,值为radio；
		- name：定义名称，n选一的单选框name值必须一致；
		- value：input的值；
		- checked：默认被选中的；
		
><form action="" method="get">
       男
       <input type="radio" checked="checked" name="gender" value="man">
       女
       <input type="radio"  name="gender" value="female">
</form>

	• <form>多选框；
		- type：多选框,值为checkbox；
		- name：定义名称；
		- value：input的值；
><form action="" method="get">
        <input type="checkbox" name="sexualorientation" value="man"/>男性
        <input type="checkbox" name="sexualorientation" value="female"/>女性
        <input type="checkbox" name="sexualorientation" value="bisexuality"/>双性
    </form>

	• <form>密码框；
		- type：密码框,值为password；
		- name：定义名称；
		- value：input的值；
		
><form>
        <input type="password" name="password" value="" placeholder="请输入密码"/> 
</form>

	• <form>隐藏域；
		- type：隐藏域,值为hidden；
		- name：定义名称；
		- value：input的值；
		
><form>
        <input type="hidden" name="user_token" value=""> 
</form>

	• <form>多行文本输入框，<textarea></textarea>；
		- type：多行文本框,值为textarea；
		- cols：宽度，n个字符宽度；
		- rows：高度，n行字读；
		- autofocus：页面加载后自动获得焦点；

><form action="" method="get">
        <textarea rows="10" cols="10" name="user_comment" placeholder="添加评论" autofocus="autofocus"></textarea>
</form>


	• <form>下拉选择框，<select></select>；
		- option：定义下拉框中的选择项；
			- value：option的值；
			- selected：值也为selected，初始选项中的选项；
					
		<form action="" method="get">
		        请选择你喜欢的手机品牌
		        <select name="test1">
		            <option value="type1">魅族</option>
		            <option value="type2">小米</option>
		            <option value="type3">华为</option>
		            <option value="type4">苹果</option>
		        </select>
		</form>

	• <lable></lable>：为input标签定义标注，当点击lable文本时，会触发相应的input控件；
		- 常用属性：for；值为input标签定义的id，将for绑定到该id上时触发。
		
		用法1：
		<form action="" method="get">
		         <label for="man">男性</label>
		        <input type="radio" name="gender" id="man"/>
		        <label for="female">女性</label>
		        <input type="radio" name="gender" id="female">
		 </form>
		
		用法2：
		<!--把input放入lable内可以不用每个选项都设定id-->
		<form action="" method="get">
		    <label>读书<input type="checkbox" name="hobby"/></label>
		    <label>写作<input type="checkbox" name="hobby"></label>
		</form>
		
	• reset：重置按钮；
		- 常用属性：value，按钮文本显示；
		
		<form action="" method="get">
		        邮箱：<input type="text"  placeholder="请输入邮箱地址" name="email"/><br/>
		        密码：<input type="password" placeholder="请输入密码" name="password"/><br/>
		        <input type="reset" value="重置"/>
		</form>
	
	• submit：提交按钮；
		- 常用属性：value，按钮文本显示；
	
		<form action="http://www.baidu.com" method="get">
		        邮箱：<input type="text"  placeholder="请输入邮箱地址" name="email"/><br/>
		        密码：<input type="password" placeholder="请输入密码" name="password"/><br/>
		        <input type="submit" value="登录"/>
		</form>
	
	• <button></button>：定义一个按钮，可放在<form>之外；
		- 常用属性：
			- value:按钮提交的值，与submit和reset有区别；
			- name:规定按钮的名字；
			- type：按钮类型；button、submit、reset等；
	
		<button type="button" name="">提交按钮</button>
	
	
##### &lt;iframe&gt;&lt;/iframe&gt; : 框架，内嵌另一个文档；

	- 常用属性：
		- src:内嵌文档的url；
		- witdth:iframe框架区域的宽度；
		- height:iframe框架区域的高度；

		<iframe src="http://www.baidu.com" width="500" height="500"></iframe>
	
##### &lt;abbr&gt;&lt;/abbr&gt; : 指示简称或是缩写，为浏览器和拼写检查、搜索引擎提供有用的信息；

	- 属性：title，当鼠标悬停在缩写文本上时，会显示title所写信息；
	
><body>
        <abbr title="wagnyingzhi">WTZ</abbr>是你的爸爸！
</body>

##### &lt;center&gt;&lt;/center&gt; : 将文本居中显示；

><body>
	<center>我是你爸爸！</center>
<body>
	
##### &lt;strong&gt;&lt;/strong&gt; : 强调部分内容；
	
><body>
	<p>我是你<strong>爸爸！<strong></p>
<body>
	
##### &lt;dl&gt;&lt;/dl&gt; : 定义列表；&lt;dt&gt;&lt;/dt&gt; : 表示定义列表项目标题、&lt;dd&gt;&lt;/dd&gt表示定义列表项目描述；
	
><body>
        <dl>
            <dt>溏（tang）</dt>
            <dd>意为大便稀稠，呈泥浆状。</dd>
            <dt>嫑（biao）</dt>
            <dd>意为不要</dd>
        </dl>
</body>





