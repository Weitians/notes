#### CSS3 模块：
	• 选择器
	• 框模型
	• 背景和边框
	• 文本效果
	• 2D/3D 转换
	• 动画
	• 多列布局
	• 用户界面
	
#### CSS3 边框：
	• border-radius: 1-4 length|% / 1-4 length|%； 斜杠前代表水平半径，斜杠后代表垂直半径。
		- border-radius:10px；创建四个角相等的圆角；
		- border-radius:10px 15px; 对角设置，①左上角，右下角，②右上角，左下角。
		- border-radius:10px 15px 5px; ①左上角，②右上角，左下角，③右下角。
		- border-radius:10px 15px 10px 5px; 顺时针分别设置四个角，①左上角，②右上角，③右下角，④左下角。
			Ø 例子： border-radius: 2em 1em 4em / 0.5em 3em；







	
	• box-shadow :  h-shadow v-shadow blur spread color inset;
		- h-shadow : 水平阴影的位置。允许负值;
		- v-shadow : 垂直阴影的位置。允许负值;
		- blur : 模糊距离;
		- spread : 阴影的尺寸;
		- color : 阴影的颜色;
		- inset : 将外部阴影 (outset) 改为内部阴影;
			Ø  例子：box-shadow: 10px 10px 10px 1px #888888;
			






			
	• border-image ：是一个简写属性，用于设置以下属性：
		- border-image-source ：用在边框的图片的路径。	
		- border-image-slice ：图片剪裁位置；	
		- border-image-width：图片边框的宽度。	
		- border-image-outset ：边框图像区域超出边框的量。	
		- border-image-repeat ：图像边框是否应平铺(repeat)、铺满(round)或拉伸(stretch-默认值)。
			Ø  例子： border-image: url(../images/cat-72-72-190415.ico) 14 initial initial stretch;

#### CSS3 背景：
	• background-size: length|percentage|cover|contain ；规定背景图片的尺寸。
		- length ：设置背景图像的高度和宽度，第一个值设置宽度，第二个值设置高度。
		- percentage：以父元素的百分比来设置背景图像的宽度和高度，第一个值设置宽度，第二个值设置高度。
		- cover ：把背景图像扩展至足够大，以使背景图像完全覆盖背景区域，某些部分也许无法显示在背景定位区域中。
		- contain：把图像图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域
		
	• background-origin: padding-box|border-box|content-box ；规定背景图片的定位区域。注释：如果背景图像的 background-attachment 属性为 "fixed"，则该属性没有效果。
		- padding-box	：背景图像相对于内边距框来定位。
		- border-box：背景图像相对于边框盒来定位。
		- content-box：背景图像相对于内容框来定位。


	• background-clip: border-box|padding-box|content-box ；规定背景的绘制区域。
		- border-box：背景被裁剪到边框盒。
		- padding-box：背景被裁剪到内边距框。
		- content-box：背景被裁剪到内容框。
		
#### CSS3 文本效果：
	• text-shadow :  h-shadow v-shadow blur color ；可向文本应用阴影，能够规定水平阴影、垂直阴影、模糊距离，以及阴影的颜色：
		- h-shadow：水平阴影的位置，允许负值。
		- v-shadow：垂直阴影的位置，允许负值。
		- blur：模糊的距离。
		- color：阴影的颜色。
			Ø 例子：text-shadow: 2px 2px 1px red;
		
		
		
		
		
		
		
	• word-wrap: normal | break-word ；属性允许长单词或 URL 地址换行到下一行。
		- normal：只在允许的断字点换行（浏览器保持默认处理）。
		- break-word：在长单词或 URL 地址内部进行换行。
			Ø 例子：word-wrap: break-word;

#### CSS3 字体：
	• @font-face ：首先定义字体的名称（比如 myFirstFont），然后指向该字体文件。
		- font-family：引用字体的名称。
			Ø 例子：<style> 
					@font-face
						{
					font-family: myFirstFont;
					src: url('Sansation_Light.ttf') format("ttf"),
					     url('Sansation_Light.eot') format("eot"); /* IE9+ */
						}
					div{
						font-family:myFirstFont;
						}
				</style>
				
#### CSS3 2D 转换：
	• transform：使元素改变形状、尺寸和位置的一种效果。
		- translate()；移动方法，根据给定的 left（x 坐标） 和 top（y 坐标） 位置参数，元素从其当前位置移动。
			Ø 例子：<style>
			        div {
			            transform: translate(50px, 100px);
			- //值 translate(50px,100px) 把元素从左侧移动 50 像素，从顶端移动 100 像素。
			            -ms-transform: translate(50px, 100px);
			            /* IE 9 */
			            -moz-transform: translate(50px, 100px);
			            /* Firefox */
			            -webkit-transform: translate(50px, 100px);
			            /* Safari and Chrome */
			            -o-transform: translate(50px, 100px);
			            /* Opera */
			        }
			</style>
			
		- rotate()；旋转方法，顺时针旋转给定的角度。允许负值，元素将逆时针旋转。
			Ø 例子：<style>
			        div {
			            transform: rotate(30deg);
			//值 rotate(30deg) 把元素顺时针旋转 30 度。
			            -ms-transform: rotate(30deg);
			            /* IE 9 */
			            -moz-transform: rotate(30deg);
			            /* Firefox */
			            -webkit-transform: rotate(30deg);
			            /* Safari and Chrome */
			            -o-transform: rotate(30deg);
			            /* Opera */
			        }
			    </style>
			
		- scale()；缩放方法，根据给定的宽度（X 轴）和高度（Y 轴）参数，元素的尺寸会增加或减少。
			Ø 例子：<style>
			        div {
			            margin: 100px;
			            transform: scale(2, 4);
			//值 scale(2,4) 把宽度转换为原始尺寸的 2 倍，把高度转换为原始高度的 4 倍。
			            -ms-transform: scale(2, 4);
			            /* IE 9 */
			            -moz-transform: scale(2, 4);
			            /* Firefox */
			            -webkit-transform: scale(2, 4);
			            /* Safari and Chrome */
			            -o-transform: scale(2, 4);
			            /* Opera */
			        }
			    </style>
			
		- skew()；倾斜方法，根据给定的水平线（X 轴）和垂直线（Y 轴）参数，元素翻转给定的角度。
			Ø  例子：<style>
			        div {
			            transform: skew(30deg, 20deg);
			//值 skew(30deg,20deg) 围绕 X 轴把元素翻转 30 度，围绕 Y 轴翻转 20 度。
			            -ms-transform: skew(30deg, 20deg);
			            /* IE 9 */
			            -moz-transform: skew(30deg, 20deg);
			            /* Firefox */
			            -webkit-transform: skew(30deg, 20deg);
			            /* Safari and Chrome */
			            -o-transform: skew(30deg, 20deg);
			            /* Opera */
			        }
			    </style>
			
		- matrix()；[#矩阵详解#] (https://www.zhangxinxu.com/wordpress/2012/06/css3-transform-matrix-%E7%9F%A9%E9%98%B5/) 把所有 2D 转换方法组合在一起，包含数学函数，允许您：倾斜、缩放、旋转、移动元素。
	 
	
	
	
	
	
	
	• transform-origin: x-axis y-axis z-axis ；改变被转换元素的位置，该属性必须与 transform 属性一同使用。



#### CSS3 3D 转换：# 2d3d转换详细参数 #
	• transform：使元素改变形状、尺寸和位置的一种效果。
		- rotateX(deg)；元素围绕其 X 轴以给定的度数进行旋转。
			Ø 例子：div
				{
					transform: rotateX(120deg);
					-webkit-transform: rotateX(120deg);	/* Safari 和 Chrome */
					-moz-transform: rotateX(120deg);	/* Firefox */
				}
			
		- rotateX(deg)；元素围绕其 Y 轴以给定的度数进行旋转。
			Ø 例子：div
				{
					transform: rotateY(130deg);
					-webkit-transform: rotateY(130deg);	/* Safari 和 Chrome */
					-moz-transform: rotateY(130deg);	/* Firefox */
				}
				
		- rotateZ(deg)；元素围绕其 Y 轴以给定的度数进行旋转。
			Ø 例子：div
				{
					transform: rotateZ(130deg);
					-webkit-transform: rotateZ(130deg);	/* Safari 和 Chrome */
					-moz-transform: rotateZ(130deg);	/* Firefox */
				}
		- rotate3d(x,y,z,deg)；元素围绕其 Y 轴以给定的度数进行旋转。
			Ø 例子：div
				{
					transform: rotate3d(10,10,10,130deg);
					-webkit-transform: rotateZ(130deg);	/* Safari 和 Chrome */
					-moz-transform: rotateZ(130deg);	/* Firefox */
				}
		
#### CSS3 过渡：
	• transition: property duration timing-function delay ；从一种样式逐渐改变为另一种的效果，要实现这一点，必须规定：1. 规定您希望把效果添加到哪个 CSS 属性上。2. 规定效果的时长。
	
		- transition-property: none|all|property ；规定设置过渡效果的 CSS 属性的名称。
			Ø none：没有属性会获得过渡效果。
			Ø all：所有属性都将获得过渡效果。
			Ø property：定义应用过渡效果的 CSS 属性名称列表，列表以逗号分隔。
			
		- transition-duration: time ；规定完成过渡效果需要多少秒或毫秒。
			Ø time：规定完成过渡效果需要花费的时间（以秒或毫秒计），默认值是 0，意味着不会有效果。
			
		- transition-timing-function: linear|ease|ease-in|ease-out|ease-in-out|cubic-
		bezier(n,n,n,n); 规定速度效果的速度曲线。 
			Ø linear：规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。
			Ø ease：规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。
			Ø ease-in：规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
			Ø ease-out：规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
			Ø ease-in-out：规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
			Ø cubic-bezier(n,n,n,n)：在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。
			
		- transition-delay: time；定义过渡效果何时开始。
			Ø time	规定在过渡效果开始之前需要等待的时间，以秒或毫秒计。
			Ø 例子：<style>
				        div {
				            width: 100px;
				            height: 100px;
				            margin: 200px;
				            background: blue;
				            -moz-transition: width 2s, height 2s, -moz-transform 2s;
				            /* Firefox 4 */
				            -webkit-transition: width 2s, height 2s, -webkit-transform 2s;
				            /* Safari and Chrome */
				            -o-transition: width 2s, height 2s -o-transform 2s;
				            /* Opera */
				        }
				
				        div:hover {
				            width: 300px;
				            height: 300px;
				            transform:rotateY(120deg);
				        }
				    </style>
	
#### CSS3 动画：
	• @keyframes ，用于创建动画。在@keyframes 创建动画时，需把它捆绑到某个选择器，否则不会产生动画效果。通过规定至少以下两项 CSS3 动画属性，即可将动画绑定到选择器：1.规定动画的名称，2.规定动画的时长。
	
		- animation:  name duration timing-function delay iteration-count direction；
			Ø animation-name：规定需要绑定到选择器的 keyframes 名称。
			Ø animation-duration：规定完成动画所花费的时间，以秒或毫秒计。
			Ø animation-timing-function：规定动画的速度曲线。
			Ø animation-delay：规定在动画开始之前的延迟。
			Ø animation-iteration-count：规定动画应该播放的次数。
				▪ n：定义动画播放次数的数值。
				▪ infinite：规定动画应该无限次播放。
			Ø animation-direction：规定是否应该轮流反向播放动画。
				▪ normal：默认值。动画应该正常播放。
				▪ alternate：动画应该轮流反向播放。
				例子：div{
						animation-name: myfirst;
						animation-duration: 5s;
						animation-timing-function: linear;
						animation-delay: 2s;
						animation-iteration-count: infinite;
						animation-direction: alternate;
						animation-play-state: running;
						}
				
			Ø 简写：animation: myfirst（name) 5s (duration) linear (timing-function) 2s (delay) infinite (iteration-count) alternate (direction) ;
				例子：div{
						animation: myfirst 5s linear 1s infinite alternate;
						}
			
#### CSS3 多列：
	• column-count：规定元素应该被分隔的列数；
				例子：div{
						-moz-column-count:3; 	/* Firefox */
						-webkit-column-count:3; /* Safari 和 Chrome */
						column-count:3;
						}
					
	• column-gap：规定列之间的间隔；
				例子：div{
						-moz-column-gap:40px;		/* Firefox */
						-webkit-column-gap:40px;	/* Safari 和 Chrome */
						column-gap:40px;
						}
						
	• column-rule: column-rule-width column-rule-style column-rule-color ；设置列之间的宽度、样式和颜色规则。
		- column-rule-width：设置列之间的宽度规则。
			Ø thin：定义纤细规则。
			Ø medium：定义中等规则。
			Ø thick：定义宽厚规则。
			Ø length：规定规则的宽度。
		- column-rule-style：设置列之间的样式规则。
			Ø none：定义没有规则。
			Ø hidden：定义隐藏规则。
			Ø dotted	：定义点状规则。
			Ø dashed：定义虚线规则。
			Ø solid：定义实线规则。	
			Ø double：定义双线规则。
			Ø groove：定义 3D grooved 规则。该效果取决于宽度和颜色值。
			Ø ridge：定义 3D ridged 规则。该效果取决于宽度和颜色值。
			Ø inset：定义 3D inset 规则。该效果取决于宽度和颜色值。
			Ø outset：定义 3D outset 规则。该效果取决于宽度和颜色值。
		- column-rule-color：设置列之间的颜色规则。
				▪  例子：<style>
				        div {
				            padding: 10px;
				            column-count: 4;
				            column-gap: 20px;
				            column-rule: thin inset #111;
				        }
				    </style>
				
	• column-span: 1|all；规定元素应横跨多少列。
		- 1：元素应横跨一列。	
		- all：元素应横跨所有列。
	
#### CSS3 用户界面：

	• resize: none|both|horizontal|vertical ；规定是否可由用户调整元素尺寸。
		- none：用户无法调整元素的尺寸。
		- both：用户可调整元素的高度和宽度。
		- horizontal：用户可调整元素的宽度。
		- vertical：用户可调整元素的高度。
		
	• box-sizing: content-box|border-box|inherit；允许您以特定的方式定义匹配某个区域的特定元素。
		- content-box：指定盒子模型为W3C盒子模型，计算width和height时，不包括padding和border。
		- 





















		- border-box：指定盒子模型为IE盒子模型，计算width和height时，包含padding和border。
		- 




















	• outline-offset: length|inherit ；对轮廓进行偏移，并在边框边缘进行绘制。
		- length：轮廓与边框边缘的距离。
		- inherit：规定应从父元素继承 outline-offset 属性的值。
		
			 例子：<style>
			        div {
			            margin: 20px;
			            width: 150px;
			            padding: 10px;
			            height: 70px;
			            border: 2px solid black;  
			            outline: 1px solid red;
			            outline-offset: 15px;
			        }
			    </style>
		
	
		
