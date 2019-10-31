---
title: '简单的使用githua Pages搭个博客'
date: 2019-09-18T20:55:51+08:00
draft: false
---

## 1、创建一个仓库

![创建仓库](https://pages.github.com/images/user-repo@2x.png)

### 特别注意

```
Github 有两种形式的 page：

1、个人或组织的 page：只能存在一个，master 分支，地址为 xxx.github.io

2、项目 page：每个项目可以生成一个，gh-pages 分支，地址为 xxx.github.io/projectname
```

我不想打开我的博客的时候还要输入仓库名称，所以我选择第一种个人 page，这要求你在创建仓库的时候，仓库名称必须为 username.github.io

## 2、进入 setting

![点击setting](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/click-setting.png)

## 3、改变主题

![改变主题](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202655.png)

## 4、选择一个主题

![选择主题](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202722.png)

## 5、commit

选择完主题后仓库会生成一个 index.md 文件，这就是你的主页了，你可以选择现在更改内容，然后 commit

## 6、访问你的主页https://username.github.io

比如我的就是[https://johnny19941216.github.io](https://johnny19941216.github.io)

## 7、修改博客名称和说明

修改`_config_yml`文件，添加`title`和`description`属性
