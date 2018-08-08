# hexo 问题集锦
## 添加404 page
source 目录新建 404/index.md
头部信息

```
title: 404 Not Found：该页无法显示
toc: false
comments: false
permalink: /404
```
注意：404 页面在本地 http://localhost:4000/ 下访问不生效
## 404 页面引入丢失儿童

添加代码

`<script type="text/javascript" src="//qzonestyle.gtimg.cn/qzone/hybrid/app/404/search_children.js" homepagename='返回主页' homepageurl="/" charset="utf-8"></script>
`

homepagename: 自定义返回主页 文字

homepageurl：自定义返回的地址

## 每次构建，都需要重新填写 Custom domain
在 source 文件夹下新建 名为 CNAME 的文件
内容为自己需要的域名，但是不用填写http://

## 文章不显示文章目录，转载权限等配置
看过代码，发现所以的配置都写着post.pug文件中，但实际生效的是page.pug文件，所以把相应的代码放到page.pug即可

## 在右侧导航栏添加文章目录
一开始在config中配置widget，并在_widget 目录下添加toc文件，但出现本地访问没有问题，构建之后不显示
后更改直接在base.pug 文件中更改
在sidebar 下添加
```
if page.toc
            #toc-widget.widget
              .widget-title
                i(class='fa fa-star-o')= ' ' + __('contents')
              #toc
                != toc(page.content, {list_number: theme.toc_number})
```
totop.js添加页面滚动事件

```
 if(!$('#toc-widget')[0]){return}
    var $prevSibling = $($('#toc-widget').prev())
    var ot = $prevSibling[0].offsetTop + $prevSibling[0].offsetHeight
    $('#toc-widget')[0].setAttribute("data-fixed",st >= ot?"fixed":"");
```
