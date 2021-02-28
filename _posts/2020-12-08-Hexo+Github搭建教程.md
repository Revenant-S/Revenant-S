---
title: Hexo+Github搭建教程
date: 2020-12-08 16:02:43
categories:
- 2020-12
tags:
- Hexo
- Github
- 博客
---



<center>Hexo+Github搭建教程</center>

<!-- more -->

# 前言

Github Pages 是GitHub提供的免费静态网页托管服务，可以用来托管博客、项目网站等静态网页。支持Jekyll、Hugo、Hexo编译静态资源，本文的主题是GitHub+Hexo。

# 准备环境
1. NodeJs，Hexo是基于NodeJs驱动的一款博客框架
2. Git，
3. npm
# 安装Hexo
在某个文件夹下，右键打开git bash执行以下命令：

```sh
npm install -g hexo-cli
```

之后执行下列命令：

```sh
hexo init filename
cd filename
npm install
```

新建完成后，运行hexo s，其中s是sever的缩写。之后访问 http://localhost:4000 就可以预览效果了。

```sh
hexo s
```
# Github
1. 账号注册
2. 创建一个仓库
# 配置SSH
有ssh则使用下列命令查看：
```
cat ~/.ssh/id_rsa.pub
```
没有ssh则执行以下命令生成：

```
git config --global user.name "用户名"
git config --global user.email "邮箱地址"
ssh-keygen -t rsa -C "上面的邮箱"
```

之后将id_rsa.pub（公钥）添加到GitHub ssh key上。

# 部署
修改 _ config.yml文件，在文件最后：

```
deploy:
  type: git
  repo: 仓库git地址，不用http
  branch: 分支名称
```

安装部署插件hexo-deployer-git

```
npm install hexo-deployer-git --save
```

本地推送：

```
hexo clean && hexo g && hexo s
```

远程推送：

```
hexo clean && hexo g && hexo d
```

# 写作

在文件根目录下打开git bash，执行命令，创建新md文件，在./source/_posts下编辑即可：

```
hexo new 文章标题
```