# 一、初始网络爬虫

## 1.1HTTP

HTTP是一个客户端和服务端之间进行请求和应答的标准

通过使用浏览器、网络爬虫或其他工具，客户端可以向服务器上在指定端口（默认为88）发起一个HTTP请求
这个 客户端称为用户代理

应答服务器上存储着HTML文件等各种 资源，这个应答服务器称为源服务器

通常由HTTP客户端发起一个请求，创建一个服务器到指定端口的TCP连接。

HTTP服务器则在该端口监听客户端的一个请求，一旦收到请求，服务器会向客户端返回一个状态以及请求的文件、错误消息等响应内容

HTTP主要包括以下请求方法：

### GET

向指定的资源发出显示请求。

只用于读取数据

HEAD

与GET方法一样，也是发出指定资源的请求，但是服务器不会回传资源的内容部分

好处在于，不必传输全部内容的情况下，只需要获取“关于该资源的信息”（元数据）

### POST

向指定资源提交数据，请求服务器进行处理（如提交表单，或上传文件）

数据被包含在请求文本中

这个请求可能会创建新资源或修改已有资源

### PUT

向指定资源上传最新内容

### DELETE

请求服务器删除Request-URL所标识的资源

### TRACE

回显服务器收到的请求

主要用于测试或判断

### OPTIONS

可使得服务器传回资源所支持的所有HTTP请求方法

"*"来代替资源名称向Web服务器发送OPTIONS请求

用于测试服务器是否正常

### CONNECT

HPPT协议中预留给能够将连接改为管道方式的代理服务器

通常用于SSL加密服务器的连接

当某个请求针对的资源不支持对应的请求方法的时候，服务器返回码为405

当服务器不认识或者不支持对于的请求方法的时候，返回状态码501

## 1.2Hello,Spider!

### 第一个爬虫程序

```python
import lxml.html,requests
#导入模块,lxml用于解析XML和HTML，可以使用XPath和CSc来定位元素

url='https://www.python.org/dev/peps/pep-0020'
xpath  = '//*[@id="the-zen-of-python"]/pre/text()'
# 定义两个变量:url是一个网页链接，可以直接在浏览器打开
#xpath是一个XPath路径表达式，用于定位元素

res= requests.get(url)
'''
使用Requests库的get()方法，对url发送了一个HTTP GET请求
将返回值赋给res，得到了一个名为res的Requests对象
接下里就可以通过这个Requests获取更多需要的信息
'''

ht = lxml.html.fromstring(res.text)
'''
lxml.html负责处理html
fromstring()方法的传入参数是res.text,即上面的Requests对象的text文本内容
即fromstring()方法根据这段文本来构建一个lxml中的HtmlElement对象
'''
text = ht.xpath(xpath)
print('Hello,\n'+''.join(text))
'''
使用XPath来定位HtmlElement中1的信息，并进行输出
text就是程序运行得到的结果
.join()用于将序列中的元素以指定的字符串连接生成一个新的字符串
因为text是一个'list'对象，所有使用''这个空字符
'''
```



### 对爬虫的思考

> 爬虫的核心任务就是访问某个站点（一般为某个URL)，
>
> 然后提取其中的特点信息
> 最后对数据进行处理

要遵循robots.txt和网站服务协议

即Robots协议，收法律约束

## 1.3调研网站

### 网站的robots.txt与Sitemap

一般而言，网站都会提供自己的robots.txt文件

Robots协议旨在让网站访问者（或访问程序）了解该网站的信息爬取限制

在爬取网站之前，检查这一文件中的内容可以降低爬虫程序被网站的反爬虫机制封禁的风险

访问方法:网站url后加上robots.txt

如[百度](www.baidu.com/tobots.txt)：

```
User-agent: //表示哪些机器人（程序）需要遵守下面的规则
Disallow: /search			Allow: /
//后面的Allow和Disallow，决定是否允许该user-agent访问该网站的这部分内容
Crawl-delay: 10
//爬虫抓取延迟，即在两次下载请求中给出5秒的时间间隔
```

> Python3自带的robotparser工具可以解析robots.txt文件并知道爬虫编写
>
> 从而避免下载robots.txt协议不允许爬取的信息，
>
> 只要在代码中加入
>
> import urllib.robotparser

```python
import urllib.robotparser as urobot
#robotparser是ullib下的一个模块
import requests

url  = "https://www.taobao.com"
rp = urobot.RobotFileParser()
#创建一个名为rp的RobotFileParser()对象
rp.set_url(url+"/robots.txt")
#加载网站的robots.txt文件
rp.read()
user_agent = 'Baiduspider'
#设置user_agent
if rp.can_fetch(user_agent,'https：//www.taobao.caom/product/'):#使用can_fetch()方法测试代理用户是否可以爬取URL对应的网页
    site  = requests.get(url)
    print('seems good')
else:
    print('cannot scrap because robots.txt banned you')
```

有时候，robots.txt还会定义一个Sitemap，即站点地图（网站地图），可以说一个任意形式的文档

一般而言，站点地图会列出网站中的所有页面

站点地图有助于访问者以及搜索引擎的爬虫找到网站中的各个页面

在搜索引擎的优化领域有很重要的作用

站点地图可以通过访问robots.txt文件来获取，如[豆瓣](https://www.douban.com/robots.txt)



### 查看网站所用技术

网站所用技术会成为影响爬虫策略的一个重要因素

使用wad模块就可以坚持网站背后所使用的技术

使用pip安装这个库:

```linux
pip install wad
```

安装完成，就可以在终端输入

```
wad -u 'https://www.baidu.com'
```

来查看百度网站使用的技术

> 如果出现报错，一种解决方法如下：
>
> ![img](https://img-bbs.csdn.net/upload/202105/20/1621491063_803110.png)

直接编写一个文件试试：

```python
import wad.detection
det = wad.detection.Detector()
url = input()
print(det.detect(url))
#接受一个URL,输入并返回wad分析的结果
```

### 查看网站所有者信息

可使用WHOIS协议来查询域名

所谓WHIOS，就是一个用来程序互联网上IP和所有者等信息的传输协议

安装python-whois库即可:

```
pip install python-whois
```

whois.whois(URL)

```python
import whois
print(whois.whois('https:www.baidu.com'))
```

### 使用开发者根据检查页面

爬取网页之前，检查目标网页是最重要的准备工作

检查网页首选Chrome Firefox

Chrome的开发者模式为用户提供了几组工具：

Elements:

​	允许也会有从浏览器的角度来观察网页：可以看到HTML,CSS，DOM对象

​	双击即可编辑页面的HTML和CSS

Network:

​	可以看到网页向服务器提供了哪些资源、资源的大小加载资源的相关信息

​	还可以查看HTTP的请求头、返回内容等

> 可以清楚的看到页面加载网络资源的过程和相关信息
>
> 请求的每一个自已资源在表格中显示为一行
>
> 对于特定的网络请求，可以进一步查看请求头、响应头以及已经返回的内容等	
>
> 勾选Preserve log复选框
>
> 在进行登录，就可以记录HTTP POST信息，查看发送的表单信息详情
>
> From Data就包含着相关信息

<img src="C:\Users\吴晗\AppData\Roaming\Typora\typora-user-images\image-20210611223623335.png" alt="image-20210611223623335"  />



Sources:

​	代码面板，用来调试JavaScript

Console:

​	控制台面板，可以显示各自警告信息和错误信息

​	开发期间，可以使用控制面板记录诊断信息

​	作为shell在 页面上与JavaScript交互

Perfromance:

​	使用这个模块可以记录和查看网站生命周期内发送的各种事件

​	来提高页面的运行性能

Memory:

​	提供比Perfromance更多的信息，如跟踪内存泄漏

Application:

​	检查加载的所有资源

Security:

​	安全面板，处理证书等问题

![image-20210611223215239](C:\Users\吴晗\AppData\Roaming\Typora\typora-user-images\image-20210611223215239.png)

值得注意的是Copy XPath

由于XPath是解析网页的利器，因此这个功能显得尤为重要

