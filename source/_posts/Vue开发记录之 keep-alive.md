---
title: Vue开发记录之 keep-alive
---

背景：项目为在线教育平台，分为直播、视频、课程和活动等模块。tabbar分为“首页”、“播放记录”、“我的”三部分。使用Vue框架和Mint-UI。

组件结构为：

	-App
		-Layout
			-Index
			-History
			-Me

在使用Vue开发项目的过程中，因经验不足，踩到了如下坑：*在History或者Me点击进入二级页面后，返回只能返回到Index，无法返回对应页面*。

经过搜索，在App.vue中直接用keep-alive将router-view包裹，结果可以正常返回。

但是这样又导致了新的问题：*所有组件都会缓存，那么，详情页也不会刷新*。比如，先点击进入id=1的课程，那么再进入id=2的课程，页面不会刷新，依然显示为id=1的课程内容。

再次搜索后，得到解决方案：需要缓存的内容和不需要缓存的内容分别设置。如下：
	
	<div id="app">
    	<keep-alive>
      		<router-view v-if="$route.meta.keepAlive"></router-view>
   		</keep-alive>
   		 <router-view v-if="!$route.meta.keepAlive"></router-view>
  	</div>

同时，需要在路由中，添加keepAlive为true或false。

在官方文档中，对keep-alive的说明如下：

> <keep-alive> 包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们。和 <transition> 相似，<keep-alive> 是一个抽象组件：它自身不会渲染一个 DOM 元素，也不会出现在父组件链中。

> 当组件在 <keep-alive> 内被切换，它的 activated 和 deactivated 这两个生命周期钩子函数将会被对应执行。

同时，keep-alive也有两个属性：include和exclude，分别表示匹配到的组件会缓存和不会缓存。这样的话，也就可以直接在keep-alive中声明是否需要缓存，而不必在路由中声明了（Vue版本不低于2.1.0）。如：

>	<!-- 逗号分隔字符串 -->
	<keep-alive include="a,b">
  		<component :is="view"></component>
	</keep-alive>

上述两个解决方案都可以解决问题，但第二个显然更简洁。