---
title: CSS布局
date: 2018-03-23 22:01:18
tags:
---

<h1>CSS左右布局</h1>
给子元素加float:left;给父元素的class加上clearfix。
但是要给父元素清除高度塌陷
代码如下：
.clearfix:befor,
.clearfix:after{
    content:'';
    display:block;
}
.clearfix{
    clear:both;
}
<h1>CSS左中右布局</h1>
float+absolute方式：
    &lt;style type="text/css"&gt;
        #content{
            position: relative;
            width:100%;
            height:300px;
        }
        .left{
            float: left;
            width: 200px;
            height:100%;
            background-color: #00a0dc;
        }
        .middle{
            position: absolute;
            top:0;
            bottom:0;
            left:200px;
            right: 300px;
            background-color: red;
        }
        .right{
            float: right;
            height:100%;
            width: 300px;
            background-color: #00a0dc;
        }
    &lt;/style&gt;

float+margin方式：
 &lt;style type="text/css"&gt;
        #content{
            height:300px;
        }
        .left{
            width: 200px;
            height:100%;
            float: left;
            background-color: #00a0dc;
        }
        .middle{
            height:100%;
            margin-left:200px;
            margin-right: 300px;
            background-color: red;
        }
        .right{
            height:100%;
            width: 300px;
            float: right;
            background-color: #00a0dc;
        }
    &lt;/style&gt;
HTML代码：
&lt;div id="content"&gt;
    &lt;div class="left"&gt;&lt;/div&gt;
    &lt;div class="middle"&gt;&lt;/div&gt;
    &lt;div class="right"&gt;&lt;/div&gt;
&lt;/div&gt;
<h1>水平居中</h1>
margin和width实现水平居中：
在分页容器上定义一个宽度，然后配合margin的左右值为“auto”实现效果：
.pagination {
  width: 293px;
  margin-left: auto;
  margin-right: auto;
}
.pagination li {
  line-height: 25px;
display: inline;
  float: left;
  margin: 0 5px;
inline-block实现水平居中：
要在元素的父容器中设置text-align的属性为“center“：
.pagination {
  text-align: center;
  font-size: 0;
  letter-spacing: -4px;
  word-spacing: -4px;
}
.pagination li {
  line-height: 25px;
  margin: 0 5px;
display: inline-block;
  *display: inline;
  zoom:1;
  letter-spacing: normal;  
  word-spacing: normal;
  font-size: 12px;
}
<h1>CSS垂直居中</h1>
方法1：使用了一个 position:absolute，有固定宽度和高度的 div。这个 div 被设置为 top:0; bottom:0;。但是因为它有固定高度，其实并不能和上下都间距为 0，因此 margin:auto; 会使它居中。使用 margin:auto;使块级元素垂直居中是很简单的。

&lt;div id="content"&gt; Content here&lt;/div&gt;  
#content {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    height: 240px;
    width: 70%;
}
方法2：只能将单行文本置中。只需要简单地把 line-height 设置为那个对象的 height 值就可以使文本居中了。

&lt;div id="content"&gt; Content here&lt;/div&gt;  
#content {
    height: 100px;
    line-height: 100px;
}