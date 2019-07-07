### 新特性:
	• 用于绘画的 canvas（画布） 元素;
	• 用于媒介回放的 video 和 audio 元素;
	• 对本地离线存储的更好的支持;
	• 新的特殊内容元素，比如 article（文章）、footer、header、nav、section;
	• 新的表单控件，比如 calendar（日历，日程表）、date、time、email、url、search;

##### &lt;video&gt;&lt;/video&gt;
	• 当前，video 元素支持三种视频格式：
		- Ogg = 带有 Theora 视频编码和 Vorbis 音频编码的 Ogg 文件；
		- MPEG4 = 带有 H.264 视频编码和 AAC 音频编码的 MPEG 4 文件；
		- WebM = 带有 VP8 视频编码和 Vorbis 音频编码的 WebM 文件；
	• controls：属性供添加播放、暂停和音量控件；
	• source：元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式；
	• autoplay：自动播放；
	• height：设置视频播放器的高度；
	• width：设置视频播放器的宽度；
	• loop：循环播放；
	• preload：预加载，并预备播放；
		    <video width="500px" height="500px" controls="controls">
		        <source src="../videos/movie.ogg" type="video/ogg">
		        <source src="../videos/movie.mp4" type="video/mp4">
		        您的浏览器不支持该视频标签。
		    </video>
		
##### &lt;audio&gt;&lt;/audio&gt;
	• 当前，audio 元素支持三种音频格式;
		- Gog Orbis 
		- MP3
		- Wav
	• Autoplay：自动播放；
	• controls：向用户显示控件；
	• loop：循环播放；
	• preload：预加载，并预备播放；
		    <audio controls="controls">
		        <source src="../videos/song.ogg" type="audio/ogg">
		        <source src="../videos/song.mp3" type="audio/mp3">
		        您的浏览器不支持该音频标签。
		    </audio>
		
##### drag and drop：[#拖动事件#](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API#Drag_Events) 即抓取对象以后拖到另一个位置，在 HTML5 中任何元素都能够拖放。
	• 具体包括:
		①开始拖拽：dragstart事件;
		②拖拽进入：dragenter事件;
		③拖拽离开：dragleave事件;
		④拖拽经过：dragover事件;
		⑤拖拽释放：drop事件;
		⑥拖拽结束：dragend事件。

	• draggable属性：设置元素是否可拖动；
		- true
		- flase
		- auto
	• ondragstart：当被拖动元素正在被拖放时运行脚本;
	• dataTransfer 对象：
		- 标准属性
			Ø DataTransfer.dropEffect ：获取当前所选拖放操作的类型，或将拖拽操作设置为新类型。值必须为none，copy，link或move中的一个。
			Ø DataTransfer.effectAllowed ：提供可能的所有类型的操作。必须是none，copy，copyLink，copyMove，link，linkMove，move，all或uninitialized中的一个。
			Ø DataTransfer.files ：拖拽的本地文件列表。如果拖动操作不涉及拖动文件，则此属性为空列表。
			Ø DataTransfer.items （只读）：提供DataTransferItemList对象，该对象是所有拖动数据的列表。
			Ø DataTransfer.types （只读）：在dragstart事件中设置数据格式，返回的是一个字符串数组。
			
		- 标准方法
			Ø DataTransfer.clearData([format]) ：删除与给定类型关联的数据。format参数是可选的。如果类型为空或未指定，则删除所有关联的数据。如果指定类型的数据不存在，或者数据传输不包含任何数据，则此方法无效。
			Ø DataTransfer.getData(format) ：返回给定类型的数据，如果该类型的数据不存在或数据传输不包含数据，则返回空字符串。
			Ø DataTransfer.setData(format, data) ：设置给定类型的数据。如果该类型的数据不存在，则在末尾添加，以使列表中的最后一项成为新格式类型。如果该类型的数据已存在，则在相同位置把现有数据替换掉。
			Ø DataTransfer.setDragImage(img, xOffset, yOffset) ：设置用于拖动的自定义图像。
		
	• preventDefault() 方法：取消事件的默认动作
		- 为了让拖动操作携带数据，应该为被拖动元素的ondragstart事件指定监听器，在该监听器中让拖动操作可以携带数据。
		
		- document对象默认阻止拖动事件，所以被拖动元素到“目的地”时不被接受。为了让document可以接受“放”，应该为document的ondragover事件指定监听器，在监听器中取消document对拖动事件默认行为。
	
	• getElementById() 方法：可返回对拥有指定 ID 的第一个对象的引用。
	• appendChild() 方法向节点添加最后一个子节点，也可用于从一个元素向另一个元素中移动元素。
	
		><head>
		    <style type="text/css">
		        #div1 {
		            width: 300px;
		            height: 200px;
		            padding: 10px;
		            border: 1px solid #aaaaaa;
		        }
		    </style>
		
		    <script type="text/javascript">
		        function allowDrop(ev) {
		            ev.preventDefault();
		        }
		        function drag(ev) {
		            ev.dataTransfer.setData("Text", ev.target.id);
		        }
		        function drop(ev) {
		            ev.preventDefault();
		            var data = ev.dataTransfer.getData("Text");
		            ev.target.appendChild(document.getElementById(data));
		        }
		    </script>
		</head>
		
		<body>
		    <p>请把 W3School 的图片拖放到矩形中：</p>
		    <div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
		    <br />
		    <img id="drag1" src="../images/upicon-72-72-190408.png" draggable="true" ondragstart="drag(event)" />
		</body>

##### &lt;canvas&gt;&lt;/canvas&gt;
		• Canvas 画布是一个矩形区域，您可以控制其每一像素，元素本身是没有绘图能力的，所有的绘制工作必须在 JavaScript 内部完成；
		
		• Canvas 实例1：使用指定的颜色来绘制渐变背景：
		
			<canvas id="sb" width="200" height="100"></canvas>
		
		Ø 纯色效果：
		    <script type="text/javascript">
		        var can = document.getElementById("sb");
		        var con = can.getContext("2d");
		       //在画布canvas上创建2d绘图环境并赋值给con
		        con.fillStyle = "#111";
			//定义填充样式
		        con.fillRect(0, 0, 100, 50);
			//定义填充区域
		    </script>
		
		Ø 渐变效果：
		    <script type="text/javascript">
		        var c = document.getElementById("sb");
		        //获取画布id并赋值给c
		        var ctx = c.getContext("2d");
		        //在画布canvas上创建2d绘图环境并赋值给ctx
		        var my_gradient = ctx.createLinearGradient(0, 0, 0, 170);
		        //在绘图区域创建线性梯度渐变图并赋值给my_gradient
		        my_gradient.addColorStop(0, "black");
		        my_gradient.addColorStop(1, "red");
		        //规定 gradient 对象中的颜色和位置
		        ctx.fillStyle = my_gradient;
		        //设置或返回用于填充绘画的颜色、渐变或模式
		        ctx.fillRect(20, 20, 150, 100);
		        //定义绘制区域形状、位置和尺寸：(x,y,width,height）
		    </script>
		
		- getElementById(ID) 方法：返回带有指定 ID 的元素；
		- getContext(contextID) 方法：返回一个用于在画布上绘图的环境；
			Ø 参数 contextID 指定了您想要在画布上绘制的类型。当前唯一的合法值是 "2d"，它指定了二维绘图，并且导致这个方法返回一个环境对象，该对象导出一个二维绘图 API。
		- context.fillStyle=color\gradient\pattern;属性：设置或返回用于填充绘画的颜色、渐变或模式；
			Ø color：指示绘图填充色的 CSS 颜色值。默认值是 #000000；
				context.fillStyle="#FF0000";
			Ø gradient：用于填充绘图的渐变对象（线性或放射性）；
				context.createLinearGradient(0,0,0,170);
				my_gradient.addColorStop(0,"black");
				my_gradient.addColorStop(1,"white");
					§ addColorStop() 方法规定 gradient 对象中的颜色和位置。gradient.addColorStop(stop,color);
			Ø pattern：用于填充绘图的 pattern 对象；
		- context.createLinearGradient(x0,y0,x1,y1)方法：创建线性的渐变对象；
			x0 	渐变开始点的 x 坐标
			y0 	渐变开始点的 y 坐标
			x1 	渐变结束点的 x 坐标
			y1 	渐变结束点的 y 坐标
		
		- context.fillRect(x,y,width,height);
	
	• Canvas 实例2：通过指定从何处开始，在何处结束，来绘制一条线：
	
		><canvas id="sb" width="200px" height="200px" style="border: 1px solid #111">
			        您的浏览器不支持canvas标签。
		</canvas>
		
		    ><script type="text/javascript">
		        var can = document.getElementById("sb");
		        var con = can.getContext("2d");
		        con.moveTo(0, 0);
		// context.moveTo(x,y) ：方法可以将子路径的起点位置移动到指定位置；
		        con.lineTo(50, 50);
		        con.lineTo(100, 50);
		//context.lineTo(x,y)：添加一个新点，然后创建从该点到画布中最后指定点的线条；
		        con.stroke();
		//stroke() 方法：会实际地绘制出通过 moveTo() 和 lineTo() 方法定义的路径。默认颜色是黑色。
		    </script>
		
	• Canvas 实例3：通过规定尺寸、颜色和位置，来绘制一个圆：
	
		- <canvas id="sb" width="200px" height="200px" style="border: 1px solid #111">
			        您的浏览器不支持canvas标签。
		</canvas>
		
		    <script type="text/javascript">
		        var can = document.getElementById("sb");
		        var con = can.getContext("2d");
		        con.beginPath();
		//beginPath() 方法开始一条路径，或重置当前的路径
		        con.arc(100, 100, 100, 0 * Math.PI, Math.PI * 2);
		//arc() 方法创建弧/曲线（用于创建圆或部分圆），如需通过 arc() 来创建圆，请把起始角设置为 0，结束角设置为 2*Math.PI。
		        con.closePath();
		//closePath() 方法创建从当前点到开始点的路径。
		        con.stroke();
		//stroke() 方法会实际地绘制出路径，
		    </script>
		
		context.arc(x,y,r,sAngle,eAngle,counterclockwise);
			x 	圆的中心的 x 坐标。
			y 	圆的中心的 y 坐标。
			r 	圆的半径。
			sAngle 	起始角，以弧度计。（弧的圆形的三点钟位置是 0 度）。
			eAngle 	结束角，以弧度计。
			counterclockwise 	可选。规定应该逆时针还是顺时针绘图。False = 顺时针，true = 逆时针。
			
	• Canvas 实例4：把一幅图像放置到画布上：

		    <canvas id="sb" width="200px" height="200px" style="border: 1px solid #111">
		        您的浏览器不支持canvas元素。
		    </canvas>
		
		- context.drawImage（）方法：在画布上绘制图像、画布或视频，也能够绘制图像的某些部分，以及/或者增加或减少图像的尺寸。
		
			Ø context.drawImage(img, x,y) ：把一幅图像放置到画布上：
				ü img 	规定要使用的图像、画布或视频。
				ü x 	在画布上放置图像的 x 坐标位置。
				ü y 	在画布上放置图像的 y 坐标位置。
		
				<script type="text/javascript">
				    var can = document.getElementById("sb");
				    var con = can.getContext("2d");
				    var img = new Image();
				    img.src = "../images/icon-256-256-190405.png";
				    con.drawImage(img, 0, 0);
				</script>
				
			Ø context.drawImage(img,x,y,width,height) ：在画布上对图像进行定位，然后规定图像的宽度和高度：
				ü img 	规定要使用的图像、画布或视频。
				ü x 	在画布上放置图像的 x 坐标位置。
				ü y 	在画布上放置图像的 y 坐标位置。
				ü width 	要使用的图像的宽度。（伸展或缩小图像）
				ü height 要使用的图像的高度。（伸展或缩小图像）
				
				    <script type="text/javascript">
				        var can = document.getElementById("sb");
				        var con = can.getContext("2d");
				        var img = new Image();
				        img.src = "../images/icon-256-256-190405.png";
				        con.drawImage(img, 0, 0,200,200);
				    </script>
				
			Ø context.drawImage(img,sx,sy,swidth,sheight,x,y,width,height) ：先剪切图片，并在画布上对已剪切的土拍你进行定位：
				ü img 	规定要使用的图像、画布或视频。
				ü sx 	开始剪切的 x 坐标位置。
				ü sy 	开始剪切的 y 坐标位置。
				ü swidth 	被剪切图像的宽度。
				ü sheight 	被剪切图像的高度。
				ü x 	在画布上放置图像的 x 坐标位置。
				ü y 	在画布上放置图像的 y 坐标位置。
				ü width 	要使用的图像的宽度。（伸展或缩小图像）
				ü height 要使用的图像的高度。（伸展或缩小图像）
				
				 <script type="text/javascript">
				        var can = document.getElementById("sb");
				        var con = can.getContext("2d");
				        var img = new Image();
				        img.src = "../images/icon-256-256-190405.png";
				        con.drawImage(img, 10,10,150,150,0,0,100,100);
				    </script>
				
				
##### &lt;svg&gt;&lt;/svg&gt; [#SVG入门教程#](http://www.ruanyifeng.com/blog/2018/08/svg.html) [#SVG基础教程#](https://segmentfault.com/a/1190000012071386)

	• SVG 指可伸缩矢量图形 (Scalable Vector Graphics)；属于对图像的形状描述，本质上是文本文件，体积较小，且不管放大多少倍都不会失真。
	• SVG 用于定义用于网络的基于矢量的图形；
	• SVG 使用 XML 格式定义图形；
	• SVG 图像在放大或改变尺寸的情况下其图形质量不会有损失；
	• SVG 是万维网联盟的标准；

	• SVG 图像可通过文本编辑器来创建和修改;
	• SVG 图像可被搜索、索引、脚本化或压缩;
	• SVG 是可伸缩的;
	• SVG 图像可在任何的分辨率下被高质量地打印；
	• SVG 可在图像质量不下降的情况下被放大；
	
##### SVG形状：
	• 矩形 <rect>:
		<svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">
		    <rect  x="20" y="20" rx="20" ry="20" width="400" height="200" style="fill:red; stroke-width:5; stroke:black;fill-opacity:0.5; stroke-opacity:1" />
		</svg>
			Ø rect 元素的 width 和 height 属性可定义矩形的高度和宽度
			Ø x 属性定义矩形的左侧位置（例如，x="0" 定义矩形到浏览器窗口左侧的距离是 0px）
			Ø y 属性定义矩形的顶端位置（例如，y="0" 定义矩形到浏览器窗口顶端的距离是 0px）
			Ø rx 和 ry 属性可使矩形产生圆角。
			Ø style 属性用来定义 CSS 属性
			Ø CSS 的 fill 属性定义矩形的填充颜色（rgb 值、颜色名或者十六进制值）
			Ø CSS 的 stroke-width 属性定义矩形边框的宽度
			Ø CSS 的 stroke 属性定义矩形边框的颜色
			Ø CSS 的 fill-opacity 属性定义填充颜色透明度（合法的范围是：0 - 1）
			Ø CSS 的 stroke-opacity 属性定义笔触颜色的透明度（合法的范围是：0 - 1）
			
	• 圆形 <circle>
		<svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">
		    <circle cx="50" cy="50" r="20" stroke="black" stroke-width="1" fill="red" />
		</svg>
			Ø cx 和 cy 属性定义圆点的 x 和 y 坐标。如果省略 cx 和 cy，圆的中心会被设置为 (0, 0)；
		
	• 椭圆 <ellipse>
		<svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">
		    <ellipse cx="150" cy="50" rx="120" ry="20" stroke="black" stroke-width="1" fill="red" />
		</svg>
			Ø cx 属性定义圆点的 x 坐标
			Ø cy 属性定义圆点的 y 坐标
			Ø rx 属性定义水平半径
			Ø ry 属性定义垂直半径
		
	• 线 <line>
		<svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">
		   <line x1="10" y1="10" x2="100" y2="100" stroke="red" stroke-width="1" />
		</svg>
			Ø x1 属性在 x 轴定义线条的开始
			Ø y1 属性在 y 轴定义线条的开始
			Ø x2 属性在 x 轴定义线条的结束
			Ø y2 属性在 y 轴定义线条的结束
		
	• 折线 <polyline>
		 <svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">
		    <polyline points="10,10 10,30 40,30 40,70 " fill=" white" stroke="black" stroke-width="1" />
		</svg>
			Ø points 属性定义折线的 x 和 y 坐标
			
	• 多边形 <polygon>
		<svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">
		     <polygon points="10,10,200,10,150,150" stroke="black" stroke-width="1" fill="gray" />
		</svg>
			Ø points 属性定义多边形每个角的 x 和 y 坐标
		
	• 路径 <path>
			Ø M = moveto
			Ø L = lineto
			Ø H = horizontal lineto
			Ø V = vertical lineto
			Ø C = curveto
			Ø S = smooth curveto
			Ø Q = quadratic Belzier curve
			Ø T = smooth quadratic Belzier curveto
			Ø A = elliptical Arc
			Ø Z = closepath
			Ø 以上所有命令均允许小写字母。大写表示绝对定位，小写表示相对定位。
		
##### SVG滤镜：[#滤镜详解#](https://blog.csdn.net/e26hcs/article/details/48435777)

	• 简单的 SVG 实例 ：
	
			<? xml version="1.0" standalone="no" ?>
			// XML 声明， standalone 属性规定此 SVG 文件是否是“独立的”，或含有对外部文件的引用。
			<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
			//引用了这个外部的 SVG DTD，该 DTD 位于 W3C，含有所有允许的 SVG 元素。
			<svg width="100%" height="100%" version="1.0" xmlns="http://www.w3.org/2000/svg">
			//width 和 height 属性可设置此 SVG 文档的宽度和高度，version 属性可定义所使用的 SVG 版本，xmlns 属性可定义 SVG 命名空间。
			    <circle cx="100" cy="50" r="40" stroke="black" stroke-width="2" fill="red" />
			//cx 和 cy 属性定义圆中心的 x 和 y 坐标，r 属性定义圆的半径，stroke 和 stroke-width 属性控制如何显示形状的轮廓，fill 属性设置形状内的颜色。
			</svg>
		
	• <embed> 是 HTML 5 中的新标签，定义嵌入的内容，比如插件。
		height：设置嵌入内容的高度。
		src：嵌入内容的 URL。
		type：定义嵌入内容的类型。
		width：设置嵌入内容的宽度。
		
##### 地理位置：getCurrentPosition（）[#详细介绍#](https://www.haorooms.com/post/html5_GPS_getCurrentPosition)

	• getCurrentPosition(successCallback,errorCallback,positionOptions);
	
		- successCallback:表示调用getCurrentPosition函数成功以后的回调函数，该函数带有一个参数，对象字面量格式，表示获取到的用户位置数据。该对象包含两个属性 coords 和 timestamp。其中 coords 属性包含以下7个值：
			Ø Accuracy : 精确度；
			Ø Latitude : 纬度；
			Ø Longtitude : 经度 ；
			Ø Altitude ： 海拔高度精确值 ；
			Ø Altitudeaccuracy : 海拔高度精确值 ； 
			Ø Heading ： 朝向 ；
			Ø Speed ： 速度；
			
		- ErrorCallback : 返回错误代码，包含以下2个属性：
			Ø message：错误信息；
			Ø Code ：错误代码；错误代码包括以下四个值：
				ü UNKNOW_ERROR :表示不包括在其它错误代码中的错误，这里可以在 message 中查找错误信息;
				ü PERMISSION_DENIED：表示用户拒绝浏览器获取位置信息的请求;
				ü  POSITION_UNAVALIABLE：表示网络不可用或者连接不到卫星;
				ü TIMEOUT：表示获取超时。必须在options中指定了timeout值时才有可能发生这种错误;
				
		- positionOptions：数据格式为JSON，有3个可选的属性：
				ü enableHighAcuracy — 布尔值： 表示是否启用高精确度模式，如果启用这种模式，浏览器在获取位置信息时可能需要耗费更多的时间。
				ü timeout — 整数： 表示浏览需要在指定的时间内获取位置信息，否则触发errorCallback。
				ü maximumAge — 整数/常量： 表示浏览器重新获取位置信息的时间间隔。
			
		<head>
		    <script type="text/javascript">
		
		       3 function showLocation(position) {
		            var latitude = position.coords.latitude;
		            var longtitude = position.coords.longitude;
		            alert("Latitude: " + latitude + "Longtitude :" + longtitude);
		        }
		
		       4 function errorHandler(error) {
		            if (error.code == 1) {
		                alert("Error: 挂球");
		            } else if (error.code == 2) {
		                alert("Error: position is unanailable!")
		            }
		        }
		
		       2 function getlocation() {
		            if (navigator.geolocation) {
		                var options = {
		                    timeout: 60000
		                }
		                navigator.geolocation.getCurrentPosition(showLocation, errorHandler, options);
		            } else {
		                alert("sorry,browser does not support geolocation!");
		            }
		        }
		
		    </script>
		</head>
		
		<body> 
		    <form>
		        <input type="button"  1. onclick="getlocation();" value="点击获取位置">
		    </form>
		</body>
		
##### web存储：HTML5 使用 JavaScript 来存储和访问数据。

	• localStorage ：没有时间限制的数据存储；
		 localStorage.setItem('myCat', 'Tom');
		//该语法用于写入 localStorage 项。
		 let cat = localStorage.getItem('myCat');
		 //该语法用于读取 localStorage 项。
		 localStorage.removeItem('myCat');
		 //该语法用于移除 localStorage 项。
		 localStorage.clear();
		 // 移除所有，该语法用于移除所有的 localStorage 项。
	
	•创建和访问 localStorage：
		    <script>
		        if (typeof(Storage) !== "undefined") {
		            // 检查浏览器是否支持；
		            localStorage.setItem("lastname", "Gates");
		            // 写入
		            document.getElementById("result").innerHTML = localStorage.getItem("lastname");
		            //读取
		        } else {
		            document.getElementById("result").innerHTML = "抱歉！您的浏览器不支持 Web Storage ...";
		        }
		    </script>
		
	•对用户访问页面的次数进行计数：
		 if (localStorage.pagecount) {
		     localStorage.pagecount = Number(localStorage.pagecount) + 1;
		    } else {
		      localStorage.pagecount = 1;
		    }
		 document.write("页面刷新" + localStorage.pagecount + "次")
	
	• sessionStorage ： 针对一个 session 的数据存储；
		  <script>
		        function clickCounter() {
		            if (typeof(Storage) !== "undefined") {
		                if (sessionStorage.clickcount) {
		                    sessionStorage.clickcount = Number(sessionStorage.clickcount) + 1;
		                } else {
		                    sessionStorage.clickcount = 1;
		                }
		                document.getElementById("result").innerHTML = "已点击 " + sessionStorage.clickcount + "次。";
		            } else {
		                document.getElementById("result").innerHTML = "滚蛋，你浏览器不行！！";
		            }
		        }
		    </script>
		
##### 应用程序缓存（Application Cache）

	• 每个指定了 manifest 的页面在用户对其访问时都会被缓存。如果未指定 manifest 属性，则页面不会被缓存（除非在 manifest 文件中直接指定了该页面），manifest 文件的建议的文件扩展名是：".appcache"，请注意，manifest 文件需要配置正确的 MIME-type，即 "text/cache-manifest"，必须在 web 服务器上进行配置。

	• 优势：
		- 离线浏览 - 用户可在应用离线时使用它们
		- 速度 - 已缓存资源加载得更快
		- 减少服务器负载 - 浏览器将只从服务器下载更新过或更改过的资源。
		
	• manifest 文件可分为三个部分：
		- CACHE MANIFEST - （显示段）在此标题下列出的文件将在首次下载后进行缓存；
		- NETWORK - （网络段）在此标题下列出的文件需要与服务器的连接，且不会被缓存；
		- FALLBACK - （默认段）在此标题下列出的文件规定当页面无法访问时的回退页面（比如 404 页面）；
		
		
		CACHE MANIFEST
		//第一行，CACHE MANIFEST，是必需的。
		/theme.css
		/logo.gif
		/main.js
		//manifest 文件列出了三个资源：一个 CSS 文件，一个 GIF 图像，以及一个 JavaScript 文件。当 manifest 文件加载后，浏览器会从网站的根目录下载这三个文件，然后，无论用户何时与因特网断开连接，这些资源依然是可用的。
		
		NETWORK:
		login.asp
		 //NETWORK 小节规定文件 "login.asp" 永远不会被缓存，且离线时是不可用的。
		
		NETWORK:
		*
		//可以使用星号来指示所有其他资源/文件都需要因特网连接。
		
		FALLBACK:
		/html5/ /404.html
		// FALLBACK 小节规定如果无法建立因特网连接，则用 "offline.html" 替代 /html5/ 目录中的所有文件，注释：第一个 URI 是资源，第二个是替补。
		
	• 实例 - 完整的 Manifest 文件：
		CACHE MANIFEST
		# 2012-02-21 v1.0.0
		/theme.css
		/logo.gif
		/main.js
		
		NETWORK:
		login.asp
		
		FALLBACK:
		/html5/ /404.html
		//以 "#" 开头的是注释行，但也可满足其他用途。应用的缓存会在其 manifest 文件更改时被更新。如果您编辑了一幅图片，或者修改了一个 JavaScript 函数，这些改变都不会被重新缓存。更新注释行中的日期和版本号是一种使浏览器重新缓存文件的办法。
		
##### HTML5表单<Input>新类型：

	• Email：用于应该包含 e-mail 地址的输入域。
		 <form action="*">
		        E-mail:<input type="email" name="user_email"><br />
		        <input type="submit">
		 </form>
		
	• Url ：用于应该包含 URL 地址的输入域。
		<form action="*">
		        网页输入：<input type="url" name="user_url"><br />
		        <input type="submit">
		</form>
		
	• Number ：用于应该包含数值的输入域。
		- max	number	规定允许的最大值
		- min	number	规定允许的最小值
		- step	number	规定合法的数字间隔（如果 step="3"，则合法的数是 -3,0,3,6 等）
		- value	number	规定默认值
		
		 <form action="*">
		        输入间隔为2的值：<input type="number" name="numberset" step="2" min="1" max="10"><br />
		        <input type="submit">
		</form>
		
	• Range ：用于应该包含一定范围内数字值的输入域，显示为滑动条。
		- max	number	规定允许的最大值
		- min	number	规定允许的最小值
		- step	number	规定合法的数字间隔（如果 step="3"，则合法的数是 -3,0,3,6 等）
		- value	number	规定默认值
		
		    <form action="*">
		        <input type="range" name="user_range" min="1" max="10"><br />
		        <input type="submit">
		    </form>
	
	• Date pickers ：拥有多个可供选取日期和时间的新输入类型。
		- date - 选取日、月、年
		- month - 选取月、年
		- week - 选取周和年
		- time - 选取时间（小时和分钟）
		- datetime - 选取时间、日、月、年（UTC 时间）
		- datetime-local - 选取时间、日、月、年（本地时间）
		
		   <form action="*">
		        <input type="date" name="user_date"><br />
		        <input type="submit">
		    </form>
		
	• Search ：用于搜索域，比如站点搜索，search 域显示为常规的文本域。
		  <form action="*">
		        <input type="search" name="user_serach"><br />
		        <input type="submit">
		    </form>
		
	• Color ：用于搜索选择器。
		    <form action="*">
		        <input type="color" name="user_color"><br />
		        <input type="submit">
		    </form>

##### HTML5表单新元素：
	• Datalist ：规定输入域的选项列表。
			<form action="">
			        <input type="email" list="email_lisk" placeholder="请输入邮箱地址">
			        <datalist id="email_list">
			            <option label="TOP1" value="复仇者联盟4" />
			            <option label="TOP2" value="波西米亚狂想曲" />
			            <option label="TOP3" value="调音师" />
			            <option label="TOP4" value="风中有朵雨做的云" />
			        </datalist>
			        <input type="submit" value="搜索">
			    </form>
			
	• Keygen ：提供一种验证用户的可靠方法。
			    <form action="*" method="get">
			        Username: <input type="text" name="usr_name" />
			        Encryption: <keygen name="security" />
			        <input type="submit" />
			    </form>
			
	• Output ：用于不同类型的输出，比如计算或脚本输出。
		
##### HTML5表单<form>新属性：
	• Autocomplete ：自动完成功能，第二次输入时弹出曾经输入过的选项，适用于 <form> 标签，以及以下类型的 <input> 标签：text, search, url, telephone, email, password, datepickers, range 以及 color。
			  <form action="*" method="get" autocomplete="on">
			        First name:<input type="text" name="fname" /><br />
			        Last name: <input type="text" name="lname" /><br />
			        E-mail: <input type="email" name="email" autocomplete="off" /><br />
			        <input type="submit" />
			</form>
			
	• Novalidate：规定在提交表单时不应该验证 form 或 input 域,，用于 <form> 以及以下类型的 <input> 标签：text, search, url, telephone, email, password, date pickers, range 以及 color.
			    <form action="*" method="get" novalidate="novalidate">
			        E-mail: <input type="email" name="user_email" />
			        <input type="submit" />
			    </form>
		
##### HTML5表单<input>新属性：
	•  Autocomplete ：自动完成功能，第二次输入时弹出曾经输入过的选项，适用于text, search, url, telephone, email, password, datepickers, range 以及 color。
			  <form action="*" method="get" autocomplete="on">
			        First name:<input type="text" name="fname" /><br />
			        Last name: <input type="text" name="lname" /><br />
			        E-mail: <input type="email" name="email" autocomplete="off" /><br />
			        <input type="submit" />
			</form>
			
	• Autofocus ：在页面加载时，域自动地获得焦点，适用于所有 <input> 标签的类型。
			 <form action="*" method="get">
			        <input type="text" placeholder="用户名" autofocus>
			        <input type="submit">
			 </form>
			
	• Form ：规定输入域所属的一个或多个表单，适用于所有 <input> 标签的类型，form 属性必须引用所属表单的 id。
			   <form action="*" method="get" id="user_form">
			        First name:<input type="text" name="fname" />
			        <input type="submit" />
			    </form>
			    <p>下面的输入域在 form 元素之外，但仍然是表单的一部分。</p>
			    Last name: <input type="text" name="lname" form="user_form" />
			
	• form override attributes ：允许您重写 form 元素的某些属性设定，适用于 <input> 标签：submit 和 image。
			Ø formaction - 重写表单的 action 属性
			Ø formenctype - 重写表单的 enctype 属性
			Ø formmethod - 重写表单的 method 属性
			Ø formnovalidate - 重写表单的 novalidate 属性
			Ø formtarget - 重写表单的 target 属性
			><form action="*" method="get">
			        <input type="email" placeholder="邮箱地址" name="user_email"><br />
			        <input type="submit" value="提交"><br/>
			        <input type="submit" formaction="*" value="再次提交"><br />
			        <input type="submit" formnovalidate="true" value="再一次提交">
			</form>
			
	• height 和 width ：规定用于 image 类型的 input 标签的图像高度和宽度，只适用于 image 类型的 <input> 标签。
			    <form action="*" method="get">
			        <input type="image" src="../images/cat-72-72-190415.ico" width="30" height="30">
			    </form>
			
	• List : 规定输入域的 datalist。datalist 是输入域的选项列表,适用于 <input> 标签：text, search, url, telephone, email, date pickers, number, range 以及 color。
			   <form action="*" method="get">
			        <input type="url" list="url_list" name="link" />
			        <datalist id="url_list">
			            <option label="W3School" value="http://www.w3school.com.cn" />
			            <option label="Google" value="http://www.google.com" />
			            <option label="Microsoft" value="http://www.microsoft.com" />
			        </datalist>
			        <input type="submit" />
			    </form>
			
	• min, max 和 step : 用于为包含数字或日期的 input 类型规定限定（约束）,适用于 <input> 标签：date pickers、number 以及 range。
			 <form action="*" method="get">
			        <input type="number" name="points" min="1" max="10" step="2">
			        <input type="submit">
			    </form>
			
	• Multiple : 规定输入域中可选择多个值, 适用于 <input> 标签：email 和 file。
			    <form action="*" method="get">
			        <input type="file" name="my_file" multiple="multiple">
			        <input type="submit">
			    </form>
			
	• pattern (regexp): 用于验证 input 域的模式（pattern），适用于 <input> 标签：text, search, url, telephone, email 以及 password。
			    <form action="*" method="get">
			        Country code: <input type="text" name="country_code" pattern="[A-z]{3}" title="Three letter country code" />
			        <input type="submit" />
			    </form>
			
	• Placeholder ：（占位文本）提供一种提示，描述输入域所期待的值，适用于 <input> 标签：text, search, url, telephone, email，password。
			    <form action="*" method="get">
			        <input type="search" name="user_search" placeholder="Search W3School" />
			        <input type="submit" />
			    </form>
			
	• Required ：规定必须在提交之前填写输入域（不能为空），适用于 <input> 标签：text, search, url, telephone, email, password, date pickers, number, checkbox, radio 以及 file。
			    <form action="*" method="get">
			        Name: <input type="text" name="usr_name" required="required" />
			        <input type="submit" />
			    </form>
