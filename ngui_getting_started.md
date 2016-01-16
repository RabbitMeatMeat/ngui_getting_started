#读NGUI 2.7.0源码

##前言

	
一不小心就走到了unity前端开发的路上，这一年来可以说一事无成，工作半年也心思不宁，心太高，想得多，做得少。最近有好好调整心态，既然已经在做unity前端开发，就要做好，所以准备从ngui的源码出发，学习一下c#的工程。**ngui现在已经是3.x版本，并且和2.x版本相差很大**

##从简单到地方说起


###关于相机
	
* 从3D物体到2D屏幕有两种投影模式：透视(perspective)和正交(orthographic)投影 
* 每个相机都有Near Plane和Far Plane两个平面
* 相机以上述其中一种模式将Near和Far两个平面内的物体投影到屏幕上
* 一般UI都是采用orthographic，场景等一般采用perspective

###关于事件
* 

##目录结构
* 	

##UICamera
	
UICamera负责事件的监听和分发。

###监听的事件包括：

* OnHover(isOver) 
* OnPress(isDown) 
* OnSelect(selected) 
* OnClick() 
* OnDoubleClock() 
* OnDray(delta) 
* OnDrop(gameObject) 
* OnInput(text) 
* OnTooltip(show) 
* OnScroll(delta) 
* OnKey(key) 

###如何监听事件：

	UICamera类有一个静态数组mlist[]存下所有UICamera的实例并按深度从小到大排序，
	Raycast() 通过按深度遍历UICamera，获取当前mousePosition位置下的gameObject
	然后判断是哪些事件发生，通过gameObject.SendMessage()发送出去
	

