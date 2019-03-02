---
layout: post
title: 如何使用Git&Github
date: 2018-08-17
categories: development-tools
---

#### git客户端配置

1. **git命令行安装**

 	* 下载[安装包](https://git-scm.com/)
 	* 执行安装包

	![git执行安装包](https://jianjustin.github.io/blog/assets/img/picture/git安装执行.png)

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

	![github配置ssh-key](https://jianjustin.github.io/blog/assets/img/picture/github配置ssh-key.png)

	* 测试与github服务器是否连通
	```
	$ ssh -T git@github.com
	```

3. **安装TortoiseGit**

	* 下载[安装包](https://tortoisegit.org/download/)
 	* 执行安装包

	![tortoiseGit安装执行](https://jianjustin.github.io/blog/assets/img/picture/tortoiseGit安装执行.png)
	
#### git命令行基本操作


* 了解帮助命令

   * `git help` : 查看命令
   * `git help add` : 查看 git add 命令的具体解释

* 仓库初始化

   * `git init` : 创建 .git, 适合在已存在项目追加版本控制
   * `git init projectname` : 创建 projectname/.git, 适合项目开始时加入版本控制

* 文件基本操作

   * `git add filename/*` : 添加文件[产生暂存文件]
   * `git commmit -m "message"` : 将添加的文件提交到本地仓库[产生提交文件]
   * `git rm filename` : 移除文件，使用 rm filename 的有暂存
   * `git add -u` . : 如果之前使用非 git 命令删除文件，可以使用这个命令把当前目录的文件重新遍历清除

   * `git rm --cache filename` : 暂存但是不参与跟踪
   * `git mv filepath newfilepath` : 移动文件
   * `git rm filepath && git add newfilepath` : 移动文件，之前使用非 git 命令移动文件
   * `git add -A .` : 如果之前使用非 git 命令移动文件，可以使用这个命令把当前目录的文件重新遍历移动，和 rm 命令类似
   * `git reset etc...` : 历史提交管理(回退，合并...)，checkout 更关注文件

* *查看文件修改

   * `git status` : 查看文件信息
   * `git diff` : 查看修改[工作树和暂存文件]
   * `git diff --staged` : 查看修改[暂存文件和最近提交文件]
   * `git diff HEAD` : 查看修改[工作树和最近提交文件]
   * `git diff --word-diff` : 查看修改的单词用颜色标出
   * `git diff --stat` : 查看修改的文件名


#### github基本使用

  * 个人账号创建

![github账号注册](https://jianjustin.github.io/blog/assets/img/picture/github账号注册.png)

  *	仓库建立

![github仓库创建](https://jianjustin.github.io/blog/assets/img/picture/github仓库创建.png)


#### github多用户协作

  * 邀请用户

![邀请用户](https://jianjustin.github.io/blog/assets/img/picture/github团队邀请用户.png)

**资料**

 * [Pro Git](https://progit.bootcss.com/)
 * [Git命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
 * [Github使用指南](https://github.com/AntBranch/awesome-github)

#### 使用gitub-lfs上传大文件

* 初始化仓库`git lfs install`
* 添加到lfs管理`git lfs track "*.pdf"`
* 添加lfs追踪文件`git add .gitattributes`
* 查看git-lfs管理文件`git lfs track`

#### 获取Github教育包

* 登录Github-education网站[链接地址](https://education.github.com)
* 提交教育信息(最好截图学信网教育信息)
* 等待Github审核通知(一般在三～五天)
* Github Education Pack内容说明
  * algolia - hosted search API
  * Atom - web editor
  * AWS Cloud educate
  * bitnami
  * cart
  * Data dog
  * Travis-CI
  * Unreal-Engine
  * transifix
  * heroku

#### 参考资料

* [markdown语法](https://www.appinn.com/markdown)
* [Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
* [常用Git命令](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)