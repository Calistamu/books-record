# 《白帽子讲web安全》自我学习

## 第1章 我的安全世界观

在这个世界里只有两个字：超越。

读遍所有有关系统安全或系统漏洞的文件。

[coolfire](https://zhuanlan.zhihu.com/p/20244214):大隐隐于市者。就像擅长捉迷藏的孩子，在说起别人总是找不到它时的那种得以。这是一种爱好，就像玩游戏打怪一样。和技术恋爱，而不是结婚。保持好奇，追求自由。酷八篇。生活黑客---刷票机的例子，系统有时差，可以被利用。



富文本：富文本格式（Rich Text Format）即RTF格式，又称多文本格式，是由微软公司开发的跨平台文档格式。大多数的文字处理软件都能读取和保存RTF文档。[富文本与markdown](https://www.jianshu.com/p/99b944dae4c3)

php0字节截断功能:已解决，从今晚后所有PHP文件操作中，文件名NULL字符截断的问题将被永久性解决了。[php-is-null-or-empty](https://stackoverflow.com/questions/8236354/php-is-null-or-empty):判断一个变量是否为NULL最好的办法就是直接使用"==="，这样就不用在is_null，isset之间犹豫。其实上述的结论也同理于False的判断。

[DEP数据执行保护](https://docs.microsoft.com/en-us/windows/win32/memory/data-execution-prevention)：检查是否安全使用内存，防止遭到恶意攻击。

[ASLR](https://docs.microsoft.com/en-us/windows/win32/api/winnt/ns-winnt-process_mitigation_aslr_policy):可以实现进程的栈基址随机变化

Pwn2own竞赛

xss蠕虫  
案例：MySpace、微博
存储型xss:当攻击者提交恶意输入，应用程序将其存储到数据库，其他用户浏览了相关页面，此时应用程序将提取数据库 中恶意数据显示到浏览器上，从而得到执行引起XSS漏洞攻击。    
反射型XSS:直接在URL中加入消息参 数，并且未将该参数经任何过滤，当用户请求包含恶意代码的URL时，经过服务器反射回来直接显示到页面中，于是恶意代码得到执行，在利用该类XSS时，存 在的不足是需要用户的点击。  
基于DOM的XSS:利用了客户端脚本中的DOM技术，测试工具主要是火狐的一个扩展dominator，目前支持到FF3.  
XSS扫描工具（Acunetix WVS、IBM的AppScan、华为的WebCruiser、诺赛科技的JSky）和[owasp测试指南](http://www.owasp.org.cn/owasp-project/OTG)或直接搜索"XSS Cheat Sheet"  
xss蠕虫实现（国外的BEEF、XSS Shell以及国内大风等人的开源作品Anehta等）  
xss防止：xss filter  
1. 在OWASP ESAPI（Enterprise Security API）中有几个安全的JavascriptEncode、HtmlEncode、XMLEncode、JSONEncode的实现  
2. 在“Apache Common Lang”的“StringEscapeUtils”里，提供了许多escape的函数。
3. Anti-Samy是OWASP上的一个开源项目，也是目前最好的XSS Filter。最早它是基于Java的，现在已经扩展到.NET等语言。


<font color=red>
问题：  

1. 远程关闭了阿里巴巴内网的一台路由设备如何实现的？  
2. [安在](www.anzerclub.com)要关注  
3. 浅黑科技-知乎专栏要关注
4. 渗透测试怎么搞的？入侵中如何提升权限？
5. php要去学习
6. CSRF如何使用一个token来进行有效防御？---csrf漏洞的成因就是网站的cookie在浏览器中不会过期，只要不关闭浏览器或者退出登录，那以后只要是访问这个网站，都会默认你已经登录的状态（所以token可以用来防止cookie不过期，这里的token相当于时间戳）。而在这个期间，攻击者发送了构造好的csrf脚本或包含csrf脚本的链接，可能会执行一些用户不想做的功能（比如是添加账号等）。这个操作不是用户真正想要执行的。攻击者盗用了你的身份，以你的名义发送恶意请求。CSRF能够做的事情包括：以你名义发送邮件，发消息，盗取你的账号，甚至于购买商品，虚拟货币转账……造成的问题包括：个人隐私泄露以及财产安全。[一个csrf有趣实验](https://www.freebuf.com/column/155800.html)
7. xss蠕虫实验搞一次[个人xss平台搭建](https://blog.csdn.net/itest_2016/article/details/77650356)
8. Linux要学，p3代码没看懂。
</font>

## 第2章客户端脚本安全

