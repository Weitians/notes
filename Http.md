#### HTTP协议（HyperText Transfer Protocol，超文本传输协议）是因特网上应用最为广泛的一种网络传输协议，所有的WWW文件都必须遵守这个标准。HTTP是一个基于TCP/IP通信协议来传递数据（HTML 文件, 图片文件, 查询结果等）。

#### HTTP 工作原理：HTTP协议工作于客户端-服务端架构上。浏览器作为HTTP客户端通过URL向HTTP服务端即WEB服务器发送所有请求。
		- Web服务器：Apache服务器，IIS服务器（Internet Information Services）等。
		- Web服务器根据接收到的请求后，向客户端发送响应信息。
		- HTTP默认端口号为80，但是你也可以改为8080或者其他端口。
		
#### HTTP三点注意事项：
		- HTTP是无连接：无连接的含义是限制每次连接只处理一个请求，服务器处理完客户的请求，并收到客户的应答后，即断开连接。
		- HTTP是媒体独立的：只要是客户端和服务器知道如何处理的数据内容，任何类型的数据都可以通过HTTP发送。
		- HTTP是无状态：HTTP协议是无状态协议，无状态是指协议对于事务处理没有记忆能力，缺少状态意味着如果后续处理需要前面的信息，则它必须重传。
		
#### HTTP 消息结构：
		- 客户端请求消息：
			- 请求行（request line）：
			- 请求头部（header）：
			- 空行：
			- 请求数据：
			
								
		- 服务器响应消息：
			- 状态行：
			- 消息报头：
			- 空行：
			- 响应正文



#### HTTP请求方法：
		- HTTP1.0：
			▪ GET：请求指定的页面信息，并返回实体主体；
			▪ HEAD：类似于get请求，只不过返回的响应中没有具体的内容，用于获取报头；
			▪ POST：向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。
			
		- HTTP1.1：
			▪ PUT：从客户端向服务器传送的数据取代指定的文档的内容；
			▪ DELETE：请求服务器删除指定的页面；
			▪ CONNECT：HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器；
			▪ OPTIONS：允许客户端查看服务器的性能；
			▪ TRACE：回显服务器收到的请求，主要用于测试或诊断；
			
#### HTTP 响应头信息：
		- Allow：服务器支持哪些请求方法（如GET、POST等）。
		
		- Content-Encoding：文档的编码（Encode）方法。只有在解码之后才可以得到Content-Type头指定的内容类型。
		
		- Content-Length：表示内容长度。只有当浏览器使用持久HTTP连接时才需要这个数据。
		
		- Content-Type：表示后面的文档属于什么MIME类型。Servlet默认为text/plain，但通常需要显式地指定为text/html。
		
		- Date：当前的GMT时间。你可以用setDateHeader来设置这个头以避免转换时间格式的麻烦。
		
		- Expires：应该在什么时候认为文档已经过期，从而不再缓存它？
		
		- Last-Modified：文档的最后改动时间。客户可以通过If-Modified-Since请求头提供一个日期，该请求将被视为一个条件GET，只有改动时间迟于指定时间的文档才会返回，否则返回一个304（Not Modified）状态。Last-Modified也可用setDateHeader方法来设置。
		
		- Location：表示客户应当到哪里去提取文档。Location通常不是直接设置的，而是通过HttpServletResponse的sendRedirect方法，该方法同时设置状态代码为302。
		
		- Refresh：表示浏览器应该在多少时间之后刷新文档，以秒计。除了刷新当前文档之外，你还可以通过setHeader("Refresh", "5; URL=http://host/path")让浏览器读取指定的页面。 
		
		- Server：服务器名字。Servlet一般不设置这个值，而是由Web服务器自己设置。
		
		- Set-Cookie：设置和页面关联的Cookie。Servlet不应使用response.setHeader("Set-Cookie", ...)，而是应使用HttpServletResponse提供的专用方法addCookie。
		
		- WWW-Authenticate	：客户应该在Authorization头中提供什么类型的授权信息，在包含401（Unauthorized）状态行的应答中这个头是必需的。
		
#### HTTP状态码：
		- HTTP状态码共分为5种类型：
			1**	信息，服务器收到请求，需要请求者继续执行操作
			2**	成功，操作被成功接收并处理
			3**	重定向，需要进一步的操作以完成请求
			4**	客户端错误，请求包含语法错误或无法完成请求
			5**	服务器错误，服务器在处理请求的过程中发生了错误
			
		- HTTP状态码列表：
			100	Continue	继续。客户端应继续其请求；
			101	Switching Protocols	切换协议。服务器根据客户端的请求切换协议。只能切换到更高级的协议，例如，切换到HTTP的新版本协议；
			
			200	OK	请求成功。一般用于GET与POST请求；
			201	Created	已创建。成功请求并创建了新的资源；
			202	Accepted	已接受。已经接受请求，但未处理完成；
			203	Non-Authoritative Information	非授权信息。请求成功。但返回的meta信息不在原始的服务器，而是一个副本；
			204	No Content	无内容。服务器成功处理，但未返回内容。在未更新网页的情况下，可确保浏览器继续显示当前文档；
			205	Reset Content	重置内容。服务器处理成功，用户终端（例如：浏览器）应重置文档视图。可通过此返回码清除浏览器的表单域；
			206	Partial Content	部分内容。服务器成功处理了部分GET请求；
			
			300	Multiple Choices	多种选择。请求的资源可包括多个位置，相应可返回一个资源特征与地址的列表用于用户终端（例如：浏览器）选择；
			301	Moved Permanently	永久移动。请求的资源已被永久的移动到新URI，返回信息会包括新的URI，浏览器会自动定向到新UR；
			302	Found	临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI；
			303	See Other	查看其它地址。与301类似。使用GET和POST请求查看；
			304	Not Modified 未修改。所请求的资源未修改，服务器返回此状态码时，不会返回任何资源；
			305	Use Proxy	使用代理。所请求的资源必须通过代理访问；
			306	Unused	已经被废弃的HTTP状态码；
			307	Temporary Redirect	临时重定向。与302类似。使用GET请求重定向；
			
			400	Bad Request	客户端请求的语法错误，服务器无法理解；
			401	Unauthorized	请求要求用户的身份认证；
			402	Payment Required	保留，将来使用；
			403	Forbidden	服务器理解请求客户端的请求，但是拒绝执行此请求；
			404	Not Found	服务器无法根据客户端的请求找到资源（网页）。通过此代码，网站设计人员可设置"您所请求的资源无法找到"的个性页面；
			405	Method Not Allowed	客户端请求中的方法被禁止；
			406	Not Acceptable	服务器无法根据客户端请求的内容特性完成请求；
			407	Proxy Authentication Required	请求要求代理的身份认证，与401类似，但请求者应当使用代理进行授权；
			408	Request Time-out	服务器等待客户端发送的请求时间过长，超时；
			409	Conflict	服务器完成客户端的PUT请求是可能返回此代码，服务器处理请求时发生了冲突；
			410	Gone 客户端请求的资源已经不存在。410不同于404，如果资源以前有现在被永久删除了可使用410代码；
			411	Length Required	服务器无法处理客户端发送的不带Content-Length的请求信息；
			412	Precondition Failed	客户端请求信息的先决条件错误；
			413	Request Entity Too Large	由于请求的实体过大，服务器无法处理，因此拒绝请求。为防止客户端的连续请求，服务器可能会关闭连接；
			414	Request-URI Too Large	请求的URI过长（URI通常为网址），服务器无法处理；
			415	Unsupported Media Type	服务器无法处理请求附带的媒体格式；
			416	Requested range not satisfiable	客户端请求的范围无效；
			417	Expectation Failed	服务器无法满足Expect的请求头信息；
			
			500	Internal Server Error	服务器内部错误，无法完成请求；
			501	Not Implemented	服务器不支持请求的功能，无法完成请求；
			502	Bad Gateway	作为网关或者代理工作的服务器尝试执行请求时，从远程服务器接收到了一个无效的响应；
			503	Service Unavailable	由于超载或系统维护，服务器暂时的无法处理客户端的请求。延时的长度可包含在服务器的Retry-After头信息中；
			504	Gateway Time-out	充当网关或代理的服务器，未及时从远端服务器获取请求；
			505	HTTP Version not supported	服务器不支持请求的HTTP协议的版本，无法完成处理；
			
#### HTTP content-type：内容类型，指网页中存在的Content-Type，用于定义网络文件的类型和网页的编码，决定浏览器将以什么形式、什么编码读取这个文件。

[详细列表] (https://www.runoob.com/http/http-content-type.html)
