#### Vue.js 起步：每个 Vue 应用都需要通过实例化 Vue 来实现。
	   <script type="text/javascript">
	        var vm = new Vue({
	            el: '#vue_det',
	            data: {
	                site: "菜鸟教程",
	                url: "www.runoob.com",
	                alexa: "10000"
	            },
	            methods: {
	                details: function() {
	                    return this.site + " - 学的不仅是技术，更是梦想！";
	                }
	            }
	        })
	    </script>
	
		- el：对应 DOM 元素中的 id。
		- data：用于定义属性，实例中有三个属性分别为：site、url、alexa。
		- methods： 用于定义的函数，可以通过 return 来返回函数值。
		- {{ }} ：用于输出对象属性和函数返回值。
	
#### Vue.js 模板语法：使用了基于 HTML 的模版语法，允许开发者声明式地将 DOM 绑定至底层 Vue 实例的数据。
	• 文本插值：使用 {{...}}（双大括号）文本插值。
		body>
		    <div id="app">
		        <P>{{message}}</P>
		    </div>
		    <script>
		        var vm = new Vue({
		            el: "#app",
		            data: {
		                message: "noob vue"
		            }
		        })
		    </script>
		</body>
		
	• Html：使用 v-html 指令用于输出 html 代码。
		<body>
		    <div id="app">
		        <div v-html=message></div>
		    </div>
		    <script>
		        new Vue({
		            el: '#app',
		            data: {
		                message: '<b>菜鸟教程</b>'
		            }
		        })
		    </script>
		</body>
		
	• 属性：HTML 属性中的值应使用 v-bind 指令。
		<body>
		    <div id="app">
		        <label for="ri">丢雷楼某</label><input type="checkbox" v-model="use" id="r1">
		        <br><br>
		        <div v-bind:class="{'class1':use}">v-bind:class 指令</div>
		//v-bind 特性被称为指令。指令带有前缀 v-，表示是 Vue 提供的特殊特性，指令会在渲染的 DOM 上应用特殊的响应式行为。
		    </div>
		    <script>
		        new Vue({
		            el: '#app',
		            data: {
		                use: true
		            }
		        });
		    </script>
		</body>
		
	• 表达式：提供了完全的 JavaScript 表达式支持。
		<body>
		    <div id="app">
		        {{5+5}}<br>
		        {{ ok ? 'YES' : 'NO' }}<br>
		//  ？： （三元运算符）条件运算符，拥有三个操作数，第一个在“ ？”之前，第二个在“？”和“：”之间，第三个在“：”之后。操作数可以是任意类型，第一个操作数是布尔值，当为真时，计算第二个操作数并返回计算结果，当为假时，计算第三个操作数并返回结果，第二三个操作数只会计算其中之一，不能同时执行。
		        {{ message.split('').reverse().join('') }}
		//.split(separator,limit）：用于把一个字符串分割成字符串数组，如果把空字符串 ("") 用作 separator，那么 stringObject 中的每个字符之间都会被分割。
		//.reverse() ：用于颠倒数组中元素的顺序。
		// . join(separator)：用于把数组中的所有元素放入一个字符串，如果省略separate参数，则使用逗号作为分隔符。
		        <div v-bind:id="'list-' + id">菜鸟教程</div>
		    </div>
		    <script>
		        new Vue({
		            el: '#app',
		            data: {
		                ok: true,
		                message: 'RUNOOB',
		                id: 1
		            }
		        })
		    </script>
		</body>
		
	• 指令：带有 v- 前缀的特殊属性，用于在表达式的值改变时，将某些行为应用到 DOM 上。
		<body>
		    <div id="app">
		        <p v-if="seen">现在你看到我了</p>
		// v-if 指令将根据表达式 seen 的值(true 或 false )来决定是否插入 p 元素。
		        <template v-if="ok">
		            <h1>菜鸟教程</h1>
		            <p>学的不仅是技术，更是梦想！</p>
		            <p>哈哈哈，打字辛苦啊！！！</p>
		        </template>
		//<template></template> 标签：用来声明是“模板元素”，<template>标签元素原本特性，天生 display:none，标签内容隐藏，<template>标签还有一个特性，就是位置任意性，可以在<head>中，也可以在<body>或者<frameset>中。
		    </div>
		    <script>
		        new Vue({
		            el: '#app',
		            data: {
		                seen: true,
		                ok: true
		            }
		        })
		    </script>
		</body>
		
	• 参数：在指令后以冒号指明。
		<body>
		    <div id="app">
		        <pre><a v-bind:href="url">菜鸟教程</a></pre>
		    </div>
		    <script>
		        new Vue({
		            el: "#app",
		            data: {
		                url: 'http://www.baidu.com'
		            }
		        })
		    </script>
		</body>
		
	• 用户输入：
		- v-model：在 input 输入框中我们可以使用 v-model 指令来实现双向数据绑定：
			<body>
			    <div id="app">
			        <p>{{message}}</p>
			        <input v-model="message">
			    </div>
			    <script>
			        new Vue({
			            el: "#app",
			            data: {
			                message: 'noob'
			            }
			        })
			    </script>
			</body>
			
		- v-on：按钮的事件我们可以使用 v-on 监听事件，并对用户的输入进行响应。
			<body>
			    <div id="app">
			        <p>{{ message }}</p>
			        <button v-on:click="reverseMessage">点击反转</button>
			    </div>
			    <script>
			        new Vue({
			            el: "#app",
			            data: {
			                message: 'noob'
			            },
			            methods: {
			                reverseMessage: function() {
			                    this.message = this.message.split('').reverse().join('')
			                }
			            }
			        })
			    </script>
			</body>
			
	• 过滤器：Vue.js 允许你自定义过滤器，被用作一些常见的文本格式化。
		- <!-- 在两个大括号中 -->
		{{ message | capitalize }}
		
			§ <body>
			    <div id="app">
			        {{ message | capitalize }}
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                message: 'runoob'
			            },
			            filters: {
			                capitalize: function(value) {
			                    if (!value) return ''
			                    value = value.toString()
			                    return value.charAt(0).toUpperCase() + value.slice(2)
			//.charAt() 方法可返回指定位置的字符。
			//.toUpperCase() 方法可大写已选字符。
			//.slice() 方法：截取字符串。
			                }
			            }
			        })
			    </script>
			</body>
			
		
	• 缩写：
		- v-bind 
			<!-- 完整语法 -->
			<a v-bind:href="url"></a>
			<!-- 缩写 -->
			<a :href="url"></a>
			
		- v-on 
			<!-- 完整语法 -->
			<a v-on:click="doSomething"></a>
			<!-- 缩写 -->
			<a @click="doSomething"></a>
			
#### Vue.js 条件与循环：
	• 条件语句：
		- v-if：
			 <p v-if="seen">现在你看到我了</p> // v-if 指令将根据表达式 seen 的值(true 或 false )来决定是否插入 p 元素。
			
		- v-else：
			<body>
			    <div id="app">
			        <div v-if="Math.random() > 0.5">noob</div>
			        <div v-else>noop</div>
			//生成一个随机数，如果>0.5输出noob，否则输出noop。
			    </div>
			    <script>
			        new Vue({
			            el: '#app'
			        })
			    </script>
			</body>
			
		- v-else-if：
			<body>
			    <div id="app">
			        <div v-if="type==='a'">a</div>
			        <div v-else-if="type==='b'">b</div>
			        <div v-else-if="type==='c'">c</div>
			        <div v-else>not a/b/c</div>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                type: 'j'
			            }
			        })
			    </script>
			</body>
			
		- v-show：根据条件展示元素
			<body>
			    <div id="app">
			        <h1 v-show="ok">Hello!</h1>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                ok: true
			            }
			        })
			    </script>
			</body>
			
	• 循环语句：
		- v-for 指令需要以 site in sites 形式的特殊语法， sites 是源数据数组并且 site 是数组元素迭代的别名。
			<body>
			    <div id="app">
			        <ol>
			            <li v-for="site in sites">{{site.name}}</li>
			        </ol>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                sites: [{
			                    name: 'google'
			                }, {
			                    name: 'baidu'
			                }, {
			                    name: 'taobao'
			                }]
			            }
			        })
			    </script>
			</body>
			
		- 模板中使用v-for：
			<body>
			    <div id="app">
			        <ul>
			            <template v-for="site in sites">
			                <li>{{site.name}}</li>
			                <i>----------</i>
			            </template>
			        </ul>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                sites: [{
			                    name: 'google'
			                }, {
			                    name: 'baidu'
			                }, {
			                    name: 'taobao'
			                }]
			            }
			        })
			    </script>
			</body>
			
		- v-for 迭代对象：
			<body>
			    <div id="app">
			        <ul>
			            <li v-for="value in object">{{value}}</li>
			        </ul>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                object: {
			                    name: 'google',
			                    sites: 'www.google.com',
			                    alexa: '1000'
			                }
			            }
			        })
			    </script>
			</body>
			
			§ 第二个的参数：
			<body>
			    <div id="app">
			        <ul>
			            <li v-for="(value, key) in object">
			                {{ key }} : {{ value }}
			            </li>
			        </ul>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                object: {
			                    name: '菜鸟教程',
			                    url: 'http://www.runoob.com',
			                    slogan: '学的不仅是技术，更是梦想！'
			                }
			            }
			        })
			    </script>
			</body>
				
			§ 第三个的参数：
			<body>
			    <div id="app">
			        <ul>
			            <li v-for="(value, key, index) in object">
			                {{ index }}. {{ key }}:{{ value }}
			            </li>
			        </ul>
			    </div>
			    <script>
			        new Vue({
			            el: '#app',
			            data: {
			                object: {
			                    name: '菜鸟教程',
			                    url: 'http://www.runoob.com',
			                    slogan: '学的不仅是技术，更是梦想！'
			                }
			            }
			        })
			    </script>
			</body>
				
		- v-for 迭代整数：
			<body>
			    <div id="app">
			        <ul>
			            <li v-for="n in 10">
			                {{ n }}
			            </li>
			        </ul>
			    </div>
			    <script>
			        new Vue({
			            el: '#app'
			        })
			    </script>
			</body>
			
#### Vue.js 计算属性：
	• computed：
		<body>
		    <div id="app">
		        <p>原始字符：{{message}}</p>
		        <p>反转字符：{{reversedMessage}}</p>
		    </div>
		    <script>
		        new Vue({
		            el: '#app',
		            data: {
		                message: 'noob'
		            },
		            computed: {
		                reversedMessage: function() {
		                    return this.message.split('').reverse().join('')
		                }
		            }
		        })
		    </script>
		</body>
		
#### Vue.js 监听属性：
	• watch：
		<body>
		    <div id="computed_props">
		        千米：<input type="text" v-model="kilometers">
		        米：<input type="text" v-model="meters">
		    </div>
		    <p id="info"></p>
		    <script type="text/javascript">
		        var vm = new Vue({
		            el: '#computed_props',
		            data: {
		                kilometers: 0,
		                meters: 0
		            },
		            methods: {},
		            computed: {},
		            watch: {
		                kilometers: function(val) {
		                    this.kilometers = val;
		                    this.meters = this.kilometers * 1000
		                },
		                meters: function(val) {
		                    this.kilometers = val / 1000;
		                    this.meters = val;
		                }
		            }
		        });
		        vm.$watch('kilometers', function(newValue, oldValue) {
		            document.getElementById("info").innerHTML = "修改前值为: " + oldValue + "，修改后值为: " + newValue;
		        })
		    </script>
		</body>
		
#### Vue.js 样式绑定：
