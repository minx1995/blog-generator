---
title: 请求和响应.md
date: 2018-03-19 19:47:43
tags:
---
<h2>请求的格式：</h2>

（1）请求方法URI协议/版本
请求的第一行是“方法URI协议/版本”例如：GET/sample.jsp HTTP/1.1
以上代码中“GET”代表请求方法，“/sample.jsp”表示URI，“HTTP/1.1代表协议和协议的版本。
（2）请求头(Request Header)
请求头包含许多有关的客户端环境和请求正文的有用信息。例如，请求头可以声明浏览器所用的语言，请求正文的长度等。例如：
Accept:image/gif.image/jpeg.*/*
Accept-Language:zh-cn
Connection:Keep-Alive
Host:localhost
User-Agent:Mozila/4.0(compatible:MSIE5.01:Windows NT5.0)
Accept-Encoding:gzip,deflate.
（3）请求正文
请求头和请求正文之间是一个空行，这个行非常重要，它表示请求头已经结束，接下来的是请求正文。请求正文中可以包含客户提交的查询字符串信息：
username=jinqiao&password=1234
在以上的例子的HTTP请求中，请求的正文只有一行内容。当然，在实际应用中，HTTP请求正文可以包含更多的内容。

用 Chrome 发请求

打开 Network
地址栏输入网址
在 Network 点击，查看 request，点击「view source」
点击「view source」
点击「view source」
点击「view source」
终于点了？可以看到请求的前三部分了
如果有请求的第四部分，那么在 FormData 或 Payload 里面可以看到
<h2>响应的格式：</h2>
1，状态行

由3部分组成，分别为：协议版本，状态码，状态码描述，之间由空格分隔

状态代码为3位数字，200~299的状态码表示成功，300~399的状态码指资源重定向，400~499的状态码指客户端请求出错，500~599的状态码指服务端出错（HTTP/1.1向协议中引入了信息性状态码，范围为100~199）
2，响应头部

与请求头部类似，为响应报文添加了一些附加信息
3，响应内容

用 Chrome 查看响应

打开 Network
输入网址
选中第一个响应
查看 Response Headers，点击「view source」，点击「view source」，点击「view source」
你会看到响应的前两部分
查看 Response 或者 Preview，你会看到响应的第 4 部分

<h2>curl命令</h2>

什么是curl命令？
curl是利用URL语法在命令行方式下工作的开源文件传输工具。它被广泛应用在Unix、多种Linux发行版中，并且有DOS和Win32、Win64下的移植版本。

curl www.baidu.com
获取到一个网页的document。 
curl www.baidu.com -i
除了获取到document外，还可以获取头信息。

curl www.baidu.com -I
仅仅获取头信息。 无document。

curl www.baidu.com -v
显示更为详细的信息， v 是 verbose 的缩写。

curl www.baidu.com/s?wd=d
这里实际上就是在模拟form表单，该表单使用的是get方法。