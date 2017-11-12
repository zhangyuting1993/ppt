title: flex全方位解读
speaker: 张宇亭
url: https://github.com/zhangyuting1993/flapyy-bird
transition: slide3
files:
theme: moon
usemathjax: yes



[slide]
[magic data-transition="newspaper"]
#flex全方位解读
[/magic]




[slide  data-transition="vertical3d"]
[magic data-transition="move"]
### 传统布局
----
* 基于盒状模型
* 依赖 display属性 + position属性 + float属性。
* 未知情况不好判断:垂直居中

====
    ```css
    //已知高度
    .parent {
        position: relative;
    }

    .child {
        position: absolute;
        top: 50 %;
        height: 100 px;
        margin-top: -50px;
    }
    ```

    ```css
    //未知高度
    .parent {
        position: relative;
    }

    .child {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
    }
    ```
    https://codepen.io/zhangyuting1993/pen/BmRQop
====
### flex
----
* 更佳有效的布局方式
* 更好的控制项目的对齐和自由分配容器空间，即使它们的大小是未知的或动态的。

```css
.parent {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```
[/magic]


[slide data-transition="zoomin"]
### 基本概念
* flexbox 分为flex容器与flex项目
* 布局基于flex-flow

<img src="/img/1.png" height="200">



[slide data-transition="zoomin"]
[magic data-transition="move"]

### flex容器属性
* display
* flex-direction
* flex-wrap
* flex-flow
* justify-content
* align-items
* align-content



====
###display

```html
.flex-layout {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
}
```



====
###flex-direction
* 这是用来创建方轴，从而定义Flex项目在Flex容器中放置的方向。
* 单方向的布局概念。Flex项目主要排列方式要么是水平排列，要么是垂直列排列。

```html
flex-direction: row | row-reverse | column | column-reverse

.flex-v-direaction{
    -webkit-box-orient: vertical/horizontal;
    -webkit-flex-direction: column;
    flex-direction: column;
}
```
https://codepen.io/zhangyuting1993/pen/xPqVwv


====
###flex-wrap
* 默认情况之下，Flex项目都尽可能在一行显示。
* 你可以根据flex-wrap的属性值来改变，让Flex项目多行显示。
```html
flex-wrap: nowrap | wrap | wrap-reverse
.flex-wrap{
    -webkit-box-lines: single/multiple;
    -webkit-flex-wrap: wrap;
    flex-wrap: wrap;
}
```
https://codepen.io/zhangyuting1993/pen/WXjodM?editors=1100



====
###flex-flow
* 这是flex-direction和flex-wrap两个属性的缩写。两个属性决定了伸缩容器的主轴与侧轴。
* 默认值是row nowrap（中间用空格隔开）
```html
flex-flow: <‘flex-direction’> || <‘flex-wrap’>
```

====
###justify-content
* 用于在主轴上对齐伸缩项目。

```html
justify-content: flex-start | flex-end | center | space-between | space-around
.flex-pack-center {
    -webkit-box-pack: start/end/center/justify;
    -webkit-justify-content: center;
    justify-content: center;
}
```

<img src="/img/2.png" height="200">




====
###align-items
* 用于在侧轴上对齐伸缩项目。

```html
align-items: flex-start | flex-end | center | baseline | stretch

.flex-align-center {
    -webkit-box-align: start/end/center/baseline/stretch;
    -webkit-align-items: center;
    align-items: center;
}
```
https://codepen.io/zhangyuting1993/pen/MOmbLx

<img src="/img/3.png" height="200">





====
###align-content
* 调准伸缩行在伸缩容器里的对齐方式。

```html

align-content: flex-start | flex-end | center | space-between | space-around | stretch

.flex-align-content {
    -webkit-align-content: center;
    align-content: center;
}

```
https://codepen.io/zhangyuting1993/pen/MOmbLx

<img src="/img/4.png" height="200">

[/magic]



[slide data-transition="zoomin"]
[magic data-transition="move"]

### flex项目属性
* order
* flex-grow
* flex-shrink
* flex-basis
* flex
* align-self


====
###order
*  控制Flex项目的顺序源
```html
flex-order:1
order:1
```
https://codepen.io/zhangyuting1993/pen/POmWPR

====
### flex-grow
* 定义一个Flex项目的扩大比例

https://codepen.io/zhangyuting1993/pen/bYWgEx

====
### flex-shrink
* 定义一个Flex项目的缩小比例
https://codepen.io/zhangyuting1993/pen/POmWNR?editors=1100

### flex-basis
* 定义了Flex项目在分配Flex容器剩余空间之前的一个默认尺寸.
* 。如果设置为auto，额外空间会基于flex-grow值做分布。
https://codepen.io/zhangyuting1993/pen/KymaMY

### flex
* flex是flex-grow，flex-shrink和flex-basis三个属性的缩写
* flex-shrink和flex-basis可选
* 默认为 0 1 auto
* flex取值为none时，其相当于取值为0 0 auto。

```html
-webkit-box-flex: 1;
-webkit-flex: 1;
flex: 1;

```
https://codepen.io/zhangyuting1993/pen/LOyxxW

* flex: 0 auto,flex: initial与flex: 0 1 auto
* flex: none与flex: 0 0 auto
* 伸缩项目不会收缩至比其最小内容尺寸


### align-self

* align-self则用来在单独的伸缩项目上覆写默认的对齐方式。


```html

align-self: auto | flex-start | flex-end | center | baseline | stretch

-webkit-align-self: center;
align-self:center;

```
https://codepen.io/zhangyuting1993/pen/OOmWxo

[/magic]

[slide data-transition="zoomin"]
### 应用举例
https://codepen.io/zhangyuting1993/pen/eeWgMJ













