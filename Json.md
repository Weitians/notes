#### JSON是JavaScript Object Notation的缩写，它是一种数据交换格式。
#### JSON 语法规则：
		- 数据在名称/值对中；// "name" : "菜鸟教程"
		- 数据由逗号分隔；
		- 大括号保存对象；
		- 中括号保存数组；
		
#### JSON数据类型：
		- number：和JavaScript的number完全一致；
			§ JSON 数字可以是整型或者浮点型：{ "age":30 }
		- boolean：就是JavaScript的true或false；
		- string：就是JavaScript的string；
		- null：就是JavaScript的null；
		- array：就是JavaScript的Array表示方式——[]；
			§ 在中括号中书写：可以包含多个对象；
		- object：就是JavaScript的{ ... }表示方式。
			§ 在大括号（{}）中书写：对象可以包含多个名称/值对：{ "name":"菜鸟教程" , "url":"www.runoob.com" }
			
#### JSON对象（object）：在大括号({})中书写，可以包含多个 key/value（键/值）对。
		- 访问对象值：
			§ 使用点号（.）来访问对象的值：
				    <script>
				        var myObj, x;
				        myObj = {
				            "name": "runoob",
				            "alexa": 10000,
				            "site": null
				        };
				        x = myObj.alexa;
				        document.getElementById("demo").innerHTML = x;
				    </script>
				
			§ 使用中括号（[]）来访问对象的值：
				    <script>
				        var myObj, x;
				        myObj = myObj = {
				            "name": "runoob",
				            "alexa": 10000,
				            "site": null
				        };
				        x = myObj["name"];
				        document.getElementById("demo").innerHTML = x;
				    </script>
				
		- 循环对象：
			 <script>
			        var myObj = {
			            "name": "noob",
			            "alexa": "1000",
			            "site": null
			        };
			        for (x in myObj) {
			            document.getElementById("demo").innerHTML += x + "<br>";
			        }
			</script>
			
		- 嵌套 JSON 对象：
			 <script>
			        var myObj = {
			            "name": "runoob",
			            "alexa": 10000,
			            "sites": {
			                "site1": "www.runoob.com",
			                "site2": "m.runoob.com",
			                "site3": "c.runoob.com"
			            }
			        }
			        document.getElementById("demo").innerHTML += myObj.sites.site2+"<br>";
			        document.getElementById("demo").innerHTML += myObj.sites["site3"];
			</script>
			
		- 修改值：
			§ 使用点号(.)来修改 JSON 对象的值：
				
				<script>
				        var myObj, i, x = "";
				        myObj = {
				            "name": "runoob",
				            "alexa": 10000,
				            "sites": {
				                "site1": "www.runoob.com",
				                "site2": "m.runoob.com",
				                "site3": "c.runoob.com"
				            }
				        }
				        myObj.sites.site1 = "www.google.com";
				        for (i in myObj.sites) {
				            x += myObj.sites[i] + "<br>";
				        }
				        document.getElementById("demo").innerHTML = x;
				</script>
				
			§ 使用中括号([])来修改 JSON 对象的值：
				<script>
				        var myObj, i, x = "";
				        myObj = {
				            "name": "runoob",
				            "alexa": 10000,
				            "sites": {
				                "site1": "www.runoob.com",
				                "site2": "m.runoob.com",
				                "site3": "c.runoob.com"
				            }
				        }
				        myObj.sites["site3"] = "www.google.com"
				        for (i in myObj.sites) {
				            x += myObj.sites[i] + "<br>";
				        }
				        document.getElementById("demo").innerHTML = x;
				</script>
				
		- 删除对象属性：
			§ 使用 delete 关键字来删除 JSON 对象的属性：
				<script>
				        var myObj, i, x = "";
				        myObj = {
				            "name": "runoob",
				            "alexa": 10000,
				            "sites": {
				                "site1": "www.runoob.com",
				                "site2": "m.runoob.com",
				                "site3": "c.runoob.com"
				            }
				        }
				        delete myObj.sites.site1;
				        for (i in myObj.sites) {
				            x += myObj.sites[i] + "<br>";
				        }
				        document.getElementById("demo").innerHTML = x;
				</script>
				
			§ 使用中括号([])来删除 JSON 对象的属性：
				<script>
				        var myObj, i, x = "";
				        myObj = {
				            "name": "runoob",
				            "alexa": 10000,
				            "sites": {
				                "site1": "www.runoob.com",
				                "site2": "m.runoob.com",
				                "site3": "c.runoob.com"
				            }
				        }
				        delete myObj.sites["site1"];
				        for (i in myObj.sites) {
				            x += myObj.sites[i] + "<br>";
				        }
				        document.getElementById("demo").innerHTML = x;
				</script>
				
#### JSON 数组（array）：在中括号中书写，数组值必须是合法的 JSON 数据类型（字符串, 数字, 对象, 数组, 布尔值或 null）。
		- 对象中的数组：
			
			    <script>
			        var myObj, x;
			        myObj = {
			            "name": "网站",
			            "num": 3,
			            "sites": ["Google", "Runoob", "Taobao"]
			        }
			        x = myObj.sites[0];
			        document.getElementById("demo").innerHTML = x;
			    </script>
			
		- 循环数组：
			▪ for/in:
			<script>
			        var myObj, i, x = "";
			        myObj = {
			            "name": "noob",
			            "num": 3,
			            "sites": ["Google", "runoob", "baidu"]
			        };
			        for (i in myObj.sites) {
			            x += myObj.sites[i] + "<br>";
			        }
			        document.getElementById("demo").innerHTML = x;
			</script>
			
			▪ for:
			<script>
			        var myarr, i, x = "";
			        myarr = {
			            "name": "noob",
			            "age": 13,
			            "sites": ["google", "baidu", "taobao"]
			        };
			        for (i = 0; i < myarr.sites.length; i++) {
			            x += myarr.sites[i] + "<br>";
			        }
			        document.getElementById("demo").innerHTML = x;
			</script>
			
		- 嵌套 JSON 对象中的数组：
			 <script>
			        var myarr, i, j, x = "";
			        myarr = {
			            "name": "网站名",
			            "num": 3,
			            "sites": [{
			                    "name": "Google",
			                    "info": ["Android", "Google 搜索", "Google 地图", "Google 翻译"]
			                },
			                {
			                    "name": "Baidu",
			                    "info": ["Baidu 搜索", "Baidu 翻译", "Baidu 图片"]
			                },
			                {
			                    "name": "Taobao",
			                    "info": ["淘宝购物", "天猫国际", "菜鸟物流"]
			                }
			            ]
			        }
			        for (i in myarr.sites) {
			            x += "<h1>" + myarr.sites[i].name + "</h1>"
			            "<br>";
			            for (j in myarr.sites[i].info) {
			                x += myarr.sites[i].info[j] + "<br>";
			            }
			        }
			        document.getElementById("demo").innerHTML = x;
			    </script>
			
		- 修改数组值：
			<script>
			        var myObj, i, x = "";
			        myObj = {
			            "name": "网站",
			            "num": 3,
			            "sites": ["Google", "Runoob", "Taobao"]
			        };
			        myObj.sites[2] = "Github";
			        for (i in myObj.sites) {
			            x += myObj.sites[i] + "<br>";
			        }
			        document.getElementById("demo").innerHTML = x;
			</script>
			
		- 删除数组元素：
			   <script>
			        var myObj, i, x = "";
			        myObj = {
			            "name": "网站",
			            "num": 3,
			            "sites": ["Google", "Runoob", "Taobao"]
			        };
			        delete myObj.sites[2];
			        for (i in myObj.sites) {
			            x += myObj.sites[i] + "<br>";
			        }
			        document.getElementById("demo").innerHTML = x;
			    </script>
			
#### JSON.parse()：将数据转换为 JavaScript 对象。
		- 解析：JSON.parse(text[, reviver])；
			▪ text:必需， 一个有效的 JSON 字符串。
			▪ reviver: 可选，一个转换结果的函数， 将为对象的每个成员调用此函数。
				    <script>
				        var obj = JSON.parse('{"name":"Google","alexa":10000,"site":"www.google.com"}');
				        document.getElementById("demo").innerHTML = obj.name + ": " + obj.site;
				    </script>
				
		- 从服务端接收 JSON 数据：
			    <script>
			        var xmlhttp = new XMLHttpRequest();
			        xmlhttp.onreadystatechange = function() {
			            if (this.readyState == 4 && this.status == 200) {
			                myObj = JSON.parse(this.responseText);
			                document.getElementById("demo").innerHTML = myObj.name;
			            }
			        };
			        xmlhttp.open("GET", "/try/ajax/json_demo.txt", true);
			        xmlhttp.send();
			    </script>
			
		- 从服务端接收数组的 JSON 数据：
			  <script>
			           var xmlhttp = new XMLHttpRequest();
			        xmlhttp.onreadystatechange = function() {
			            if (this.readyState == 4 && this.status == 200) {
			                myArr = JSON.parse(this.responseText);
			                document.getElementById("demo").innerHTML = myArr[1];
			            }
			        };
			        xmlhttp.open("GET", "/try/ajax/json_demo_array.txt", true);
			        xmlhttp.send();
			    </script>
			
		- 异常：JSON 不能存储 Date 对象，如果你需要存储 Date 对象，需要将其转换为字符串，之后再将字符串转换为 Date 对象。
			    <script>
			        var text = '{ "name":"Runoob", "initDate":"2013-12-14", "site":"www.runoob.com"}';
			        var obj = JSON.parse(text, function(key, value) {
			            if (key == "initDate") {
			                return new Date(value);
			            } else {
			                return value;
			            }
			//字符串转换为 Date 对象
			        });
			        document.getElementById("demo").innerHTML = obj.name + "创建日期：" + obj.initDate;
			    </script>
			
		- 解析函数：JSON 不允许包含函数，但你可以将函数作为字符串存储，之后再将字符串转换为函数。
			    <script>
			        var text = '{ "name":"Runoob", "alexa":"function () {return 10000;}", "site":"www.runoob.com"}';
			        var obj = JSON.parse(text);
			        obj.alexa = eval("(" + obj.alexa + ")");
			        document.getElementById("demo").innerHTML = obj.name + " Alexa 排名：" + obj.alexa();
			    </script>
			
#### JSON.stringify()：将 JavaScript 对象转换为字符串。
		- JSON.stringify(value[, replacer[, space]]) 
			▪ value：必需， 要转换的 JavaScript 值（通常为对象或数组）；
			▪ replacer：可选。用于转换结果的函数或数组；
			▪ space：可选，文本添加缩进、空格和换行符。
			
		- JavaScript 对象转换：
			 <script>
			        var obj = {
			            "name": "runoob",
			            "alexa": 10000,
			            "site": "www.runoob.com"
			        };
			        var myJson = JSON.stringify(obj);
			        document.getElementById("demo").innerHTML = myJson;
			</script>
			
		- JavaScript 数组转换：
			<script>
			        var arr = ["Google", "Runoob", "Taobao", "Facebook"];
			        var myArr = JSON.stringify(arr);
			        document.getElementById("demo").innerHTML = myArr;
			</script>
			
		- 异常：JSON 不能存储 Date 对象，如果你需要存储 Date 对象，需要将其转换为字符串，之后再将字符串转换为 Date 对象。
			<script>
			        var obj = {
			            "name": "Runoob",
			            "initDate": new Date(),
			            "site": "www.runoob.com"
			        };
			        var myJSON = JSON.stringify(obj);
			//JSON.stringify 将 Date 对象转换为字符串
			        document.getElementById("demo").innerHTML = myJSON;
			</script>
			
		- 解析函数：JSON 不允许包含函数，JSON.stringify() 会删除 JavaScript 对象的函数，包括 key 和 value。
			  <script>
			        var obj = {
			            "name": "Runoob",
			            "alexa": function() {
			                return 10000;
			            },
			//JSON.stringify 将删除对象中的函数：
			            "site": "www.runoob.com"
			        };
			        var myJSON = JSON.stringify(obj);
			        document.getElementById("demo").innerHTML = myJSON;
			    </script>
			
			解决方案：
			 <script>
			        var obj = {
			            "name": "Runoob",
			            "alexa": function() {
			                return 10000;
			            },
			            "site": "www.runoob.com"
			        };
			        obj.alexa = obj.alexa.toString();
			//在执行 JSON.stringify() 函数前将函数转换为字符串来保留函数。
			        var myJSON = JSON.stringify(obj);
			        document.getElementById("demo").innerHTML = myJSON;
			</script>
			
#### JSON 使用：
		-  eval() 可用于将 JSON 文本转换为 JavaScript 对象。
			<script>
			        var txt = '{ "sites" : [' +
			            '{ "name":"菜鸟教程" , "url":"www.runoob.com" },' +
			            '{ "name":"google" , "url":"www.google.com" },' +
			            '{ "name":"微博" , "url":"www.weibo.com" } ]}';
			        var obj = eval("(" + txt + ")");
			        document.getElementById("name").innerHTML = obj.sites[0].name
			        document.getElementById("url").innerHTML = obj.sites[0].url
			</script>
			// eval() 函数可编译并执行任何 JavaScript 代码。这隐藏了一个潜在的安全问题。
			
		- JSON 解析器：
			    <script>
			        var txt = '{ "sites" : [' +
			            '{ "name":"菜鸟教程" , "url":"www.runoob.com" },' +
			            '{ "name":"google" , "url":"www.google.com" },' +
			            '{ "name":"微博" , "url":"www.weibo.com" } ]}';
			        obj = JSON.parse(txt);
			        document.getElementById("name").innerHTML = obj.sites[0].name
			        document.getElementById("url").innerHTML = obj.sites[0].url
			    </script>
			
#### JSONP 应用：Jsonp(JSON with Padding) 是 json 的一种"使用模式"，可以让网页从别的域名（网站）那获取资料，即跨域读取数据。
		- 同源策略： 详情 同源是指，域名，协议，端口相同，是浏览器的行为。
		- JSONP 应用：
			▪ 服务端JSONP格式数据：
				<body>
				    <div id="divCustomers"></div>
				    <script type="text/javascript">
				        function callbackFunction(result, methodName) {
				            var html = '<ul>';
				            for (var i = 0; i < result.length; i++) {
				                html += '<li>' + result[i] + '</li>';
				            }
				            html += '</ul>';
				            document.getElementById('divCustomers').innerHTML = html;
				        }
				    </script>
				    <script type="text/javascript" src="http://www.runoob.com/try/ajax/jsonp.php?jsoncallback=callbackFunction"></script>
				</body>
					
#### 序列化：
		var xiaoming = {
		    name: '小明',
		    age: 14,
		    gender: true,
		    height: 1.65,
		    grade: null,
		    'middle-school': '\"W3C\" Middle School',
		    skills: ['JavaScript', 'Java', 'Python', 'Lisp'],
		    toJSON: function () {
		        return { // 只输出name和age，并且改变了key：
		            'Name': this.name,
		            'Age': this.age
		        };
		    }
		};
		
		JSON.stringify(xiaoming); // '{"Name":"小明","Age":14}'
		
#### 反序列化: 拿到一个JSON格式的字符串，我们直接用JSON.parse()把它变成一个JavaScript对象：
		JSON.parse('[1,2,3,true]'); // [1, 2, 3, true]
		JSON.parse('{"name":"小明","age":14}'); // Object {name: '小明', age: 14}
		JSON.parse('true'); // true
		JSON.parse('123.45'); // 123.45

		var obj = JSON.parse('{"name":"小明","age":14}', function (key, value) {
		    if (key === 'name') {
		        return value + '同学';
		    }
		    return value;
		});
		console.log(JSON.stringify(obj)); // {name: '小明同学', age: 14}
