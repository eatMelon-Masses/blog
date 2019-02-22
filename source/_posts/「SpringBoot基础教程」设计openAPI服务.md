---
layout: post
title: 「SpringBoot基础教程」设计openAPI服务
date: 2019-02-11
categories: spring
---

#### 前言

在前后端分离开发过程中，我们肯定会涉及到API；后端需要通过openAPI标准化数据服务内容，而前端则需要通过openAPI了解服务格式和交互内容，从而提高应用开发的速度；同时在第三方数据源接入中，通过openAPI可以标准化数据的传输

#### openAPI标准

OpenAPI Initiative（OAI）由一个具有前瞻性的行业专家组成的联盟创建,他们认识到标准化REST API如何描述的巨大价值;作为Linux Foundation下的开放式治理结构，OAI专注于创建，发展和推广供应商中立的描述格式;SmartBear Software将Swagger规范直接捐赠给OAI，作为开放规范的基础


* openAPI描述API包括：

    * 有关API的一般信息
    * 可用路径（/资源）
    * 每条路径上的可用操作（获取/资源）
    * 每个操作的输入/输出


* 查询openAPI规范文件
    
    * [参考文档](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md)
    * [参考教程](http://apihandyman.io)
    * [资源汇总](https://github.com/DragorWW/awesome-swagger)
    * [openAPI规范](https://github.com/OAI/OpenAPI-Specification)

#### 什么是swagger

>可能大家在平时的开发中更多的是：使用swagger实现restfulAPI，那么什么是swagger呢？

Swagger 是一款目前世界最流行的API管理工具，是一个规范和完整的框架，用于生成、描述、调用和可视化 RESTful 风格的 Web 服务。文档提供了一个方法，我们可以用指定的 JSON 或者 YAML 摘要来描述你的 API[官网](https://swagger.io)


* swagger项目组主要包括：

    * swagger-js
    * swagger-ui
    * swagger-tools
    * swagger-editor
    * swagger-core
    * swagger-parser
    * swagger-codegen
    * swagger-node
    * validator-badge

* 什么是Springfox
>Springfox项目是用于spring系列项目自动生成JSON API的机器和人类可读规范  

    * [Springfox文档](https://springfox.github.io/springfox/docs)
    * [Springfox demos](https://github.com/springfox/springfox-demos)
    * [springfox和swagger的关系](https://springfox.github.io/springfox/docs/snapshot/#answers-to-common-questions-and-problems)


#### SpringBoot项目添加Springfox支持

* 添加springfox maven配置

  ```xml
  <dependency>
      <groupId>io.springfox</groupId>
      <artifactId>springfox-swagger2</artifactId>
      <version>2.9.2</version>
  </dependency>
  ```

  ```xml
  <dependency>
	  <groupId>io.springfox</groupId>
	  <artifactId>springfox-swagger-ui</artifactId>
	   <version>2.9.2</version>
  </dependency>
  ```

* Springfox基本配置

    * 启用swagger`@EnableSwagger2`
    * 配置扫描包路径`@ComponentScan(basePackage = {})`
    * 配置swagger文档信息
    ```java
    public ApiInfo apiInfo() {
      return new ApiInfoBuilder()
        .title("openAPI服务")
        .version("版本号:"+swaggerVersion)
        .license("MIT License")
        .build();
    }
    ```
    * 配置API扫描路径
    ```java
    @Bean
    public Docket memberApi() {
      return new Docket(DocumentationType.SWAGGER_2)
        .groupName("member")//设置API分组
        .select()
        .paths(PathSelectors.ant("/member/**"))//设置URL过滤
        .build()
        .apiInfo(apiInfo())
        .enable(swaggerSwitch);//设置是否启用swagger
    }
    ```
    ```java
    @Value("${swagger.switch}")
    private boolean swaggerSwitch;//需要在application.properties中设置
    ```

* Springfox开放API文档配置

    * 实现步骤：

        * controllor添加API注解
        ```java
        @RestController
        @Api(tags="member.user",value="用户模块")
        @RequestMapping(value = "/member/user/",produces = { "application/json" })
        ```
        * 处理方法添加API注解
        ```java
        @ApiOperation(value = "新增用户")
        @RequestMapping(method = RequestMethod.POST)
        public ResponseEntity<?> save(
            @ApiParam(value = "实体数据", required = true) @RequestBody MemberUser memberUser) {
          memberUserService.save(memberUser);
          return new ResponseEntity<MemberUser>(HttpStatus.OK);
        }
        ```

    * 常用API注解

        * `@ApiParam#value()`
        * `@ApiImplicitParam#value()`
        * `@ApiModelProperty#value()`
        * `@ApiOperation#value()`
        * `@ApiOperation#notes()`
        * `@RequestParam#defaultValue()`
        * `@RequestHeader#defaultValue()`


* Springfox安全配置




















