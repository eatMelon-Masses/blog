---
layout: post
title: 如何使用Git&Github
date: 2018-08-17
categories: development-tools
---

##### 文章要点
* [git客户端配置](#git客户端配置)
* [git命令行基本操作](#git命令行基本操作)
* [github基本使用](#github基本使用)
* [github多用户协作](#github多用户协作)

<a name="git客户端配置"/>
### git客户端配置
----------------

1. **git命令行安装**

 	* 下载[安装包](https://git-scm.com/)
 	* 执行安装包

	![git执行安装包](/assets/img/picture/git安装执行.png)

2. **本地ssh-key配置**

	* 检查是否已配置ssh-key
	```
	$ cd ~/.ssh
	$ ls
	```

	* 配置本地信息
	```
	$  git config --global user.name "提交人"
	$  git config --global user.email "提交邮箱"
	```

	* 生成本地ssh-key
	```
	$  ssh-keygen -t rsa -C "提交邮箱"
	```

	* 查看本地ssh-key
	```
	cat ~/.ssh/id_rsa.pub
	```

	* github配置ssh-key

	![github配置ssh-key](/assets/img/picture/github配置ssh-key.png)

	* 测试与github服务器是否连通
	```
	$ ssh -T git@github.com
	```

3. **安装TortoiseGit**

	* 下载[安装包](https://tortoisegit.org/download/)
 	* 执行安装包

	![tortoiseGit安装执行](/assets/img/picture/tortoiseGit安装执行.png)
	


<a name="git命令行基本操作"/>
### git命令行基本操作
----------------
  * `clone`
  *	`commit`
  *	`pull`
  *	`push`
  *	`checkout`

<a name="github基本使用"/>
### github基本使用
----------------
  * 个人账号创建

![github账号注册](/assets/img/picture/github账号注册.png)

  *	仓库建立

![github仓库创建](/assets/img/picture/github仓库创建.png)


<a name="github多用户协作"/>
### github多用户协作
----------------
  * 邀请用户

![邀请用户](/assets/img/picture/github团队邀请用户.png)


**资料**

 * [Pro Git](https://progit.bootcss.com/)
 * [Git命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
 * [Github使用指南](https://github.com/AntBranch/awesome-github)


