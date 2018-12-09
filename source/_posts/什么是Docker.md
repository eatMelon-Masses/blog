---
layout: post
title: 什么是Docker
date: 2018-11-29
categories: 技术
---

### 前言

最近因为安装sqlserver时涉及到Docker，所以希望能够了解Docker是如何虚拟化物理资源的，提高自己对运维这块的了解

[Docker官网：https://www.docker.com/](https://www.docker.com/)

### Docker简介

> Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly

上面这一段是官网对Docker的描述：Docker是一个用于开发,运行并管理应用程序的开放平台.Docker能够分离你的应用程序和基础架构,使你能够快速交付.

> 备注：Docker许可证————**open source Apache 2.0 license**

###### Docker解决什么问题

软件开发最大的麻烦事之一，就是环境配置；我们在平时的开发过程中，经常出现在本地或者测试环境测试通过了，但是却在正式环境跪了的情况；然后我们就会去比较两者的环境差别。

###### Docker技术实现

Docker 基于Linux容器技术,使用Go开发实现;

###### Docker用途

1. 提供一次性的环境
2. 提供弹性的云服务
3. 组建微服务架构

###### Docker基本概念

![Docker基本结构](https://jianjustin.github.io/blog/assets/img/picture/engine-components-flow.png)



### Docker objects

###### 镜像

>An *image* is a read-only template with instructions for creating a Docker container. Often, an image is *based on*another image, with some additional customization. 

以上是官网对镜像的定义：镜像是一个用于创建容器的只读模板，而镜像是存在依赖关系的，你可以在基础镜像上构建自定义镜像

###### 容器

> A container is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. 

容器则是镜像所创建出的可运行实例，你可以通过Docker API等对容器进行操作。所以说在实际中我们主要会操作容器

###### 仓库

我们在自定义镜像进行构建后可能会在不同的物理机进行使用，所以就需要一个集中的存储、分发镜像的服务；常用是：`Docker Hub`



### Docker使用

> Docker的安装比较简单，和正常的程序安装基本一致

* mac：https://docs.docker.com/docker-for-mac/install/
* window：https://docs.docker.com/docker-for-windows/install/

> 验证Docker是否成功安装：`docker version`

###### 镜像操作

* 镜像拉取：`docker pull [OPTIONS] NAME[:TAG|@DIGEST]`

  eg:`docker pull centos`

* 镜像搜索：`docker search [OPTIONS] TERM`

* 列出本地镜像：`docker images [OPTIONS] [REPOSITORY[:TAG]]`
* 本地镜像构建：`docker build [OPTIONS] PATH | URL |`



###### 容器操作

* 显示本地容器：`docker ps [OPTIONS]`
* 连接运行中容器：`docker attach [OPTIONS] CONTAINER`
* 容器端口映射信息：`docker port [OPTIONS] CONTAINER [PRIVATE_PORT[/PROTO]]`
* 容器启动：`docker start `
* 容器停止：`docker stop`
* 容器重启：`docker restart`
* 创建新容器并运行：`docker run`
* 清理已终止容器：`docker container prune`

### Docker使用案例

###### Docker安装MYSQL

* 查询mysql镜像：`docker search mysql`
* 拉取mysql镜像：`docker pull mysql`
* 创建容器：`docker run -p 33060:3306 --name mymysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql`
* 查看本地容器：`docker ps [container_id]`

###### Docker安装mongoDB

* 查询mongoDB镜像：`docker search mongo`
* 拉取mongoDB镜像：`docker pull mongo`
* 创建mongoDB容器：`docker run --name mymongo -p 27017:27017 -v /data/db:/data/db -d mongo --auth`
* 进入mongo容器：`docker exec -it mymongo mongo admin`
* 创建管理员账号：`db.createUser({ user: '<USER>', pwd: '<PASSWORD>', roles: [ { role: 'userAdminAnyDatabase', db: 'admin' } ]})`
* 退出mongo容器，以校验方式进入：`docker exec -it <YOUR-NAME> mongo -u <USER> -p <PASSWORD> --authenticationDatabase admin`

[参考链接](https://brickyang.github.io/2017/03/15/%E5%88%A9%E7%94%A8-Docker-%E8%BF%90%E8%A1%8C-MongoDB/)

Docker安装redis

* 查询redis镜像：`docker search redis`
* 拉取redis镜像：`docker pull redis`
* 创建redis容器并运行：`docker run -d --name myredis -p 6379:6379 redis --requirepass "mypassword"`
* 进入redis容器中并执行redis-cli：`docker exec -it b98b0c0e3797 redis-cli -a "jian031018"`

Docker安装sqlserver

* 

### Docker图形化管理

* 配置portainer目录：`docker volume create portainer_data`

* 安装portainer容器：`docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer`