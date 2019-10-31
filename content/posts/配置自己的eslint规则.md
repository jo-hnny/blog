---
title: '配置自己的eslint规则'
date: 2019-09-18T20:56:39+08:00
draft: true
---

## 虽然要遵守这些条条框框，但是 eslint 确实使得代码更规范，最重要的是它能预防一些错误；我使用的是 standard 规范,为什么使用它？因为它默认规则行尾不加分号，嗯，对，就因为这个。

## 我配置的是全局的，下面是配置步骤。

### 1、全局安装 eslint

`npm i eslint -g`

### 2、初始化 eslint 规则

直接打开命令行，在用户目录下初始化 eslint 配置文件
`eslint --init`  
![eslint --init](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202802.png)
选择 Use a popular style guide
![eslint --init](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202827.png)
选择 Standard 规范
![eslint --init](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202852.png)
我选 JSON，接下来就会安装各种依赖
![eslint --init](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202917.png)
报了个错，不管它，继续全局安装一些必要的依赖，这点比较坑，为什么不全部自动安装，莫非是因为这个错误中断了？  
`npm i eslint-plugin-standard eslint-plugin-promise eslint-plugin-node eslint-plugin-import eslint-config-standard -g`  
到这就可以用了，我用的编辑器是 vscode，打开 vscode 安装 eslint 插件，他会对你的代码进行错误提示，然后呢，我写代码大致是遵循规范的，但是总有几个括号之间的空格忘敲了，所以我需要代码 format 工具，正好 vscod 自带了 format 工具，不用安装任何额外的插件，但是 format 工具格式化后的代码和 standard 规范又有一些出入，所以我修改了一点规则，这个修改可以根据自己的需求进行，比如说：  
![space-before-function-paren](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918202943.png)
Standard 规范不允许方法的小括号和方法名之间没有空格，但是 vscode format 之后，空格就没了，怎么办，我们修改一下 eslint 配置文件：  
![.eslintrc.json](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918203010.png)
这是之前初始化的配置文件，图上可以看到路径的位置，自己请在自己的用户目录下找，然后我们进行修改
![rules](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918203029.png)
添加了一条规则，这条规则会覆盖默认的规则，`0代表off，关闭这条规则，1代表warning，会警告，2代表error，会报错`  
现在再看之前报错的代码  
![代码](https://raw.githubusercontent.com/johnny19941216/storage-room/master/img/20190918203107.png)
可以看到之前函数括号的错误已经没了，Generator 函数的`*`号还有错误，只要按照之前的方法去修改规则就可以了，如果以后再遇到什么情况，我会继续更新。
