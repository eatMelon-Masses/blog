---
layout: post
title: linux入门简易教程
date: 2018-03-28
categories: 技术
---

## 命令

#### 基础命令

<span style="color:red">apt-get</span>

* update - 重新获取软件列表
* install - 安装新软件包
* remove - 移除软件包
* clean - 清除下载的归档文件
* check - 检查是否有损坏的依赖

<span style="color:red">export</span>

* `-f` - 代表[变量名称]为函数名称
* `-n` - 删除指定环境变量
* `-p` - 列举所有环境变量

<span style="color:red">find</span>

* find <指定目录> <指定条件> <指定动作> -- 文件查询

<span style="color:red">whereis</span>

<span style="color:red">source</span>

* source /etc/profile - 更新系统配置信息 

<span style="color:red">yum</span>

* install - 通过包管理工具获取依赖

<span style="color:red">systemctl</span>
>systemctl命令是系统服务管理器指令，它实际上将 service 和 chkconfig 这两个命令组合到一起

* enable - 使某服务自启动
* status - 检查服务状态
* list-units - 显示所有已启动服务
* start - 启动某服务

## 工具

* Systemd - 启动守护进程
* openssh-server - 开发SSH服务
* firewall-cmd - 防火墙软件
* postfix - 邮件服务器














