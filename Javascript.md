#### JavaScript：改变 HTML 内容：
	• document.getElementByID("some id")；
		- 改变文本内容：
			§ <body>
			    <div id="demo">javasc能够改变html元素内容。</div>
			    <script>
			        function myFirst() {
			            x = document.getElementById("demo");
			            x.innerHTML = "看我七十二变！";
			        }
			    </script>
			    <button type="button" onclick="myFirst()">点击</button>
			</body>
			
		- 改变图像：
			§ <body>
			    <script>
			        function changeImage() {
			            element = document.getElementById("myimg");
			            if (element.src.match("bulbon")) {
			                element.src = "../images/eg_bulboff.gif";
			            } else {
			                element.src = "../images/eg_bulbon.gif";
			            }
			        }
			    </script>
			    <img id="myimg" onclick="changeImage()" src="../images/eg_bulboff.gif" alt="myimages" />
			</body>
			
		- 验证输入：
			§ <body>
			    <input id="demo" type="text">
			    <script>
			        function myFunction() {
			            var x = document.getElementById("demo").value;
			            if (x == "" || isNaN(x)) {
			                alert("not numeric");
			            }
			        }
			    </script>
			    <button type="button" onclick="myFunction()">提交</button>
			</body>
			
#### JavaScript 变量：
	• 变量必须以字母开头；
	• 变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）；
	• 变量名称对大小写敏感（y 和 Y 是不同的变量）；
	
#### JavaScript 数据类型：JavaScript拥有动态类型，这意味着相同的变量可用作不同的类型。
	• 字符串：可以是引号中的任意文本，您可以使用单引号或双引号。
		- var answer="Nice to meet you!";
		- var answer="He is called 'Bill'";
		- var answer='He is called "Bill"';
		
	• 数字：只有一种数字类型，数字可以带小数点，也可以不带，极大或极小的数字可以通过科学（指数）计数法来书写。
		- var x1=34.00;      //使用小数点来写
		- var x2=34;         //不使用小数点来写
		- var y=123e5;      // 12300000
		- var z=123e-5;     // 0.00123
		
	• 布尔：布尔（逻辑）只能有两个值：true 或 false，常用在条件测试中。
		- var x=true
		- var y=false
		
	• 数组：数组下标是基于零的，所以第一个项目是 [0]，第二个是 [1]，以此类推。
		- var cars=new Array();
		cars[0]="Audi";
		cars[1]="BMW";
		cars[2]="Volvo";
			或者
		var cars=new Array("Audi","BMW","Volvo");
		
	• 对象：由花括号分隔，在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义，属性由逗号分开。
		- var person={firstname:"Bill", lastname:"Gates", id:5566}；
		
			§ 对象属性有两种寻址方式：
				Ø name=person.lastname;
				Ø name=person["lastname"];
				
	• Null：空。
	
	• Undefined：未定义。
	
	• Map：是一组键值对的结构，具有极快的查找速度。
		- 初始化Map需要一个二维数组，或者直接初始化一个空Map。Map具有以下方法：
			var m = new Map(); // 空Map
			m.set('Adam', 67); // 添加新的key-value
			m.set('Bob', 59);
			m.has('Adam'); // 是否存在key 'Adam': true
			m.get('Adam'); // 67
			m.delete('Adam'); // 删除key 'Adam'
			m.get('Adam'); // undefined
			
		- 由于一个key只能对应一个value，所以，多次对一个key放入value，后面的值会把前面的值冲掉：
			var m = new Map();
			m.set('Adam', 67);
			m.set('Adam', 88);
			m.get('Adam'); // 88
	
	• Set也是一组key的集合，但不存储value。由于key不能重复，所以，在Set中，没有重复的key。
		- 要创建一个Set，需要提供一个Array作为输入，或者直接创建一个空Set：
			var s1 = new Set(); // 空Set
			var s2 = new Set([1, 2, 3]); // 含1, 2, 3
		
		- 重复元素在Set中自动被过滤：
			var s = new Set([1, 2, 3, 3, '3']);
			s; // Set {1, 2, 3, "3"}
		
		- 通过add(key)方法可以添加元素到Set中，可以重复添加，但不会有效果：
			s.add(4);
			s; // Set {1, 2, 3, 4}
			s.add(4);
			s; // 仍然是 Set {1, 2, 3, 4}
			
		- 通过delete(key)方法可以删除元素：
			var s = new Set([1, 2, 3]);
			s; // Set {1, 2, 3}
			s.delete(3);
			s; // Set {1, 2}

#### 声明变量类型：JavaScript 变量均为对象，当您声明一个变量时，就创建了一个新的对象。
	• 声明新变量时，可以使用关键词 "new" 来声明其类型：
		- var carname=new String;
		var x= new Number;
		var y= new Boolean;
		var cars= new Array;
		var person= new Object;
		
#### JavaScript 函数：由事件驱动的或者当它被调用时执行的可重复使用的代码块。
	• JavaScript 函数语法：包裹在花括号中的代码块，前面使用了关键词 function；
		- function functionname(){
			这里是要执行的代码
		}
		
	• myFunction(argument1,argument2)
		- function myFunction(var1,var2){
			这里是要执行的代码
		}
		
#### JavaScript 运算符：
	• 算术运算符：
		+	加	x=y+2	x=7
		-	减	x=y-2	x=3
		*	乘	x=y*2	x=10
		/	除	x=y/2	x=2.5
		%	求余数 (保留整数)	x=y%2	x=1
		++	累加	x=++y	x=6
		--	递减	x=--y	x=4
	•  赋值运算符：
		=	x=y	 	x=5
		+=	x+=y	x=x+y	x=15
		-=	x-=y	x=x-y	x=5
		*=	x*=y	x=x*y	x=50
		/=	x/=y	x=x/y	x=2
		%=	x%=y	x=x%y	x=0
		
#### JavaScript 比较和逻辑运算符：
	• 比较运算符：
		==	等于	x==8 为 false
		===	全等（值和类型）	x===5 为 true；x==="5" 为 false
		!=	不等于	x!=8 为 true
		>	大于	x>8 为 false
		<	小于	x<8 为 true
		>=	大于或等于	x>=8 为 false
		<=	小于或等于	x<=8 为 true
	• 逻辑运算符：
		&&	and	(x < 10 && y > 1) 为 true
		||	or	(x==5 || y==5) 为 false
		!	not	!(x==y) 为 true
	• 条件运算符：
		- variablename=(condition)?value1:value2 
		
#### JavaScript 条件语句：
	• if 语句 - 只有当指定条件为 true 时，使用该语句来执行代码：
		<body>
		    <button onclick="myFunction()">点击</button>
		    <p id="demo"></p>
		    <script>
		        function myFunction() {
		            var x = "";
		            var time = new Date().getHours();
		            if (time < 21) {
		                x = "good day";
		            }
		            document.getElementById("demo").innerHTML = x;
		        }
		    </script>
		</body>
	
	• if...else 语句 - 当条件为 true 时执行代码，当条件为 false 时执行其他代码：
		<body>
		    <button onclick="myFunction()">点击这里</button>
		    <p id="demo"></p>
		    <script>
		        function myFunction() {
		            var x = "";
		            var time = new Date().getHours();
		            if (time < 20) {
		                x = "good day";
		            } else {
		                x = "bad day";
		            }
		            document.getElementById("demo").innerHTML = x;
		        }
		    </script>
		</body>
		
	• if...else if....else 语句 - 使用该语句来选择多个代码块之一来执行：
		<body>
		    <button onclick="myFunction()">点击这里</button>
		    <p id="demo"></p>
		    <script>
		        function myFunction() {
		            var x = "";
		            var time = new Date().getHours();
		            if (time < 10) {
		                x = "good day";
		            } else if (time < 21) {
		                x = "bad day";
		            }
		            document.getElementById("demo").innerHTML = x;
		        }
		    </script>
		</body>
	
	• switch 语句 - 使用该语句来选择多个代码块之一来执行：
		<body>
		    <button onclick="myFunction()">点击这里</button>
		    <p id="demo"></p>
		    <script>
		        function myFunction() {
		            var x;
		            var day = new Date().getDay();
		            switch (day) {
		                case 0:
		                    x = "today is sunday";
		                    break;
		                case 1:
		                    x = "today is monday";
		                    break;
		                case 2:
		                    x = "today is tuesday";
		                    break;
		                case 3:
		                    x = "today is wednesday";
		                    break;
		                case 4:
		                    x = "today is thursday";
		                    break;
		                case 5:
		                    x = "today is friday";
		                    break;
		                case 6:
		                    x = "today is saturday";
		                    break;
		            }
		            document.getElementById("demo").innerHTML = x;
		        }
		    </script>
		</body>
		
	• default 关键词：规定匹配不存在时做的事情。
		<body>
		    <button onclick="myFunction()">点击这里</button>
		    <p id="demo"></p>
		    <script>
		        function myFunction() {
		            var x;
		            var day = new Date().getDay();
		            switch (day) {
		                case 0:
		                    x = "today is sunday";
		                    break;
		                case 5:
		                    x = "today is saturday";
		                    break;
		                default:
		                    x="looking forward to the weekend"
		//当数据不匹配时，输出默认信息。
		            }
		            document.getElementById("demo").innerHTML = x;
		        }
		    </script>
		</body>
		
#### JavaScript 循环语句：
	• for循环：循环代码块一定的次数。
		- for (语句 1; 语句 2; 语句 3)
		  {
		  被执行的代码块
		  }
		语句 1 在循环（代码块）开始前执行；
		语句 2 定义运行循环（代码块）的条件；
		语句 3 在循环（代码块）已被执行之后执行；
		
		- <body>
		    <button onclick="myFunction()">点</button>
		    <p id="demo"></p>
		    <script>
		        function myFunction() {
		            var a = "";
		            for (var b = 0; b < 5; b++) {
		                a = a + "the number is " + b + "<br>";
		            }
		            document.getElementById("demo").innerHTML = a;
		        }
		    </script>
		</body>

	• for/in - 循环遍历对象的属性：
		- <body>
		    <p id="demo"></p>
		    <button onclick="myFunction()">点击</button>
		    <script>
		        function myFunction() {
		            var a;
		            var b = "";
		            var per = {
		                fname: "wang",
		                lname: "yingzhi",
		                age: 26
		            };
		            for (a in per) {
		                b = b + per[a];
		            }
		            document.getElementById("demo").innerHTML = b;
		        }
		    </script>
		</body>
		
	• for/of：只循环集合本身的元素，修复了for/in遍历对象属性的缺陷；
		<script>
		        var a = ['a', 'b', 'c'];
		        var b = new Set(['a', 'b', 'c']);
		        var c = new Map([
		            [1, 'z'],
		            [2, 'y'],
		            [3, 'z']
		        ]);
		
		        for (var x of a) {
		            document.write(x);
		        }
		        for (var x of b) {
		            document.write(x);
		        }
		        for (var x of c) {
		            document.write(x);
		        }
		</script>
		
	• while - 当指定的条件为 true 时循环指定的代码块：
		<body>
		    <button onclick="myFunction()">点击</button>
		    <script>
		        function myFunction() {
		            var a = "",
		                b = 0;
		            while (b < 5) {
		                a = a + "this number is " + b + "<br>";
		                b++;
		            }
		            document.getElementById("demo").innerHTML = a;
		        }
		    </script>
		    <p id="demo"></p>
		</body>
		
	• do/while - 同样当指定的条件为 true 时循环指定的代码块，该循环至少会执行一次，即使条件是 false。
		<body>
		    <button onclick="myFunction()">点击</button>
		    <script>
		        function myFunction() {
		            var a = "",
		                b = 0;
		            do {
		                a = a + "this number is " + b + "<br>";
		                b++;
		            } while (b < 10) {
		                document.getElementById("demo").innerHTML = a;
		            }
		        }
		    </script>
		    <p id="demo"></p>
		</body>
		
#### Break 和 Continue 语句：
	• break语句：用于跳出循环；只能用在循环或 switch 中。
		<body>
		    <button onclick="myFunction()">点击</button>
		    <script>
		        function myFunction() {
		            var a = "";
		            for (b = 0; b < 10; b++) {
		                if (b == 5) {
		                    break;
		                }
		                a = a + "this number is " + b + "<br>";
		            }
		            document.getElementById("demo").innerHTML = a;
		        }
		    </script>
		    <p id="demo"></p>
		</body>
		
	• Continue 语句：用于中断循环中的迭代，如果出现了指定的条件，然后继续循环中的下一个迭代。只能用在循环中。
		<body>
		    <button onclick="myFunction()">点击</button>
		    <script>
		        function myFunction() {
		            var a = "";
		            for (b = 0; b < 10; b++) {
		                if (b == 5) continue;
		                a = a + "this is " + b + "<br>";
		            }
		            document.getElementById("demo").innerHTML = a;
		        }
		    </script>
		    <p id="demo"></p>
		</body>
		
#### JavaScript 错误：
	• try 语句-测试代码块的错误，允许我们定义在执行时进行错误测试的代码块。
	• catch 语句-处理错误，允许我们定义当 try 代码块发生错误时，所执行的代码块。
		 <script>
		        var txt = "";
		        function message() {
		            try {
		                adddlert("Welcome guest!");
		            } catch (err) {
		                txt = "本页有一个错误。\n\n";
		                txt += "错误描述：" + err.message + "\n\n";
		                txt += "点击确定继续。\n\n";
		                alert(txt);
		            }
		        }
		    </script>
		//try和catch总是成对出现。
		<body>
		    <input type="button" value="查看消息" onclick="message()" />
		</body>
		
	• throw 语句-创建或抛出异常，创建自定义错误。
		<body>
		    <script>
		        function myFunction() {
		            try {//测试错误！
		                var a = document.getElementById("demo").value;
		                if (a == "") throw "值为空";
		                if (isNaN(a)) throw "非数字";
		                if (a > 10) throw "请按提示输入";
		                if (a < 5) throw "请按提示输入";
		//抛出异常！
		            } catch (err) {
		                var c = document.getElementById("mess");
		                c.innerHTML = "错误：" + err + " .";
		//处理错误！
		            }
		        }
		    </script>
		    <p>请输入 5 到 10 之间的数字：</p>
		    <input id="demo" type="text">
		    <button type="button" onclick="myFunction()">测试输入值</button>
		    <p id="mess"></p>
		</body>
    
#### JavaScript 字符串：用' '或" "括起来的字符表示。
	• 多行字符串：换行时由于\n太麻烦，可以使用 ` ` 用于一次性换行。
		console.log(`多行
		字符串
		测试`);
		
	• 模板字符串：多个字符串连接，可以用+号，如果很多变量需要连接时，可使用 ` ` 自动替换变量 
		var name = '小明';
		var age = 20;
		var message = ` 你好, ${name}, 你今年${age}岁了! `;
		alert(message);
		
	• 操作字符串：avaScript为字符串提供了一些常用方法，调用这些方法本身不会改变原有字符串的内容，而是返回一个新字符串。
		- toUpperCase（）；把一个字符串全部变为大写。
			var s = 'Hello';
			s.toUpperCase(); // 返回'HELLO'
			
		- toLowerCase（）；把一个字符串全部变为小写。
			var s = 'Hello';
			var lower = s.toLowerCase(); // 返回'hello'并赋值给变量lower
			lower; // 'hello'
			
		- indexOf（）；搜索指定字符串出现的位置。
			var s = 'hello, world';
			s.indexOf('world'); // 返回7
			s.indexOf('World'); // 没有找到指定的子串，返回-1
			
		- substring（）；返回指定索引区间的子串。
			var s = 'hello, world'
			s.substring(0, 5); // 从索引0开始到5（不包括5），返回'hello'
			s.substring(7); // 从索引7开始到结束，返回'world'
			

#### JavaScript 对象：JavaScript 中的所有事物都是对象：字符串、数字、数组、日期，等等。
	• 创建对象的三种方法：
		Ø 对象直接量：使用object.prototype作为原型；
		Ø 通过new创建：使用构造函数的prototype属性作为原型；
				    <script>
				        x = new Object();
				        x.firstname = "wang";
				        x.lastname = "yingzhi";
				        x.age = "26";
				        x.eyecolor = "yellow";
				        document.write(x.firstname + x.lastname + " is " + x.age + "years old");
				    </script>
			
		Ø 通过 object.create()创建：使用第一个参数（也可以是null）作为原型；
	
	• 对象是拥有属性和方法的数据。
		- 访问属性：objectName.propertyName
			 <script>
			        var message = "hello dsb";
			        var x = message.length;
			        document.write(x);
			    </script>
		
		- 访问方法：objectName.methodName()
			    <script>
			        var message = "hello dsb";
			        var x = message.toUpperCase();
			        document.write(x);
			    </script>
	
	• 对象属性：1.原型（prototype）2.类（class）3.可扩展性（extensible attribute）；
		- 原型属性：用以继承属性；
		- 类属性：是一个字符串，用以表示对象的类型信息；
		- 可扩展属性：用以表示是否可以给对象添加新属性；
			§ 访问属性是通过 . 操作符完成的，但这要求属性名必须是一个有效的变量名。如果属性名包含特殊字符，就必须用 ' ' 括起来。
			§ 检测对象是否拥有某一属性，可以用in操作符。
				var xiaoming = {
				    name: '小明',
				    birth: 1990,
				    school: 'No.1 Middle School',
				    height: 1.70,
				    weight: 65,
				    score: null
				};
				'name' in xiaoming; // true
				'grade' in xiaoming; // false
				
				Ø 如果in判断一个属性存在，这个属性不一定是该对象的，它可能是对象继承得到的：所有对象最终都会在原型链上指向object。
					ü 检测一个对象是否是另一个对象的原型：使用 isPrototyOf（）方法：
						 <script>
						        var p = {x: 1};
						        var o = Object.create(p);//使用第一个参数作为原型
						        x = p.isPrototypeOf(o);
						        //检测p是否是o的原型。
						        Object.prototype.isPrototypeOf(o);
						        //检查 object.prototype 是否是o的原型。
						    </script>
				
			§ 判断一个属性是否是自身拥有的，而不是继承得到的，可以用hasOwnProperty()方法：
				var xiaoming = {
				    name: '小明'
				};
				xiaoming.hasOwnProperty('name'); // true
				xiaoming.hasOwnProperty('toString'); // false

	• 对象方法：
		- toString(); 没有参数，将返回一个表示调用这个方法的对象值的字符串；
			var s = {x:1,y:1}.toString(); //返回：[Object Object]
			
		- toLocaleString();  返回一个表示这个对象的本地化字符串；
		- toJSON();  需要执行序列化的对象来说，JSON.stringify()方法会调用toJSON方法；
		- valueOf(); 将对象转换为某种原始值时需要调用该方法；
		
#### JavaScript 数组：JavaScript的Array可以包含任意数据类型，并通过索引来访问每个元素。
	• 要取得Array的长度，直接访问length属性：
		var arr = [1, 2, 3.14, 'Hello', null, true];
		arr.length; // 6

	• 直接给Array的length赋一个新的值会导致Array大小的变化：
		var arr = [1, 2, 3];
		arr.length; // 3
		arr.length = 6;
		arr; // arr变为[1, 2, 3, undefined, undefined, undefined]
		arr.length = 2;
		arr; // arr变为[1, 2]
		
	• Array可以通过索引把对应的元素修改为新的值，因此，对Array的索引进行赋值会直接修改这个Array：
		var arr = ['A', 'B', 'C'];
		arr[1] = 99;
		arr; // arr现在变为['A', 99, 'C']
	-----------------------------------------------------------------
	• indexOf（）；Array也可以通过indexOf()来搜索一个指定的元素的位置。
		var arr = [10, 20, '30', 'xyz'];
		arr.indexOf(10); // 元素10的索引为0
		arr.indexOf(20); // 元素20的索引为1
		arr.indexOf(30); // 元素30没有找到，返回-1
		arr.indexOf('30'); // 元素'30'的索引为2
		
	• slice（）；对应String的substring()版本，它 截取（非删除）Array的部分元素，然后返回一个新的Array。
		var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
		arr.slice(0, 3); // 从索引0开始，到索引3结束，但不包括索引3: ['A', 'B', 'C']
		arr.slice(3); // 从索引3开始到结束: ['D', 'E', 'F', 'G']
		//如果不给slice()传递任何参数，它就会从头到尾截取所有元素。利用这一点，我们可以很容易地复制一个Array：
			var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
			var aCopy = arr.slice();
			aCopy; // ['A', 'B', 'C', 'D', 'E', 'F', 'G']
		
	• push（）；向Array的末尾添加若干元素；
	• pop（）；则把Array的最后一个元素删除掉。
		var arr = [1, 2];
		arr.push('A', 'B'); // 返回Array新的长度: 4
		arr; // [1, 2, 'A', 'B']
		arr.pop(); // pop()返回'B'
		arr; // [1, 2, 'A']
		arr.pop(); arr.pop(); arr.pop(); // 连续pop 3次
		arr; // []
		arr.pop(); // 空数组继续pop不会报错，而是返回undefined
		arr; // []
		
	• unshift（）；往Array的头部添加若干元素；
	• shift（）；把Array的第一个元素删掉。
		var arr = [1, 2];
		arr.unshift('A', 'B'); // 返回Array新的长度: 4
		arr; // ['A', 'B', 1, 2]
		arr.shift(); // 删除'A'
		arr; // ['B', 1, 2]
		arr.shift(); arr.shift(); arr.shift(); // 连续shift 3次
		arr; // []
		arr.shift(); // 空数组继续shift不会报错，而是返回undefined
		arr; // []
		
	• sort（）；可以对当前Array进行排序，它会直接修改当前Array的元素位置，直接调用时，按照默认顺序排序。
		var arr = ['B', 'C', 'A'];
		arr.sort();
		arr; // ['A', 'B', 'C']
		
	• reverse（）；把整个Array的元素给掉个个，也就是反转：
		var arr = ['one', 'two', 'three'];
		arr.reverse(); 
		arr; // ['three', 'two', 'one']
		
	• splice（）；方法是修改Array的“万能方法”，它可以从指定的索引开始删除若干元素，然后再从该位置添加若干元素：
		var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
		arr.splice(2, 3, 'Google', 'Facebook'); 
		arr; 
		// 从索引2开始（包含2）删除3个元素,然后再添加两个元素:
		arr.splice(2, 2);
		 arr; 
		//只删除，不添加
		arr.splice(2, 0, 'Google', 'Facebook'); 
		arr; 
		//只添加，不删除
		
	• concat（）；方法把当前的Array和另一个Array连接起来，并返回一个新的Array。
		var arr = ['A', 'B', 'C'];
		var added = arr.concat([1, 2, 3]);
		added; // ['A', 'B', 'C', 1, 2, 3]
		arr; // ['A', 'B', 'C']
		
	• join（）；方法是一个非常实用的方法，它把当前Array的每个元素都用指定的字符串连接起来，然后返回连接后的字符串。
		var arr = ['A', 'B', 'C', 1, 2, 3];
		arr.join('-'); // 'A-B-C-1-2-3'
		
#### JavaScript 函数：最基本的一种代码抽象的方式。
	• 定义函数①：
		- function abs(x) {
		    if (x >= 0) {
		        return x;
		    } else {
		        return -x;
		    }
		}
			§ function：指出这是一个函数定义；
			§ abs：是函数的名称；
			§ (x)：括号内列出函数的参数，多个参数以  , 分隔；
			§ { ... }：之间的代码是函数体，可以包含若干语句，甚至可以没有任何语句。
		
	• 定义函数②：
		- var abs = function (x) {
		    if (x >= 0) {
		        return x;
		    } else {
		        return -x;
		    }
		};
			§ 在这种方式下，function (x) { ... }是一个匿名函数，它没有函数名。但是，这个匿名函数赋值给了变量abs，所以，通过变量abs就可以调用该函数。
			
			§ 上述两种定义完全等价，注意第二种方式按照完整语法需要在函数体末尾加一个;，表示赋值语句结束。
			
	• 调用函数：按顺序传入参数即可。
		- function abs(x) {
		    if (typeof x !== 'number') {
		        throw 'Not a number';
		    }
		    if (x >= 0) {
		        return x;
		    } else {
		        return -x;
		    }
		}
		abs（10）；//10
		
		- arguments：只在函数内部起作用，并且永远指向当前函数的调用者传入的所有参数。
			§ function foo(x) {
			    console.log('x = ' + x); // 10
			    for (var i=0; i<arguments.length; i++) {
			        console.log('arg ' + i + ' = ' + arguments[i]); // 10, 20, 30
			    }
			}
			foo(10, 20, 30);
			
		- rset参数：rest参数只能写在最后，前面用 … 标识。
			§ <script>
			        function abs(a, b, ...rset) {
			            document.write('a= ' + a + '<br>');
			            document.write('b= ' + b + '<br>');
			            document.write(rset);
			        }
			        abs(10, 30, 1, 2, 3, 4);
			</script>
			//传入的参数先绑定a、b，多余的参数以数组形式交给变量rest，所以，不再需要arguments我们就获取了全部参数。
			
	• 变量提升：先扫描整个函数体的语句，把所有申明的变量“提升”到函数顶部。
		function foo() {
		    var x = 'Hello, ' + y;
		    console.log(x);
		    var y = 'Bob';
		}
		foo();
		//语句var x = 'Hello, ' + y;并不报错，原因是变量y在稍后申明了。但是console.log显示Hello, undefined，说明变量y的值为undefined。这正是因为JavaScript引擎自动提升了变量y的声明，但不会提升变量y的赋值。
		
	• 全局作用域：JavaScript默认有一个全局对象window，全局作用域的变量实际上被绑定到window的一个属性。
		var course = 'Learn JavaScript';
		alert(course); // 'Learn JavaScript'
		alert(window.course); // 'Learn JavaScript'
		//直接访问全局变量course和访问window.course是完全一样的。
		
		- 减少命名冲突的方式是把自己的所有变量和函数全部绑定到一个全局变量中。
			// 唯一的全局变量MYAPP:
			var MYAPP = {};
			
			// 其他变量:
			MYAPP.name = 'myapp';
			MYAPP.version = 1.0;
			
			// 其他函数:
			MYAPP.foo = function () {
			    return 'foo';
			};
			//把自己的代码全部放入唯一的名字空间MYAPP中，会大大减少全局变量冲突的可能
		
	• 局部作用域：由于JavaScript的变量作用域实际上是函数内部，循环等语句块中是无法定义具有局部作用域的变量的，用 let替代var可以申明一个块级作用域的变量。
		function foo() {
		    var sum = 0;
		    for (let i=0; i<100; i++) {
		        sum += i;
		    }
		    // SyntaxError:
		    i += 1;
		}
		
	• 常量：ES6中引入 const 用以声明常量，与 let 一样拥有块级作用域。
		const PI = 3.14;
		PI = 3; // 某些浏览器不报错，但是无效果！
		PI; // 3.14
		
	• 解构赋值：从ES6开始，JavaScript引入了解构赋值，可以同时对一组变量进行赋值。
		- <script>
		        var [x, y, z] = ['hello', 'today', 'u'];
		        document.write('x= ' + x + '  y= ' + y + '  z= ' + z);
		</script>
		//对数组元素进行解构赋值时，多个变量要用 [...] 括起来。
		
		- 如果数组本身还有嵌套，也可以通过下面的形式进行解构赋值，注意嵌套层次和位置要保持一致：
		
		let [x, [y, z]] = ['hello', ['JavaScript', 'ES6']];
		x; // 'hello'
		y; // 'JavaScript'
		z; // 'ES6'
		
		- 解构赋值还可以忽略某些元素：
		
		let [, , z] = ['hello', 'JavaScript', 'ES6']; // 忽略前两个元素，只对z赋值第三个元素
		z; // 'ES6'
		
		- 如果变量已经被声明了，再次赋值的时候，正确的写法也会报语法错误：
			// 声明变量:
			var x, y;
			// 解构赋值:
			{x, y} = { name: '小明', x: 100, y: 200};
			// 语法错误: Uncaught SyntaxError: Unexpected token；
			//这是因为JavaScript引擎把{开头的语句当作了块处理，于是=不再合法。解决方法是用小括号括起来：
			
			({x, y} = { name: '小明', x: 100, y: 200});
			
	• 方法：在一个对象中绑定函数，称为这个对象的方法。
		- this：在一个方法内部，this是一个特殊变量，它始终指向当前对象，也就是函数定义的变量。

#### 高阶函数：一个函数接收另一个函数作为参数，这种函数就称之为高阶函数。
	• map（）：将调用的数组的每个元素传递给指定的函数，并返回一个新的数组并不修改原数组内容，它包含该函数的返回值。
		<script>
		        function a(x) {
		            return x * x;
		        }
		        var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
		        var results = arr.map(a);
		//将调用的数组的每个元素传递给指定的函数，并返回一个新的数组并不修改原数组内容。
		        document.write(results);
		</script>
		
	• reduce（）：把结果继续和序列的下一个元素做累积计算。
		   <script>
		        function a(x, y) {
		            return x + y;
		        }
		        var arr = [1, 3, 5, 7, 9];
		        var results = arr.reduce(a);
		////将调用的数组的每个元素传递给指定的函数，并作累计计算后返回结果。
		        document.write(results);
		</script>
		
		- parseInt(string, radix)函数：将给定的字符串以指定的基数解析为整数。
			§ string：要被解析的字符串。
			§ radix：表示使用的进制，我们一般使用10进制，也可能会有到8或者16进制。规定必须要明确给出第二个参数的值。
				
		- Number（）在不用new操作符时，可以用来执行类型转换。
			§ 如果无法转换为数字，就返回NaN。

	• filter（）：用于筛选，也是一个常用的操作，它用于把Array的某些元素过滤掉，然后返回剩下的元素，和map()不同的是，filter()把传入的函数依次作用于每个元素，然后根据返回值是true还是false决定保留还是丢弃该元素。
		<script>
		        var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 21, 34, 56];
		        var x = arr.filter(function(x) {
		            return x % 2 !== 0;
		//删掉偶数，保留奇数
		        });
		        document.write(x);
		</script>
		
	• sort（）：用于排序，对于两个元素x和y，如果认为x < y，则返回-1，如果认为x == y，则返回0，如果认为x > y，则返回1。
		 <script>
		        a = ['apple', 'Apple', 'chorme', 'Google'].sort();
		        b = [1, 20, 3, 40, 5, 50].sort();
		
		        c = b.sort(function(x, y) {
		            if (x < y) {
		                return -1;
		            }
		            if (x > y) {
		                return 1;
		            }
		            return 0;
		        });
		//比较数字
		        d = a.sort(function(s1, s2) {
		            x1 = s1.toUpperCase();
		            x2 = s2.toLowerCase();
		            if (x1 < x2) {
		                return -1;
		            }
		            if (x1 > x2) {
		                return 1;
		            }
		            return 0;
		        });
		//比较字母
		        document.write(d);
		  </script>
		
	• every（）：方法可以判断数组的所有元素是否满足测试条件。
		var arr = ['Apple', 'pear', 'orange'];
		console.log(arr.every(function (s) {
		    return s.length > 0;
		})); // true, 因为每个元素都满足s.length>0
		
		console.log(arr.every(function (s) {
		    return s.toLowerCase() === s;
		})); // false, 因为不是每个元素都全部是小写
		
	• find（）：用于查找符合条件的第一个元素，如果找到了，返回这个元素，否则，返回undefined。
		  <script>
		        var a = ['Apple', 'chorme', 'APPLE']
		        e = a.find(function(v) {
		            return v.toUpperCase() === v;
		        });
		//找到全是大写的元素并返回
		        document.write(e);
		    </script
		
	• findIndex（）和find（）类似，也是查找符合条件的第一个元素，不同之处在于findIndex()会返回这个元素的索引，如果没有找到，返回-1。
		   <script>
		        var a = ['Apple', 'chorme', 'APPLE']
		        e = a.findIndex(function(v) {
		            return v.toUpperCase() === v;
		        });
		        document.write(e);
		    </script>
		
	• forEach()和map()类似，它也把每个元素依次作用于传入的函数，但不会返回新的数组。forEach()常用于遍历数组。

	• 闭包：JavaScript允许函数嵌套，内部函数可以访问定义在外部函数中的所有变量和函数以及外部函数能访问的所有变量和函数，外部函数不能够访问定义在内部函数中的变量和函数，当内部函数生存周期大于外部函数时，由于内部函数可以访问外部函数的作用域，定义在外部函数的变量和函数的生存周期就会大于外部函数本身，当内部函数以某一种方式被任何一个外部函数作用域访问时，一个闭包就产生了。
		
		- 
		- //返回闭包时牢记的一点就是：返回函数不要引用任何循环变量，或者后续会发生变化的变量。




	• 箭头函数：箭头函数相当于匿名函数，并且简化了函数定义。
		- 第一种格式：
		
		function (x) {
		    return x * x;
		}
		//简化写法
		x => x * x  
			
		- 第二种格式：
		
		x => {
		    if (x > 0) {
		        return x * x;
		    }
		    else {
		        return - x * x;
		    }
		}
		
#### 标准对象：在JavaScript的世界里，一切都是对象。
	• 用typeof操作符获取对象的类型，它总是返回一个字符串
		typeof 123; // 'number'
		typeof NaN; // 'number'
		typeof 'str'; // 'string'
		typeof true; // 'boolean'
		typeof undefined; // 'undefined'
		typeof Math.abs; // 'function'
		typeof null; // 'object'
		typeof []; // 'object'
		typeof {}; // 'object'
		//nul l的类型是 object，Array 的类型也是 object
	
#### 包装对象：JavaScript还提供了包装对象。
	• 用new创建。
		var n = new Number(123); // 123,生成了新的包装类型
		var b = new Boolean(true); // true,生成了新的包装类型
		var s = new String('str'); // 'str',生成了新的包装类型
		
注意：
		
	• 不要使用new Number()、new Boolean()、new String()创建包装对象；
	
	• 用parseInt()或parseFloat()来转换任意类型到number；
	
	• 用String()来转换任意类型到string，或者直接调用某个对象的toString()方法；
	
	• 通常不必把任意类型转换为boolean再判断，因为可以直接写if (myVar) {...}；
	
	• typeof操作符可以判断出number、boolean、string、function和undefined；
	
	• 判断Array要使用Array.isArray(arr)；
	
	• 判断null请使用myVar === null；
	
	• 判断某个全局变量是否存在用typeof window.myVar === 'undefined'；
	
	• 函数内部判断某个变量是否存在用typeof myVar === 'undefined'。

#### Date对象：用来表示日期和时间。
	• 第一种方法：获取系统当前时间：
		var now = new Date();
		now; // Wed Jun 24 2015 19:49:22 GMT+0800 (CST)
		now.getFullYear(); // 2015, 年份
		now.getMonth(); // 5, 月份，注意月份范围是0~11，5表示六月
		now.getDate(); // 24, 表示24号
		now.getDay(); // 3, 表示星期三
		now.getHours(); // 19, 24小时制
		now.getMinutes(); // 49, 分钟
		now.getSeconds(); // 22, 秒
		now.getMilliseconds(); // 875, 毫秒数
		now.getTime(); // 1435146562875, 以number形式表示的时间戳
		
	• 第二种方法：解析一个符合ISO 8601格式的字符串：
		var d = Date.parse('2015-06-24T19:49:22.875+08:00');
		d; // 1435146562875 返回的不是Date对象，而是一个时间戳。 
		var d = new Date(1435146562875);
		d; // Wed Jun 24 2015 19:49:22 GMT+0800 (CST)
		d.getMonth(); // 5
		
	• 时区：只要我们传递的是一个number类型的时间戳，我们就不用关心时区转换。任何浏览器都可以把一个时间戳正确转换为本地时间。
		- 要获取当前时间戳，可以用：
			<script>
			        if (Date.now) {
			            document.write(Date.now());
			        } else {
			            document.write(new Date().getTime());
			        }
			</script>
			
#### RegExp：正则表达式用来匹配字符串。
	• 在正则表达式中，如果直接给出字符，就是精确匹配。
		- \d 可以匹配一个数字； 
		- \w 可以匹配一个字母或数字 ；
		- \s 可以匹配一个空格（也包括Tab等空白符），所以\s+表示至少有一个空格，例如匹配' '，'\t\t'等；
		- . 可以匹配任意字符；
		- * 表示任意个字符（包括0个）；
		- + 表示至少一个字符；
		- ? 表示0个或1个字符；
		- {n} 表示n个字符；
		- {n,m} 表示n-m个字符；
		
			§ 例子：\d{3}\s+\d{3,8}
				Ø \d{3}表示匹配3个数字，例如'010'；
				Ø \s可以匹配一个空格（也包括Tab等空白符），所以\s+表示至少有一个空格，例如匹配' '，'\t\t'等；
				Ø \d{3,8}表示3-8个数字，例如'1234567'。
				
	• 更精确匹配：用 [] 表示范围；
		- [0-9a-zA-Z\_]可以匹配一个数字（0-9）、小写字母（a-z）、大写字母（A-Z）或者下划线(\_)；
		
		- [0-9a-zA-Z\_]+ 可以匹配至少一个数字、字母或者下划线组成的字符串，比如'a100'，'0_Z'，'js2015'等等；
		
		- [a-zA-Z\_\$][0-9a-zA-Z\_\$]* 可以匹配由字母或下划线、$开头，后接任意个由一个数字、字母或者下划线、$组成的字符串，也就是JavaScript允许的变量名；
		
		- [a-zA-Z\_\$][0-9a-zA-Z\_\$]{0, 19}更精确地限制了变量的长度是1-20个字符（前面1个字符+后面最多19个字符）。
		
		- A|B可以匹配A或B，所以(J|j)ava(S|s)cript可以匹配'JavaScript'、'Javascript'、'javaScript'或者'javascript'。
		
		- ^表示行的开头，^\d表示必须以数字开头。
		
		- $表示行的结束，\d$表示必须以数字结束。
	
	• 创建正则表达式：
		- 第一种方法：直接通过/正则表达式/写出来；
			§ var re1 = /ABC\-001/;
			
		- 第二种方法：通过new RegExp('正则表达式')创建一个RegExp对象；
			§ var re2 = new RegExp('ABC\\-001');
			
	• 切分字符串：
		- 'a,b;; c  d'.split(/[\s\,\;]+/); // ['a', 'b', 'c', 'd']
		- // split() 方法用于把一个字符串分割成字符串数组。
		
	• 分组：正则表达式还有提取子串的强大功能。用()表示的就是要提取的分组（Group）。
		var re = /^(\d{3})-(\d{3,8})$/;
		re.exec('010-12345'); // ['010-12345', '010', '12345']
		re.exec('010 12345'); // null
		//如果正则表达式中定义了组，就可以在RegExp对象上用exec()方法提取出子串来。
		//exec()方法在匹配成功后，会返回一个Array，第一个元素是正则表达式匹配到的整个字符串，后面的字符串表示匹配成功的子串。
		//exec()匹配失败后返回null。
		
	• 贪婪匹配：正则匹配默认是贪婪匹配，也就是匹配尽可能多的字符。
		var re = /^(\d+)(0*)$/;
		re.exec('102300'); // ['102300', '102300', '']
		//由于\d+采用贪婪匹配，直接把后面的0全部匹配了，结果0*只能匹配空字符串了。
		
		var re = /^(\d+?)(0*)$/;
		re.exec('102300'); // ['102300', '1023', '00']
		//必须让\d+采用非贪婪匹配（也就是尽可能少匹配），才能把后面的0匹配出来，加个 ? 就可以让\d+采用非贪婪匹配：
		
	• 全局搜索：g表示全局匹配。
		var s = 'JavaScript, VBScript, JScript and ECMAScript';
		var re=/[a-zA-Z]+Script/g;
		
		// 使用全局匹配:
		re.exec(s); // ['JavaScript']
		re.lastIndex; // 10
		
		re.exec(s); // ['VBScript']
		re.lastIndex; // 20
		
		re.exec(s); // ['JScript']
		re.lastIndex; // 29
		
		re.exec(s); // ['ECMAScript']
		re.lastIndex; // 44
		
		re.exec(s); // null，直到结束仍没有匹配到
		
#### 面向对象编程：
	• 基本概念：
		- 类：类是对象的类型模板，例如，定义Student类来表示学生，类本身是一种类型，Student表示学生类型，但不表示任何具体的某个学生；
		
		- 实例：实例是根据类创建的对象，例如，根据Student类可以创建出xiaoming、xiaohong、xiaojun等多个实例，每个实例表示一个具体的学生，他们全都属于Student类型。
		
	• JavaScript不区分类和实例的概念，而是通过原型（prototype）来实现面向对象编程。
	
	• 创建对象：JavaScript对每个创建的对象都会设置一个原型，指向它的原型对象。
		- 当我们用obj.xxx访问一个对象的属性时，JavaScript引擎先1，在当前对象上查找该属性 ，如果没有找到，就到 2，其原型对象上找，如果还没有找到，就一直上溯 3，到Object.prototype对象，最后，如果还没有找到，就只能4，返回undefined。
		
			§ var arr = [1, 2, 3];
			//其原型链是：arr ----> Array.prototype ----> Object.prototype ----> null
			
			§ function foo() {
			    return 0;
			}
			//其原型链是：foo ----> Function.prototype ----> Object.prototype ----> null
			
			§     <script>
			        function student(name) {
			            this.name = name;
			        }
			
			        student.prototype.hello = function() {
			            alert('hello,' + this.name + '!')
			        }
			//要让创建的对象共享一个hello函数，根据对象的属性查找原则，我们只要把hello函数移动到xiaoming、xiaohong这些对象共同的原型上就可以了，也就是Student.prototype：
			        var xiaoming = new student('小明');
			        var xiaohong = new student('小红');
			        xiaoming.name;
			        xiaohong.name;
			        xiaohong.hello();
			        xiaoming.hello();
			    </script>
			//创建基于原型的JavaScript对象。
			
			§ 调用构造函数千万不要忘记写new。为了区分普通函数和构造函数，按照约定，构造函数首字母应当大写，而普通函数首字母应当小写，这样，一些语法检查工具如 jslint 将可以帮你检测到漏写的new。
			
			§ 所谓"构造函数"，其实就是一个普通函数，但是内部使用了this变量。对构造函数使用 new 运算符，就能生成实例，并且this变量会绑定在实例对象上。
				
	• 原型继承：JavaScript的原型继承实现方式就是。
		- 定义新的构造函数，并在内部用call()调用希望“继承”的构造函数，并绑定this；
		
		- 借助中间函数F实现原型链继承，最好通过封装的inherits函数完成；
		
		- 继续在新的构造函数的原型上定义新方法。

	• class继承：让JavaScript引擎去实现原来需要我们自己编写的原型链代码。简而言之，用class的好处就是极大地简化了原型链代码。
		class PrimaryStudent extends Student {
		    constructor(name, grade) {
		        super(name); // 记得用super调用父类的构造方法!
		        this.grade = grade;
		    }
		    myGrade() {
		        alert('I am at grade ' + this.grade);
		    }
		}
		//注意PrimaryStudent的定义也是class关键字实现的，而extends则表示原型链对象来自Student。子类的构造函数可能会与父类不太相同，例如，PrimaryStudent需要name和grade两个参数，并且需要通过super(name)来调用父类的构造函数，否则父类的name属性无法正常初始化。
		
#### 浏览器对象：JavaScript可以获取浏览器提供的很多对象，并进行操作。
	• window：对象不但充当全局作用域，而且表示浏览器窗口。
		- innerWidth属性：获取浏览器窗口的内部宽度。
		- innerHeight属性：获取浏览器窗口的内部高度。
			§ 内部宽高是指除去菜单栏、工具栏、边框等占位元素后，用于显示网页的净宽高。
		- outerWidth属性：获取浏览器窗口的整体宽度。
		- outerHeight属性：可以获取浏览器窗口的整体高度。
		
	• navigator：对象表示浏览器的信息。
		- navigator.appName：浏览器名称；
		- navigator.appVersion：浏览器版本；
		- navigator.language：浏览器设置的语言；
		- navigator.platform：操作系统类型；
		- navigator.userAgent：浏览器设定的User-Agent字符串。
		
	• screen：对象表示屏幕的信息，常用的属性有：
		- screen.width：屏幕宽度，以像素为单位；
		- screen.height：屏幕高度，以像素为单位；
		- screen.colorDepth：返回颜色位数，如8、16、24。
		
	• location：对象表示当前页面的URL信息。
		- http://www.example.com:8080/path/index.html?a=1&b=2#TOP;
		- 可以用location.href获取。要获得URL各个部分的值，可以这么写：
			location.protocol; // 'http'
			location.host; // 'www.example.com'
			location.port; // '8080'
			location.pathname; // '/path/index.html'
			location.search; // '?a=1&b=2'
			location.hash; // 'TOP'
		
	• document：对象表示当前页面。
		- 由于HTML在浏览器中以DOM形式表示为树形结构，document对象就是整个DOM树的根节点，document的title属性是从HTML文档中的<title>xxx</title>读取的，但是可以动态改变：
			§ getElementById()：按ID获得一个DOM节点；
			§ getElementsByTagName()：按Tag名称获得一组DOM节点；
			§ document.cookie读取到当前页面的Cookie；
				Ø Cookie是由服务器发送的key-value标示符。因为HTTP协议是无状态的，但是服务器要区分到底是哪个用户发过来的请求，就可以用Cookie来区分。当一个用户成功登录后，服务器发送一个Cookie给浏览器，例如user=ABC123XYZ(加密的字符串)...，此后，浏览器访问该网站时，会在请求头附上这个Cookie，服务器根据Cookie即可区分出用户。

	• history：对象保存了浏览器的历史记录，JavaScript可以调用history对象的back()或forward ()，相当于用户点击了浏览器的“后退”或“前进”按钮。		
			
