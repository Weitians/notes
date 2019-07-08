#### CSS定义：

	• CSS层叠样式表（cascading style sheets），定义如何显示html元素，实现了内容与表现分离；

#### 实现方式：

	• 浏览器缺省设置；
	• 外部样式表；例：<link type="text/css" rel="stylesheet" href="CSS/index.css">
	• 内部样式表；例：
	<style type="text/css">
	            div{
	                font-size: 40px;
	                background-color: bisque;
	            }
	</style>
	• 内联样式；例：<div style="color: aqua">先天下之忧而忧，后天下之乐而乐。</div>

`优先级：1.内联样式表 2.内部样式表 3.外部样式表 4.缺省设置 `

#### CSS语法：选择器+n条说明（n≥0）；

	•  格式：选择器{声明；声明；声明 ；…..}；例： div{width: 500px;height: 500px;}
	
		- 选择器：告诉浏览器你要改变哪一个dom元素的样式；
		- 声明；告诉浏览器dom元素要改变成什么样式，属性+值；

#### CSS选择器：

	• 元素选择器（标签选择器）；
		- 选择某一种标签，该标签都会更改样式；语法：标签名：{}；
		<style type="text/css">
		            div{
		                font-size: 40px;
		                background-color: bisque;
		            }
		</style>
	• 类选择器；要先在标签中设置属性为： class=" *** ”例：<div class="test1">hahaha</div>;
		- 语法：.类名{}；
		<head>
		        <title>cascadind style sheets</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
		        <style type="text/css">
		            .test1{
		                background-color: red;
		            }
		            .test2{
		                background-color: green;
		            }
		            .test3{
		                background-color: aqua;
		            }
		        </style>
		    </head>
		    <body>
		        <div class="test1">先天下之忧而忧，后天下之乐而乐。</div>
		        <ul>
		            <li>吃饭</li>
		            <li>睡觉</li>
		            <li>打豆豆</li>
		        </ul>
		        <p class="test2">先天下之忧而忧，后天下之乐而乐。</p>
		        <h1 class="test3">先天下之忧而忧，后天下之乐而乐。</h1>
		    </body>
	• id选择器；要现在标签中设置属性为：id=“***”例：<div id="test">hahaha</div>
		- 语法：#id名{};
		 <head>
		        <title>cascadind style sheets</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
		        <style type="text/css">
		            #test{
		                background-color: red;
		            }
		           
		        </style>
		    </head>
		    <body>
		        <div id="test">先天下之忧而忧，后天下之乐而乐。</div>
		</body>
		
	• 属性选择器；选择带有***属性的标签，或者选择***属性是+++的标签，然后设置样式；
		- 语法：[***]{}; 或者[***=+++]{};
		 <head>
		        <title>cascadind style sheets</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
		        <style type="text/css">
		            [type]{ 
		                 background-color: red;
		            }
		            [type=password]{
		                background-color: aqua;
		            }
		        </style>
		    </head>
		    <body>
		        <div id="test">先天下之忧而忧，后天下之乐而乐。</div>
		        <input type="text" value="hahah"/>
		        <input type="password" value="hahaha"/>
		        <input type="submit" value="提交"/>
		 </body>
		
	• 派生选择器（包含选择器）；根据元素在其位置的上下文关系来定义样式；
		- 语法1：选择器 选择器{};  包含关系，只要是包含其中都能生效；
		 <head>
		        <title>cascadind style sheets</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
		        <style type="text/css">
		            h1 span{
		                color: aqua;
		            }
		        </style>
		    </head>
		    <body>
		        <h1>456<span>789</span></h1>
		        <span>456789</span>
		</body>
		
		- 语法2：选择器 > 选择器{}; 子元素关系，必须是前者的子元素才能生效；
		<head>
		        <title>cascadind style sheets</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
		        <style type="text/css">
		            h1 > span{
		                color: aqua;
		            }
		        </style>
		    </head>
		    <body>
		        <h1>456<span>789</span></h1>
		</body>
		
	• 练习：#nav > div .info{} ; 解释：id选择器的子元素是div，然后是类选择器；
		<head>
		        <title>cascadind style sheets</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
		        <style type="text/css">
		            #nav > div .info{
		                color: red;
		            }
		        </style>
		    </head>
		    <body>
		      1 <div id="nav">
		          2 <div>
		             3 <p class="info">hahaha</p>
		            </div>
		        </div>
		</body>
		
`简单选择器的优先级：id选择器 > 类选择器 > 标签选择器 `

`同类型选择器的优先级：<div class="test" "test1"></div>,同类型同级别情况下，写在后面的生效。`

`作用在同一标签的选择器，权重越大越先生效；`

	• id选择器权重为100； 
	• 类选择器与属性选择器权重为10；
	• 标签选择器权重为1；

`!important：样式最高优先级,放在样式的最后一条声明“；”之前时起作用；`

	 <head>
	        <title>cascadind style sheets</title>
	        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
	        <style type="text/css">
	            p{
	                color: red !important;
	            }   
	        </style>
	    </head>
	    <body>
	        <p style="color: aquamarine">惠风和畅</p>
	</body>

#### Background-color：设置背景颜色 ；
	
	• 颜色名称：red、blue、yellow；
	• 十六进制颜色值：#ffffff;
	• rgb颜色值:rgb(255,255,255);
	• Transparent:默认值，透明的；
	• inherit：继承父元素背景；

#### Background-image：设置背景图片 ；

	• Url:图片目录；
	• background-repeat：设置背景图片是否重复 ；
		- repeat:横向纵向都重复；
		- repeat-x:横向重复；
		- repeat-y：纵向重复
		- no-repeat：不重复；
	• background-position：设置背景图片的位置 ；
		- 位置：top、left、right、bottom、center；
		- 百分比：x%，y%；
		- 像素值：xpx，ypx；
		
		<style type="text/css">
		            div{
		                height: 1800px;
		                border: 1px solid red;
		                background-image: url('../images/dome1.jpg');
		                background-repeat:no-repeat;
		                background-position:bottom;
		            }   
		</style>
		
#### 绝对路径时目录选择方法：
	• "./": 表示当前目录
	• "../": 表示父级目录
	• "/" : 表示根目录

#### background：设置背景属性；

	• background：#ffffff；
	• background：url('') 0 0 no-repeat;

#### color：设置字体颜色；

#### Text-indent：设置字体缩进，多行内容时只有首行缩进；

	• xpx：像素；
	• x%：百分百；
	• inherit：继承父元素；

#### Text-align：设置文本对齐方式，基于块级元素；

	• left：左对齐；
	• right；右对齐；
	• center：文本居中；

#### Font-size：设置文本字体大小；

	• xpx:文字大小为px；
	• xem;文字大小为em；
	
	
#### Font-family：设置字体类型；

#### Font-style：设置文本正常或倾斜；

	• normal：文本正常显示；
	• italic：文本倾斜显示；
	• oblique：文本倾斜显示；

#### Font-weight：设置字体加粗；

	• normal：正常大小，默认值；
	• bold：粗字体；
	• bolder：更粗字体；
	• light：更细字体；
	• 100-900：400相当于noemal，700相当于bold；

#### Line-height：设置行高;

	• xpx:行高为px；
	• xem;行高为em

#### Letter-spacing:设置字母间距，作用于字母与字母之间；

#### Word-spacing:设置字间距，作用于单词与单词之间；

`中文设置间隔使用letter-spacing `

#### Text-transform:设置字母大小写；

	• none：不做任何处理；
	• uppercase：全部大写；
	• lowercase：全部小写；
	• capitalize：首字母大写；

#### Text-decoration：文本装饰；
 
	• None:不做任何处理；
	• Underline:下划线；
	• Overline:上划线；
	• Line-through:贯穿线；
	• Blink:文字闪烁；

#### a伪类：用以区分a链接在不同状态下的样式；

	• a：link{}：未访问的链接；
	• a：visited{}：已访问的链接；
	• a：hover{}：鼠标悬停时的样式；
	• a：active{}：点击时的样式；
	<head>
	        <title>background-image</title>
	        <meta http-equiv="content-type" content="text/html" charset="utf-8"> 
	        <style type="text/css">
	            a{
	                font-size: 30px;
	                text-decoration: none;
	             }     
	            a:link{color:blue}
	            a:visited{color: beige}
	            a:hover{color: red}
	            a:active{color:blueviolet}
	        </style>
	    </head>
	    <body>
	        <a href="http://www.autohome.com">汽车之家</a>
	</body>
	
#### list-style-type:列表样式类型；

	• none：无标志；
	• disc：实心圆标志；
	• circle：空心圆标志；
	• square：实心方块标志；
	• decimal：数字标志，从1开始的自然数；
	• lower-roman,upper-roman,lower-alpha,upper-alpha;

#### list-style-position:列表项标志的位置；

	• outside:标志在文本外，默认值；
	• Side:标志在文本内；

#### list-style-image：列表项图片的位置；

	• url（）；图片的相对路径或是绝对路径；例：list-style-image: url('../images/dome2.ico');


#### 盒模型：包括内容、内边距、边框、外边距；

	• width：宽度；
	• height：高度；
	• display：设置元素的盒模型类型；
		- none：不显示，隐藏；
		- inline：变为内联元素；
		- block：变为块级元素； 会占据一整行
		- inline-block：行内块级元素；占据行内的一小块
	• padding：内边距；
		- padding-left：左内边距；
		- padding-right：右内边距；
		- padding-bottom：下内边距；
		- padding-top：上内边距；

	• margin：外边距：
		- margin-left：左外边距；
		- margin-right：右外边距；
		- margin-top：上外边距；
		- margin-bottom：下外边距；

	• border-width：边框宽度；
		- border-left-width：左边框宽度；
		- border-right-width：右边框宽度；
		- border-top-width：上边框宽度；
		- border-bottom-width：下边框宽度；
		
	• border-color：边框颜色；
		- border-left-color：左边框颜色；
		- border-right-color：右边框颜色；
		- border-top-color：上边框颜色；
		- border-bottom-color：下边框颜色；
		
	• border-style：边框样式；
		- none：无样式；
		- dotted: 点状边框；
		- dashed: 虚线边框；
		- solid: 实线边框；
		- double: 双实线边框；
		
	• border-radius：边框圆角；
		- xpx：数值；
	
	• box-shadow：边框阴影；
		- box-shadow：apx bpx cpx #xxx; 例：box-shadow: 3px 3px 5px #111; apx表示水平方向，bpx表示竖直方向，cpx表示阴影的模糊距离。
		- box-shadow: apx bpx cpx rgba(0,0,0,0.1); 例：box-shadow: 5px 5px 5px rgba(0,0,0,1);
		
#### CSS定位机制：普通流、浮动、定位；

	• 定位：position；
		• static：默认，正常显示；
		• relative：相对定位，基于自己定位，不脱离文档流，位置改变时其最初位置依然保留；正值向下，负值向上；
		• absolute：绝对定位，基于其外层属性有定位属性的元素偏移距离，脱离文档流，位置改变时其最初位置不保留；
		• fixed：固定定位；基于浏览器窗口偏移距离，脱离文档流，原有位置不保留；
		
	• 浮动：float；
		- none：不浮动，在文档流内，默认值；
		- left：左浮动，脱离文档流；
		- right：右浮动，脱离文档流；
		
	• 多个元素浮动：浮动元素浮动到外包含层的边缘或者紧挨其他的浮动元素，当外包含层无法包含所有的浮动元素时，后面的浮动元素向下浮动。
	• clear：清除浮动；
		- left：左侧不允许右浮动；
		- right：右侧不允许有浮动；
		- both：两侧都不允许有浮动；
		- none：允许两侧有浮动，默认值；
		 <head>
		        <title>float test</title>
		        <meta http-equiv="content-type" content="text/html" charset="utf-8">
		        <meta http-equiv="X-UA-Compatible" content="IE=Edge,chorme=1">
		        <meta http-equiv="refresh" content="1800">
		        <style type="text/css">
		            .main{
		                width: 800px;
		                text-align: center;
		                margin: 20px auto;
		            }
		            .content1,.content3{
		                height: 150px;
		                background-color:red;
		                margin: 10px 0px;;
		            }
		            .float_left{
		                float: left;
		                width: 395px;
		                height: 100px;
		                background-color:red;
		            }
		            .float_right{
		                float: right;
		                width: 395px;
		                height: 100px;
		                background-color:red;
		            }
		            .clear{
		                clear: both;
		            }
		        </style>
		    </head>
		    <body>
		        <div class="main">
		            <div class="content1">饮用纯净水</div>
		            <div class="content2">
		                <div class="float_left">afdsfa</div>
		                <div class="float_right">adfdafa</div>
		                <div class="clear"></div>
		            </div>
		            <div class="content3">饮用纯净水</div>
		        </div>
		 </body>
		
	
 #### CSS权威指南（复习）:
 ***
#### 字体：
	• font:其中font-size和font-family是必要的；
		<style>
		       p {
		            font-family: sans-serif;
		            /*字体系列*/
		            font-weight: normal;
		            /*字体加粗*/
		            font-size: 20px;
		            /*字体大小*/
		            font-style: italic;
		            /*字体风格*/
		            font-variant: small-caps;
		            /*字体变形*/
		            font-stretch: normal;
		            /*字体拉伸，已废弃*/
		            font-size-adjust: auto;
		            /*字体调整，已废弃*/
		        }
		        p {
		            font:bold italic small-caps 50px/1.2  sans-serif;
		        }
		</style>
		
		
	• @font-face:注意： Internet Explorer 8 以及更早的版本不支持新的 @font-face 规则。
	
		- 在新的 @font-face 规则中，必须首先定义字体的名称（比如 myFirstFont），然后指向该字体文件。
		
		<style>
		    @font-face {
		        font-family: myFirstFont;
		        src: url(sansation_light.woff);
		    }
		    div {
		    font-family: myFirstFont;
		    }
		    </style>
		<body>
		        <div>阿里达摩院</div>
		</body>
		
#### 文本：
	• text-indent：文本缩进；
	• text-align：文本对齐；left、right、center；
	• line-height：行高；normal；
	• vertical-align：垂直对齐；baseline(基线对齐)、sub(下标）、super(上标）；bottom（底部对齐）；top（顶部对齐）、middle（居中对齐）；
	• word-spacing：字间隔；
	• lette-spacing：字母间隔；
	• text-transform：文本转换；uppercase(全部大写),lowercase(全部小写),capitalize(首字母大写);
	• text-decoration：文本装饰；underline（下划线），overline（上划线），line-through（贯穿线）；
	• text-shadow：文本阴影；（CSS2.1已废弃）；
	• white-space：空白符处理啊、；pre-line,normal,nowrap,pre,pre-wrap;
	• direction：文本阅读方向；rlt（r to l 从右向左),(l to r 从左向右）；

		<head>
		    <meta charset="UTF-8">
		    <title>Document</title>
		    <link rel="stylesheet" type="text/css" href="../css/inex.css">
		</head>
		<style>
		    p {
		        text-indent: 5px;
		        /*文本缩进*/
		        text-align: left;
		        /*文本对齐*/
		        vertical-align: baseline;
		        /*垂直对齐*/
		        line-height: inherit;
		        /*行高*/
		        word-spacing: normal;
		        /*字间隔*/
		        letter-spacing: normal;
		        /*字间隔*/
		        text-transform: capitalize;
		        /*文本转换*/
		        text-decoration: line-through;
		        /*文本装饰*/
		        text-shadow:normal;
		        /*文本阴影，已废弃*/
		        white-space: pre-wrap;
		        /*空白符处理*/
		        direction: ltr;
		        /*阅读方向*/
		</style>
		<body>
		    <div>
		        <p>this is a good git</p>
		    </div>
		</body
		
	

