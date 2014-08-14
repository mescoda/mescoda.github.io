---
layout: post
status: publish
published: true
title: CSS3 Animation 操作总结
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
excerpt: "在腾讯实习的时候除了做产品妹子们提来的需求，还搞了个电商前端实验室的概念版出来，实体在内网运行，这里是 <a href=\"http://mescoda.com/demo/ecdlab/\">demo</a>。\r\n\r\n这是一个用于展示电商用户体验设计部前端自研工具的实验室，不考虑低级浏览器（为了更好的体验做成了
  webkit only ，虽然我是 Firefox 控），是个 CSS3 Animation 密集型项目。\r\n\r\n在 Animation 的处理上我采用的是添加
  className 的方法，方便复用且不污染 html，每个动画效果都可以分为三个基本的步骤，用三种 className 来控制：\r\n\r\n<ol>\r\n<li>动画开始前的状态
  className</li>\r\n<li>动画过程中的过程 className</li>\r\n<li>动画结束后的状态 className</li>\r\n</ol>\r\n\r\n区别市面上大多的只用
  Animation 做渐进增强（类似呼吸 button 效果）的项目，这里需要状态 class，一来帮助处理动画前后元素的样式变化，二来也为可能存在的连续多个
  Animation 提供方便。\r\n\r\n一个栗子：list-item 的方形旋转为圆形的步骤为\r\n\r\n<ol>\r\n<li>动画开始前的状态 className：square-list-item</li>\r\n<li>动画过程中的过程
  className：squareRotate</li>\r\n<li>动画结束后的状态 className：circle-list-item</li>\r\n</ol>\r\n\r\n顺便说下我的
  className 命名规则：\r\n连字符表示且仅表示层级关系；同级 className 赋予前缀表示模块；Animation 的过程 className 因为只通过
  JS 赋予且只是中间量不长期存在 html 中，所以驼峰化。\r\n\r\n"
wordpress_id: 609
wordpress_url: http://mescoda.com/?p=609
date: '2012-10-30 23:36:40 +0800'
date_gmt: '2012-10-30 15:36:40 +0800'
categories:
- "稀烂的技术"
tags:
- CSS3
comments: []
---
<p>在腾讯实习的时候除了做产品妹子们提来的需求，还搞了个电商前端实验室的概念版出来，实体在内网运行，这里是 <a href="http://mescoda.com/demo/ecdlab/">demo</a>。</p>
<p>这是一个用于展示电商用户体验设计部前端自研工具的实验室，不考虑低级浏览器（为了更好的体验做成了 webkit only ，虽然我是 Firefox 控），是个 CSS3 Animation 密集型项目。</p>
<p>在 Animation 的处理上我采用的是添加 className 的方法，方便复用且不污染 html，每个动画效果都可以分为三个基本的步骤，用三种 className 来控制：</p>
<ol>
<li>动画开始前的状态 className</li>
<li>动画过程中的过程 className</li>
<li>动画结束后的状态 className</li>
</ol>
<p>区别市面上大多的只用 Animation 做渐进增强（类似呼吸 button 效果）的项目，这里需要状态 class，一来帮助处理动画前后元素的样式变化，二来也为可能存在的连续多个 Animation 提供方便。</p>
<p>一个栗子：list-item 的方形旋转为圆形的步骤为</p>
<ol>
<li>动画开始前的状态 className：square-list-item</li>
<li>动画过程中的过程 className：squareRotate</li>
<li>动画结束后的状态 className：circle-list-item</li>
</ol>
<p>顺便说下我的 className 命名规则：<br />
连字符表示且仅表示层级关系；同级 className 赋予前缀表示模块；Animation 的过程 className 因为只通过 JS 赋予且只是中间量不长期存在 html 中，所以驼峰化。</p>
<p><a id="more"></a><a id="more-609"></a></p>
<p>具体对 Animation 的控制为触发事件后移除最初的状态 class，添加过程 class，动画执行完毕后移除过程 class，添加结束后的状态 class。</p>
<p>最初遇到的问题是，Animation 是异步的，所以如果有连续多个动画过程（例如 list-item 旋转结束后 list-item-detail-circle 才能呈现）就需要时间上的控制。</p>
<p>最初想到的是用 CSS3 原生的 animation-delay 属性，但一旦改动最初的动画时间就需要到 css 里修改之后所有的 delay，而且不利于独立每个效果帮助复用。</p>
<p>之后用 setTimeout ，相当于把 delay 时间提出到 JS 中控制，简单的搞下还行，写多了就越来越奇怪，除了不优雅外，依旧存在修改时间的问题，但是当时急着完成就先写了个函数简单处理了下然后上线了。</p>
<p>离职之后才发现 animationend 和 transitionend 事件，可以在 animation 和 transition 结束后绑定其他事件，解决了修改时间的问题。</p>
<p>浏览器事件名称差异的解决：</p>
<pre><code>
var VENDORS = ["Moz",'webkit','ms','O'];
var TRANSITION_END_NAMES = {
	"Moz" : "transitionend"
	,"webkit" : "webkitTransitionEnd"
	,"ms" : "MSTransitionEnd"
	,"O" : "oTransitionEnd"
}
var ANIMATION_END_NAMES = {
	"Moz" : "animationend"
	,"webkit" : "webkitAnimationEnd"
	,"ms" : "MSAnimationEnd"
	,"O" : "oAnimationEnd"
}
var css3Prefix,TRANSITION_END_NAME,ANIMATION_END_NAME;
var mTestElement = document.createElement("div");

for (var i = 0,l = VENDORS.length; i < l; i++) {
	css3Prefix = VENDORS[i];
	if ((css3Prefix + "Transition") in mTestElement.style) {
		break;
	}
	css3Prefix = false;
}

if(css3Prefix) {
	TRANSITION_END_NAME = TRANSITION_END_NAMES[css3Prefix];
	ANIMATION_END_NAME = ANIMATION_END_NAMES[css3Prefix];
}
</code></pre>
<p>animationend 之后，还有回调嵌套的问题。</p>
<p>多个 Animation 的连续很容易把代码写成这种糟糕的样子，</p>
<pre><code>
elemA.addEventListener(ANIMATION_END_NAME,function() {
	elemA.doSth();
	elemB.addEventListener(ANIMATION_END_NAME,function() {
		elemB.doSth();
		elemC.addEventListener(ANIMATION_END_NAME,function() {
			elemC.doSth();
		})
	})
})
</code></pre>
<p>我写了个 MesAnimateEffect 类 ，用来设定动画效果。对于连续的动画，可以用 runAnimateList 来保证一个接一个的触发，细节上有 node 的影子。</p>
<pre><code>
function EventEmitter() {
	this.events = {};
}
EventEmitter.prototype.on = function(eventName,callback) {
	if(this.events[eventName] instanceof Array) {
		// pass
	} else {
		this.events[eventName] = [];
	}
	this.events[eventName].push(callback);
}
EventEmitter.prototype.emit = function(eventName) {
	if(this.events[eventName] instanceof Array) {
		var callbacks = this.events[eventName];
		for(var i = 0,l = callbacks.length;i < l;i++) {
			callbacks[i]();
		}
	}
}

function MesAnimateEffect(elem,classList,stopP) {
	EventEmitter.call(this);
	this.elem = elem;
	if(classList instanceof Array) {
		this.prev = classList[0];
		this.process = classList[1];
		this.next = classList[2];
	} else {
		this.prev = classList.prev.join(" ");
		this.process = classList.process.join(" ");
		this.next = classList.next.join(" ");
	}
	
	this.stopP = stopP || false;	
}
MesAnimateEffect.prototype = new EventEmitter();
MesAnimateEffect.prototype.start = function() {
	var self = this;
	(this.elem).removeClass(this.prev).addClass(this.process);
	(this.elem).unbind(ANIMATION_END_NAME).bind(ANIMATION_END_NAME,function() {
		(self.elem).removeClass(self.process).addClass(self.next);
		self.emit("end");
	})
	return this;
}

function runAnimateList() {
	var animateList = arguments;
	var length = animateList.length;
	for(var i = 0;i < length;i++) {
		if(animateList[i+1]) {
			animateList[i].on("end",(function(num) {
				return function() {
					if(typeof animateList[num+1] == "function") {
						animateList[num+1]();
					} else {
						animateList[num+1].start();
					}
				}
			})(i))
		}
	}
	animateList[0].start();
}

</code></pre>
<p>现在处理这种连续 Animation 只需要先设定具体的效果，然后用按顺序添加为 runAnimateList 的参数，有了把回调嵌套拉平的感觉。</p>
<p>一个栗子，list-item 的完整旋转显示内容过程</p>
<pre><code>
var forwardEffect = new MesAnimateEffect($this,["square-list-item",forwardClassName,"circle-list-item"]);

var innerShowEffect = new MesAnimateEffect($this.find(".list-item-detail-circle"),["","detailCircleShow",""],true);

runAnimateList(forwardEffect,innerShowEffect,function() {
	if($this.hasClass("circle-list-item")) {
		$this.find(".list-item-detail").removeClass("hide-list-item-detail").addClass("show-list-item-detail");
	}
});
</code></pre>
<p>写完之后发给基友，被指责了临时写 list 还是麻烦。。 orz<br />
等过段时间再监视一遍</p>
