[上一篇](../gitbook入门/.gitbook.md)搭建使用gitbook搭建属于自己的博客

这一篇就给大家分享一下，结合github如何将自己的博客同步到GitHubPage，以供别人在公网访问。

前提你需要有github账号以及掌握git命令的使用

1.首先在GitHub上面建一个book仓库
2.在项目中创建一个.gitignore文件，内容如下：
```
# 忽略gitbook生成的项目目录
_book
```

然后终端打开项目，输入如下命令,来提交文档源码：
```
git init
git add .
git commit -m '初始化gitbook本地项目'
git remote add origin https://github.com/coderja/book.git 
git push -u origin master
```

上面命令执行结束后，就会把代码提交到github上的仓库。
注意仓库地址要替换成你自己的链接。

为了部署方便，可以创建一个脚本文件deploy.sh,内容如下：

```
#!/usr/bin/env sh
 
echo '开始执行命令'
# 生成静态文件
echo '执行命令：gitbook build .'
gitbook build .
 
# 进入生成的文件夹
echo "执行命令：cd ./_book\n"
cd ./_book
 
# 初始化一个仓库，仅仅是做了一个初始化的操作，项目里的文件还没有被跟踪
echo "执行命令：git init\n"
git init
 
# 保存所有的修改
echo "执行命令：git add -A"
git add -A
 
# 把修改的文件提交
echo "执行命令：commit -m 'deploy'"
git commit -m 'deploy'
 
# 如果发布到 https://<USERNAME>.github.io/<REPO>
echo "执行命令：git push -f https://github.com/coderja/book.git master:gh-pages"
git push -f https://github.com/coderja/book.git master:gh-pages
 
# 返回到上一次的工作目录
echo "回到刚才工作目录"
cd -
```

为脚本添加权限
```
chmod 777 ./depoly.sh
```

执行脚本`./depoly`
执行成功后，在github网站上的仓库里面点击Settings -> GitHub Pages选项中 -> Source里面选择gh-pages branch 然后点击Save按钮，然后在GitHub Pages下面就会看见一个网站，这个网站就是最终的网站。


coderja.github.io.com/book/ 替换成自己的


这样你的博客就可以在公网上面供别人访问了