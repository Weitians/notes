#### DOM 节点：
	• 根据 W3C 的 HTML DOM 标准，HTML 文档中的所有内容都是节点：
		- 整个文档是一个文档节点；
		- 每个 HTML 元素是元素节点；
		- HTML 元素内的文本是文本节点；
		- 每个 HTML 属性是属性节点；
		- 注释是注释节点；
		
#### DOM节点树：
	• 在节点树中，顶端节点被称为根（root）；
	• 每个节点都有父节点、除了根（它没有父节点）；
	• 一个节点可拥有任意数量的子；
	• 同胞是拥有相同父节点的节点；
	







#### DOM 编程接口:
	• 可通过 JavaScript （以及其他编程语言）对 HTML DOM 进行访问。
	• 所有 HTML 元素被定义为对象，而"编程接口"则是对象方法和对象属性。
	• 方法：是您能够执行的动作（比如添加或修改元素）。
	• 属性：是您能够获取或设置的值（比如节点的名称或内容）。
	
		- 常用的 HTML DOM 方法：
			§ getElementById()：返回带有指定 ID 的元素；
			§ getElementsByTagName()：返回包含带有指定标签名称的所有元素的节点列表（集合/节点数组）；
			§ getElementsByClassName()：返回包含带有指定类名的所有元素的节点列表；
			§ appendChild()：把新的子节点添加到指定节点；
			§ removeChild()：删除子节点；
			§ replaceChild()：替换子节点；
			§ insertBefore()：在指定的子节点前面插入新的子节点；
			§ createAttribute()：创建属性节点；
			§ createElement()：创建元素节点；
			§ createTextNode()：创建文本节点；
			§ getAttribute()：返回指定的属性值；
			§ setAttribute()：把指定属性设置或修改为指定的值；
			
		- 常用的 HTML DOM 属性：
			§ innerHTML - 节点（元素）的文本值
			§ parentNode - 节点（元素）的父节点
			§ childNodes - 节点（元素）的子节点
			§ attributes - 节点（元素）的属性节点
				
#### HTML DOM 访问：
	• 查找 HTML 元素：
		- 通过 id 找到 HTML 元素：
			§ var x=document.getElementById("intro");
			
		- 通过标签名找到 HTML 元素:
			§ var x=document.getElementById("main");
			var y=x.getElementsByTagName("p");
			
		- 通过类名找到 HTML 元素: ！！！


#### HTML DOM 修改：
	•  改变 HTML：
		- document.getElementById(id).innerHTML=new HTML：改变 HTML 内容。
			<body>
			<p id="demo">hello today</p>
			<script>
			    document.getElementById("demo").innerHTML="hello nimane？";    
			</script>
			</body>
			
		- document.getElementById(id).attribute=new value：改变 HTML 属性。
			<body>
			    <img id="demo" src="../images/cat-72-72-190415.ico" alt="cat">
			    <script>
			        document.getElementById("demo").src = "../images/eg_bulbon.gif";
			    </script>
			</body>
			
	• 改变 CSS：
		- document.getElementById(id).style.property=new style：改变 HTML 样式。
			<body>
			   <p id="demo">hello man</p>
			   <script>
			    document.getElementById("demo").style.textTransform="capitalize";
			    </script>
			</body>
			
#### HTML DOM 元素（节点）：
	• 添加元素：
		- <script>
		        var hgr = document.createElement('p');
		//创建“p" 元素。
		        var node = document.createTextNode("我是你爸爸！");
		//创建文本信息。
		        hgr.appendChild(node);
		//将文本信息写入“p”元素。
		        var ele = document.getElementById("div1");
		//获取包含元素信息。
		        ele.appendChild(hgr);
		//将“p“元素写入包含元素
		    </script>
		
	• 删除元素：DOM 需要清楚您需要删除的元素，以及它的父元素。
		<script>
		        var x = document.getElementById("div1");
		        var v = document.getElementById("p2");
		        x.parentNode.removeChild(x);
		//parentNode:用于找到要删除元素的父元素，
		//removeChild：用于删除元素；
		    </script>
		
	• 替换元素：
		<body>
		    <div id="demo">
		        <p id="p1">niba</p>
		        <p id="p2">nima</p>
		    </div>
		    <script>
		        var a = document.createElement("p");
		        var b = document.createTextNode("nigege");
		        a.appendChild(b);
		        var c = document.getElementById("demo");
		        var d = document.getElementById("p2");
		        c.replaceChild(a, d);
		    </script>
		</body>

 #### HTML DOM 事件：
	• onclick事件：在对象被点击时触发；
		-  <p onclick="this.innerHTML='good'">你好！</p>
		
	• onload 和 onunload 事件：可用于处理 cookie，onload 事件用于检测访问者的浏览器类型和浏览器版本，并基于信息加载网页的正确版本。
		- <body onload="checkCookies()">
		    <script>
		        function checkCookies() {
		            if (navigator.cookieEnabled == true) {
		                alert("已启用cookie")
		            } else {
		                alert("未启用cookie")
		            }
		        }
		    </script>
		</body>
		
	• onchange 事件：常结合对输入字段的验证来使用。
		- <head>
		    <script>
		        function myfunction() {
		            var x = document.getElementById("demo");
		            x.value = x.value.toUpperCase();
		        }
		    </script>
		</head>
		<body>
		    <input type="text" id="demo" onchange="myfunction()">
		</body>
		
	• onmouseover 和 onmouseout 事件：用于在用户的鼠标移至 HTML 元素上方或移出元素时触发函数。
		- <body>
		    <div onmouseover="mOver(this)" onmouseout="mOut(this)">sddd</div>
		    <script>
		        function mOver(obj) {
		            obj.innerHTML = "nima";
		        }
		        function mOut(obj) {
		            obj.innerHTML = "what every"
		        }
		    </script>
		</body>
		
	• onmousedown 和 onmouseup 事件：
		- <body>
		    <div onmousedown="mDown(this)" onmouseup="mUp(this)" >请点击这里</div>
		    <script>
		        function mDown(obj) {
		            obj.style.backgroundColor = "#1ec5e5";
		            obj.innerHTML = "请释放鼠标按钮"
		        }
		        function mUp(obj) {
		            obj.style.backgroundColor = "green";
		            obj.innerHTML = "请按下鼠标按钮"
		        }
		    </script>
		</body>
		
#### HTML DOM 导航：
	• nodeName - 规定节点的名称。
		Ø 元素节点的 nodeName 与标签名相同
		Ø 属性节点的 nodeName 与属性名相同
		Ø 文本节点的 nodeName 始终是 #text
		Ø 文档节点的 nodeName 始终是 #document
		
	• nodeValue - 规定节点的值
		Ø 元素节点的 nodeValue 是 undefined 或 null
		Ø 文本节点的 nodeValue 是文本本身
		Ø 属性节点的 nodeValue 是属性值
			§ <body>
			    <p id="p1">ni</p>
			    <p>hao</p>
			    <p>me</p>
			    <script>
			        x = document.getElementById("p1");
			        document.write(x.firstChild.nodeValue);
			    </script>
			</body>
			
	§ nodeType - 返回节点的类型
		Ø 元素	1
		Ø 属性	2
		Ø 文本	3
		Ø 注释	8
		Ø 文档	9	
