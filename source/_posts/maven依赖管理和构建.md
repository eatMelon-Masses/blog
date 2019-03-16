---
layout: post
title: maven依赖管理和构建
date: 2018-02-06
categories: 技术
---


## 基础使用
#### 基础命令

1. `mvn clean`    清空构建包文件
2. `mvn compiler` 编译源文件
3. `mvn deploy`  部署构建包
4. `mvn failsafe` 集成测试
5. `mvn install`  构建包文件到本地repository
6. `mvn resources` 实现不同环境下配置的替换
7. `mvn site`     生成站点，根据report节点
8. `mvn surefire` 用例测试
9. `mvn verifier` 构建包验证

#### 扩展使用命令

1. `mvn archetype:generate` 创建项目骨架

#### maven参数配置

###### 配置本地仓库位置

```xml
<localRepository><localRepository/>
```

###### 配置是否以离线方式构建项目

```xml
<offline><offline/>
```

###### 配置远程仓库

```xml
<servers>
    <server>
      <id>server001</id>
        <!--maven所连接的repository/mirror唯一编号-->
      <username>my_login</username>
        <!--mirror服务器名称-->
      <password>my_password</password>
        <!--mirror服务器密码-->
      <privateKey>${user.home}/.ssh/id_dsa</privateKey> 
        <!--mirror服务器私钥-->
      <passphrase>some_passphrase</passphrase>
        <!--mirror服务器密钥-->
      <filePermissions>664</filePermissions>
        <!--mirror服务器文件创建权限-->
      <directoryPermissions>775</directoryPermissions>
        <!--mirror服务器目录创建权限-->
      <configuration></configuration>
        <!--mirror服务器配置信息-->
    </server>
  </servers>
```

###### 配置mirror节点

```xml
<mirror>
    <id>planetmirror.com</id>
    <!--镜像站id-->
    <name>PlanetMirror Australia</name>
    <!--镜像站name-->
    <url>url</url>
    <!--镜像站url-->
    <mirrorOf>central</mirrorOf>
    <!--镜像站内仓库地址，central表示主仓库，可与id相关联-->
</mirror>
```

###### properties节点配置

```xml
<profiles>
   <profile>
     <properties>
       <user.install>
           ${user.home}/our-project
        </user.install>
     </properties>
   </profile>
 </profiles>
```

###### Repositories配置

```xml
<profile>
   <repositories>
     <repository>
       <id>codehausSnapshots</id>
       <name>Codehaus Snapshots</name>
       <releases><!--发布版本信息配置-->
         <enabled>false</enabled>
           <!--是否开启发布版本依赖构件下载-->
         <updatePolicy>always</updatePolicy>
         <checksumPolicy>warn</checksumPolicy>
       </releases>
       <snapshots><!--快照版本信息配置-->
         <enabled>true</enabled>
         <!--是否开启快照版本依赖构件下载-->
         <updatePolicy>never</updatePolicy>
         <checksumPolicy>fail</checksumPolicy>
       </snapshots>
      <url>${url}</url>
      <layout>default</layout>
     </repository>
   </repositories>
   <pluginRepositories><!-- 远程插件仓库配置 -->
   </pluginRepositories>
 </profile>
```

#### 项目POM配置

###### 项目POM整体配置

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                        http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <!--POM文件版本，4.0.0说明POM支持2&3版本的maven-->
    <!-- The Basics -->
    <!-- 说明:版本标识  <主版本>.<次版本>.<增量版本>-<限定符>-->
    <groupId></groupId>
    <!--通常是组织或项目的唯一表示，用于表示项目的主目录结构-->
    <artifactId></artifactId>
    <!--代表项目名称，用于项目的唯一标识-->
    <version></version>
    <!--代表项目版本，用于定位唯一版本项目-->
    <packaging></packaging>
    <!--打包方式,主要包括 jar or war，默认打包方式是jar-->
    <classifier></classifier>
    <!--用于生成构建包-->
    <dependencies></dependencies>
    <parent></parent>
    <dependencyManagement></dependencyManagement>
    <modules></modules>
    <properties></properties>

    <!-- Build Settings -->
    <build></build>
    <reporting></reporting>

    <!-- More Project Information -->
    <name></name>
    <!--项目别名-->
    <description></description>
    <!--项目描述-->
    <url></url>
    <!--项目路径-->
    <inceptionYear></inceptionYear>
    <!--项目修改路径-->
    <licenses></licenses>
    <!--项目协议-->
    <organization></organization>
    <!--项目所在组织-->
    <developers></developers>
    <!--项目开发者列表-->
    <contributors></contributors>
    <!--贡献者列表-->

    <!-- Environment Settings -->
    <issueManagement></issueManagement>
    <!--缺陷追踪系统信息-->
    <ciManagement></ciManagement>
    <!--配置持续集成管理系统-->
    <mailingLists></mailingLists>
    <!--管理邮箱列表-->
    <scm></scm>
    <!--软件管理信息-->
    <prerequisites></prerequisites>
    <repositories></repositories>
    <pluginRepositories></pluginRepositories>
    <distributionManagement></distributionManagement>
    <profiles></profiles>
  </project>
```

###### 项目POM依赖管理

```xml
<dependencies>
 <dependency>
   <groupId>junit</groupId>
     <!--依赖主版本-->
   <artifactId>junit</artifactId>
     <!--依赖次版本-->
   <version>4.0</version>
     <!--依赖版本号-->
   <type>jar</type>
     <!--依赖打包类型-->
   <scope>test</scope>
     <!--指定依赖使用范围-->
   <systemPath></systemPath>
     <!--仅适用于scope节点为system-->
   <optional>true</optional>
     <!--将依赖设置为可选依赖，不进行依赖传递-->
   <exclusions>
       <!--排除依赖，用于解除依赖传递-->
     <exclusion>
       <groupId>org.apache.maven</groupId>
       <artifactId>maven-core</artifactId>
     </exclusion>
   </exclusions>
 </dependency>
   </dependencies>
```

###### 项目POM构建管理

```xml
<build></build>
<profiles>
  <profile>
    <build>...</build>
  </profile>
</profiles>
```

* 配置构建节点

```xml
 <build>
      <defaultGoal>install</defaultGoal>
      <!--设置构建目标-->
      <directory>${basedir}/target</directory>
      <!--构建目标路径-->
      <finalName>
          ${artifactId}-${version}
      </finalName>
      <!--构建结果名称-->
      <filters>
      <!--配置构建参数-->
        <filter>
            filters/filter1.properties
          </filter>
      </filters>
    </build>
```

* 配置resources节点

```xml
<resources>
  <resource>
    <targetPath>META-INF/plexus</targetPath>
    <filtering>false</filtering>
    <directory>
        ${basedir}/src/main/plexus
      </directory>
    <includes>
      <include>configuration.xml</include>
    </includes>
    <excludes>
      <exclude>**/*.properties</exclude>
    </excludes>
  </resource>
</resources>
```

* 配置plugins节点

```xml
<plugins>
   <plugin>
     <groupId>
         org.apache.maven.plugins
     </groupId>
     <artifactId>maven-jar-plugin</artifactId>
     <version>2.6</version>
     <extensions>false</extensions>
     <inherited>true</inherited>
     <configuration>
       <classifier>test</classifier>
     </configuration>
     <dependencies>...</dependencies>
     <executions>...</executions>
   </plugin>
 </plugins>
```

#### 生命周期

* clean周期
* 默认周期
* site周期

#### 插件管理

1. `maven-assembly-plugin`
  用于将指定文件进行自定义打包
2. `maven-dependency-plugin`
  检查pom依赖关系：
     Used undeclared dependencies: 表示项目中使用到的，但是没有显示声明的依赖
     Unused declared dependencies: 表示项目中未使用的，但显示声明的依赖
  运行命令:
3. `maven-resources-plugin`
4. `maven-compiler-plugin`
5. `maven-surefire-plugin`
6. `maven-jar-plugin`
7. `maven-install-plugin`
