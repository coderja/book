> 准备工作 安装nodejs 安装git 准备一个GitHub账号 熟悉Markdown语法

 我们可以直接在gitbook官网直接发布文章，但是那种界面行的类似有道云读书笔记，是专门给那些不懂代码的运营人员使用，我这边给大家分享一个我在注册gitbook账号的时候遇到的坑，使用GitHub账号授权gitbook登陆的时候会遇到这样的错
 
 ``` 
  A network error has occurred. The service may be blocked by your ISP or in your area. 
 ```

 <font color='#f00'>解决方案就是因为访问gitbook官网需要vpn所有需要设置VPN的节点,出站模式 选择 全局连接 </font>

前提工作准备好后，我们就可以开始愉快的玩耍了 

首先全局安装`gitbook-cli` 工具

```
npm install gitbook-cli -g
```

查看是否安装成功
```
gitbook --version
```

#### 安装好后我们就可以初始化书籍项目
```
mkdir gitbook 
cd gitbook 
gitbook init
```

此时项目中会生成两个文件`README.md`和`SUMMARY.md` 这两个文件都是基于Markdown语法，不熟悉Markdown语法的可以查阅我另一篇笔记[markdown教程](../markdown/markdown.md)

README.md文件是项目的首页

```
# WEB
##### 欢迎来到我的前端小站,本人从事互联网工作将近5年，1年美工、3年前端工作经验。平时喜欢记录工作中遇到的一些坑，希望可以跟大家成为朋友！
#### [博客园地址](https://www.cnblogs.com/tw6668/)

#### 另外家中产<font color='#f00'>大闸蟹</font>，需要的朋友也可以联系我！

#### 联系方式 WX:1107854543 
```

SUMMARY.md是项目的目录页面
```
# Summary

* [简介](README.md)

* [编辑器](doc/编辑器/edit.md)

* [HTML](doc/html/html.md)

* [markdown](doc/markdown/markdown.md)

```

我们在根目录下面创建一个doc，该目录下面就是我们最终要写的文件，最终呈现给用户查看，目录层级最终就是在网页左侧你所看到的

此时我们在命令行输入`gitbook serve`
就会在本地启动一个服务器默认访问4000端口

这样你的gitbook项目框架就搭建好了，基于gitbook搭建的博客就OK了！但是这样只能给自己访问，如果想要发布到公网上面，那边就得借助GitHub关于如何发布GitHub请查阅我的另外一篇文章[gitbook整合GitHub](../gitbook中级/gitbook.md)

