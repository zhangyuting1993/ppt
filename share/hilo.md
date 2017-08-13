title: 一款炫酷的游戏引擎HILO
speaker: 张宇亭
url: https://github.com/zhangyuting1993/flapyy-bird
transition: slide3
files:
theme: dark
usemathjax: yes



[slide]
[magic data-transition="newspaper"]
#HILO
====
##一个炫酷的游戏引擎
[/magic]




[slide  data-transition="vertical3d"]
[magic data-transition="horizontal3d"]
###简介
----
* 淘宝的一套HTML5跨终端互动游戏方案，开源。 {:&.zoomIn}
* 源码地址：https://github.com/hiloteam/Hilo
* 文档：http://hiloteam.github.io/Hilo/docs/api-zh/index.html
====
### 特点
----
* 极简内核： Hilo核心模块极精简，保留了2D游戏引擎最必要的模块，同时采用模块化管理。 {:&.fadeIn}
* 完善接入&扩展： Hilo 支持多种模块范式的包装版本，包括AMD，CMD，Standalone多种方式接入。
* 多种渲染方式：提供DOM，Canvas，Flash，WebGL等多种渲染方案，可以做到跨全端，高性能的要求。
* 完善的周边工具：提供动画编辑器 ，Yeoman脚手架及典型案例产出的辅助开发工具。
[/magic]





[slide data-transition="zoomin"]
[magic data-transition="newspaper"]
##极简内核
====
###核心模块包括
* 基础类工具
* 事件系统
* 渲染
* 可视对象
<div>
 <img src="/media/1-1.png" height="320">
</div>
[/magic]



[slide data-transition="circle"]
[magic data-transition="zoomout"]
##接入与扩展
====
###接入
* 使用@module来标记模块名称，@require标记模块依赖，编译时根据标记获取模块信息，编译生成不同模块范式定义的代码。

			```html
				 * @private
				 * @class FlashAdaptor
				 * @module hilo/flash/FlashAdaptor
				 * @requires hilo/core/Hilo
				 * @requires hilo/view/Text
				 * @requires hilo/view/Graphics
				 * @requires hilo/media/WebAudio
				 * @requires hilo/media/WebSound
				 * @requires hilo/view/Stage
				 * @requires hilo/flash/FlashRenderer
			 ```
    
* 提供AMD、CommonJS、CMD等多种模块范式。

====
## 扩展

* `Class.create `

	* 是Hilo里创建类的主要方法，如下

	 * Extends - 指定一个父类。
	 * Mixes - 指定混入对象。可以是一个Object或Array。
	 * Statics - 指定静态属性。
	 * constructor - 创建类的构造函数。

* `Class.mix(target, [mixinObject])`
   *  可以为target混入属性和方法。

====

###例如可视对象的基础类View
<div>
 <img src="/media/2.png" height="200">
</div>
利用创建类扩展类方法，扩展出可是对象的管理的Container类
<div>
 <img src="/media/3.png" height="200">
</div>
类似可扩展出舞台Stage、位图Bitmap、精灵动画Sprite等
[/magic]





[slide data-transition="circle"]
[magic data-transition="zoomout"]
##多种渲染方式
====
###游戏的核心流程
<div>
 <img src="/media/5.png" height="200">
</div>
====
###渲染方式
----
* DOM 、Canvas、 Flash或者WebGL 四种渲染的方式来实现render
* 这四种渲染方式是和View独立分开的
* View在更新自身属性时，无需考虑如何被绘制。
====
* View的分类
	* 普通类 （Bitmap，Container,Button，Sprite）
	* 文字类
	* 画图类 （Graphic 矢量图相关）

* 普通类在渲染层面主要处理图片展示问题
	* Dom中时设置background
	* Canvas中 利用drawImage
[/magic]


[slide data-transition="circle"]
[magic data-transition="zoomout"]
##扩展能力
====
###骨骼动画
* 使用一套资源完成各种动作变化，优于精灵动画
* hilo中支持免费的成熟产品DragonBones

====
* 骨骼动画将可视对象进行分解，得到一个个可视组件。
* 这些一个个可视组件本身就是一个个View.
* 调整相应的时间片内调整这些View的transform属性，把他们组合起来就是一套完整的动作。

<div>
 <img src="/media/6.png" height="320">
</div>
[demo](http://hiloteam.github.io/Hilo/src/extensions/dragonbones/demo/index.html)

====
加载
<!-- <div>
 <img src="/media/7.png" height="200">
</div> -->
```html
<script src='../../../../build/standalone/hilo-standalone.min.js'></script>
<script src='../../../../build/dragonbones/dragonbones.min.js'></script>
<script src='./data/dragon/skeleton.js'></script>
<script src='./data/dragon/texture.js'></script>
```
====
dragonBones动画的载入
<div>
 <img src="/media/8.png" height="400">
</div>
* 创建工厂类型对象
* 解析外部数据，添加至工厂类对象中
* 设置动画中的贴图

* 提取骨架对象，提取骨架显示对象
* 显示对象添加至舞台之中

* 获取第一个动画进行播放
* 在点击之后依次播放下面的动画

`git subtree push --prefix=dist origin gh-pages`
[/magic]







