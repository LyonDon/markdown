##线程和进程

###创建多线程
*	用threading模块创建多线程
*	从threading.Thread继承创建线程类

###协程
用户级轻量级线程（单线程，省去了cpu的调度开销）
spawn():形成协程
joinall()：添加协程，并启动运行
Pool对象：可对协程的并发数量进行管理

###分布式进程
将Process进程分布到多台机器上

**PS：**
CPU密集型操作：推荐多进程，因为多线程只能调用一个cpu内核
IO密集型操作：推荐多线程，可提高效率
***

##网络编程

###socket（套接字）
一个socket表示“打开了一个网络链接”
打开一个socket需要知道目标计算机的IP地址和端口号，再指定协议类型
Python提供两个基本的Socket模块
>Socket：提供标准API
>SocketServer：提供服务器中心类，简化网络服务器开发

###html
###CSS
###javascript
>严格区分大小写，忽略空格，制表符和换行符
####数据类型
Number整型
字符串类型
布尔值类型
数组类型
对象类型

function关键字：用来定义函数
*允许传入任意个参数而不影响调用*
当结果错误时返回NaN

###XPath
在XML中查找信息的语言，也可在html文档中工作
>xml:lang="en":
>>这是一个W3C的标准；
lang代表语言，这儿是英语；改成zh-cn指简体中文
xml:lang就是xml的语言，这儿的xml是一种html扩展语言，功能很强大；因为各浏览器的兼容不一样，所以就有这么一个机构，想做出一个统一标准的兼容方案；在html代码中加入这样一个代码，可使所有浏览器都按标准的排版去设计；如果去掉，可能部分浏览器不兼容，最好都加上，因为是标准。
XPath进行属性选取的时候可以使用通配符*匹配未知元素

###JSON
JSON是JavaScript对象表示法，用于存储和交换文本信息
JSON语法
>JSON名称/值对。类似python中的字典
>JSON值
>JSON对象：可包含多个名称/值对
>JSON数组：在方括号中书写，可包含多个对象

##HTTP标准
###HTTP请求过程
1.	首先客户端与服务器建立连接
2.	建立链接后，客户端发送一个请求给服务器
3.	服务器接到请求，给予相应的响应信息，格式为一个状态行
4.	客户端接收服务器所返回的信息，通过浏览器将信息显示在用户的显示屏上

这些过程由HTTP协议自己完成

###HTTP状态码含义
1\*\*信息，服务器收到请求，需进一步操作
2\*\*成功
3\*\*重定向
4\*\*客户端错误
5\*\*服务器错误

###HTTP头部信息
HTTP头部信息由众多头域组成，每个头域有一个域名，冒号和域值
GET
Host头域
User-Agent头域
Accept请求报头域
Accept-Language请求报头域
......
***
#初识网络爬虫
###网络爬虫结构
![网络爬虫结构](https://github.com/LyonDon/python-learning/raw/master/python-reptile/photo/%E5%9B%BE%E5%83%8F%201.png)
##HTTP的python实现
###urllib2/urllib实现
urllib2和urllib是python中的两个内置模块，要实现HTTP功能，实现方式以urllib2为主，urllib为辅
###httplib/urllib实现
###更人性化的Requests

***
#HTML解析大法
##初识Firebug
一个用于web前端开发的工具，是FireFox浏览器的一个扩展插件。可以用于调试JavaScript、查看DOM、分析CSS、监控网络流量以及进行Ajax交互等。几乎提供了前端开发需要的全部功能

##正则表达式
是由普通字符以及特殊字符组成的文字模式
\b是正则表达式规定的一个特殊代码，被称为元字符，代表单词的开头或结尾，也就是单词的分解处
*常用元字符*
元字符主要有四种作用

*	匹配字符
*	匹配位置
*	匹配数量
*	匹配模式

![正则表达式常用元字符](https://github.com/LyonDon/python-learning/raw/master/python-reptile/photo/%E5%9B%BE%E5%83%8F%203.png)

*字符转义*
*重复*
*字符集合*
*分支条件*
*字符集合*
*分支条件*
*分组*
*反义*
*后向引用*

###python与正则
python通过re模块提供对正则表达式的支持
使用re的一般步骤：

1.	将正则表达式的字符串形式编译为pattern实例
2.	使用pattern实例处理文本并获取匹配结果
3.	使用Match实例获得信息

主要用到的方法：

re.copile(string[,flag])
re.match(pattern,string[,flags])
>从输入参数string的开头开始，尝试匹配pattern，一直向后匹配。遇到无法匹配的字符或者到达string的末尾，立即返回none，繁殖获取匹配的结果

re.search(pattern,string[,flsgs])
>与match很相似，区别在于后者只从string的开始位置匹配，前者会扫描整个string查找匹配

re.split(psttern,string[,maxsplit])
re.findall(pattern,string[,flags])
re.finditer(pattern.string,[flags]}
re.sub(pattern.repl,string[,count])
re.subn(pattern,repl,string[,count])

##强大的BeautifulSoup

#数据存储（无数据库版）

##HTML正文抽取
对HTML正文的抽取存储，主要将HTML正文存储为两种格式：JSON和CSV

###存储为JSON
python对json文件的操作分为编码和解码，通过json模块来实现

*	编码过程：python对象转化为json对象（通过dump（将json文件通过fp文件流写入文件中）和dumps）
*	*	>FILE:系统定义的一种结构类型 的名称。
		FILE *fp:变量类型声明。声明 fp 是 FILE型指针，用于指向 FILE类型 （文件结构）。
 		文件流 :排成一队，有先后次序的 输入（或输出）一串数据，驻留并通过 输入输出缓冲区，进出程序。如同水流般地流入或流出。它来自文件或写入文件。

*	解码过程：json对象转化为python对象：（通过load和loads：类比dump和dumps）

python的一些基本类型通过编码之后，tuple类型就转化成了list类型；再将其转回python对象时，list类型并没有变回tuple类型

###存储为CSV
逗号分隔值

*	CSV文件实例
			ID，Uesrname，Password，age，country
            1001，"harry","harry_pass",20,"China"
            1002,"Coj","Coj_pass",22,"America"

python使用csv库读取CSV文件
**将csv文件实例内容写为.csv文件，需要用到Writer对象
.csv文件的读取需要用到reader对象**
存储CSV文件时，需要统一存储数据的类型。使用encode（'tf-8'）的作用是将title、real_title,href,date变量类型统一为str

##多媒体文件抽取
urllib模块中的urlretrieve()函数：直接将远程任务下载到本地

##Email提醒
Python对SMTP的支持有smtplib和email两个模块，email负责构造邮件，smtplib负责发送邮件

###MIME类型
>浏览器中显示的内容有 HTML、有 XML、有 GIF、还有 Flash。浏览器通过MIME tpye（多用途Internet邮件扩展（MIME）类型 ）区分它们，决定什么内容用什么形式来显示
>>浏览器通常使用MIME类型（而不是文件扩展名）来确定如何处理文档；因此服务器设置正确以将正确的MIME类型附加到响应对象的头部是非常重要的
>####语法
>>>1.	通用结构
type/subtype
MIME的组成结构非常简单；由类型与子类型两个字符串中间用'/'分隔而组成。并不允许空格存在。type 表示可以被分为复数子类的独立类型。subtype 表示细分后的每个类型。
**MIME类型对大小写不敏感，但是传统写法都是小写**
>>>2.	独立类型
>>>![独立类型](https://github.com/LyonDon/python-learning/raw/master/python-reptile/photo/%E5%9B%BE%E5%83%8F4.png)

>>>3.	Multipart类型
>>>Multipart 类型表示细分领域的文件类型的种类，经常对应不同的 MIME 类型。这是复合文件的一种表现方式。对于 multipart/form-data 的例外部分，可以使用HTML Forms 和 POST 方法，此外 multipart/byteranges使用状态码206 Partial Content来发送整个文件的子集，而HTTP不能处理的复合文件使用一个特殊的方式：将信息直接传送给浏览器

>>###重要的MIME类型
>>application/octet-stream、text/plain、text/css、text/html、图片类型、音频与视频类型、multipart/form-data、multipart/byteranges

##实战项目：基础爬虫
###基础爬虫框架
*主要包括五大模块*：爬虫调度器，URL管理器，HTML下载器，HTML解析器，数据存储器

*	####URL管理器
包括已爬取的URL集合和未爬取的URL集合以及一些接口
链接去重方法:

	*	内存去重（set）
	*	关系数据库去重
	*	缓存数据库去重
	
    接口：
    		has_new_url()
            add_new_url(url),ad_new_urls(urls)
            get_new_url()
			new_url_size()
            old_url_size()

*	####HTML下载器
用来下载网页
需要用到request模块，实现一个接口：download（url）

*	####HTML解析器
需要解析的部分主要为提取相关词条页面的URL和提取当前词条的标题和摘要信息

*	####数据存储器
主要包括两个方法
	*	store_data(data)用于将解析出来的数据存储到闪存中
	*	output_html()用于将存储的数据输出为指定的文件格式

**ps：一次性写入文件容易使系统出现异常，造成数据丢失。当数据很多时，采用分批存储的方法比较好**

*	####爬虫调度器
首先初始化各个模块，然后通过crawl（root_url）方法传入入口url，方法内部实现按照运行流程控制各个模块的工作

##简单分布式爬虫
采用主从模式：
>主从模式是指由一台主机作为控制节点负责所有运行网络爬虫的主机进行管理，爬虫只需要从控制节点那里接收任务，并把新生成任务提交给控制节点就可以了，在这个过程中不必与其他爬虫通信，这种方式实现简单利于管理。而控制节点则需要与所有爬虫进行通信，因此可以看到主从模式是有缺陷的，控制节点会成为整个系统的瓶颈，容易导致整个分布式网络爬虫系统性能下降

###控制节点
*	URL管理器
*	数据存储器
*	控制调度器




