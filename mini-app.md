#### 事件分类：
	• 冒泡事件：当一个组件上的事件被触发后，该事件会向父节点传递。
		- touchstart：手指触摸动作开始	
		- touchmove：手指触摸后移动	
		- touchcancel：手指触摸动作被打断，如来电提醒，弹窗	
		- touchend：手指触摸动作结束	
		- tap：手指触摸后马上离开	
		- longpress：手指触摸后，超过350ms再离开，指定了事件回调函数并触发了这个事件，tap事件将不被触发
		- longtap：手指触摸后，超过350ms再离开（推荐使用longpress事件代替）	
		- transitionend：会在 WXSS transition 或 wx.createAnimation 动画结束后触发	
		- animationstart：会在一个 WXSS animation 动画开始时触发	
		- animationiteration：会在一个 WXSS animation 一次迭代结束时触发	
		- animationend：会在一个 WXSS animation 动画完成时触发	
		- touchforcechange：在支持 3D Touch 的 iPhone 设备，重按时会触发	1.9.90
		
	• 非冒泡事件：当一个组件上的事件被触发后，该事件不会向父节点传递
	
	bind事件绑定不会阻止冒泡事件向上冒泡，catch事件绑定可以阻止冒泡事件向上冒泡。

#### 浏览器事件模型中捕获阶段、目标阶段、冒泡阶段实例详解：
	• 捕获阶段：事件从根节点流向目标节点，途中流经各个DOM节点，在各个节点上触发捕获事件，直到达到目标节点，捕获阶段的主要任务是建立传播路经，在冒泡阶段根据这个路经回溯到文档根节点。
	
	• 目标阶段：事件到达目标节点时，就到了目标阶段，事件在目标节点上被触发
	
	• 冒泡阶段：事件在目标节点上触发后，不会终止，一层层向上冒，回溯到根节点。
