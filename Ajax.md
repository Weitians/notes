#### AJAX（异步 JavaScript 和 XML）：是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术。
	• XMLHttpRequest对象：用于在后台与服务器交换数据，所有现代浏览器均支持该对象（IE5 和 IE6 使用 ActiveXObject）。
	
	• 创建XMLHttpRequest对象：
		- variable=new XMLHttpRequest(); 现代浏览器（IE7+、Firefox、Chrome、Safari 以及 Opera）均内建 XMLHttpRequest 对象。
		- variable=new ActiveXObject("Microsoft.XMLHTTP"); 老版本的 Internet Explorer （IE5 和 IE6）使用 ActiveX 对象。
				Ø 判断浏览器是否支持：
				 var xmlhttp;
				        if (window.XMLHttpRequest) {
				            //  IE7+, Firefox, Chrome, Opera, Safari 浏览器执行代码
				            xmlhttp = new XMLHttpRequest();
				        } else {
				            // IE6, IE5 浏览器执行代码
				            xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
				        }
				
	• 向服务器发送请求：使用 XMLHttpRequest 对象的 open() 和 send() 方法：
		- xmlhttp.open("GET","ajax_info.txt",true)；
			§ open(method,url,async)：规定请求的类型、URL 以及是否异步处理请求。
				Ø method：请求的类型；GET 或 POST；
					ü 与 POST 相比，GET 更简单也更快，并且在大部分情况下都能用。然而，在以下情况中，请使用 POST 请求；
						v 无法使用缓存文件（更新服务器上的文件或数据库）；
						v 向服务器发送大量数据（POST 没有数据量限制）；
						v 发送包含未知字符的用户输入时，POST 比 GET 更稳定也更可靠；
							xmlhttp.open("GET","/try/ajax/demo_get.php",true);
							xmlhttp.send();
							xmlhttp.open("POST","/try/ajax/demo_post.php",true);
							xmlhttp.send();
				Ø url：文件在服务器上的位置；
					ü 该文件可以是任何类型的文件，比如 .txt 和 .xml，或者服务器脚本文件，比如 .asp 和 .php （在传回响应之前，能够在服务器上执行任务）。
							xmlhttp.open("GET","ajax_test.html",true)；
				Ø async：true（异步）或 false（同步）；XMLHttpRequest 对象如果要用于 AJAX 的话，其 open() 方法的 async 参数必须设置为 true：
					ü Async=true；当使用 async=true 时，请规定在响应处于 onreadystatechange 事件中的就绪状态时执行的函数：
						   xmlhttp.onreadystatechange = function() {
						                if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
						                    document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
						                }
						            }
						            xmlhttp.open("GET", "/try/ajax/ajax_info.txt", true);
						            xmlhttp.send();
						        }
					ü Async = false；如需使用 async=false，请将 open() 方法中的第三个参数改为 false，当使用 async=false 时，不要编写 onreadystatechange 函数 - 把代码放到 send() 语句后面即可：
						xmlhttp.open("GET", "/try/ajax/ajax_info.txt", false);
						xmlhttp.send();
						document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
		- xmlhttp.send()；
			§ send(string)：将请求发送到服务器。
				Ø string：仅用于 POST 请求；
				
	• 服务器响应：如需获得来自服务器的响应，请使用 XMLHttpRequest 对象的 responseText 或 responseXML 属性。
		- responseText：获得字符串形式的响应数据；如果来自服务器的响应并非 XML，使用 responseText 属性。
		- responseXML：获得 XML 形式的响应数据；如果来自服务器的响应是 XML，且需要作为 XML 对象解析，使用 responseXML 属性：
			    function loadXMLDoc() {
			            var xmlhttp;
			            var txt, x, i;
			            
			            if (window.XMLHttpRequest) {
			                xmlhttp = new XMLHttpRequest();
			            } else {
			                xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
			            }
			            
			            xmlhttp.onreadystatechange = function() {
			                if (xmlhttp.readyState === 4 && xmlhttp.status === 200) {
			                    xmlDoc = xmlhttp.responseXML;
			                    txt = "";
			                    x = xmlDoc.getElementsByTagName("ARTIST");
			                    for (i = 0; i < x.length; i++) {
			                        txt = txt + x[i].childNodes[0].nodeValue + "<br>";
			                    }
			                    document.getElementById("myDiv").innerHTML = txt;
			                }
			            }
			            xmlhttp.open("GET", "cd_catalog.xml", true);
			            xmlhttp.send();
			        }
			
	• onreadystatechange 事件：onreadystatechange	存储函数（或函数名），每当 readyState 属性改变时，就会调用该函数。
		- readyState：存有 XMLHttpRequest 的状态。从 0 到 4 发生变化。
			0: 请求未初始化
			1: 服务器连接已建立
			2: 请求已接收
			3: 请求处理中
			4: 请求已完成，且响应已就绪
		- status：	
			200: "OK"
			404: 未找到页面
			
				xmlhttp.onreadystatechange = function() {
				                if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
				                    document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
				                }
				            }
				
	• 回调函数实例：
		<head>
		    <script>
		        var xmlhttp;
		        function loadXMLDoc(url, cfunc) {
		            if (window.XMLHttpRequest) {
		                xmlhttp = new XMLHttpRequest();
		            } else {
		                xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
		            }
		            xmlhttp.onreadystatechange = cfunc;
		            xmlhttp.open("GET", url, true);
		            xmlhttp.send();
		        }
		        function myFunction() {
		            loadXMLDoc("/try/ajax/ajax_info.txt", function() {
		                if (xmlhttp.readyState === 4 && xmlhttp.status === 200) {
		                    document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
		                }
		            });
		        }
		    </script>
		</head>
		<body>
		    <div id="myDiv">
		        <h2>使用 AJAX 修改文本内容</h2>
		    </div>
		    <button type="button" onclick="myFunction()">修改内容</button>
		</body>
	• AJAX ASP / PHP实例：
		<head>
		    <meta charset="utf-8">
		    <script>
		        function showHint(str) {
		            var xmlhttp;
		            if (str.length == 0) {
		                document.getElementById("txtHint").innerHTML = "";
		                return;
		            }
		//如果输入框为空 str.length==0，则该函数清空 txtHint 占位符的内容，并退出函数。
		            if (window.XMLHttpRequest) {
		                xmlhttp = new XMLHttpRequest();//在现代浏览器中正常运行
		            } else {
		                xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");//在IE5，IE6中使用
		            }
		//判断XMLHttpRequest对象运行环境
		            xmlhttp.onreadystatechange = function() {
		                if (xmlhttp.readyState === 4 && xmlhttp.status === 200) {
		                    document.getElementById("txtHint").innerHTML = xmlhttp.responseText;
		                }
		            }
		//响应服务器请求
		            xmlhttp.open("GET", "/try/ajax/gethint.php?q=" + str, true);
		            xmlhttp.send();
		        }
		//发送请求文件
		    </script>
		</head>
		<body>
		    <h3>在输入框中尝试输入字母 a:</h3>
		    <form action="">
		        输入姓名: <input type="text" id="txt1" onkeyup="showHint(this.value)" />
		//调用showHint()函数
		    </form>
		    <p>提示信息: <span id="txtHint"></span></p>
		</body>
	• AJAX Database（数据库） 实例：
		<head>
		    <meta charset="utf-8">
		    <script>
		        function showCustomer(str) {
		            var xmlhttp;
		            if (str == "") {
		                document.getElementById("txtHint").innerHTML = "";
		                return;
		            }
		//检查是否做出选择
		            if (window.XMLHttpRequest) {
		                // IE7+, Firefox, Chrome, Opera, Safari 浏览器执行代码
		                xmlhttp = new XMLHttpRequest();
		            } else {
		                // IE6, IE5 浏览器执行代码
		                xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
		            }
		//创建XMLHttpRequest对象
		            xmlhttp.onreadystatechange = function() {
		                if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
		                    document.getElementById("txtHint").innerHTML = xmlhttp.responseText;
		                }
		            }
		//响应服务器请求
		            xmlhttp.open("GET", "/try/ajax/getcustomer.php?q=" + str, true);
		            xmlhttp.send();
		        }
		//发送请求文件
		    </script>
		</head>
		<body>
		    <form action="">
		        <select name="customers" onchange="showCustomer(this.value)" style="font-family:Verdana, Arial, Helvetica, sans-serif;">
		            <option value="APPLE">Apple Computer, Inc.</option>
		            <option value="BAIDU ">BAIDU, Inc</option>
		            <option value="Canon">Canon USA, Inc.</option>
		            <option value="Google">Google, Inc.</option>
		            <option value="Nokia">Nokia Corporation</option>
		            <option value="SONY">Sony Corporation of America</option>
		        </select>
		    </form>
		    <br>
		//调用showCustomer()函数
		    <div id="txtHint">客户信息将显示在这...</div>
		</body>
	• AJAX XML 实例：
		function loadXMLDoc() {
		  var xhttp = new XMLHttpRequest();
		  xhttp.onreadystatechange = function() {
		    if (this.readyState == 4 && this.status == 200) {
		    myFunction(this);
		    }
		  };
		  xhttp.open("GET", "cd_catalog.xml", true);
		  xhttp.send();
		}
		function myFunction(xml) {
		  var i;
		  var xmlDoc = xml.responseXML;
		  var table="<tr><th>Artist</th><th>Title</th></tr>";
		  var x = xmlDoc.getElementsByTagName("CD");
		  for (i = 0; i <x.length; i++) { 
		    table += "<tr><td>" +
		    x[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
		    "</td><td>" +
		    x[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
		    "</td></tr>";
		  }
		  document.getElementById("demo").innerHTML = table;
		}
		
