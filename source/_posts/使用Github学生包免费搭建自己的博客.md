---
title: 使用Github学生包配合Github pages免费搭建自己的博客
date: 2017-10-14 19:34:00
tags: hexo 博客
---

## 1. 前言
### 1.1 最好的工具给最好的你
　　“纸上得来终觉浅，绝知此事要躬行”，对于技术学习来说，多动手才能让自己进步的更快。但是问题来了，我只是一个穷学生，开发工具又那么贵怎么办呢？现在就介绍一下我们的主角--Github学生包。

[获取你的工具包](https://education.github.com/discount_requests/new)

    获取过程很简单，只要你按照提示一步步做就好了。可以使用教育邮箱（推荐），如果你像我一样没有教育邮箱也可以把你的身份证明（学生证）拍成照片提交。

搭建博客要用到的工具是[Namecheap](https://www.namecheap.com)
> NameCheap是一家领先的ICANN认可的域名注册和网站托管公司，成立于2000年，今天有超过50万域名客户和超过100万网站客户选择Namecheap，我们同时提供免费DNS解析，网址转发（可隐藏原URL，支持301重定向）、电邮转发、A记录、CNAME别名记录、MX邮件记录、TXT文本记录、NS记录、AAAA记录（IPV6），还可以设置动态域名解析。

使用Github学生包免费申请一个.me的域名待用。

### 1.2 Github pages
使用github pages 服务搭建博客的好处有：
　　* 全是静态页面，访问速度快
　　* 免费方便，不用一分钱就可以搭建一个个人博客
　　* 可以随意绑定知己的域名
　　* 数据绝对安全，配合Github的版本管理，可以恢复到任何历史版本

### 1.3 准备工作
1. 一个github账号
2. 一个域名
3. 安装了node.js、npm, 了解相关知识
4. 安装了git

我使用的环境：
* Mac os 10.12
* node.js - v6.11.4
* git - v2.14.1
* hexo - v3.3.9

## 2. 搭建github博客
### 2.1 创建代码仓库
　　登录github，点击右上角的小加号，选择New repository新建一个代码仓库:
[](/pic/blogimg/newrepo.png)
　　进入代码仓库创建页面：
在Repository name里面填写yourname.github.io（必须是你的github用户名），Description (optional)里面填写描述（不写也可以），然后点击Create repository：
[](/pic/blogimg/yourname.png)
完成之后你就可以通过https://yourname.github.io 来访问你的博客了！

### 2.2 绑定域名
　　你说不绑定域名？那当然可以，你直接使用https://youname.github.io 来访问你的博客也是可以的，但是既然我们有免费的域名和DNS解析服务，为何不搞一下呢。
　　拿出我们在namecheap搞到的域名，登录namecheap，点击Domains下的FreeDNS进入DNS的配置界面，点击左边的Domain List，右边会显示你的域名列表，选择你要绑定的域名，点击MANAGE，选择最右边的Advanced DNS。
　　我们要添加两个记录，CNAME和A记录，由于A记录指向的是IP，所以我们要先ping一下youname.github.io的到IP地址，点击ADD NEW RECORD，将A记录指向ping出来的IP，将CNAME指向yourname.github.io：
[](/pic/blogimg/setdns.png)
然后在github根目录新建一个CNAME文件，里面填写你的域名。
[](/pic/blogimg/cname.png)
## 3设置SSH key
为了不用每次提交博文都输入密码，我们要先配置一下ssh key


