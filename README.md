# Awesome HTTP [![jaywcjlove/sb](https://jaywcjlove.github.io/sb/ico/awesome.svg)](https://github.com/semlinker/awesome-http)

## 目录

* [B/S 结构定义](#bs-结构定义)
* [URI (统一资源标志符)](#uri-统一资源标志符)
* [MIME](#mime)
* [HTTP 协议](#http-协议)
* [HTTP 请求报文](#http-请求报文)
* [HTTP 响应报文](#http-响应报文)
* [HTTP Methods](#http-methods)
* [HTTP Status Code](#http-status-code)
* [HTTP Cookie & Session](#http-cookie--session)
* [HTTP Cache (缓存)](#http-cache缓存)
* [HTTP CORS (跨域资源共享)](#http-cors-跨域资源共享)
* [HTTPS](#https)
* [HTTP/2](#http2)
* [HTTP 安全](#http-安全)
* [HTTP 面试](#http-面试)
* [HTTP 爬虫](#http-爬虫)
* [HTTP 资源](#http-资源)
* [HTTP 抓包工具及教程](#http-抓包工具及教程)
* [Chrome HTTP 插件](#chrome-http-插件)
* [HTTP 平台资源库](#http-平台资源库)
* [HTTP 压力测试](#http-压力测试)
* [HTTP 代理服务器](#http-代理服务器)
* [HTTP 图书](#http-图书)
* [参考资源](#参考资源)

## B/S 结构定义

> **浏览器-服务器（Browser/Server）结构**，简称[B/S结构](https://zh.wikipedia.org/wiki/B/S%E7%BB%93%E6%9E%84)，与[C/S结构](https://zh.wikipedia.org/wiki/C/S%E7%BB%93%E6%9E%84)不同，其客户端不需要安装专门的[软件](https://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6)，只需要[浏览器](https://zh.wikipedia.org/wiki/%E6%B5%8F%E8%A7%88%E5%99%A8)即可，浏览器通过[Web](https://zh.wikipedia.org/wiki/Web)[服务器](https://zh.wikipedia.org/wiki/%E6%9C%8D%E5%8A%A1%E5%99%A8)与[数据库](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E5%BA%93)进行交互，可以方便的在不同平台下工作；服务器端可采用高性能[计算机](https://zh.wikipedia.org/wiki/%E8%AE%A1%E7%AE%97%E6%9C%BA)，并安装[Oracle](https://zh.wikipedia.org/wiki/Oracle)、[Sybase](https://zh.wikipedia.org/wiki/Sybase)、[Informix](https://zh.wikipedia.org/w/index.php?title=Informix&action=edit&redlink=1)等大型数据库。B/S结构简化了客户端的工作，它是随着[Internet](https://zh.wikipedia.org/wiki/Internet)技术兴起而产生的，对C/S技术的改进，但该结构下服务器端的工作较重，对服务器的性能要求更高。—— 维基百科

![B/S结构](./images/http-resource-1.png)

(图片资源来源于网络)

## URI (统一资源标志符)

> 在[电脑](https://zh.wikipedia.org/wiki/%E9%9B%BB%E8%85%A6)术语中，**统一资源标识符**（英语：Uniform Resource Identifier，或**URI**)是一个用于[标识](https://zh.wikipedia.org/wiki/%E6%A0%87%E8%AF%86)某一[互联网](https://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%94%E7%BD%91)[资源](https://zh.wikipedia.org/wiki/%E8%B5%84%E6%BA%90)名称的[字符串](https://zh.wikipedia.org/wiki/%E5%AD%97%E7%AC%A6%E4%B8%B2)。 该种标识允许用户对网络中（一般指[万维网](https://zh.wikipedia.org/wiki/%E4%B8%87%E7%BB%B4%E7%BD%91)）的资源通过特定的[协议](https://zh.wikipedia.org/wiki/%E5%8D%8F%E8%AE%AE)进行交互操作。URI的最常见的形式是[统一资源定位符](https://zh.wikipedia.org/wiki/%E7%BB%9F%E4%B8%80%E8%B5%84%E6%BA%90%E5%AE%9A%E4%BD%8D%E7%AC%A6)（URL），经常指定为非正式的网址。更罕见的用法是[统一资源名称](https://zh.wikipedia.org/wiki/%E7%BB%9F%E4%B8%80%E8%B5%84%E6%BA%90%E5%90%8D%E7%A7%B0)（URN），其目的是通过提供一种途径。用于在特定的[命名空间](https://zh.wikipedia.org/wiki/%E5%91%BD%E5%90%8D%E7%A9%BA%E9%97%B4)资源的标识，以补充网址。—— 维基百科

### URI 文法

> URI文法由[URI协议](https://zh.wikipedia.org/w/index.php?title=URI%E5%8D%8F%E8%AE%AE&action=edit&redlink=1)名（例如“[`http`](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)”，“[`ftp`](https://zh.wikipedia.org/wiki/%E6%96%87%E4%BB%B6%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)”，“[`mailto`](https://zh.wikipedia.org/wiki/%E7%94%B5%E5%AD%90%E9%82%AE%E4%BB%B6)”或“`file`”），一个[冒号](https://zh.wikipedia.org/wiki/%E5%86%92%E5%8F%B7)，和协议对应的内容所构成。特定的协议定义了协议内容的语法和[语义](https://zh.wikipedia.org/wiki/%E8%AF%AD%E4%B9%89)，而所有的协议都必须遵循一定的URI文法通用规则，亦即为某些专门目的保留部分特殊字符。—— 维基百科

下面展示了 URI 例子及它们的组成部分：

```shell
                       权限                 路径
        ┌───────────────┴───────────────┐┌───┴────┐
  abc://username:password@example.com:123/path/data?key=value&key2=value2#fragid1
  └┬┘   └───────┬───────┘ └────┬────┘ └┬┘           └─────────┬─────────┘ └──┬──┘
  协议        用户信息         主机名    端口                  查询参数          片段
```

## MIME

> MIME(Multipurpose Internet Mail Extensions)多用途互联网邮件扩展类型。是设定某种[扩展名](http://baike.baidu.com/item/%E6%89%A9%E5%B1%95%E5%90%8D)的[文件](http://baike.baidu.com/item/%E6%96%87%E4%BB%B6)用一种[应用程序](http://baike.baidu.com/item/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F)来打开的方式类型，当该扩展名文件被访问的时候，[浏览器](http://baike.baidu.com/item/%E6%B5%8F%E8%A7%88%E5%99%A8)会自动使用指定应用程序来打开。多用于指定一些[客户端](http://baike.baidu.com/item/%E5%AE%A2%E6%88%B7%E7%AB%AF)[自定义](http://baike.baidu.com/item/%E8%87%AA%E5%AE%9A%E4%B9%89)的[文件名](http://baike.baidu.com/item/%E6%96%87%E4%BB%B6%E5%90%8D)，以及一些媒体文件打开方式。 —— 百度百科

### 文件格式

每个 MIME 类型由两部分组成，前面是数据的大类别，例如声音audio、图象image等，后面定义具体的种类。

常见的 MIME 类型有：

| 资源名称      | 后缀    | 类型              |
| --------- | ----- | --------------- |
| 超文本标记语言文本 | .html | text/html       |
| xml文档     | .xml  | text/xml        |
| 普通文本      | .txt  | text/plain      |
| PNG图像     | .png  | image/png       |
| PDF文档     | .pdf  | application/pdf |

了解更多的 MIME 类型 - [互联网媒体类型](https://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%94%E7%BD%91%E5%AA%92%E4%BD%93%E7%B1%BB%E5%9E%8B)

## HTTP 协议

> **超文本传输协议**（[英文](https://zh.wikipedia.org/wiki/%E8%8B%B1%E6%96%87)：**HyperText Transfer Protocol**，[缩写](https://zh.wikipedia.org/wiki/%E7%B8%AE%E5%AF%AB)：**HTTP**）是[互联网](https://zh.wikipedia.org/wiki/%E7%B6%B2%E9%9A%9B%E7%B6%B2%E8%B7%AF)上应用最为广泛的一种[网络协议](https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C%E5%8D%8F%E8%AE%AE)。设计HTTP最初的目的是为了提供一种发布和接收[HTML](https://zh.wikipedia.org/wiki/HTML)页面的方法。通过HTTP或者HTTPS协议请求的资源由[统一资源标识符](https://zh.wikipedia.org/wiki/%E7%B5%B1%E4%B8%80%E8%B3%87%E6%BA%90%E6%A8%99%E8%AD%98%E7%AC%A6)（Uniform Resource Identifiers，URI）来标识。—— 维基百科

HTTP 协议是基于请求与相应，具体如下图所示：

![http-protocol](./images/http-resource-2.png)

(图片资源来源于网络)

### HTTP 协议主要特点

- 简单快速：当客户端向服务器端发送请求时，只是简单的填写请求路径和请求方法即可，然后就可以通过浏览器或其他方式将该请求发送就行了
- 灵活：HTTP 协议允许客户端和服务器端传输任意类型任意格式的数据对象
- 无连接：无连接的含义是限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接，采用这种方式可以节省传输时间。(当今多数服务器支持Keep-Alive功能，使用服务器支持长连接，解决无连接的问题)
- 无状态：无状态是指协议对于事务处理没有记忆能力，服务器不知道客户端是什么状态。即客户端发送HTTP请求后，服务器根据请求，会给我们发送数据，发送完后，不会记录信息。(使用 cookie 机制可以保持 session，解决无状态的问题)

## HTTP 请求报文

HTTP 请求报文由**请求行**、**请求头**、**空行** 和 **请求体(请求数据)** 4 个部分组成，如下图所示：

![request-message](./images/http-resource-3.png)

(图片资源来源于网络)

### 请求报文示例

```
GET / HTTP/1.1
Host: www.baidu.com
Connection: keep-alive
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/57.0.2987.110 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: zh-CN,zh;q=0.8,en;q=0.6,id;q=0.4
Cookie: PSTM=1490844191; BIDUPSID=2145FF54639208435F60E1E165379255; BAIDUID=CFA344942EE2E0EE081D8B13B5C847F9:FG=1;
```

### 请求行

请求行由请求方法、URL 和 HTTP 协议版本组成，它们之间用空格分开。

```shell
GET / HTTP/1.1
```

### 请求头

请求头由 `key-value` 对组成，每行一对，key (键) 和 value (值)用英文冒号 `:` 分隔。请求头通知服务器有关于客户端请求的信息，典型的请求头有：

- User-Agent：用户代理信息 - Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_3) AppleWebKit/537.36 ...
- Accept：客户端可识别的内容类型列表 - text/html,application/xhtml+xml,application/xml
- Accept-Language：客户端可接受的自然语言 -  zh-CN,zh;q=0.8,en;q=0.6,id;q=0.4
- Accept-Encoding：客户端可接受的编码压缩格式 - gzip, deflate, sdch, br
- Host：请求的主机名，允许多个域名同处一个IP地址，即虚拟主机 - `www.baidu.com`
- connection：连接方式 
  - close：告诉WEB服务器或代理服务器，在完成本次请求的响应后，断开连接
  - keep-alive：告诉WEB服务器或代理服务器。在完成本次请求的响应后，保持连接，以等待后续请求
- Cookie：存储于客户端扩展字段，向同一域名的服务端发送属于该域的cookie - PSTM=1490844191; BIDUPSID=2145FF54639208435F60E1E165379255;

### 空行

最后一个请求头之后是一个空行，发送回车符和换行符，通知服务器以下不再有请求头。

### 请求体

请求数据不在 GET 方法中使用，而是在 POST 方法中使用。与请求数据相关的最常使用的请求头是 Content-Type和 Content-Length。

## HTTP 响应报文

HTTP响应报文由**状态行、响应头、空行和响应体**4 个部分组成，如下图所示：

![response-message](./images/http-resource-4.png)

(图片资源来源于网络)

### 响应报文示例

```
HTTP/1.1 200 OK
Server: bfe/1.0.8.18
Date: Thu, 30 Mar 2017 12:28:00 GMT
Content-Type: text/html; charset=utf-8
Connection: keep-alive
Cache-Control: private
Expires: Thu, 30 Mar 2017 12:27:43 GMT
Set-Cookie: BDSVRTM=0; path=/
```

### 状态行

状态行格式： HTTP-Version Status-Code Reason-Phrase CRLF

- HTTP-Version - HTTP 协议版本
- Status-Code - 状态码
- Reason-Phrase - 状态码描述
- CRLF - 回车/换行符

### 响应头

响应头由 `key-value` 对组成，每行一对，key (键) 和 value (值)用英文冒号 `:` 分隔。响应头域允许服务器传递不能放在状态行的附加信息，这些域主要描述服务器的信息和Request-URI进一步的信息，典型的响应头有：

- Server：包含处理请求的原始服务器的软件信息
- Date：服务器日期
- Content-Type：返回的资源类型 (MIME)
- Connection：连接方式
  - close：连接已经关闭
  - keep-alive：连接已保持，在等待本次连接的后续请求
- Cache-Control：缓存控制
- Expires：设置过期时间
- Set-Cookie：设置 Cookie 信息

### 空行

最后一个响应头之后是一个空行，发送回车符和换行符，通知浏览器以下不再有响应头。

### 响应体

服务器返回给浏览器的响应信息，下面是百度首页的响应体片段：

```html
<!DOCTYPE html>
<!--STATUS OK-->
<html>
<head>
    <meta http-equiv="content-type" content="text/html;charset=utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    <link rel="icon" sizes="any" mask href="//www.baidu.com/img/baidu.svg">
    <title>百度一下，你就知道</title>
</head>
<body>
  ...
</body>
</html>
```

## HTTP Methods

HTTP 协议的请求方法有：GET、POST、HEAD、PUT、DELETE、OPTIONS、TRACE、CONNECT、PATCH、HEAD

HTTP 常用的请求方法：

- GET - 获取资源，使用 URL 方式传递参数，大小为 2KB
  - `http://www.example.com/users` - 获取所有用户
- POST - 传输资源，HTTP Body, 大小默认8M
  - `http://www.example.com/users/a-unique-id ` - 新增用户
- PUT - 资源更新
  - `http://www.example.com/users/a-unique-id` - 更新用户
- DELETE - 删除资源
  - `http://www.example.com/users/a-unique-id` - 删除用户

## HTTP Status Code

状态代码由三位数字组成，第一个数字定义了响应的类别，且有五种可能取值：

- 1xx：指示信息 – 表示请求已接收，继续处理
- 2xx：成功 – 表示请求已被成功接收
- 3xx：重定向 – 要完成请求必须进行更进一步的操作
- 4xx：客户端错误 – 请求有语法错误或请求无法实现
- 5xx：服务器错误 – 服务器未能实现合法的请求

常见状态代码、状态描述的说明如下：

- 200 OK：客户端请求成功
- 204 No Content：没有新文档，浏览器应该继续显示原来的文档
- 206 Partial Content：客户发送了一个带有Range头的GET请求，服务器完成了它
- 301 Moved Permanently：所请求的页面已经转移至新的url
- 302 Found：所请求的页面已经临时转移至新的url
- 304 Not Modified：客户端有缓冲的文档并发出了一个条件性的请求，服务器告诉客户，原来缓冲的文档还可以继续使用。
- 400 Bad Request：客户端请求有语法错误，不能被服务器所理解
- 401 Unauthorized：请求未经授权，这个状态代码必须和WWW-Authenticate报头域一起使用
- 403 Forbidden：对被请求页面的访问被禁止
- 404 Not Found：请求资源不存在
- 500 Internal Server Error：服务器发生不可预期的错误
- 503 Server Unavailable：请求未完成，服务器临时过载或当机，一段时间后可能恢复正常

## HTTP Cookie & Session

- [简书 - 全面解读 HTTP Cookie](http://www.jianshu.com/p/1e28fe8125dc)
- [简书 - Cookie 机制](http://www.jianshu.com/p/a6d9a7f06955)
- [阮一峰 - JavaScript 标准参考教程 - Cookie](http://javascript.ruanyifeng.com/bom/cookie.html#toc1)
- [segmentfault - 聊一聊 Cookie](https://segmentfault.com/a/1190000004556040)
- [知乎 - COOKIE和SESSION有什么区别？](https://www.zhihu.com/question/19786827)

## HTTP Cache(缓存)

- [alloyteam - Web 缓存机制系列](http://www.alloyteam.com/2012/03/web-cache-1-web-cache-overview/)


- [imweb前端社区 - HTTP 缓存控制小结](http://imweb.io/topic/5795dcb6fb312541492eda8c)


- [在前端性能优化中应用HTTP缓存的三部曲](http://insights.thoughtworkers.org/trilogy-of-apply-http-cache-to-front-end/)
- [彻底弄懂 Http 缓存机制 - 基于缓存策略三要素分解法](http://mp.weixin.qq.com/s/qOMO0LIdA47j3RjhbCWUEQ)
- [胡子大哈 - 掌握 HTTP 缓存——从请求到响应过程的一切（上）](http://huziketang.com/blog/posts/detail?postId=58b77935204d50674934c3ad)
- [胡子大哈 - 掌握 HTTP 缓存——从请求到响应过程的一切（下）](http://huziketang.com/blog/posts/detail?postId=58bd4dd1204d50674934c3b0)

## HTTP CORS (跨域资源共享)

- [MDN - 浏览器同源策略](https://developer.mozilla.org/zh-CN/docs/Web/Security/Same-origin_policy)


- [MDN - HTTP CORS](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS)
- [阮一峰 - 跨域资源共享 CORS 详解](http://www.ruanyifeng.com/blog/2016/04/cors.html)

## HTTPS

- [imweb前端社区 - HTTPS科普扫盲贴](http://imweb.io/topic/56d67baaca5e865230c1d4fa)
- [也许，这样理解HTTPS更容易](http://showme.codes/2017-02-20/understand-https/)
- [一篇文章为你深度解析HTTPS 协议](http://www.jianshu.com/p/abb8ea2e26ac)
- [阮一峰 - HTTPS 升级指南](http://www.ruanyifeng.com/blog/2016/08/migrate-from-http-to-https.html)
- [全站 HTTPS 来了](https://segmentfault.com/a/1190000004199917)
- [扒一扒HTTPS网站的内幕](https://segmentfault.com/a/1190000003801450)
- [又拍云 - HTTPS 原理详解](http://support.upyun.com/hc/kb/article/1031843/)
- [掘金 - 九个问题从入门到熟悉HTTPS](https://juejin.im/post/58c5268a61ff4b005d99652a)
- [理解HTTPS为什么安全前，先看看这些东西](http://mp.weixin.qq.com/s/7ImZolr7m3tUuyOgMJeFYg)
- [HTTPS为什么安全 &分析 HTTPS 连接建立全过程](http://www.jianshu.com/p/0d8575b132a8)
- [HTTPS 免费证书申请教程](https://juejin.im/entry/589d44dd61ff4b006b3896d0)
- [掘金 - 升级 Https 的那些事](https://juejin.im/entry/58aba456128fe1006a4f3393)
- [简书 - Android 使用 HTTPS](http://www.jianshu.com/p/9e944688fab9)
- [知乎专栏 - iOS开发中的HTTPS](https://zhuanlan.zhihu.com/p/22749689)
- [简书 - iOS开发HTTPS实现之信任SSL证书和自签名证书](http://www.jianshu.com/p/6b9c8bd5005a)

## HTTP/2

- [segmentfault - HTTP/2 新特性浅析](https://segmentfault.com/a/1190000002765886)
- [简书 - 未来已到——HTTP/2](http://www.jianshu.com/p/565a69f574a8)


- [掘金 - HTTP 2.0 的那些事](https://juejin.im/entry/57fa127d816dfa0056b7d710)
- [HTTP/2 发展历程](https://coyee.com/article/10917-journey-to-http-2)
- [掘金 - Web 开发者的 HTTP/2 性能优化指南](https://juejin.im/entry/56ce7d1a1532bc005372a7fa)
- [前端开发与 HTTP/2 的羁绊——安利篇](https://aotu.io/notes/2016/03/17/http2-char/?o2src=juejin&o2layout=compat)
- [简书 - 让你的网站升级到HTTP/2](http://www.jianshu.com/p/68ef142c7ee2)
- [简书 - HTTP/2 流量调试](http://www.jianshu.com/p/83551b91e9a2)
- [GitBook - http2 讲解](https://www.gitbook.com/book/ye11ow/http2-explained/details)

## HTTP 安全

- [Web 安全入门-书籍及建议](http://www.jianshu.com/p/6dcebd54fb24)
- [Github - 实用性开发人员安全须知](https://github.com/FallibleInc/security-guide-for-developers)


- [segmentfault - 阿里聚安全2016年报](https://segmentfault.com/a/1190000008629001)
- [segmentfault - web权限验证方法说明](https://segmentfault.com/a/1190000004086946)
- [HTTP的识别,认证与安全——《HTTP权威指南》系列](https://segmentfault.com/a/1190000006758679)
- [HTTP认证的底层技术简析与揭秘](http://www.freebuf.com/articles/web/129527.html)
- [SegmentFault 技术周刊 Vol.12 - Web 安全指南（上）](https://segmentfault.com/a/1190000007492381)
- [SegmentFault 技术周刊 Vol.13 - Web 安全指南（下）](https://segmentfault.com/a/1190000007564080)
- [简书 - Web前端攻防，一不小心就中招了](http://www.jianshu.com/p/15fece7e1a3e)
- [如何防范常见的Web攻击](http://blog.720ui.com/2016/security_web/)
- [简书 - Web安全之SQL注入攻击技巧与防范](http://www.jianshu.com/p/436917dfa8df)

## HTTP 面试

- [知乎 - 怎么回答面试官的题目：你是怎么理解 http？](https://www.zhihu.com/question/53226983)
- [segmentfault - 前端经典面试题: 从输入URL到页面加载发生了什么?](https://segmentfault.com/a/1190000006879700)
- [alloy - HTTP,HTTP2.0,SPDY,HTTPS你应该知道的一些事](http://www.alloyteam.com/2016/07/httphttp2-0spdyhttps-reading-this-is-enough/)
- [github.io - HTTP 协议 (笔试面试知识整理)](https://hit-alibaba.github.io/interview/basic/network/HTTP.html)  -  里面的东西很全面
- [掘金 - 面试 - 网络 HTTP](https://juejin.im/post/5872309261ff4b005c4580d4)
- [csdn - HTTP 必知必会 — 常见面试题总结](http://blog.csdn.net/zhangliangzi/article/details/51336564)
- [简书 -TCP/IP（六）：HTTP 与 HTTPS 简介](http://www.jianshu.com/p/6e7521041e92)
- [简书 - 面试时如何优雅的谈论HTTP／1.0／1.1／2.0](http://www.jianshu.com/p/52d86558ca57)
- [猫哥网络编程系列：详解 BAT 面试题](https://github.com/kaiye/kaiye.github.com/issues/3)
- [segmentfault - GET请求和POST请求的区别](https://segmentfault.com/a/1190000004014583)
- [开源中国 - 99%的人理解错 HTTP 中 GET 与 POST 的区别](https://www.oschina.net/news/77354/http-get-post-different)

## HTTP 爬虫

### Resources

- [知乎 - 爬虫学习资源整理](https://zhuanlan.zhihu.com/p/25250739)
- [简书 - 2016年，我对爬虫的总结](http://www.jianshu.com/p/53948b9c5f9b)
- [简书 - 一篇文章了解爬虫技术现状](http://www.jianshu.com/p/fbdad6f77d0c)
- [女朋友的微博情绪监控](https://www.anotherhome.net/2920)

### Node.js

- [掘金 - nodeJS实现基于Promise爬虫 定时发送信息到指定邮件](https://juejin.im/post/58db9371a22b9d00647d5aff)

### Java

- [java-spring-mybatis整合实现爬虫之《今日头条》搞笑动态图片爬取](http://z77z.oschina.io/2016/12/29/java-spring-mybatis%E6%95%B4%E5%90%88%E5%AE%9E%E7%8E%B0%E7%88%AC%E8%99%AB%E4%B9%8B%E3%80%8A%E4%BB%8A%E6%97%A5%E5%A4%B4%E6%9D%A1%E3%80%8B%E6%90%9E%E7%AC%91%E5%8A%A8%E6%80%81%E5%9B%BE%E7%89%87%E7%88%AC%E5%8F%96/)
- [掘金 - 重构：抓取一个视频网站上 2016 年所有电影的下载链接](https://juejin.im/post/58974ae91b69e600599486a9)
- [开源中国 - SpringBoot+SpringMVC+MybatisPlus框架整合练习之美女图片爬虫---图文详细流程](https://my.oschina.net/z707z/blog/829662)

### PHP

-  [segmentfault - php爬虫：知乎用户数据爬取和分析](https://segmentfault.com/a/1190000004357994)

### Python

- [伯乐在线 - Python 爬虫的工具列表](http://python.jobbole.com/82633/)
- [简书 - Python爬虫库-Beautiful Soup的使用](http://www.jianshu.com/p/5c239bcd05a3)
- [漫谈Pyspider网络爬虫的实践](https://www.figotan.org/2016/08/10/pyspider-as-a-web-crawler-system/)
- [简书 - 500 行 Python 代码构建一个轻量级爬虫框架](http://www.jianshu.com/p/5a8dd8a100b7)
- [Python爬虫一步步抓取房产信息](http://mp.weixin.qq.com/s/g82o4DgJ-2McztVBzSnGew)
- [Python爬虫之模拟知乎登录](https://foofish.net/python-auto-login-zhihu.html)
- [怎样借助Python爬虫给宝宝起个好名字](http://www.crazyant.net/2076.html)
- [简书 - Python爬虫-用Scrapy框架实现漫画的爬取](http://www.jianshu.com/p/c1704b4dc04d)
- [简书 - 使用python抓取美女福利图片](http://www.jianshu.com/p/c9b64ea3ecab)
- [简书 - Python 福利小爬虫，爬取今日头条街拍美女图](http://www.jianshu.com/p/d67b1d4b99ad)
- [掘金 - Python 爬虫：把廖雪峰的教程转换成 PDF 电子书](https://juejin.im/post/589d1dac1b69e60059ba1017)

## HTTP 资源

### 文章

- [阮一峰 - HTTP 协议入门](http://www.ruanyifeng.com/blog/2016/08/http.html)
- [HTTP 协议详解](http://mp.weixin.qq.com/s/27zpNIGhVbx-on9FDs_6dw)
- [扒一扒HTTP的构成](http://mrpeak.cn/blog/http-constitution/)
- [跟着 Github 学习 Restful HTTP API 设计](http://cizixs.com/2016/12/12/restful-api-design-guide)
- [imweb前端社区 - HTTP1.1与前端性能](http://imweb.io/topic/554c5879718ba1240cc1dd8a)
- [关于 Web 安全，99% 的网站都忽略了这些](https://segmentfault.com/a/1190000003852910)

### 视频

* [百度传课 - WEB系统测试 - HTTP协议详解](https://www.chuanke.com/v2858504-166873-765686.html)
* [慕课网 - PHP中的HTTP协议](http://www.imooc.com/learn/758)

## HTTP 抓包工具及教程

### 工具

- [Browser Develop Tools](https://developer.mozilla.org/zh-CN/docs/Learn/Discover_browser_developer_tools) - 浏览器开发者工具


- [Fiddler for Windows](http://www.telerik.com/fiddler) - Fiddler是一个 HTTP 协议调试代理工具
- [Charles for Mac](https://www.charlesproxy.com/)  Mac下HTTP 协议调试代理工具
- [Fiddler-AddOns](http://www.telerik.com/fiddler/add-ons) - Fiddler 插件地址
- [Wireshark](https://www.wireshark.org/) - 是一个网络封包分析软件，网络封包分析软件的功能是撷取网络封包，并尽可能显示出最为详细的网络封包资料
- [mitmproxy](https://mitmproxy.org/) - 一款可交互式的命令行抓包工具

### 教程

- [博客园 - Chrome开发者工具不完全指南](http://www.cnblogs.com/constantince/category/712675.html)


- [Fiddler CertMaker for iOS and Android](http://www.telerik.com/docs/default-source/fiddler/addons/fiddlercertmaker.exe?sfvrsn=2) - HTTPS 证书生成插件
- [简书 - HTTPS以及Fiddler抓取HTTPS协议](http://www.jianshu.com/p/66e6e5a76bea) - APP HTTPS 抓包
- [简书 - 抓包工具 Fiddler 相关知识总结](http://www.jianshu.com/p/4a8dae519efe)
- [简书 - Fiddler 教程](http://www.jianshu.com/p/99b6b4cd273c)
- [简书 - 抓包工具Wireshark基本介绍和学习TCP三次握手](http://www.jianshu.com/p/4d99babf63a1)
- [TMQ - 从wireshark抓包开始学习https](http://tmq.qq.com/2016/12/https_from_wireshark/)
- [掘金 - 一步一步教你 HTTPS 抓包 (mitmproxy)](https://juejin.im/post/584b711d8e450a006c586ca6)

## Chrome HTTP 插件

- Proxy SwitchyOmega - 轻松快捷地管理和切换多个代理设置
- CORS Toggle - 允许跨域请求
- Postman - 功能超级强大 HTTP Client

## HTTP 平台资源库

### Browser

- [jQuery](https://jquery.com/) 
- [jquery-pjax](https://github.com/defunkt/jquery-pjax)
- [zepto](http://zeptojs.com/)
- [fetch](https://github.com/github/fetch)
- [axios](https://github.com/mzabriskie/axios)
- [mockjs](http://mockjs.com/)

### Node.js

- [request](https://www.npmjs.com/package/request) - Request is designed to be the simplest way possible to make http calls
- [axios](https://www.npmjs.com/package/axios)- Promise based HTTP client for the browser and node.js
- [http-proxy](https://www.npmjs.com/package/http-proxy) - It is an HTTP programmable proxying library that supports websockets
- [superagent](https://www.npmjs.com/package/superagent) - SuperAgent is a small progressive **client-side** HTTP request library
- [morgan](https://www.npmjs.com/package/morgan) - HTTP request logger middleware for node.js

### Java

- [HttpClient](http://hc.apache.org/downloads.cgi) 

### Android

* [okhttp](https://github.com/square/okhttp)
  * [慕课网 - okhttp框架解析与应用](http://www.imooc.com/learn/732)

### Python

- [urllib](https://docs.python.org/2/library/urllib.html#urllib.urlencode)
- [urllib2](https://docs.python.org/2/library/urllib2.html#urllib2.Request)
- [httplib](https://docs.python.org/2/library/httplib.html)


- [Requests](http://docs.python-requests.org/en/master/)
  - [慕课网 - 走进Requests库](http://www.imooc.com/learn/736)

**若只使用python3.X, 下面可以不看了, 记住有个urllib的库就行了**

python2.X 有这些库名可用: [urllib](https://docs.python.org/2/library/urllib.html#urllib.urlencode), [urllib2](https://docs.python.org/2/library/urllib2.html#urllib2.Request), urllib3, [httplib](https://docs.python.org/2/library/httplib.html), httplib2, requests

python3.X 有这些库名可用: urllib, urllib3, httplib2, requests

两者都有的urllib3和requests, 它们不是标准库. urllib3 提供线程安全连接池和文件post支持,与urllib及urllib2的关系不大. [requests](http://docs.python-requests.org/en/latest/index.html) 自称HTTP for Humans, 使用更简洁方便。

详细信息请参考 - [开源中国 - python中 urllib, urllib2, httplib, httplib2 几个库的区别](https://my.oschina.net/sukai/blog/611451)

## HTTP 压力测试

### 工具

- LoadRunner
- SoapUI


- Jmeter 
- http_load
- webbench
- ab
- siege

### 教程

- [51testing - 性能自动化测试工具](http://www.51testing.com/zhuanti/LoadRunner.html)


- [博客园 - Jmeter教程 简单的压力测试](http://www.cnblogs.com/TankXiao/p/4059378.html)
- [慕课网 - 接口测试基础入门篇](http://www.imooc.com/learn/738)
- [慕课网 - JMeter之HTTP协议接口性能测试](http://www.imooc.com/learn/791)
- [介绍几款Web服务器性能压力测试工具](http://www.qixing318.com/article/introduce-a-few-web-server-performance-pressure-testing-tools.html)

## HTTP 代理服务器

### 产品

- [Nginx](https://github.com/nginx/nginx)
- [squid](https://github.com/squid-cache/squid)
- Privoxy
- [varnish](https://github.com/varnishcache/varnish-cache)
- Polipo
- Tinyproxy
- HAProxy
- ATS
- [nuster](https://github.com/jiangwenyuan/nuster)

### 文章

- [知乎 - 反向代理为何叫反向代理?](https://www.zhihu.com/question/24723688)
- [51cto - 图解正向代理、反向代理、透明代理](http://z00w00.blog.51cto.com/515114/1031287)
- [Anker - 正向代理与反向代理总结](http://www.cnblogs.com/Anker/p/6056540.html)


- [五大开源 Web 代理服务器横评](https://linux.cn/article-7119-1.html)
- [简书 - 反向代理服务器比较(Nginx，ATS，Squid等)](http://www.jianshu.com/p/4ed6144fe333)
- [简书 - Apache vs Nginx：基于实践经验的比较](http://www.jianshu.com/p/785597987dad)
- [简书 - 主机、服务器，代理服务器，反向代理服务器理解（自用）](http://www.jianshu.com/p/8aede64efb0d)
- [简书- 大型网站架构系列：负载均衡详解](http://www.jianshu.com/p/215b5575107c)
- [使用squid搭建代理服务器](http://www.hawu.me/operation/852)
- [简书 - 实战Nginx笔记](http://www.jianshu.com/p/dff2c0497840)
- [简书 - Nginx Proxy Cache原理和最佳实践](http://www.jianshu.com/p/625c2b15dad5)

## HTTP 图书

- [豆瓣读书 - HTTP 权威指南](https://book.douban.com/subject/10746113/)
- [豆瓣读书 - 图解 HTTP](https://book.douban.com/subject/25863515/)

## 参考资源

- [HTTP请求报文和HTTP响应报文以及工作原理](http://www.kannng.com/http/2016/10/26/http-packets.html)
- [百度百科 - HTTP](http://baike.baidu.com/link?url=Z2p_PetqY7-ujWiMn15wvG6z4K7ORksVt8Dy47sWI2KF_p4VEZKZrN_7vfwuF1HLBfzLs_vJJNyyF-xAQ4AyuK#1)

**[⬆ 返回顶部](#目录)**

