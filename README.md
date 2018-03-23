# Spring Boot Guide

Spring Boot Reference Guide for 2.0.0.RELEASE


# I. Spring Boot 文档
## 1. 关于
## 2. 帮助
## 3. 第一步
## 4. Spring Boot 使用
## 5. Spring Boot 特性
## 6. 生产使用
## 7. 高级特性

# II. 入门
## 8. Spring Boot 介绍
## 9. 系统要求
### 9.1. Servlet 容器
## 10. Spring Boot 安装
### 10.1. Java 环境安装说明
#### 10.1.1. Maven 安装
#### 10.1.2. Gradle 安装
### 10.2. Spring Boot CLI 安装
#### 10.2.1. 手动安装
#### 10.2.2. SDKMAN 安装
#### 10.2.3. OSX Homebrew 安装
#### 10.2.4. MacPorts 安装
#### 10.2.5. Command-line 工作
#### 10.2.6. Spring CLI 入门示例
### 10.3. Spring Boot 旧版本升级
## 11. 开发你的第一个 Spring Boot 应用
### 11.1. 创建 POM
### 11.2. 添加类路径依赖关系
### 11.3. 绑定代码
#### 11.3.1. @RestController 和 @RequestMapping 注解
#### 11.3.2. @EnableAutoConfiguration 注解
#### 11.3.3. “main” 方法
### 11.4. 运行示例
### 11.5. 创建可执行 Jar 包
## 12. 接下来要阅读的内容

# III. 使用 Spring Boot
## 13. 构建
### 13.1. 依赖管理
### 13.2. Maven
#### 13.2.1. 继承 Starter Parent
#### 13.2.2. 使用 Spring Boot 不依赖父 POM
#### 13.2.3. 使用 Spring Boot Maven 插件
### 13.3. Gradle
### 13.4. Ant
### 13.5. Starters

## 14. 组织你的代码
### 14.1. 使用“默认”包
### 14.2. 查找主要应用程序类

## 15. 配置类
### 15.1. 导入其他配置类
### 15.2. 导入 XML 配置

## 16. Auto-configuration
### 16.1. 逐渐替换 Auto-configuration
### 16.2. 禁用特定的 Auto-configuration 类

## 17. Spring Beans 和依赖注入
## 18. 使用 @SpringBootApplication 注解
## 19. 运行你的应用
### 19.1. 使用 IDE 运行
### 19.2. 运行打包应用
### 19.3. 使用 Maven 插件
### 19.4. 使用 Gradle 插件
### 19.5. 热交换

## 20. 开发工具
### 20.1. 属性默认值
### 20.2. 自动重启
#### 20.2.1. 记录条件评估中的更改
#### 20.2.2. 排除资源
#### 20.2.3. 观察额外的路径
#### 20.2.4. 禁用重新启动
#### 20.2.5. 使用触发文件
#### 20.2.6. 自定义重启类加载器
#### 20.2.7. 已知限制
### 20.3. 实时加载
### 20.4. 全局设置
### 20.5. 远程应用
#### 20.5.1. 运行远程客户应用
#### 20.5.2. 远程更新

## 21. 为生产环境打包应用
## 22. 接下来要阅读的内容


# I. Spring Boot 文档

本节主要是简要介绍Spring Boot参考文档。它作为文档其余部分的指引。

## 1. 关于

文档的形式：

* HTML
* PDF
* EPUB

>Copies of this document may be made for your own use and for distribution to others, provided that you do not charge any fee for such copies and further provided that each copy contains this Copyright Notice, whether distributed in print or electronically.

## 2. 帮助

如果您在Spring Boot遇到问题，我们希望能提供帮助。

## 3. 第一步

如果您正准备开始使用 Spring Boot 或 Spring ，请从以下主题开始:

* 从头开始: Overview | Requirements | Installation
* 教程: Part 1 | Part 2
* 运行例子: Part 1 | Part 2

## 4. Spring Boot 使用

准备好真正开始使用 Spring Boot 吗？

* 构建工具: Maven | Gradle | Ant | Starters
* 最佳实践: Code Structure | @Configuration | @EnableAutoConfiguration | Beans and Dependency Injection
* 运行你的代码: IDE | Packaged | Maven | Gradle
* 打包应用: Production jars
* Spring Boot CLI: Using the CLI

## 5. Spring Boot 特性

需要更多关于 Spring Boot 核心功能的细节？ 为你准备了以下内容:

* 核心特性: SpringApplication | External Configuration | Profiles | Logging
* Web 应用: MVC | Embedded Containers
* 使用数据库: SQL | NO-SQL
* 消息: Overview | JMS
* 测试: Overview | Boot Applications | Utils
* 扩展: Auto-configuration | @Conditions

## 6. 生产使用

当你准备部署你的 Spring Boot 应用到生产环境中, 我们有一些你可能会喜欢的技巧:

* 管理端点: Overview | Customization
* 连接选项: HTTP | JMX
* 监控: Metrics | Auditing | Tracing | Process

## 7. 高级特性

最后, 我们为高级用户提供了一些特性:

* Spring Boot 应用部署: Cloud Deployment | OS Service
* 构建工具: Maven | Gradle
* 附录: Application Properties | Auto-configuration classes | Executable Jars


# II. 入门

如果您正准备开始使用Spring Boot，或者使用“Spring”，请先阅读本节。

它回答了基本的“what？”，“how？”和“why？”的问题。它包括Spring Boot的介绍以及安装说明。

然后，我们将引导您构建您的第一个Spring Boot应用程序，并在讨论一些核心原则。

## 8. Spring Boot 介绍

Spring Boot可以轻松创建可独立运行的、生产级的基于Spring的应用程序。我们对Spring平台和第三方库采取自己的解决方案，以便您少遇问题。大多数Spring Boot应用程序只需要很少的Spring配置。 您可以使用Spring Boot来创建一个java应用程序，这个应用程序可以使用 `java -jar` 或更传统的 war 包部署启动。我们还提供了一个运行“spring scripts”的命令行工具。

我们的主要目标是:

* 为所有Spring开发提供一个更快，更广泛的入门体验。
* 提供开箱即用的默认配置，但这些默认配置可随需求变化而改动。
* 提供大型项目通用的一系列非功能性功能。（如嵌入式服务器，安全性，指标，运行状况检查和外部配置）
* 绝对不会生成代码，并且不需要XML配置。

## 9. 系统要求

Spring Boot 2.0.0.RELEASE 需要：

1. Java 8 or Java 9
2. Spring Framework 5.0.4.RELEASE 或更高. 
3. Maven 3.2+ 和 Gradle 4.

### 9.1. Servlet 容器

Spring Boot 支持以下嵌入式 servlet 容器:

|名称	|Servlet 版本
|---|---
|Tomcat 8.5 |3.1
|Jetty 9.4 |3.1
|Undertow 1.4 |3.1

你也可以将 Spring Boot 应用部署到任何兼容 Servlet 3.0+ 的容器中。

## 10. Spring Boot 安装

Spring Boot可以与“classic”Java开发工具一起使用，也可以作为命令行工具安装。无论哪种方式，您都需要Java SDK v1.8或更高版本。在开始之前，您应该使用以下命令检查当前的Java安装：

```shell
$ java -version
```
如果您对Java开发不熟悉，或者想要试验Spring Boot，则可能需要先尝试Spring Boot CLI（命令行界面）。否则，请阅读“classic”安装说明。

### 10.1. Java 环境安装说明

您可以像使用任何标准Java库一样使用Spring Boot。为此，请在类路径中包含相应的`spring-boot-*.jar`文件。 Spring Boot不需要任何特殊的工具集成，因此您可以使用任何IDE或文本编辑器。此外，Spring Boot应用程序没有什么特别之处，因此您可以像运行其他任何Java程序一样运行和调试Spring Boot应用程序。

虽然您可以复制Spring Boot jar，但我们通常建议您使用支持依赖管理的构建工具（如Maven或Gradle）。

#### 10.1.1. Maven 安装

Spring Boot与Apache Maven 3.2或更高版本兼容。如果您尚未安装Maven，则可以按照maven.apache.org上的说明进行操作。

在许多操作系统上，Maven可以与包管理器一起安装。

如果您使用OSX Homebrew，请尝试 `brew install maven`。 

Ubuntu用户可以运行 `sudo apt-get install maven`。

具有Chocolatey的Windows用户可以在管理员权限提示符下运行 `choco install maven`。

Spring Boot依赖使用 `org.springframework.boot` `groupId`。通常，您的Maven POM文件继承自`spring-boot-starter-parent`项目并将依赖关系声明为一个或多个“Starter”。 Spring Boot还提供了一个可选的 Maven plugin 来创建可执行的jar。

以下列表显示了一个典型的pom.xml文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.example</groupId>
	<artifactId>myproject</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<!-- Inherit defaults from Spring Boot -->
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.0.0.RELEASE</version>
	</parent>

	<!-- Add typical dependencies for a web application -->
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
	</dependencies>

	<!-- Package as an executable jar -->
	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>

```

`Spring-Boot-starter-parent` 是使用Spring Boot的好方法，但它可能并不适合所有的时间。有时您可能需要从不同的父POM继承，或者您可能不喜欢我们的默认设置。在这些情况下，请参见第13.2.2节“使用没有父POM的Spring Boot”，了解使用导入范围的替代解决方案。

#### 10.1.2. Gradle 安装

Spring Boot 与Gradle 4兼容。如果您尚未安装Gradle，可以按照 gradle.org/ 上的说明进行操作。

Spring Boot 依赖可以通过使用`org.springframework.boot` `group`声明。通常，您的项目将依赖项声明为一个或多个“Starter”。 Spring Boot提供了一个有用的 Gradle plugin，可以用来简化依赖声明和创建可执行的jar。

Gradle Wrapper 

当您需要构建项目时，Gradle Wrapper提供了一种“获取”Gradle的好方法。这是一个小脚本和库，与代码一起提交以引导构建过程。有关详细信息，请参阅

docs.gradle.org/4.2.1/userguide/gradle_wrapper.html。

以下示例显示了一个典型的build.gradle文件：

```java
plugins {
	id 'org.springframework.boot' version '2.0.0.RELEASE'
	id 'java'
}


jar {
	baseName = 'myproject'
	version =  '0.0.1-SNAPSHOT'
}

repositories {
	jcenter()
}

dependencies {
	compile("org.springframework.boot:spring-boot-starter-web")
	testCompile("org.springframework.boot:spring-boot-starter-test")
}
```

### 10.2. Spring Boot CLI 安装

Spring Boot CLI（Command Line Interface）是一个命令行工具，您可以使用它来快速使用Spring进行原型开发。它可以让你运行Groovy脚本，这意味着你有一个熟悉的类Java语法，没有太多的样板代码。 

您不需要使用CLI来使用Spring Boot，但它绝对是让Spring应用程序实现最快的最快捷方式。

#### 10.2.1. 手动安装

您可以从Spring软件存储库下载Spring CLI分发版：

* spring-boot-cli-2.0.0.RELEASE-bin.zip
* spring-boot-cli-2.0.0.RELEASE-bin.tar.gz

最先进的快照分布也可用。 

下载完成后，请按照解压缩归档中的 INSTALL.txt 说明进行操作。总之，在`.zip`文件的`bin/` 目录中有一个spring 脚本（用于Windows的`spring.bat`）。或者，您可以使用带有`.jar` 文件的 `java -jar`（该脚本可帮助您确定类路径设置正确）。

#### 10.2.2. SDKMAN 安装

SDKMAN!（The Software Development Kit Manager）可用于管理各种二进制SDK的多个版本，包括 Groovy 和 Spring Boot CLI。获取 SDKMAN！从 sdkman.io 安装并使用以下命令安装Spring Boot：

```
$ sdk install springboot
$ spring --version
Spring Boot v2.0.0.RELEASE
```
如果您为CLI开发功能并希望轻松访问您构建的版本，请使用以下命令：

```
$ sdk install springboot dev /path/to/spring-boot/spring-boot-cli/target/spring-boot-cli-2.0.0.RELEASE-bin/spring-2.0.0.RELEASE/
$ sdk default springboot dev
$ spring --version
Spring CLI v2.0.0.RELEASE
```
 
前面的指令安装一个称为`dev`实例的`spring`的本地实例。它指向您的目标构建位置，所以每次重建Spring Boot时，`spring`都是最新的。

您可以通过运行以下命令来查看它：

```
$ sdk ls springboot

================================================================================
Available Springboot Versions
================================================================================
> + dev
* 2.0.0.RELEASE

================================================================================
+ - local version
* - installed
> - currently in use
================================================================================
```

#### 10.2.3. OSX Homebrew 安装

如果您在Mac上并使用Homebrew，则可以使用以下命令安装Spring Boot CLI：

```
$ brew tap pivotal/tap
$ brew install springboot
```

Homebrew 安装 spring 到 /usr/local/bin 目录下。

> 如果您没有看到该项目，那么您的brew的安装可能会过时。在这种情况下，运行`brew update`并重试。

#### 10.2.4. MacPorts 安装

如果您在Mac上并使用MacPorts，则可以使用以下命令安装Spring Boot CLI：

```
$ sudo port install spring-boot-cli
```

#### 10.2.5. Command-line 工作

Spring Boot CLI包含为 BASH 和 zsh shell 提供命令完成的脚本。您可以在任何shell中将该脚本（也称为spring）源代码或将其放入个人或系统范围的bash完成初始化中。在Debian系统中，系统范围的脚本位于`/shell-completion/bash`中，并且在新shell启动时执行该目录中的所有脚本。

例如，要通过使用SDKMAN！安装，手动运行脚本，请使用以下命令：

```
$ . ~/.sdkman/candidates/springboot/current/shell-completion/bash/spring
$ spring <HIT TAB HERE>
  grab  help  jar  run  test  version
```

> 如果您使用Homebrew或MacPorts安装Spring Boot CLI，则命令行完成脚本会自动在您的shell中注册。

#### 10.2.6. Spring CLI 入门示例

您可以使用以下Web应用程序来测试您的安装。首先，创建一个名为`app.groovy`的文件，如下所示：

```
@RestController
class ThisWillActuallyRun {

	@RequestMapping("/")
	String home() {
		"Hello World!"
	}
}
```

然后从shell运行它，如下所示:

```
$ spring run app.groovy
```

在网页浏览器中打开 localhost:8080。您应该看到以下输出：

```
Hello World!
```

### 10.3. Spring Boot 旧版本升级

如果您是从早期版本的Spring Boot进行升级，请查看项目wiki上的“迁移指南”，其中提供了详细的升级说明。还要检查“发行说明”，以获取每个发行版的“新功能”和“值得注意”功能列表。

要升级现有的CLI安装，请使用相应的软件包管理器命令（例如，`brew upgrade`），或者如果您手动安装了CLI，请遵循标准说明，记住更新`PATH`环境变量以删除所有旧的引用。

## 11. 开发你的第一个 Spring Boot 应用

本节介绍如何开发一个简单的“Hello World！”Web应用程序，该应用程序重点介绍Spring Boot的一些主要功能。

我们使用Maven来构建这个项目，因为大多数IDE都支持它。

在开始之前，请打开终端并运行以下命令以确保您已安装了Java和Maven的有效版本：

```
$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)
```

```
$ mvn -v
Apache Maven 3.3.9 (bb52d8502b132ec0a5a3f4c09453c07478323dc5; 2015-11-10T16:41:47+00:00)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation
```

此示例需要在其自己的文件夹中创建。后续说明假定您已经创建了合适的文件夹，并且它是您当前的目录。

### 11.1. 创建 POM

我们需要从创建一个Maven pom.xml文件开始。 pom.xml是用于构建项目的配方。

打开您最喜欢的文本编辑器并添加以下内容：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.example</groupId>
	<artifactId>myproject</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.0.0.RELEASE</version>
	</parent>

	<!-- Additional lines to be added here... -->

</project>
```

前面的列表应该给你一个工作版本。您可以通过运行mvn包来测试它（现在，您可以忽略“jar将为空 - 没有内容被标记为包含！”警告）。


>此时，您可以将项目导入IDE（大多数现代Java IDE包含对Maven的内置支持）。为了简单起见，我们在本例中继续使用纯文本编辑器。

### 11.2. 添加类路径依赖关系

Spring Boot提供了许多“Starters”，这可让您将jar添加到类路径中。我们的示例应用程序已经在POM的父节点中使用了`spring-boot-starter-parent`。 `spring-boot-starter-parent`是一个特别的启动器，它提供了有用的Maven默认值。它还提供了一个`dependency-management` 部分，以便您可以省略“version”依赖项的版本标签。

其他“Starters”提供了在开发特定类型的应用程序时可能需要的依赖关系。由于我们正在开发一个Web应用程序，因此我们添加了`spring-boot-starter-web`依赖项。在此之前，我们可以通过运行以下命令来查看我们目前的功能：

```
$ mvn dependency:tree

[INFO] com.example:myproject:jar:0.0.1-SNAPSHOT
``

`mvn dependency:tree` 命令打印项目依赖关系的树形表示。你可以看到`spring-boot-starter-parent`本身不提供依赖关系。要添加必要的依赖关系，请编辑您的pom.xml并在父节点下方添加`spring-boot-starter-web`依赖项：

```xml
<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
</dependencies>
```

如果您再次运行 `mvn dependency：tree`，则会发现现在还有许多其他依赖项，包括Tomcat Web服务器和Spring Boot本身。


### 11.3. 编写代码

为了完成我们的应用程序，我们需要创建一个Java文件。默认情况下，Maven会从 `src/main/java` 编译源代码，因此您需要创建该文件夹结构，然后添加名为 `src/main/java/Example.java` 的文件以包含以下代码：

```java
import org.springframework.boot.*;
import org.springframework.boot.autoconfigure.*;
import org.springframework.web.bind.annotation.*;

@RestController
@EnableAutoConfiguration
public class Example {

	@RequestMapping("/")
	String home() {
		return "Hello World!";
	}

	public static void main(String[] args) throws Exception {
		SpringApplication.run(Example.class, args);
	}

}
```

虽然这里没有太多的代码，但还是有很多。我们将在接下来的几节中介绍一些重要的部分。

#### 11.3.1. @RestController 和 @RequestMapping 注解

我们的`Example`类的第一个注释是`@RestController`。这被称为刻板印记。它为阅读代码的人提供了线索，对于Spring来说，这个类扮演着特定的角色。在这种情况下，我们的类是一个web `@Controller`，所以Spring在处理传入的Web请求时会考虑它。 

`@RequestMapping`注释提供了“routing”信息。它告诉Spring，任何带有`/` 路径的HTTP请求都应该映射到`home`方法。 `@RestController`注释告诉Spring将结果字符串直接呈现给调用者。

> `@RestController` 和 `@RequestMapping` 注解是Spring MVC注释。 （它们并不特定于Spring Boot。）有关更多详细信息，请参阅Spring参考手册中的MVC部分。

#### 11.3.2. @EnableAutoConfiguration 注解

第二个类级注释是 `@EnableAutoConfiguration`。这个注解告诉Spring Boot根据你添加的jar依赖来“猜测”你想要如何配置Spring。由于 `spring-boot-starter-web` 添加了Tomcat和Spring MVC，因此自动配置假定您正在开发Web应用程序并相应地设置Spring。

```
启动器和自动配置

自动配置旨在与“Starter”配合使用，但这两个概念并不直接相关。您可以自由选择初学者之外的jar依赖项。 Spring Boot仍然尽力自动配置您的应用程序。
```

#### 11.3.3. “main” 方法

我们应用程序的最后一部分是 `main` 方法。这只是遵循Java约定的应用程序入口点的标准方法。我们的主要方法通过调用 `run` 来委托 `Spring Boot` 的 `SpringApplication` 类。 SpringApplication启动我们的应用程序，从Spring开始，然后启动自动配置的Tomcat Web服务器。我们需要将 `Example.class` 作为参数传递给run方法，以告知`SpringApplication` 是Spring的主要组件。 args数组也被传递以暴露任何命令行参数。

### 11.4. 运行示例

这时，你的应用程序应该工作。由于您使用了 `spring-boot-starter-parent` POM，因此您可以使用有用的`run`目标来启动应用程序。键入 `mvn spring-boot:run` 从根项目目录运行以启动应用程序。您应该看到类似于以下内容的输出：

```
$ mvn spring-boot:run

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v2.0.0.RELEASE)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.222 seconds (JVM running for 6.514)
```

如果您打开一个Web浏览器到 `http://localhost:8080` ，您应该看到以下输出：

```
Hello World!
```

要正常退出应用程序，请按 ctrl-c。

### 11.5. 创建可执行 Jar 包

我们通过创建一个完全独立的可执行jar文件来完成我们的示例，该文件可以在生产环境中运行。可执行jar（有时称为“fat jars”）是包含您的编译类以及您的代码需要运行的所有jar依赖项的归档文件。

可执行的 jars 和 Java 

Java没有提供加载嵌套jar文件的标准方式（本身包含在jar中的jar文件）。如果您想分发自包含的应用程序，这可能会有问题。 

为了解决这个问题，许多开发者使用 “uber” jars。一个超级jar将所有应用程序依赖关系中的所有类打包到一个单独的存档中。这种方法的问题是很难看到你的应用程序中有哪些库。如果在多个 jar 中使用相同的文件名（但是具有不同的内容），则它也可能是有问题的。 

Spring Boot 采用了不同的方法，可以让您直接嵌入 jars。

要创建一个可执行的 jar，我们需要将 `spring-boot-maven-plugin` 添加到我们的pom.xml中。为此，请在依赖性部分的下面插入以下几行：

```xml
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>
```

`spring-boot-starter-parent` POM包含 `<executions>` 配置来绑定重新打包目标。如果您不使用父POM，则需要自行声明此配置。有关详细信息，请参阅插件文档。

保存你的pom.xml并从命令行运行mvn包，如下所示：

```
$ mvn package

[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building myproject 0.0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] .... ..
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ myproject ---
[INFO] Building jar: /Users/developer/example/spring-boot-example/target/myproject-0.0.1-SNAPSHOT.jar
[INFO]
[INFO] --- spring-boot-maven-plugin:2.0.0.RELEASE:repackage (default) @ myproject ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```

如果您查看目标目录，则应该看到 `myproject-0.0.1-SNAPSHOT.jar`。该文件的大小应该在10 MB左右。

如果你想在里面偷看，你可以使用 `java -jar`，如下所示：

```
$ jar tvf target/myproject-0.0.1-SNAPSHOT.jar
```

您还应该在目标目录中看到名为 `myproject-0.0.1-SNAPSHOT.jar.original` 的小得多的文件。这是Maven在被`Spring Boot`重新包装之前创建的原始jar文件。

要运行该应用程序，请使用`java -jar`命令，如下所示：

```
$ java -jar target/myproject-0.0.1-SNAPSHOT.jar

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v2.0.0.RELEASE)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.536 seconds (JVM running for 2.864)
```

和以前一样，要退出应用程序，请按ctrl-c。

## 12. 接下来要阅读的内容

希望本节提供了一些Spring Boot的基础知识，并帮助您编写自己的应用程序。如果您是面向任务的开发人员，则可能需要跳至spring.io，查看一些入门指南，以解决具体的“我该如何使用Spring？”问题。我们也有Spring Boot专用的“How-to”参考文档。

Spring Boot存储库还有一堆你可以运行的样本。样本与代码的其余部分无关（也就是说，您不需要构建其余代码以运行或使用样本）。

否则，下一个逻辑步骤是阅读第三部分“使用Spring Boot”。如果你真的不耐烦，你也可以跳到前面阅读Spring Boot的功能。


# III. 使用 Spring Boot

本节将详细介绍如何使用Spring Boot。它涵盖了构建系统，自动配置以及如何运行应用程序等主题。我们还介绍了一些Spring Boot的最佳实践。尽管Spring Boot没有特别的特殊之处（它只是您可以使用的另一个库），但有一些建议，如果遵循这些建议，您的开发过程会更容易一些。

如果您刚开始使用Spring Boot，那么在深入本节之前，您应该阅读入门指南。

## 13. 构建

强烈建议您选择支持依赖关系管理的构建系统，并且可以使用发布到“Maven Central”存储库的构件。我们建议您选择 Maven 或 Gradle。 Spring Boot可以与其他构建系统（例如Ant）一起工作，但它们并没有得到特别好的支持。


### 13.1. 依赖管理

Spring Boot的每个发行版都提供了它支持的依赖关系的策略列表。实际上，您不需要为构建配置中的任何这些依赖项提供版本，因为Spring Boot为您管理这些版本。当您升级Spring Boot本身时，这些依赖关系也会以一致的方式升级。

> 如果需要的话，你仍然可以指定一个版本并覆盖Spring Boot的建议。

策划列表包含您可以在 Spring Boot 中使用的所有 Spring 模块以及第三方库的精炼列表。该列表可用作 Bills of Materials（spring-boot-dependencies），可用于 Maven 和Gradle。

> Spring Boot 的每个版本都与 Spring Framework 的基本版本相关联。我们强烈建议您不要指定其版本。

### 13.2. Maven

Maven用户可以继承 `spring-boot-starter-parent` 项目以获得合理的默认值。父项目提供以下功能：

* Java 1.8作为默认的编译器级别。
* UTF-8源码编码。
* 依赖管理部分，继承自spring-boot-dependencies pom，用于管理公共依赖的版本。这种依赖关系管理可以让您在自己的pom中使用这些依赖项时忽略<version>标记。
* 智能的资源过滤。
* 智能的插件配置（exec 插件，Git commit ID 和 shade）。
* 对 `application.properties` 和 `application.yml` 进行智能的资源过滤，包括特定于配置文件的文件（例如，`application-dev.properties` 和 `application-dev.yml`）

请注意，由于 `application.properties` 和 `application.yml` 文件接受Spring样式占位符（`$ {...}`），因此Maven过滤将更改为使用 `@..@` 占位符。 （您可以通过设置名为`resource.delimiter`的 Maven属性来覆盖该属性。）

#### 13.2.1. 继承 Starter Parent

要将项目配置为从`spring-boot-starter-parent`继承，请按如下所示设置父项：

```xml
<!-- Inherit defaults from Spring Boot -->
<parent>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-parent</artifactId>
	<version>2.0.0.RELEASE</version>
</parent>
```

> 您应该只需在此依赖项上指定Spring Boot版本号。如果您导入其他启动器，则可以安全地省略版本号。

通过该设置，您还可以通过覆盖自己项目中的属性来覆盖各个依赖项。例如，要升级到另一个`Spring Data`发行版，您可以将以下内容添加到您的pom.xml中：

```xml
<properties>
	<spring-data-releasetrain.version>Fowler-SR2</spring-data-releasetrain.version>
</properties>

```

> 检查`spring-boot-dependencies` pom以获取支持的属性列表。

#### 13.2.2. 使用 Spring Boot 不依赖父 POM

不是每个人都喜欢从`spring-boot-starter-parent` POM继承。您可能拥有自己的公司标准父项，或者您可能更愿意明确声明所有Maven配置

如果你不想使用`spring-boot-starter-parent`，你仍然可以通过使用`scope = import` dependency来保持依赖管理的好处（但不是插件管理），如下所示：

```xml
<dependencyManagement>
	<dependencies>
		<dependency>
			<!-- Import dependency management from Spring Boot -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>2.0.0.RELEASE</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>
```

如上所述，上述示例设置不会让您使用属性重写个别依赖关系。要达到相同的结果，需要在`spring-boot-dependencies`条目之前在项目的`dependencyManagement`中添加一个条目。例如，要升级到另一个Spring Data发行版，您可以将以下元素添加到您的pom.xml中：

```xml
<dependencyManagement>
	<dependencies>
		<!-- Override Spring Data release train provided by Spring Boot -->
		<dependency>
			<groupId>org.springframework.data</groupId>
			<artifactId>spring-data-releasetrain</artifactId>
			<version>Fowler-SR2</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>2.0.0.RELEASE</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>
```

> 在前面的例子中，我们指定了一个BOM，但是任何依赖类型都可以用相同的方式覆盖。

#### 13.2.3. 使用 Spring Boot Maven 插件

Spring Boot 包含一个Maven插件，可以将项目打包为可执行的jar。如果要使用插件，请将插件添加到`<plugins>`部分，如以下示例所示：

```xml
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>

```

> 如果您使用Spring Boot启动器父POM，则只需添加插件。除非您想更改父级中定义的设置，否则无需对其进行配置。

### 13.3. Gradle

要了解如何使用Spring Boot和Gradle，请参阅Spring Boot的Gradle插件的文档：

* 参考 (HTML and PDF)
* API

### 13.4. Ant

可以使用Apache Ant + Ivy构建Spring Boot项目。 `spring-boot-antlib` “AntLib”模块也可以帮助Ant创建可执行的jar文件。 为了声明依赖关系，典型的`ivy.xml`文件看起来像下面的例子：

```xml
<ivy-module version="2.0">
	<info organisation="org.springframework.boot" module="spring-boot-sample-ant" />
	<configurations>
		<conf name="compile" description="everything needed to compile this module" />
		<conf name="runtime" extends="compile" description="everything needed to run this module" />
	</configurations>
	<dependencies>
		<dependency org="org.springframework.boot" name="spring-boot-starter"
			rev="${spring-boot.version}" conf="compile" />
	</dependencies>
</ivy-module>
```

典型的build.xml如下例所示：

```xml
<project
	xmlns:ivy="antlib:org.apache.ivy.ant"
	xmlns:spring-boot="antlib:org.springframework.boot.ant"
	name="myapp" default="build">

	<property name="spring-boot.version" value="2.0.0.RELEASE" />

	<target name="resolve" description="--> retrieve dependencies with ivy">
		<ivy:retrieve pattern="lib/[conf]/[artifact]-[type]-[revision].[ext]" />
	</target>

	<target name="classpaths" depends="resolve">
		<path id="compile.classpath">
			<fileset dir="lib/compile" includes="*.jar" />
		</path>
	</target>

	<target name="init" depends="classpaths">
		<mkdir dir="build/classes" />
	</target>

	<target name="compile" depends="init" description="compile">
		<javac srcdir="src/main/java" destdir="build/classes" classpathref="compile.classpath" />
	</target>

	<target name="build" depends="compile">
		<spring-boot:exejar destfile="build/myapp.jar" classes="build/classes">
			<spring-boot:lib>
				<fileset dir="lib/runtime" />
			</spring-boot:lib>
		</spring-boot:exejar>
	</target>
</project>

```

> 如果您不想使用 `spring-boot-antlib`模块，请参见第86.9节 “在不使用`spring-boot-antlib`的情况下从Ant生成可执行文件”“操作方法”

### 13.5. Starters

启动器是一套方便的依赖描述符，可以包含在应用程序中。您可以获得所需的所有Spring及相关技术的一站式商店，而无需查看示例代码并复制粘贴依赖描述符。例如，如果您想开始使用Spring和JPA进行数据库访问，请在项目中包含 `spring-boot-starter-data-jpa` 依赖项。

starters 包含很多依赖项，您需要快速启动并快速运行项目，并且需要一组支持的可传递依赖关系。

> 怎么命名？
> 
> 所有官方首发者都遵循类似的命名模式; `spring-boot-starter-*`，其中`*`是特定类型的应用程序。这种命名结构旨在帮助您在需要查找启动器时。许多IDE中的Maven集成允许您按名称搜索依赖项。例如，通过安装适当的Eclipse或STS插件，您可以在POM编辑器中按`ctrl-space`并键入`spring-boot-starter`获取完整列表。
> 
> 正如“创建自己的启动器”部分所述，第三方启动器不应该从启动引导开始，因为它是为官方Spring Boot工件保留的。相反，第三方初学者通常以项目名称开头。例如，名为thirdpartyproject的第三方启动器项目通常会被命名为thirdpartyproject-spring-boot-starter。

以下应用程序 starters 由 Spring Boot 在`org.springframework.boot`组下提供：

Spring Boot application starters

|名字|描述|Pom
|---|---|---
|spring-boot-starter|核心启动，包含自动配置支持，logging and YAML|Pom
|spring-boot-starter-activemq|以JMS方式使用 Apache ActiveMQ|Pom
|spring-boot-starter-amqp|使用 Spring AMQP and Rabbit MQ|Pom
|spring-boot-starter-aop|使用Spring AOP and AspectJ 面向切面编程|Pom
|spring-boot-starter-artemis|以JMS方式使用 Apache Artemis|Pom
|spring-boot-starter-batch|使用 Spring Batch|Pom
|spring-boot-starter-cache|使用 Spring Framework’s caching|Pom
|spring-boot-starter-cloud-connectors|使用 Spring Cloud Connectors|Pom
|spring-boot-starter-data-cassandra|使用 Spring Data Cassandra|Pom
|spring-boot-starter-data-cassandra-reactive|使用响应式 Spring Data Cassandra|Pom
|spring-boot-starter-data-couchbase|使用 Spring Data Couchbase |Pom
|spring-boot-starter-data-couchbase-reactive|使用响应式 Spring Data Couchbase |Pom
|spring-boot-starter-data-elasticsearch|使用 Spring Data Elasticsearch|Pom
|spring-boot-starter-data-jpa|使用 Spring Data JPA with Hibernate|Pom
|spring-boot-starter-data-ldap|使用 Spring Data LDAP|Pom
|spring-boot-starter-data-mongodb|使用 Spring Data MongoDB |Pom
|spring-boot-starter-data-mongodb-reactive|使用响应式 Spring Data MongoDB |Pom
|spring-boot-starter-data-neo4j|使用 Spring Data Neo4j|Pom
|spring-boot-starter-data-redis|使用 Spring Data Redis|Pom
|spring-boot-starter-data-redis-reactive|使用响应式 Spring Data Redis|Pom
|spring-boot-starter-data-rest|使用 Spring Data REST|Pom
|spring-boot-starter-data-solr|使用 Apache Solr 搜索|Pom
|spring-boot-starter-freemarker|使用 FreeMarker 模板做视图层|Pom
|spring-boot-starter-groovy-templates|使用 Groovy 模板做视图层|Pom
|spring-boot-starter-hateoas|使用 Spring MVC 和 Spring HATEOAS|Pom
|spring-boot-starter-integration |使用 Spring Integration|Pom
|spring-boot-starter-jdbc |使用 Tomcat JDBC 连接池|Pom
|spring-boot-starter-jersey |使用 JAX-RS 和 Jersey|Pom
|spring-boot-starter-jooq |使用 jOOQ 访问 SQL 数据库|Pom
|spring-boot-starter-json |读写json|Pom
|spring-boot-starter-jta-atomikos |使用 Atomikos 做 JTA|Pom
|spring-boot-starter-jta-bitronix |使用 Bitronix 做 JTA|Pom
|spring-boot-starter-jta-narayana |使用 Spring Boot Narayana JTA|Pom
|spring-boot-starter-mail |使用 Java Mail 和 Spring Framework’s email|Pom
|spring-boot-starter-mustache |使用 Mustache 做视图层|Pom
|spring-boot-starter-quartz |使用 Spring Boot Quartz|Pom
|spring-boot-starter-security |使用 Spring Security|Pom
|spring-boot-starter-test |使用 JUnit, Hamcrest and Mockito 做测试|Pom
|spring-boot-starter-thymeleaf |使用 Thymeleaf 做视图层|Pom
|spring-boot-starter-validation |使用 Java Bean Validation with Hibernate Validator|Pom
|spring-boot-starter-web |使用 Spring MVC|Pom
|spring-boot-starter-web-services |使用 Spring Web Services|Pom
|spring-boot-starter-webflux |构建 WebFlux 应用|Pom
|spring-boot-starter-websocket |构建 WebSocket 应用|Pom

除应用程序启动器外，还可以使用以下启动器来添加生产准备功能：

Spring Boot production starters

|名字|描述|Pom
|---|---|---
|spring-boot-starter-actuator|帮助监控生产服务器的健康状况|Pom


最后，Spring Boot还包含以下启动器，如果您想要排除或交换特定技术方面，可以使用以下启动器：

|名字|描述|Pom
|---|---|---
|spring-boot-starter-jetty|Jetty容器|Pom
|spring-boot-starter-log4j2|log4j2日志系统|Pom
|spring-boot-starter-logging|logging日志系统|Pom
|spring-boot-starter-reactor-netty|响应式netty容器|Pom
|spring-boot-starter-tomcat|Tomcat容器|Pom
|spring-boot-starter-undertow|Undertow容器|Pom


## 14. 组织你的代码

Spring Boot不需要任何特定的代码布局来工作。但是，有一些最佳实践可以提供帮助。



### 14.1. 使用“默认”包

当一个类不包含包声明时，它被认为是在“默认包”中。通常不鼓励使用“默认包”，应该避免使用。对于使用`@ComponentScan`，`@EntityScan`或`@SpringBootApplication`批注的Spring Boot应用程序，它可能会导致特定问题，因为每个jar的每个类都被读取。

> 我们建议您遵循Java推荐的软件包命名约定并使用反向域名（例如，com.example.project）。

### 14.2. 查找主要应用程序类

我们通常建议您将主应用程序类定位在其他类上方的根包中。 `@EnableAutoConfiguration` 注释通常放在您的主类上，它隐式地为特定项目定义了一个基本“搜索包”。例如，如果您正在编写JPA应用程序，则使用`@EnableAutoConfiguration`注释类的包来搜索`@Entity`项目。

使用根包也可以使用`@ComponentScan`注释而无需指定`basePackage`属性。如果您的主类位于根包中，您还可以使用`@SpringBootApplication`注释。

下面的清单显示了一个典型的布局：

```
com
 +- example
     +- myapplication
         +- Application.java
         |
         +- customer
         |   +- Customer.java
         |   +- CustomerController.java
         |   +- CustomerService.java
         |   +- CustomerRepository.java
         |
         +- order
             +- Order.java
             +- OrderController.java
             +- OrderService.java
             +- OrderRepository.java
```

Application.java文件将声明主要方法以及基本的@Configuration，如下所示：

```java
package com.example.myapplication;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.EnableAutoConfiguration;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

@Configuration
@EnableAutoConfiguration
@ComponentScan
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

}
```

## 15. 配置类

Spring Boot 支持基于Java的配置。虽然可以将`SpringApplication`与XML源一起使用，但我们通常建议您的主源是一个`@Configuration`类。通常，定义主要方法的类作为主要`@Configuration`是一个很好的候选者。

> 许多使用XML配置的互联网上发布了Spring配置示例。如果可能，请始终尝试使用等效的基于Java的配置。搜索启用*注释可能是一个很好的起点。



### 15.1. 导入其他配置类

你不需要把你所有的`@Configuration`放到一个类中。 `@Import`注释可用于导入其他配置类。或者，您可以使用`@ComponentScan`自动获取所有Spring组件，包括`@Configuration`类。

### 15.2. 导入 XML 配置

如果您必须使用基于XML的配置，我们建议您仍以`@Configuration`类开头。然后您可以使用`@ImportResource`注释来加载XML配置文件。

## 16. Auto-configuration

Spring Boot自动配置会尝试根据您添加的jar依赖关系自动配置您的Spring应用程序。例如，如果HSQLDB在您的类路径中，并且您尚未手动配置任何数据库连接Bean，则Spring Boot会自动配置内存数据库。

您需要选择加入自动配置，方法是将`@EnableAutoConfiguration`或`@SpringBootApplication`注释添加到其中一个`@Configuration`类中。

> 您应该只添加一个`@EnableAutoConfiguration`注释。我们通常建议您将它添加到您的主要`@Configuration`类中。


### 16.1. 逐渐替换 Auto-configuration

自动配置是非侵入式的。在任何时候，您都可以开始定义自己的配置以替换自动配置的特定部分。例如，如果您添加自己的DataSource Bean，则默认的嵌入式数据库支持会被取消。 

如果您需要了解当前正在应用的自动配置以及为什么使用--debug开关启动应用程序。这样做可以为选定的核心记录器启用调试日志，并将条件报告记录到控制台。

### 16.2. 禁用特定的 Auto-configuration 类

如果您发现不需要的特定自动配置类正在应用，则可以使用@EnableAutoConfiguration的exclude属性来禁用它们，如以下示例所示：

```java
import org.springframework.boot.autoconfigure.*;
import org.springframework.boot.autoconfigure.jdbc.*;
import org.springframework.context.annotation.*;

@Configuration
@EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class})
public class MyConfiguration {

}
```

如果该类不在类路径中，则可以使用注释的`excludeName`属性并改为指定完全限定名称。最后，您还可以通过使用`spring.autoconfigure.exclude`属性来控制要排除的自动配置类的列表。

>您可以通过注释级别和使用属性来定义排除。

## 17. Spring Beans 和依赖注入

您可以自由使用任何标准的Spring框架技术来定义您的bean及其注入的依赖关系。为了简单起见，我们经常发现使用`@ComponentScan`（查找bean）和使用`@Autowired`（执行构造函数注入）效果很好。

如果按照上面的建议构建代码（将您的应用程序类定位到根包中），则可以添加`@ComponentScan`而不带任何参数。所有的应用程序组件（`@Component`，`@Service`，`@Repository`，`@Controller`等）都会自动注册为Spring Bean。

以下示例显示了一个`@Service` Bean，它使用构造函数注入来获取必需的RiskAssessor bean：

```java

package com.example.service;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

@Service
public class DatabaseAccountService implements AccountService {

	private final RiskAssessor riskAssessor;

	@Autowired
	public DatabaseAccountService(RiskAssessor riskAssessor) {
		this.riskAssessor = riskAssessor;
	}

	// ...

}
```

如果一个bean有一个构造函数，那么可以省略@Autowired，如下例所示：

```
@Service
public class DatabaseAccountService implements AccountService {

	private final RiskAssessor riskAssessor;

	public DatabaseAccountService(RiskAssessor riskAssessor) {
		this.riskAssessor = riskAssessor;
	}

	// ...

}
```

> 注意如何使用构造函数注入让riskAssessor字段被标记为final，表明它不能被随后改变。

## 18. 使用 @SpringBootApplication 注解

许多Spring Boot开发人员总是使用`@Configuration`，`@EnableAutoConfiguration`和`@ComponentScan`注解其主类。由于这些注释经常一起使用（特别是如果您遵循上述最佳实践），Spring Boot提供了一种方便的`@SpringBootApplication`替代方法。

`@SpringBootApplication`注释等价于使用`@Configuration`，`@EnableAutoConfiguration`和`@ComponentScan`及其默认属性，如以下示例所示：


```java

package com.example.myapplication;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication // same as @Configuration @EnableAutoConfiguration @ComponentScan
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

}
```

> `@SpringBootApplication`还提供别名来自定义`@EnableAutoConfiguration`和`@ComponentScan`的属性。


## 19. 运行你的应用

将应用程序打包为jar并使用嵌入式HTTP服务器的最大优点之一是，您可以像运行其他应用程序一样运行应用程序。调试Spring Boot应用程序也很容易。您不需要任何特殊的IDE插件或扩展。

> 本节仅涵盖基于jar的包装。如果您选择将应用程序打包为war文件，则应参考您的服务器和IDE文档。


### 19.1. 使用 IDE 运行

您可以从IDE运行Spring Boot应用程序作为简单的Java应用程序。但是，您首先需要导入您的项目。导入步骤取决于您的IDE和构建系统。大多数IDE可以直接导入Maven项目。例如，Eclipse用户可以从 File 菜单中选择 `Import ...→Existing Maven Projects`。

如果您无法直接将您的项目导入IDE，则可以使用构建插件生成IDE元数据。 Maven包含Eclipse和IDEA的插件。 Gradle为各种IDE提供插件。

> 如果您意外运行了两次Web应用程序，则会看到“端口已被使用”错误。 STS用户可以使用`Relaunch`按钮而不是运行按钮来确保关闭任何现有的实例。


### 19.2. 运行打包应用

如果使用Spring Boot Maven或Gradle插件创建可执行jar，则可以使用`java -jar`运行应用程序，如以下示例所示：

```
$ java -jar target/myapplication-0.0.1-SNAPSHOT.jar
```

也可以在启用远程调试支持的情况下运行打包的应用程序。这样做可以让您将调试器附加到打包的应用程序，如以下示例所示：

```
$ java -Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n \
       -jar target/myapplication-0.0.1-SNAPSHOT.jar
```

### 19.3. 使用 Maven 插件

Spring Boot Maven插件包含一个可用于快速编译和运行应用程序的运行目标。应用程序以分解形式运行，就像它们在IDE中一样。以下示例显示了运行Spring Boot应用程序的典型Maven命令：

```
$ mvn spring-boot:run
```
您可能还想使用`MAVEN_OPTS`操作系统环境变量，如下例所示：

```
$ export MAVEN_OPTS=-Xmx1024m
```

### 19.4. 使用 Gradle 插件

Spring Boot Gradle插件还包含一个bootRun任务，可用于以分解形式运行您的应用程序。每当您应用org.springframework.boot和java插件并在以下示例中显示时，都会添加bootRun任务：

```
$ gradle bootRun
```

您可能还想使用`JAVA_OPTS`操作系统环境变量，如以下示例所示：

```
$ export MAVEN_OPTS=-Xmx1024m

```

### 19.5. 热交换

由于Spring Boot应用程序只是普通的Java应用程序，所以JVM热插拔应该可以开箱即用。 JVM热插拔在可以替换的字节码方面有所限制。对于更完整的解决方案，可以使用JRebel。

`spring-boot-devtools`模块还包含对快速重新启动应用程序的支持。

有关详细信息，请参阅本章后面的第20章开发人员工具部分以及热插拔“操作方法”。

## 20. 开发工具

Spring Boot包含一组额外的工具，可以使应用程序开发体验更愉快。 `spring-boot-devtools`模块可以包含在任何项目中以提供额外的开发时间功能。要包含devtools支持，请将模块依赖项添加到您的构建中，如Maven和Gradle的以下列表所示：

Maven:

```xml
<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-devtools</artifactId>
		<optional>true</optional>
	</dependency>
</dependencies>
```

```gradle
dependencies {
	compile("org.springframework.boot:spring-boot-devtools")
}
```

>运行完整打包的应用程序时，开发人员工具会自动禁用如果您的应用程序是从`java -jar`启动的，或者如果它是从特殊的类加载器启动的，那么它被认为是“生产应用程序”。将依赖标记为`optional`是一种最佳实践，可防止devtools被传递应用到其他使用您项目的模块。 Gradle不支持可选的依赖关系，因此您可能需要查看propdeps插件。
>
>重新打包的档案在默认情况下不包含devtools。如果您想使用某个远程devtools功能，则需要禁用excludeDevtools生成属性以包含它。该属性支持Maven和Gradle插件。

### 20.1. 属性默认值

`Spring Boot`支持的一些库使用缓存来提高性能。例如，`template engines`缓存已编译的模板以避免重复解析模板文件。另外，`Spring MVC`可以在服务静态资源时将HTTP缓存头添加到响应中。

虽然缓存在生产中非常有用，但它在开发过程中会起到反作用，使您无法看到您在应用程序中所做的更改。因此，`spring-boot-devtools`默认禁用缓存选项。

缓存选项通常由您的`application.properties`文件中的设置进行配置。例如，Thymeleaf提供了`spring.thymeleaf.cache`属性。而不是需要手动设置这些属性，`spring-boot-devtools`模块会自动应用合理的开发时配置。

> 有关devtools应用的属性的完整列表，请参阅DevToolsPropertyDefaultsPostProcessor。


### 20.2. 自动重启

每当类路径上的文件发生更改时，使用`spring-boot-devtools`的应用程序都会自动重新启动。在IDE中工作时，这可能是一个有用的功能，因为它为代码更改提供了非常快速的反馈循环。默认情况下，监视指向文件夹的类路径上的任何条目以进行更改。请注意，某些资源（如静态资产和视图模板）不需要重新启动应用程序。

触发重启

由于DevTools监控类路径资源，触发重启的唯一方法是更新类路径。导致类路径更新的方式取决于您使用的IDE。在Eclipse中，保存修改后的文件会导致更新类路径并触发重新启动。在IntelliJ IDEA中，构建项目（`Build - > Make Project`）具有相同的效果。

> 只要启用forking，您也可以使用受支持的构建插件（Maven和Gradle）启动您的应用程序，因为DevTools需要隔离的应用程序类加载器才能正常运行。默认情况下，当他们在类路径中检测到DevTools时，Gradle和Maven会这样做。

> 与LiveReload一起使用时，自动重启的效果非常好。有关详细信息，请参阅LiveReload部分。如果使用JRebel，则禁用自动重新启动，以支持动态类重新加载。其他devtools功能（例如LiveReload和属性覆盖）仍然可以使用。

> DevTools依靠应用程序上下文的关闭挂钩在重新启动期间关闭它。如果您禁用了关闭挂钩（`SpringApplication.setRegisterShutdownHook（false）`），它将无法正常工作。

> 在决定类路径中的条目是否会在更改时触发重新启动时，DevTools会自动忽略名为`spring-boot`，`spring-boot-devtools`，`spring-boot-autoconfigure`，`spring-boot-actuator`和`spring-boot-starter`的项目。

> DevTools需要自定义`ApplicationContext`使用的`ResourceLoader`。如果你的应用程序已经提供了一个，它将被包装。不支持直接覆盖`ApplicationContext` 上的 `getResource`方法。

>Restart vs Reload
>
>Spring Boot提供的重启技术通过使用两个类加载器来工作。不改变的类（例如来自第三方jar的类）被加载到基类加载器中。您正在开发的类会加载到重启类加载器中。当应用程序重新启动时，重新启动类加载器将被丢弃并创建一个新类。这种方法意味着应用程序重启通常比“冷启动”快得多，因为基类加载器已经可用并且已经被填充。
>
>如果您发现重启对于您的应用程序来说不够快，或者遇到类加载问题，则可以考虑从ZeroTurnaround中重新加载技术，例如JRebel。这些工作通过在加载类时重写类，使它们更易于重新加载。

#### 20.2.1. 记录条件评估中的更改

默认情况下，每次应用程序重新启动时，都会记录显示条件评估增量的报告。该报告显示了在您进行更改（如添加或删除Bean以及设置配置属性）时对应用程序自动配置的更改。

要禁用报告的日志记录，请设置以下属性:

```
spring.devtools.restart.log-condition-evaluation-delta=false
```

#### 20.2.2. 排除资源

某些资源不一定需要在更改时触发重新启动。例如，可以就地编辑Thymeleaf模板。默认情况下，更改 `/META-INF/maven`，`/META-INF/resources`，`/resources`，`/static`，`/public`或`/templates`中的资源不会触发重新启动，但会触发实时重新加载。如果你想自定义这些排除，你可以使用`spring.devtools.restart.exclude`属性。例如，要仅排除`/static`和`/public`，您将设置以下属性：

```
spring.devtools.restart.exclude=static/**,public/**
```

> 如果要保留这些默认值并添加其他排除项，请改为使用`spring.devtools.restart.additional-exclude`属性。

#### 20.2.3. 监控额外的路径

您可能希望在更改不在类路径中的文件时重新启动或重新加载应用程序。为此，请使用`spring.devtools.restart.additional-paths`属性来配置其他路径以监视更改。您可以使用前面介绍的`spring.devtools.restart.exclude`属性来控制其他路径下的更改是触发完全重新启动还是实时重新加载。

#### 20.2.4. 禁用重新启动

如果您不想使用重新启动功能，则可以使用`spring.devtools.restart.enabled`属性将其禁用。在大多数情况下，您可以在`application.properties`中设置此属性（这样做仍会初始化重新启动类加载器，但它不会监视文件更改）。

如果需要完全禁用重新启动支持（例如，因为它不适用于特定库），则在调用`SpringApplication.run（...）`之前，需要将`spring.devtools.restart.enabled` System属性设置为false，如如下例所示：

```java
public static void main(String[] args) {
	System.setProperty("spring.devtools.restart.enabled", "false");
	SpringApplication.run(MyApp.class, args);
}
```


#### 20.2.5. 使用触发文件

如果您使用持续编译更改文件的IDE，则可能只希望在特定时间触发重新启动。为此，您可以使用“触发文件”，这是一个特殊的文件，当您想要实际触发重新启动检查时必须对其进行修改。只有更改文件才会触发检查，并且仅在Devtools检测到必须执行某些操作时才会重新启动。触发文件可以手动更新或使用IDE插件更新。

要使用触发器文件，请将spring.devtools.restart.trigger-file属性设置为触发器文件的路径。

> 您可能希望将spring.devtools.restart.trigger-file设置为全局设置，以便所有项目的行为方式相同。



#### 20.2.6. 自定义重启类加载器

如前面的“Restart vs Reload”部分所述，重新启动功能通过使用两个类加载器来实现。对于大多数应用程序，这种方法运作良好但是，它有时会导致类加载问题。

默认情况下，IDE中的任何打开的项目都会加载“restart”类加载器，并且任何常规的`.jar`文件都会加载“base”类加载器。如果您使用多模块项目，并且不是每个模块都导入到IDE中，则可能需要自定义。为此，您可以创建一个 `META-INF/spring-devtools.properties` 文件。

`spring-devtools.properties`文件可以包含以`restart.exclude`和`restart.include`为前缀的属性。 include元素是应该被拉入到“重启”类加载器中的项目，而排除元素是应该下推到“基本”类加载器中的项目。该属性的值是应用于类路径的正则表达式模式，如以下示例所示：

```
restart.exclude.companycommonlibs=/mycorp-common-[\\w-]+\.jar
restart.include.projectcommon=/mycorp-myproj-[\\w-]+\.jar
```

> 所有属性键必须是唯一的。只要属性以`restart.include`或`restart.exclude`。已经被考虑了。
> 
> 加载类路径中的所有`META-INF/spring-devtools.properties`。您可以将文件打包到您的项目中，也可以打包到项目使用的库中

#### 20.2.7. 已知限制

对于使用标准`ObjectInputStream`进行反序列化的对象，重新启动功能无法正常工作。如果你需要反序列化数据，你可能需要结合使用Spring的`ConfigurableObjectInputStream`和`Thread.currentThread()`。`getContextClassLoader()`。 

不幸的是，有些第三方库反序列化而没有考虑上下文类加载器。如果您发现这样的问题，您需要向原作者请求修复。

### 20.3. 实时加载

`spring-boot-devtools`模块包含一个嵌入式LiveReload服务器，可用于在更改资源时触发浏览器刷新。 LiveReload浏览器扩展可免费用于livereload.com的Chrome，Firefox和Safari。 

如果您不想在应用程序运行时启动LiveReload服务器，则可以将`spring.devtools.livereload.enabled`属性设置为false。

> 一次只能运行一个LiveReload服务器。在开始应用程序之前，请确保没有其他LiveReload服务器正在运行。如果您从IDE启动多个应用程序，则只有第一个应用程序支持LiveReload。

### 20.4. 全局设置

您可以通过将名为`.spring-boot-devtools.properties`的文件添加到您的`$HOME`文件夹来配置全局devtools设置（请注意文件名以“。”开头）。添加到此文件的任何属性都适用于使用devtools的计算机上的所有Spring Boot应用程序。例如，要将重新启动配置为始终使用触发器文件，您可以添加以下属性：

~/.spring-boot-devtools.properties. 

```
spring.devtools.reload.trigger-file=.reloadtrigger
```

### 20.5. 远程应用

Spring Boot开发人员工具不限于本地开发。远程运行应用程序时，您还可以使用多个功能。远程支持是选择加入。要启用它，您需要确保devtools包含在重新打包的存档中，如下所示：

```
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
			<configuration>
				<excludeDevtools>false</excludeDevtools>
			</configuration>
		</plugin>
	</plugins>
</build>
```

然后你需要设置一个`spring.devtools.remote.secret`属性，如下例所示：

```
spring.devtools.remote.secret=mysecret
```

> 在远程应用程序上启用`spring-boot-devtools`存在安全风险。您不应该在生产部署上启用支持。

远程devtools支持分两部分提供：接受连接的服务器端端点以及您在IDE中运行的客户端应用程序。当设置了`spring.devtools.remote.secret`属性时，服务器组件会自动启用。客户端组件必须手动启动。

#### 20.5.1. 运行远程客户应用

远程客户端应用程序旨在从您的IDE中运行。您需要使用与您连接的远程项目相同的类路径运行`org.springframework.boot.devtools.RemoteSpringApplication`。应用程序的单个必需参数是它所连接的远程URL。

例如，如果您使用的是Eclipse或STS，并且您已经将一个名为my-app的项目部署到了​​Cloud Foundry，则可以执行以下操作：

* 从`Run`菜单中选择 `Run Configurations…​` 
* 创建一个新的 `Java Application`“启动配置”。 
* 浏览`my-app`项目。 
* 使用`org.springframework.boot.devtools.RemoteSpringApplication`作为主类。 
* 将`https://myapp.cfapps.io`添加到程序参数（或任何远程URL）。

正在运行的远程客户端可能类似于以下列表：

```
  .   ____          _                                              __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _          ___               _      \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` |        | _ \___ _ __  ___| |_ ___ \ \ \ \
 \\/  ___)| |_)| | | | | || (_| []::::::[]   / -_) '  \/ _ \  _/ -_) ) ) ) )
  '  |____| .__|_| |_|_| |_\__, |        |_|_\___|_|_|_\___/\__\___|/ / / /
 =========|_|==============|___/===================================/_/_/_/
 :: Spring Boot Remote :: 2.0.0.RELEASE

2015-06-10 18:25:06.632  INFO 14938 --- [           main] o.s.b.devtools.RemoteSpringApplication   : Starting RemoteSpringApplication on pwmbp with PID 14938 (/Users/pwebb/projects/spring-boot/code/spring-boot-devtools/target/classes started by pwebb in /Users/pwebb/projects/spring-boot/code/spring-boot-samples/spring-boot-sample-devtools)
2015-06-10 18:25:06.671  INFO 14938 --- [           main] s.c.a.AnnotationConfigApplicationContext : Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext@2a17b7b6: startup date [Wed Jun 10 18:25:06 PDT 2015]; root of context hierarchy
2015-06-10 18:25:07.043  WARN 14938 --- [           main] o.s.b.d.r.c.RemoteClientConfiguration    : The connection to http://localhost:8080 is insecure. You should use a URL starting with 'https://'.
2015-06-10 18:25:07.074  INFO 14938 --- [           main] o.s.b.d.a.OptionalLiveReloadServer       : LiveReload server is running on port 35729
2015-06-10 18:25:07.130  INFO 14938 --- [           main] o.s.b.devtools.RemoteSpringApplication   : Started RemoteSpringApplication in 0.74 seconds (JVM running for 1.105)
```

> 由于远程客户端使用与真实应用程序相同的类路径，它可以直接读取应用程序属性。这是如何读取`spring.devtools.remote.secret`属性并将其传递给服务器以进行身份​​验证。

> 始终建议使用`https://`作为连接协议，以便流量加密并且密码不会被拦截。

> 如果您需要使用代理来访问远程应用程序，请配置`spring.devtools.remote.proxy.host`和`spring.devtools.remote.proxy.port`属性。

#### 20.5.2. 远程更新

远程客户端以与本地重启相同的方式监视应用程序类路径的更改。任何更新的资源都会被推送到远程应用程序，并且（如果需要）会触发重新启动。如果您对使用本地没有的云服务的功能进行迭代，这会很有帮助。通常，远程更新和重新启动比完整的重建和部署周期快得多。

> 仅在远程客户端运行时才监视文件。如果在启动远程客户端之前更改文件，则不会将其推送到远程服务器。

## 21. 为生产环境打包应用

可执行的 jars 可用于生产部署。由于它们是独立的，它们也非常适合基于云的部署。 

对于额外的“生产就绪”功能，例如运行状况，审计和公制REST或JMX端点，请考虑添加`Spring Boot Actuator`。有关详细信息，请参见第V部分“Spring Boot Actuator：生产就绪功能”。

## 22. 接下来要阅读的内容

您现在应该了解如何使用Spring Boot以及您应遵循的一些最佳实践。您现在可以继续深入了解特定的Spring Boot功能，或者可以跳过并阅读Spring Boot的“生产准备”部分。