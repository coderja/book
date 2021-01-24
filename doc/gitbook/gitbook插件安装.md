安装和使用插件方法

在根目录下创建book.json

在该文件中按照指定格式插入以下插件对应的代码。

安装插件有两种方式 ：

一种是在book.json写入相应插件和配置后，

使用gitbook install安装插件。

一种是使用npm install pluginName安装，然后写入配置

> hide-element 隐藏元素
主要用来隐藏不想看到的元素。

如：

默认的gitbook左侧提示：Published with GitBook

使用方式： 在book.json中写入以下内容

```
{
    "plugins": [
        "hide-element"
    ],
    "pluginsConfig": {
        "hide-element": {
            "elements": [".gitbook-link"]
        }
    }
}
```

> back-to-top-button 回到顶部

当文章篇幅较长时，页面底部会显示按钮，一键点击自动回到顶部。

使用方式:

在book.json中写入以下内容

```
{
    "plugins": [
         "back-to-top-button"
    ]
}
```

> chapter-fold 导航目录折叠

在book.json中写入以下内容
```
{
    "plugins": ["chapter-fold"]
}
```

> code 复制代码
在代码域的右上角添加一个复制按钮，点击一键复制代码。

使用方式：

在book.json中写入以下内容
```
{
    "plugins" : [ "code" ]
}
```

> github图标

在book.json中写入以下内容

```
{
    "plugins": [ "github" ],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/your/repo"
        }
    }
}

```

> splitter 侧边栏宽度可调节

左侧目录和右侧文章可以拖动调节宽度。

使用方式：

在book.json中写入以下内容
```
{
    "plugins": [
        "splitter"
    ]
}
```

> search-pro 高级搜索
支持中英文，准确率更高一些。

使用方式：

在book.json中写入以下内容
```
{
    "plugins": [
          "-lunr", 
          "-search", 
          "search-pro"
    ]
}
```
> insert-logo 插入logo

在左侧导航栏上方插入logo。

使用方式： 在book.json中写入以下内容

url支持本地图片也支持网络图片链接
```
{
    "plugins": [ "insert-logo" ]
    "pluginsConfig": {
      "insert-logo": {
        "url": "images/logo.png",
        "style": "background: none; max-height: 30px; min-height: 30px"
      }
    }
}
```

> pageview-count 阅读量计数
记录每个文章页面被访问的次数。

使用方式：

在book.json中写入以下内容
```
{
  "plugins": [ "pageview-count"]
}
```

> tbfed-pagefooter 页面添加页脚

在每个文章下面标注版权信息和文章时间。

使用方式：

在book.json中写入以下内容

```
{
    "plugins": [
       "tbfed-pagefooter"
    ],
    "pluginsConfig": {
        "tbfed-pagefooter": {
            "copyright":"Copyright &copy meetwen.com 2021",
            "modify_label": "该文章修订时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}
```

> popup 弹出大图
点击可以在新窗口展示图片。

使用方式：

在book.json中写入以下内容
```
{
  "plugins": [ "popup" ]
}
```

> sharing-plus 分享当前页面

gitbook默认只有Facebook、Google+、Twiter、Weibo、Instapaper

插件可以有更多分享方式，也可以关闭指定分享方式。

使用方式：

在book.json中写入以下内容

```
{
    "plugins": ["-sharing", "sharing-plus"],
    "pluginsConfig": {
        "sharing": {
             "douban": true,
             "facebook": true,
             "google": true,
             "pocket": true,
             "qq": true,
             "qzone": true,
             "twitter": true,
             "weibo": true,
          "all": [
               "douban", "facebook", "google", "instapaper", "linkedin","twitter", "weibo", 
               "messenger","qq", "qzone","viber","whatsapp"
           ]
       }
    }
}
```

book.json配置代码

```
{
    "plugins": [
        "back-to-top-button",
        "chapter-fold",
        "code",
        "splitter",
        "-lunr",
        "-search",
        "search-pro",
        "insert-logo",
        "custom-favicon",
        "pageview-count",
        "tbfed-pagefooter",
        "hide-element",
        "popup",
        "-sharing",
        "sharing-plus",
        "donate",
        "github",
        "klipse" 
    ],
    "pluginsConfig": {
        "expandable-chapters":{},
        "github": {
     	   "url": "https://github.com/coderja"
  	    },
        "hide-element": {
            "elements": [".gitbook-link"]
        },
        "insert-logo": {
            "url": "https://www.smallsticker.com/static/bf6df360995b416f4af4e88a52f5fce7/7cce6/bcb9d8146cb3f6850336c70f05dd11f9.jpg",
            "style": "background: none; max-height: 60px; min-height: 60px"
        },
        "favicon": "./icon/favicon.ico",
        "tbfed-pagefooter": {
            "copyright": "Copyright &copy meetwen.com 2021",
            "modify_label": "该文章修订时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        },
        "sharing": {
            "douban": false,
            "facebook": false,
            "google": false,
            "pocket": false,
            "qq": false,
            "qzone": false,
            "twitter": false,
            "weibo": false,
            "all": [
             "qq", "qzone","viber","whatsapp",
              "douban", "facebook", "google", "instapaper", "linkedin",
              "messenger","twitter", "weibo"
          ]
      },
      "donate": {
        "wechat": "https://www.smallsticker.com/static/bf6df360995b416f4af4e88a52f5fce7/7cce6/bcb9d8146cb3f6850336c70f05dd11f9.jpg",
        "alipay": "./assets/img/donate/alipay.jpg",
        "title": "",
        "button": "赏",
        "alipayText": "支付宝打赏",
        "wechatText": "微信打赏"
    }
    }
}
```