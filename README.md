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
## 404 页面引入丢失儿童

添加代码

`<script type="text/javascript" src="//qzonestyle.gtimg.cn/qzone/hybrid/app/404/search_children.js" homepagename='返回主页' homepageurl="/" charset="utf-8"></script>
`
homepagename: 自定义返回主页 文字
homepageurl：自定义返回的地址

## 每次构建，都需要重新填写 Custom domain
在 source 文件夹下新建 名为 CNAME 的文件
内容为自己需要的域名，但是不用填写http://
