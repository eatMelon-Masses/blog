---
layout: post
title: maven-项目管理
date: 2018-02-06
categories: 技术
---


## 基础使用
### 基础命令
1. mvn clean    清空构建包文件
2. mvn compiler 编译源文件
3. mvn deploy   部署构建包
4. mvn failsafe 集成测试
5. mvn install  构建包文件到本地repository
6. mvn resources实现不同环境下配置的替换
7. mvn site     生成站点，根据report节点
8. mvn surefire 用例测试
9. mvn verifier 构建包验证

### 扩展使用命令
1. mvn archetype:generate 创建项目骨架

### settings.xml配置

  1. 整体配置

    <settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                          https://maven.apache.org/xsd/settings-1.0.0.xsd">
      <!--简单配置-->
      <localRepository><localRepository/><!--本地仓库位置，用于包依赖管理；同时本地构建会将包放置在本地仓库-->
      <interactiveMode><interactiveMode/><!--配置是否与用户进行交互输入-->
      <usePluginRegistry><usePluginRegistry/><!--默认是false,用于管理plugins版本，通过${user.home}/.m2/plugin-registry.xml文件进行版本管理-->
      <offline><offline/><!--配置是否以离线方式进行依赖管理和项目构建-->
      <!--复杂多节点配置-->
      <pluginGroups><pluginGroups/><!--插件管理-->
      <servers><servers/>
      <mirrors><mirrors/>
      <proxies><proxies/>
      <profiles>
        <profile>
          <activation></activation>
          <properties></properties>
          <repositories></repositories>
        </profile>
      <profiles/>
      <activeProfiles><activeProfiles/>
    </settings>

  2. servers节点配置：

    <servers>
        <server>
          <id>server001</id><!--maven所连接的repository/mirror唯一编号-->
          <username>my_login</username><!--repository/mirror服务器名称-->
          <password>my_password</password><!--repository/mirror服务器密码-->
          <privateKey>${user.home}/.ssh/id_dsa</privateKey><!--repository/mirror服务器私钥-->
          <passphrase>some_passphrase</passphrase><!--repository/mirror服务器密钥-->
          <filePermissions>664</filePermissions><!--repository/mirror服务器文件创建权限，对应unix文件权限编号-->
          <directoryPermissions>775</directoryPermissions><!--repository/mirror服务器目录创建权限，对应unix目录权限编号-->
          <configuration></configuration><!--repository/mirror服务器配置信息-->
        </server>
      </servers>

  3. mirrors节点配置：

    <mirror>
        <id>planetmirror.com</id><!--镜像站id,用于标识mirror；同时可与server节点相关联-->
        <name>PlanetMirror Australia</name><!--镜像站name-->
        <url>http://downloads.planetmirror.com/pub/maven2</url><!--镜像站url-->
        <mirrorOf>central</mirrorOf><!--镜像站内仓库地址，central表示主仓库，可与id相关联-->
    </mirror>    

  4. proxies节点配置:

    <proxy>
      <id>myproxy</id><!--代理id-->
      <active>true</active><!--是否开启代理-->
      <protocol>http</protocol><!--代理连接协议-->
      <host>proxy.somewhere.com</host><!--代理主机ip-->
      <port>8080</port><!--代理主机端口号-->
      <username>proxyuser</username><!--代理主机用户名-->
      <password>somepassword</password><!--代理主机密码-->
      <nonProxyHosts>*.google.com|ibiblio.org</nonProxyHosts><!--代理过滤主机-->
    </proxy>  

  5. activation节点配置:

    说明:根据环境参数调整构建系统，仅用于配置系统相关的环境参数(与pom.xml的profile节点相对应)
    <profile><!--包含(activation,repositories,pluginRepositories,properties)四个节点，用于配置构建系统-->
      <id>test</id>
      <activation>
        <activeByDefault>false</activeByDefault>
        <jdk>1.5</jdk><!--activation有一个内建的java版本检测，如果检测到jdk版本与期待的一样，profile被激活。 -->
        <os>
          <name>Windows XP</name>
          <family>Windows</family>
          <arch>x86</arch>
          <version>5.1.2600</version>
        </os>
        <property>
          <name>mavenVersion</name>
          <value>2.0.3</value>
        </property>
        <file><!--指定目录文件存在，profile被激活。 -->
          <exists>${basedir}/file2.properties</exists>
          <missing>${basedir}/file1.properties</missing>
        </file>
      </activation>
    </profile>


  6. properties节点配置:

    <profiles><!--${user.install}配置可应用于全局-->
       <profile>
         <properties>
           <user.install>${user.home}/our-project</user.install>
         </properties>
       </profile>
     </profiles>

  7. repositories节点配置:

    <profile>
       <repositories><!--远程仓库配置-->
         <repository>
           <id>codehausSnapshots</id>
           <name>Codehaus Snapshots</name>
           <releases><!--发布版本信息配置-->
             <enabled>false</enabled><!--是否开启发布版本依赖构件下载-->
             <updatePolicy>always</updatePolicy><!--构件更新策略，用pom文件时间戳进行匹配,always or daily or interval:X or never-->
             <checksumPolicy>warn</checksumPolicy><!--构件更新失败提示策略-->
           </releases>
           <snapshots><!--快照版本信息配置-->
             <enabled>true</enabled><!--是否开启快照版本依赖构件下载-->
             <updatePolicy>never</updatePolicy><!--构件更新策略，用pom文件时间戳进行匹配-->
             <checksumPolicy>fail</checksumPolicy><!--构件更新失败提示策略-->
           </snapshots>
           <url>http://snapshots.maven.codehaus.org/maven2</url><!--远程仓库url-->
           <layout>default</layout><!--用于定位和排序构件的仓库布局类型,default or legacy-->
         </repository>
       </repositories>
       <pluginRepositories><!-- 远程插件仓库配置 -->
       </pluginRepositories>
     </profile>


### pom.xml配置

    1. 整体配置：

      <project xmlns="http://maven.apache.org/POM/4.0.0"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                            http://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion><!--POM文件版本，4.0.0说明POM支持2&3版本的maven-->

        <!-- The Basics -->
        <!-- 说明:版本标识  <主版本>.<次版本>.<增量版本>-<限定符>-->
        <groupId></groupId><!--通常是组织或项目的唯一表示，用于表示项目的主目录结构-->
        <artifactId></artifactId><!--代表项目名称，用于项目的唯一标识-->
        <version></version><!--代表项目版本，用于定位唯一版本项目-->
        <packaging></packaging><!--打包方式,主要包括 jar or war，默认打包方式是jar-->
        <classifier></classifier><!--用于生成构建包-->
        <dependencies></dependencies>
        <parent></parent>
        <dependencyManagement></dependencyManagement>
        <modules></modules>
        <properties></properties>

        <!-- Build Settings -->
        <build></build>
        <reporting></reporting>

        <!-- More Project Information -->
        <name></name><!--项目别名-->
        <description></description><!--项目描述-->
        <url></url><!--项目路径-->
        <inceptionYear></inceptionYear><!--项目修改路径-->
        <licenses></licenses><!--项目协议-->
        <organization></organization><!--项目所在组织-->
        <developers></developers><!--项目开发者列表-->
        <contributors></contributors><!--贡献者列表-->

        <!-- Environment Settings -->
        <issueManagement></issueManagement><!--缺陷追踪系统信息-->
        <ciManagement></ciManagement><!--配置持续集成管理系统-->
        <mailingLists></mailingLists><!--管理邮箱列表-->
        <scm></scm><!--软件管理信息-->
        <prerequisites></prerequisites>
        <repositories></repositories>
        <pluginRepositories></pluginRepositories>
        <distributionManagement></distributionManagement>
        <profiles></profiles>
      </project>

  2. dependencies节点配置说明:

    <dependencies><!--maven包依赖管理-->
     <dependency>
       <groupId>junit</groupId><!--依赖主版本-->
       <artifactId>junit</artifactId><!--依赖次版本-->
       <version>4.0</version><!--依赖版本号-->
       <type>jar</type><!--依赖打包类型-->
       <scope>test</scope><!--指定依赖使用范围-->
       <systemPath></systemPath><!--仅适用于scope节点为system-->
       <optional>true</optional><!--将依赖设置为可选依赖，不进行依赖传递-->
       <exclusions><!--排除依赖，用于解除依赖传递-->
         <exclusion>
           <groupId>org.apache.maven</groupId>
           <artifactId>maven-core</artifactId>
         </exclusion>
       </exclusions>
     </dependency>
   </dependencies>

     a. 下载指定依赖:mvn install: install-file -Dfile=non-maven-proj.jar -DgroupId=some.group -DartifactId=non-maven-proj -Dversion=1 -Dpackaging=jar
     b. scope(依赖作用域):
       1. compile(默认依赖作用域)
       2. provided(说明依赖有JDK或虚拟机提供)
       3. runtime(说明依赖作用于运行测试期间，但是不在编译类路径)
       4. test(说明依赖只在测试编译和测试执行期间引入)
       5. system(说明依赖由JDK或虚拟机提供，与systemPath节点相关)
       6. import(导入另一个POM中 dependency management 里声明的依赖仲裁)

     c. inheritance(继承管理)
     <parent><!--定义父节点-->
      <groupId>org.codehaus.mojo</groupId>
      <artifactId>my-parent</artifactId>
      <version>2.0</version>
      <relativePath>../my-parent</relativePath>
    </parent>

    d. Aggregation(集成管理):
    <modules>
     <module>my-project</module>
     <module>another-project</module>
     <module>third-project/pom-example.xml</module>
    </modules>    



 3. build节点配置:

         <!--包括两种方式-->
         <build></build>
         <profiles>
           <profile>
             <!-- "Profile Build" contains a subset of "Project Build"s elements -->
             <build>...</build>
           </profile>
         </profiles>

        a. 全局基本节点
         <build>
           <defaultGoal>install</defaultGoal><!--设置构建目标-->
           <directory>${basedir}/target</directory><!--构建目标路径-->
           <finalName>${artifactId}-${version}</finalName><!--构建结果名称-->
           <filters><!--配置构建参数-->
             <filter>filters/filter1.properties</filter>
           </filters>
         </build>

         b. resources节点配置：
         <resources>
           <resource>
             <targetPath>META-INF/plexus</targetPath>
             <filtering>false</filtering>
             <directory>${basedir}/src/main/plexus</directory>
             <includes>
               <include>configuration.xml</include>
             </includes>
             <excludes>
               <exclude>**/*.properties</exclude>
             </excludes>
           </resource>
         </resources>

         c. plugins节点配置：
         <plugins>
            <plugin>
              <groupId>org.apache.maven.plugins</groupId>
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


### 生命周期
1. clean周期
2. 默认周期
3. site周期

## 插件管理
1. maven-assembly-plugin
  用于将指定文件进行自定义打包
2. maven-dependency-plugin
  检查pom依赖关系：
     Used undeclared dependencies: 表示项目中使用到的，但是没有显示声明的依赖
     Unused declared dependencies: 表示项目中未使用的，但显示声明的依赖
  运行命令:
3. maven-resources-plugin
4. maven-compiler-plugin
5. maven-surefire-plugin
6. maven-jar-plugin
7. maven-install-plugin
