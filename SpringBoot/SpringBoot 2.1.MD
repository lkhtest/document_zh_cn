# **1 Spring Boot文档**

&emsp;&emsp;本节简要概述SpringBoot参考文档。它用作文档其余部分的地图。

## **1.1 关于这篇文档**

&emsp;&emsp;SpringBoot参考指南如下所示

- HTML
- PDF
- EPUB

&emsp;&emsp;最新的副本可在docs.spring.io/spring-boot/docs/current/reference上找到。

&emsp;&emsp;本文档的副本可供您自己使用并分发给他人，前提是您不对此类副本收取任何费用，并且每份副本均包含本版权声明，无论是以印刷版还是电子版分发。

## **1.2 获取帮助**

&emsp;&emsp;如果您在使用Spring Boot时遇到问题，我们非常乐意为您提供帮助。

- 尝试使用第9章。 他们为最常见的问题提供解决方案。
- 学习Spring基础知识。 Spring Boot建立在许多其他Spring项目之上。 查看spring.io网站以获取大量参考文档。 如果您刚开始使用Spring，请尝试其中一个指南。
- 问一个问题。 我们监控stackoverflow.com以获取用spring-boot标记的问题。
- 在github.com/spring-projects/spring-boot/issues上以Spring Boot报告错误。

>注：所有Spring Boot都是开源的，包括文档。 如果您发现文档存在问题或者想要改进它们，请参与其中。

## **1.3 第一步**

&emsp;&emsp;如果您开始使用Spring Boot或“Spring”，请从以下主题开始：

- 从头开始：2.1 Spring Boot介绍、2.2 系统要求、2.3 安装Spring Boot
- 教程：第1章、第2章
- 运行您的示例：第1章、第2章


## **1.4 使用Spring Boot**

&emsp;&emsp;准备好开始使用Spring Boot了吗？ 我们为您提供：

- 构建系统：3.1.2 Maven、3.1.3 Gradle、3.1.4 Ant、3.1.5 Starters
- 最佳实践：3.2 构建您的代码、3.3 配置类、3.4 自动配置、3.5 Spring Beans和依赖注入
- 运行代码：3.7.1 从IDE运行、3.7.2 作为打包应用程序运行、3.7.3 使用Maven插件、3.7.4 使用Gradle插件
- 打包应用：3.9 打包您的生产应用程序
- Spring Boot CLI：第7章


## **1.5 了解Spring Boot功能**

&emsp;&emsp;需要有关Spring Boot核心功能的更多细节？ 以下内容适合您：

- 核心功能：4.1 SpringApplication、4.2 外化配置、4.3 配置文件、4.4 日志
- Web应用：4.6.1 Spring Web MVC框架、4.6.4 嵌入式Servlet容器支持
- 使用数据库：4.8 使用SQL数据库、4.9 使用NoSQL技术
- 消息：4.11 消息、4.11.1 JMS
- 测试：4.23 测试、4.23.3 测试Spring Boot应用程序、4.23.4 测试工具包
- 扩展：4.26 创建自己的自动配置、4.26.3 条件注解


## **1.6 转向生产**

&emsp;&emsp;当您准备好将Spring Boot应用程序推向生产环境时，我们会提供一些您可能喜欢的技巧：

- 管理端点：5.2 Endpoints
- 连接选项：5.3 通过HTTP进行监控和管理、5.4 JMX的监控和管理
- 监控：5.6 Metrics、5.7 审计、5.9 过程监控


## **1.7 深入问题**

&emsp;&emsp;最后，我们为更高级的用户提供了一些主题：

- Spring Boot应用程序部署：6.1 部署到Cloud、6.2.2 Unix/Linux服务
- 构建工具插件：8.1 Spring Boot Maven插件、8.2 Spring Boot Gradle插件
- 附录：10.1 常见的应用属性、10.3 自动配置类、10.5 可执行的Jar格式

# **2 入门**

&emsp;&emsp;如果您开始使用Spring Boot或一般的“Spring”，请首先阅读本节。 它回答了基本的“什么？”，“如何？”和“为什么？”的问题。 它包括Spring Boot简介以及安装说明。 然后，我们将引导您构建您的第一个Spring Boot应用程序，并在我们讨论时讨论一些核心原则。

## **2.1 Spring Boot介绍**

&emsp;&emsp;Spring Boot可以轻松创建可以运行的独立的，生产级的基于Spring的应用程序。 我们对Spring平台和第三方库有一个独断专行的看法，这样您就可以轻松上手了。 大多数Spring Boot应用程序只需要很少的Spring配置。

&emsp;&emsp;您可以使用Spring Boot创建可以使用java -jar或更传统的war部署启动的Java应用程序。 我们还提供了一个运行“spring脚本”的命令行工具。

&emsp;&emsp;我们的主要目标是：

- 为所有Spring开发提供从根本上更快且可广泛访问的入门体验。
- 开箱即用，但随着需求开始偏离默认值而迅速摆脱困境。
- 提供大型项目（例如嵌入式服务器，安全性，度量标准，运行状况检查和外部化配置）通用的一系列非功能性功能。
- 绝对没有代码生成，也不需要XML配置。

## **2.2 系统要求**

&emsp;&emsp;Spring Boot 2.1.3.RELEASE需要Java 8，并且与Java 11兼容（包括在内）。 还需要Spring Framework 5.1.5.RELEASE或更高版本。

&emsp;&emsp;为以下构建工具提供了显式构建支持：

<table>
	<tr>
		<th>Build Tool</th>
		<th>Version</th>
	</tr>
	<tr>
		<td>Maven</td>
		<td>3.3+</td>
	</tr>
	<tr>
		<td>Gradle</td>
		<td>4.4+</td>
	</tr>
</table>

### **2.2.1 Servlet容器**

&emsp;&emsp;Spring Boot支持以下嵌入式servlet容器：

<table>
	<tr>
		<th>Name</th>
		<th>Servlet Version</th>
	</tr>
	<tr>
		<td>Tomcat 9.0</td>
		<td>4.0</td>
	</tr>
	<tr>
		<td>Jetty 9.4</td>
		<td>3.1</td>
	</tr>
	<tr>
		<td>Undertow 2.0</td>
		<td>4.0</td>
	</tr>
</table>

&emsp;&emsp;您还可以将Spring Boot应用程序部署到任何兼容Servlet 3.1+的容器。

## **2.3 安装Spring Boot**

&emsp;&emsp;Spring Boot可以与“经典”Java开发工具一起使用，也可以作为命令行工具安装。 无论哪种方式，您都需要Java SDK v1.8或更高版本。 在开始之前，您应该使用以下命令检查当前的Java安装：

``` 
$ java -version
```

&emsp;&emsp;如果您不熟悉Java开发，或者想要尝试Spring Boot，则可能需要先尝试Spring Boot CLI（命令行界面）。 否则，请继续阅读“经典”安装说明。

### **2.3.1 Java Developer的安装说明**

&emsp;&emsp;您可以像使用任何标准Java库一样使用Spring Boot。 为此，请在类路径中包含相应的spring-boot - * .jar文件。 Spring Boot不需要任何特殊工具集成，因此您可以使用任何IDE或文本编辑器。 此外，Spring Boot应用程序没有什么特别之处，因此您可以像运行任何其他Java程序一样运行和调试Spring Boot应用程序。

&emsp;&emsp;虽然您可以复制Spring Boot jar，但我们通常建议您使用支持依赖关系管理的构建工具（例如Maven或Gradle）。

**2.3.1.1 Mave安装**

&emsp;&emsp;Spring Boot与Apache Maven 3.3或更高版本兼容。 如果您还没有安装Maven，可以按照maven.apache.org上的说明进行操作。

<table>
	<tr>
		<td>注：在许多操作系统上，Maven可以与软件包管理器一起安装。 如果您使用OSX Homebrew，请尝试brew install maven。 Ubuntu用户可以运行sudo apt-get install maven。 使用Chocolatey的Windows用户可以从提升（管理员）提示符运行choco install maven。</td>
	</tr>
</table>

&emsp;&emsp;Spring Boot依赖项使用org.springframework.boot groupId。 通常，您的Maven POM文件继承自spring-boot-starter-parent项目，并声明对一个或多个“Starters”的依赖关系。 Spring Boot还提供了一个可选的Maven插件来创建可执行jar。

&emsp;&emsp;以下清单显示了典型的pom.xml文件：

``` 
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
		<version>2.1.3.RELEASE</version>
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

>注：spring-boot-starter-parent是一种使用Spring Boot的好方法，但它可能并不总是适用。 有时您可能需要从不同的父POM继承，或者您可能不喜欢我们的默认设置。 在这些情况下，请参见第3.1.2.2 “在没有父POM的情况下使用Spring Boot”作为使用导入范围的替代解决方案。

**2.3.1.2 Gradle安装**

&emsp;&emsp;Spring Boot与Gradle 4.4及更高版本兼容。 如果您尚未安装Gradle，则可以按照gradle.org上的说明进行操作。

&emsp;&emsp;可以使用org.springframework.boot组声明Spring Boot依赖项。 通常，您的项目会声明对一个或多个“Starters”的依赖关系。 Spring Boot提供了一个有用的Gradle插件，可用于简化依赖声明和创建可执行jar。

&emsp;&emsp;Gradle Wrapper 当您需要构建项目时，Gradle Wrapper提供了一种“获取”Gradle的好方法。 它是一个小脚本和库，您可以与代码一起提交以引导构建过程。 有关详细信息，请参阅docs.gradle.org/4.2.1/userguide/gradle_wrapper.html。 有关Spring Boot和Gradle入门的更多详细信息，请参阅Gradle插件参考指南的“入门”部分。

### **2.3.2 安装Spring Boot CLI**

&emsp;&emsp;Spring Boot CLI（命令行界面）是一个命令行工具，您可以使用它来快速使用Spring进行原型设计。 它允许您运行Groovy脚本，这意味着您拥有熟悉的类似Java的语法，而没有太多的样板代码。

&emsp;&emsp;您不需要使用CLI来使用Spring Boot，但它绝对是实现Spring应用程序的最快方法。

**2.3.2.1 手动安装**

&emsp;&emsp;您可以从Spring软件库下载Spring CLI发行版：

- spring-boot-cli-2.1.3.RELEASE-bin.zip
- spring-boot-cli-2.1.3.RELEASE-bin.tar.gz


&emsp;&emsp;还提供最先进的快照分发。

&emsp;&emsp;下载完成后，请按照解压缩的存档中的INSTALL.txt说明进行操作。 总之，.zip文件中的bin /目录中有一个spring脚本（用于Windows的spring.bat）。 或者，您可以将java -jar与.jar文件一起使用（该脚本可帮助您确保正确设置类路径）。

**2.3.2.2 使用SDKMAN！安装**

&emsp;&emsp;SDKMAN！（软件开发工具包管理器）可用于管理各种二进制SDK的多个版本，包括Groovy和Spring Boot CLI。 获取SDKMAN！ 从sdkman.io中，使用以下命令安装Spring Boot：

``` 
$ sdk install springboot
$ spring --version
Spring Boot v2.1.3.RELEASE
```

&emsp;&emsp;如果您为CLI开发功能并希望轻松访问您构建的版本，请使用以下命令：

``` 
$ sdk install springboot dev /path/to/spring-boot/spring-boot-cli/target/spring-boot-cli-2.1.3.RELEASE-bin/spring-2.1.3.RELEASE/
$ sdk default springboot dev
$ spring --version
Spring CLI v2.1.3.RELEASE
```

&emsp;&emsp;前面的说明安装了一个名为dev实例的spring的本地实例。 它指向您的目标构建位置，因此每次重建Spring Boot时，spring都是最新的。

&emsp;&emsp;您可以通过运行以下命令来查看它：

``` 
$ sdk ls springboot

================================================================================
Available Springboot Versions
================================================================================
> + dev
* 2.1.3.RELEASE

================================================================================
+ - local version
* - installed
> - currently in use
================================================================================
```

**2.3.2.3 OSX Homebrew安装**

&emsp;&emsp;如果您使用的是Mac并使用Homebrew，则可以使用以下命令安装Spring Boot CLI：

``` 
$ brew tap pivotal/tap
$ brew install springboot
```

&emsp;&emsp;Homebrew将spring安装到/usr/local/bin。

>注：如果您没有看到公式，那么您的brew安装可能已过时。 在这种情况下，请运行brew update并再试一次。

**2.3.2.4 MacPorts安装**

&emsp;&emsp;如果您使用的是Mac并使用MacPorts，则可以使用以下命令安装Spring Boot CLI：

``` 
$ sudo port install spring-boot-cli
```

**2.3.2.5 命令行完成**

&emsp;&emsp;Spring Boot CLI包含为BASH和zsh shell提供命令完成的脚本。 您可以在任何shell中获取脚本（也称为spring），或将其放入个人或系统范围的bash完成初始化中。 在Debian系统上，系统范围的脚本位于/shell-completion/bash中，当新shell启动时，该目录中的所有脚本都会执行。 例如，要使用SDKMAN！安装，请手动运行脚本，请使用以下命令：

``` 
$ . ~/.sdkman/candidates/springboot/current/shell-completion/bash/spring
$ spring <HIT TAB HERE>
  grab  help  jar  run  test  version
```

>注：如果使用Homebrew或MacPorts安装Spring Boot CLI，则命令行完成脚本会自动注册到shell。

**2.3.2.6 Windows Scoop安装**

&emsp;&emsp;如果您使用的是Windows并使用Scoop，则可以使用以下命令安装Spring Boot CLI：

``` 
> scoop bucket add extras
> scoop install springboot
```

&emsp;&emsp;Scoop安装spring到~/scoop/apps/spring boot/current/bin。

>注：如果您没有看到应用清单，则您的scoop安装可能已过时。 在这种情况下，运行scoop update并再试一次。

**2.3.2.7 快速启动Spring CLI示例**

&emsp;&emsp;您可以使用以下Web应用程序来测试您的安装。 首先，创建一个名为app.groovy的文件，如下所示：

``` 
@RestController
class ThisWillActuallyRun {

	@RequestMapping("/")
	String home() {
		"Hello World!"
	}

}
```

&emsp;&emsp;然后从shell运行它，如下所示：

``` 
$ spring run app.groovy
```

>注：应用程序的第一次运行速度很慢，因为下载了依赖项。 后续运行要快得多

&emsp;&emsp;在您喜欢的Web浏览器中打开localhost:8080。 您应该看到以下输出：

``` 
Hello World!
```

### **2.3.3 从早期版本的Spring Boot升级**

&emsp;&emsp;如果要从早期版本的Spring Boot升级，请查看项目Wiki上的“迁移指南”，其中提供了详细的升级说明。 另请查看“发行说明”，了解每个版本的“新的和值得注意的”功能列表。

&emsp;&emsp;升级到新功能版本时，某些属性可能已重命名或删除。 Spring Boot提供了一种在启动时分析应用程序环境和打印诊断的方法，还可以在运行时临时迁移属性。 要启用该功能，请将以下依赖项添加到项目中：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-properties-migrator</artifactId>
	<scope>runtime</scope>
</dependency>
```

>注：在环境中添加的属性（例如使用@PropertySource时）将不会被考虑在内。 完成迁移后，请确保从项目的依赖项中删除此模块。

&emsp;&emsp;要升级现有CLI安装，请使用相应的软件包管理器命令（例如，brew upgrade），或者，如果手动安装CLI，请按照标准说明操作，记住更新PATH环境变量以删除任何旧引用。

## **2.4 开发您的第一个Spring Boot应用程序**

&emsp;&emsp;本节介绍如何开发一个简单的“Hello World！”Web应用程序，该应用程序突出了Spring Boot的一些主要功能。 我们使用Maven来构建这个项目，因为大多数IDE都支持它。

>注：spring.io网站包含许多使用Spring Boot的“入门”指南。 如果您需要解决特定问题，请先检查一下。 您可以通过转到start.spring.io并从依赖关系搜索器中选择“Web”启动器来快捷执行以下步骤。 这样做会生成一个新的项目结构，以便您可以立即开始编码。 有关更多详细信息，请查看Spring Initializr文档。

&emsp;&emsp;在开始之前，打开终端并运行以下命令以确保安装了有效的Java和Maven版本：

``` 
$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)
```

``` 
$ mvn -v
Apache Maven 3.5.4 (1edded0938998edf8bf061f1ceb3cfdeccf443fe; 2018-06-17T14:33:14-04:00)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation
```

>注：此示例需要在其自己的文件夹中创建。 后续说明假定您已创建了一个合适的文件夹，并且它是您当前的目录。

### **2.4.1 创建POM**

&emsp;&emsp;我们需要从创建Maven pom.xml文件开始。 pom.xml是用于构建项目的配方。 打开您喜欢的文本编辑器并添加以下内容：

``` 
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
		<version>2.1.3.RELEASE</version>
	</parent>

	<!-- Additional lines to be added here... -->

</project>
```

&emsp;&emsp;上面的清单应该为您提供有效的构建。 您可以通过运行mvn包来测试它（现在，您可以忽略“jar will be empty - no content was marked for inclusion!”警告）。

>注：此时，您可以将项目导入IDE（大多数现代Java IDE包括对Maven的内置支持）。 为简单起见，我们继续为此示例使用纯文本编辑器

### **2.4.2 添加Classpath依赖项**

&emsp;&emsp;Spring Boot提供了许多“Starters”，可以将jar添加到类路径中。 我们的示例应用程序已经在POM的父节中使用了spring-boot-starter-parent。 spring-boot-starter-parent是一个特殊的启动器，提供有用的Maven默认值。 它还提供了一个依赖项管理部分，以便您可以省略“blessed”依赖项的版本标记。

&emsp;&emsp;其他“Starters”提供了在开发特定类型的应用程序时可能需要的依赖项。 由于我们正在开发Web应用程序，因此我们添加了一个spring-boot-starter-web依赖项。 在此之前，我们可以通过运行以下命令来查看当前的内容：

``` 
$ mvn dependency:tree

[INFO] com.example:myproject:jar:0.0.1-SNAPSHOT
```

&emsp;&emsp;mvn dependency:tree命令打印项目依赖项的树表示。 您可以看到spring-boot-starter-parent本身不提供依赖关系。 要添加必要的依赖项，请编辑pom.xml并在父节下面添加spring-boot-starter-web依赖项：

``` 
<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
</dependencies>
```

&emsp;&emsp;如果再次运行mvn dependency:tree，您会看到现在有许多其他依赖项，包括Tomcat Web服务器和Spring Boot本身。

### **2.4.3 编写代码**

&emsp;&emsp;要完成我们的应用程序，我们需要创建一个Java文件。 默认情况下，Maven从src/main/java编译源代码，因此您需要创建该文件夹结构，然后添加名为src/main/java/Example.java的文件以包含以下代码：

``` 
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

	public static void main(String[] args) {
		SpringApplication.run(Example.class, args);
	}

}
```

&emsp;&emsp;虽然这里的代码不多，但还是有很多代码。 我们将在接下来的几节中逐步介绍重要部分。

**2.4.3.1 @RestController和@RequestMapping注解**

&emsp;&emsp;我们的Example类的第一个注释是@RestController。 这被称为构造型注释。 它为阅读代码的人提供了提示，而为Spring提供了特定角色的提示。 在这种情况下，我们的类是一个Web @Controller，所以Spring在处理传入的Web请求时会考虑它。

&emsp;&emsp;@RequestMapping注释提供“路由”信息。 它告诉Spring，任何带有/的HTTP请求都应该映射到home方法。 @RestController注释告诉Spring将结果字符串直接渲染回调用者。

>注：@RestController和@RequestMapping注释是Spring MVC注释。 （它们不是Spring Boot特有的。）有关更多详细信息，请参阅Spring参考文档中的MVC部分。

**2.4.3.2 @EnableAutoConfiguration注解**

&emsp;&emsp;第二个类级别注释是@EnableAutoConfiguration。 这个注释告诉Spring Boot根据你添加的jar依赖关系“猜测”你想要如何配置Spring。 由于spring-boot-starter-web添加了Tomcat和Spring MVC，因此自动配置假定您正在开发Web应用程序并相应地设置Spring。

&emsp;&emsp;Starters 和 Auto-configuration 自动配置旨在与“启动器”配合使用，但这两个概念并不直接相关。 您可以自由选择并在首发之外选择jar依赖项。 Spring Boot仍然尽力自动配置您的应用程序。

**2.4.3.3 “main” 方法**

&emsp;&emsp;我们的应用程序的最后一部分是main方法。 这只是遵循应用程序入口点的Java约定的标准方法。 我们的main方法通过调用run来委托Spring Boot的SpringApplication类。 SpringApplication引导我们的应用程序，启动Spring，然后启动自动配置的Tomcat Web服务器。 我们需要将Example.class作为参数传递给run方法，以告诉SpringApplication是主要的Spring组件。 args数组也被传递以公开任何命令行参数。

### **2.4.4 运行示例**

&emsp;&emsp;此时，您的应用程序应该可以运行了。 由于您使用了spring-boot-starter-parent POM，因此您可以使用一个有用的运行目标来启动应用程序。 键入mvn spring-boot:run 从根项目目录运行以启动应用程序。 您应该看到类似于以下内容的输出：

``` 
$ mvn spring-boot:run

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v2.1.3.RELEASE)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.222 seconds (JVM running for 6.514)
```

&emsp;&emsp;如果您将Web浏览器打开到localhost:8080，您应该看到以下输出：

``` 
Hello World!
```

&emsp;&emsp;要正常退出应用程序，请按ctrl-c。

### **2.4.5 创建一个可执行的Jar**

&emsp;&emsp;我们通过创建一个完全自包含的可执行jar文件来完成我们的示例，我们可以在生产中运行它。 可执行jar（有时称为“fat jar”）是包含已编译类以及代码需要运行的所有jar依赖项的归档。

>**可执行jar和java** 
Java没有提供加载嵌套jar文件的标准方法（jar文件本身包含在jar中）。 如果您要分发自包含的应用程序，这可能会有问题。 
>
为了解决这个问题，许多开发人员使用“uber” jar。 uber jar将所有应用程序依赖项中的所有类打包到一个存档中。 这种方法的问题在于很难看出您的应用程序中有哪些library。
如果在多个jar中使用相同的文件名（但具有不同的内容），也可能会有问题。 
>
Spring Boot采用不同的方法，让您直接嵌套jar。

&emsp;&emsp;要创建可执行jar，我们需要将spring-boot-maven-plugin添加到我们的pom.xml中。 为此，请在依赖项部分下方插入以下行：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>
```

>spring-boot-starter-parent POM包含<executions>配置以绑定重新打包目标。 如果您不使用父POM，则需要自己声明此配置。 有关详细信息，请参阅插件文档。

&emsp;&emsp;保存pom.xml并从命令行运行mvn package，如下所示：

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
[INFO] --- spring-boot-maven-plugin:2.1.3.RELEASE:repackage (default) @ myproject ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```

&emsp;&emsp;如果查看目标目录，则应该看到myproject-0.0.1-SNAPSHOT.jar。 该文件大小应为10 MB左右。 如果你想查看内部，你可以使用jar tvf，如下所示：

``` 
$ jar tvf target/myproject-0.0.1-SNAPSHOT.jar
```

&emsp;&emsp;您还应该在目标目录中看到名为myproject-0.0.1-SNAPSHOT.jar.original的小得多的文件。 这是Maven在Spring Boot重新打包之前创建的原始jar文件。

&emsp;&emsp;要运行该应用程序，请使用java -jar命令，如下所示：

``` 
$ java -jar target/myproject-0.0.1-SNAPSHOT.jar

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v2.1.3.RELEASE)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.536 seconds (JVM running for 2.864)
```

&emsp;&emsp;和以前一样，要退出应用程序，请按ctrl-c。

## **2.5 接下来要阅读的内容**

&emsp;&emsp;希望本节提供了一些Spring Boot基础知识，让您开始编写自己的应用程序。 如果您是面向任务的开发人员类型，您可能需要跳转到spring.io并查看一些入门指南，这些指南解决了具体的“如何使用Spring？”问题。 我们还有特定于Spring Boot的“操作方法”参考文档。

&emsp;&emsp;Spring Boot存储库还有一堆可以运行的示例。 样本独立于其余代码（也就是说，您无需构建其余代码来运行或使用示例）。

&emsp;&emsp;否则，下一个步骤是阅读第3章“使用Spring Boot”。 如果你真的很不耐烦，你也可以跳过去阅读第4章 Spring Boot功能。

# **3 使用Spring Boot**

&emsp;&emsp;本节详细介绍了如何使用Spring Boot。 它涵盖了诸如构建系统，自动配置以及如何运行应用程序等主题。 我们还介绍了一些Spring Boot最佳实践。 虽然Spring Boot没有什么特别之处（它只是你可以使用的另一个库），但是有一些建议，如果遵循这些建议，你的开发过程会更容易一些。

&emsp;&emsp;如果您刚开始使用Spring Boot，那么在深入了解本节之前，您应该阅读“入门指南”。

## **3.1 构建系统**

&emsp;&emsp;强烈建议您选择支持依赖关系管理且可以使用发布到“Maven Central”存储库的artifacts的构建系统。 我们建议您选择Maven或Gradle。 可以让Spring Boot与其他构建系统（例如Ant）一起工作，但它们并没有得到特别好的支持。

## **3.1.1 依赖管理**

&emsp;&emsp;每个版本的Spring Boot都提供了它支持的依赖项的精选列表。 实际上，您不需要为构建配置中的任何这些依赖项提供版本，因为Spring Boot会为您管理这些依赖项。 当您升级Spring Boot时，这些依赖项也会以一致的方式升级。

>如果需要，您仍然可以指定版本并覆盖Spring Boot的建议。

&emsp;&emsp;管理列表包含了您可以在SpringBoot中使用的所有Spring模块，以及一个完善的第三方库列表。该列表可作为标准的配件清单（spring-boot-dependencies）提供，可与Maven和Gradle一起使用。

>每个版本的Spring Boot都与Spring Framework的基本版本相关联。 我们强烈建议您不要指定其版本

### **3.1.2 Maven**

&emsp;&emsp;Maven用户可以继承spring-boot-starter-parent项目以获得合理的默认值。 父项目提供以下功能：

- Java 1.8作为默认编译器级别。
- UTF-8源编码。
- 继承自spring-boot-dependencies pom的依赖关系管理部分，用于管理公共依赖关系的版本。 此依赖关系管理允许您在自己的pom中使用时省略这些依赖项的<version>标记。
- 带有重新打包执行id的重打包目标的执行。
- 合理的资源过滤。
- 合理的插件配置 (exec plugin, Git commit ID, and shade)
- application.properties和application.yml的合理资源过滤，包括特定于配置文件的文件（例如，application-dev.properties和application-dev.yml）


&emsp;&emsp;请注意，由于application.properties和application.yml文件接受Spring样式占位符（$ {...}），因此Maven过滤更改为使用@ .. @占位符。 （您可以通过设置名为resource.delimiter的Maven属性来覆盖它。）

**3.1.2.1 继承Starter Parent**

&emsp;&emsp;要将项目配置为从spring-boot-starter-parent继承，请按如下所示设置父项：

``` 
<!-- Inherit defaults from Spring Boot -->
<parent>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-parent</artifactId>
	<version>2.1.3.RELEASE</version>
</parent>
```

>您应该只需要在此依赖项上指定Spring Boot版本号。 如果导入其他启动器，则可以安全地省略版本号。

&emsp;&emsp;通过该设置，您还可以通过覆盖自己项目中的属性来覆盖单个依赖项。 例如，要升级到另一个Spring Data版本系列，您需要将以下内容添加到pom.xml：

``` 
<properties>
	<spring-data-releasetrain.version>Fowler-SR2</spring-data-releasetrain.version>
</properties>
```

>检查spring-boot-dependencies pom以获取支持的属性列表。

**3.1.2.2 在没有父POM的情况下使用Spring Boot**

&emsp;&emsp;不是每个人都喜欢继承spring-boot-starter-parent POM。 您可能拥有自己需要使用的公司标准父级，或者您可能更愿意明确声明所有Maven配置。

&emsp;&emsp;如果您不想使用spring-boot-starter-parent，您仍然可以通过使用scope = import依赖项来保持依赖项管理（但不是插件管理）的好处，如下所示：

``` 
<dependencyManagement>
		<dependencies>
		<dependency>
			<!-- Import dependency management from Spring Boot -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>2.1.3.RELEASE</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>
```

&emsp;&emsp;如上所述，前面的示例设置不允许您使用属性覆盖单个依赖项。 要获得相同的结果，您需要在spring-boot-dependencies条目之前在项目的dependencyManagement中添加一个条目。 例如，要升级到另一个Spring Data版本系列，可以将以下元素添加到pom.xml：

``` 
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
			<version>2.1.3.RELEASE</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>
```

>在前面的示例中，我们指定了BOM，但是可以以相同的方式覆盖任何依赖关系类型。

**3.1.2.3 使用Spring Boot Maven插件**

&emsp;&emsp;Spring Boot包含一个Maven插件，可以将项目打包为可执行jar。 如果要使用插件，请将插件添加到<plugins>部分，如以下示例所示：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>
```

>如果使用Spring Boot启动程序父pom，则只需添加插件。 除非您要更改父级中定义的设置，否则无需对其进行配置

### **3.1.3 Gradle**

&emsp;&emsp;要了解如何将Spring Boot与Gradle一起使用，请参阅Spring Boot的Gradle插件的文档：

- Reference (HTML and PDF)
- API


### **3.1.4 Ant**

&emsp;&emsp;可以使用Apache Ant + Ivy构建Spring Boot项目。 spring-boot-antlib“AntLib”模块也可用于帮助Ant创建可执行jar。

&emsp;&emsp;要声明依赖项，典型的ivy.xml文件类似于以下示例：

``` 
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

&emsp;&emsp;典型的build.xml类似于以下示例：

``` 
<project
	xmlns:ivy="antlib:org.apache.ivy.ant"
	xmlns:spring-boot="antlib:org.springframework.boot.ant"
	name="myapp" default="build">

	<property name="spring-boot.version" value="2.1.3.RELEASE" />

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

>如果您不想使用spring-boot-antlib模块，请参见第9.16.9节“从Ant构建可执行文件，而不使用spring-boot-antlib”“操作方法”。

### **3.1.5 Starters**

&emsp;&emsp;启动器是一组方便的依赖关系描述符，您可以在应用程序中包含这些描述符。 您可以获得所需的所有Spring和相关技术的一站式服务，而无需查看示例代码和复制粘贴依赖描述符的负载。 例如，如果要开始使用Spring和JPA进行数据库访问，请在项目中包含spring-boot-starter-data-jpa依赖项。

&emsp;&emsp;启动器包含许多依赖项，这些依赖项是使项目快速启动和运行所需的依赖项，以及一组受支持的托管传递依赖项。

&emsp;&emsp;名字里有什么 所有官方首发都遵循类似的命名模式; spring-boot-starter- *，其中*是特定类型的应用程序。 此命名结构旨在帮助您找到启动器。 许多IDE中的Maven集成允许您按名称搜索依赖项。 例如，安装了适当的Eclipse或STS插件后，您可以在POM编辑器中按ctrl-space并输入“spring-boot-starter”以获取完整列表。 正如“创建自己的启动器”部分所述，第三方启动器不应该以spring-boot启动，因为它是为官方Spring Boot工件保留的。 相反，第三方启动器通常以项目名称开头。 例如，名为thirdpartyproject的第三方启动项目通常被命名为thirdpartyproject-spring-boot-starter。

&emsp;&emsp;以下应用程序启动程序由org.springframework.boot组下的Spring Boot提供：

表13.1. Spring Boot应用程序启动器

<table>
	<tr>
		<th>名称</th>
		<th>描述</th>
		<th>Pom</th>
	</tr>
	<tr>
		<td>spring-boot-starter</td>
		<td>核心启动器，包括自动配置支持，日志记录和YAML</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-activemq</td>
		<td>使用Apache ActiveMQ进行JMS消息传递的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-amqp</td>
		<td>使用Spring AMQP和Rabbit MQ的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-aop</td>
		<td>使用Spring AOP和AspectJ进行面向方面切面的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-artemis</td>
		<td>使用Apache Artemis进行JMS消息传递的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-batch</td>
		<td>使用Spring Batch的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-cache</td>
		<td>使用Spring Framework的缓存支持的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-cloud-connectors</td>
		<td>使用Spring Cloud Connectors的启动器，简化了Cloud Foundry和Heroku等云平台中的服务连接</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-cassandra</td>
		<td>使用Cassandra分布式数据库和Spring Data Cassandra的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-cassandra-reactive</td>
		<td>使用Cassandra分布式数据库和Spring Data Cassandra Reactive的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-couchbase</td>
		<td>使用Couchbase面向文档的数据库和Spring Data Couchbase的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-couchbase-reactive</td>
		<td>使用Couchbase面向文档的数据库和Spring Data Couchbase Reactive的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-elasticsearch</td>
		<td>使用Elasticsearch搜索和分析引擎以及Spring Data Elasticsearch的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-jdbc</td>
		<td>使用Spring Data JDBC的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-jpa</td>
		<td>将Spring Data JPA与Hibernate一起使用的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-ldap</td>
		<td>使用Spring Data LDAP的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-mongodb</td>
		<td>使用MongoDB面向文档的数据库和Spring Data MongoDB的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-mongodb-reactive</td>
		<td>使用MongoDB面向文档的数据库和Spring Data MongoDB Reactive的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-neo4j</td>
		<td>使用Neo4j图形数据库和Spring Data Neo4j的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-redis</td>
		<td>在Spring Data Redis和Lettuce客户端上使用Redis键值数据存储的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-redis-reactive</td>
		<td>使用带有Spring Data Redis被动的Redis键值数据存储和Lettuce客户端的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-rest</td>
		<td>使用Spring Data REST通过REST公开Spring Data存储库的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-data-solr</td>
		<td>在Spring Data Solr中使用Apache Solr搜索平台的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-freemarker</td>
		<td>使用FreeMarker视图构建MVC Web应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-groovy-templates</td>
		<td>使用Groovy模板视图构建MVC Web应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-hateoas</td>
		<td>使用Spring MVC和Spring HATEOAS构建基于超媒体的RESTful Web应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-integration</td>
		<td>使用Spring Integration的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-jdbc</td>
		<td>将JDBC与HikariCP连接池一起使用的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-jersey</td>
		<td>使用JAX-RS和Jersey构建RESTful Web应用程序的启动器。 spring-boot-starter-web的替代品</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-jooq</td>
		<td>使用jOOQ访问SQL数据库的启动器。 spring-boot-starter-data-jpa或spring-boot-starter-jdbc的替代品</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-json</td>
		<td>读和写json的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-jta-atomikos</td>
		<td>使用Atomikos进行JTA事物的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-jta-bitronix</td>
		<td>使用Bitronix进行JTA事务的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-mail</td>
		<td>使用Java Mail和Spring Framework的电子邮件发送支持的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-mustache</td>
		<td>使用Mustache视图构建Web应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-oauth2-client</td>
		<td>使用Spring Security的OAuth2 / OpenID Connect客户端功能的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-oauth2-resource-server</td>
		<td>使用Spring Security的OAuth2资源服务器功能的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-quartz</td>
		<td>使用Quartz调度程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-security</td>
		<td>使用Spring Security的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-test</td>
		<td>使用JUnit，Hamcrest和Mockito等库来测试Spring Boot应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-thymeleaf</td>
		<td>使用Thymeleaf视图构建MVC Web应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-validation</td>
		<td>使用Java Bean Validation和Hibernate Validator的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-web</td>
		<td>使用Spring MVC构建Web（包括RESTful）应用程序的启动器。 使用Tomcat作为默认嵌入式容器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-web-services</td>
		<td>使用Spring Web Services的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-webflux</td>
		<td>使用Spring Framework的Reactive Web支持构建WebFlux应用程序的启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-websocket</td>
		<td>使用Spring Framework的WebSocket支持构建WebSocket应用程序的启动器</td>
		<td>Pom</td>
	</tr>
</table>

&emsp;&emsp;除应用程序启动器外，还可以使用以下启动器添加生产就绪功能：

表13.2 Spring Boot生产启动器

<table>
	<tr>
		<th>名称</th>
		<th>描述</th>
		<th>Pom</th>
	</tr>
	<tr>
		<td>spring-boot-starter-actuator</td>
		<td>使用Spring Boot的Actuator的启动器，它提供生产就绪功能，帮助您监控和管理您的应用程序</td>
		<td>Pom</td>
	</tr>
</table>

&emsp;&emsp;最后，如果要排除或交换特定的技术方面，Spring Boot还包括以下启动器：

表13.3 Spring Boot技术启动器

<table>
	<tr>
		<th>名称</th>
		<th>描述</th>
		<th>Pom</th>
	</tr>
	<tr>
		<td>spring-boot-starter-jetty</td>
		<td>使用Jetty作为嵌入式servlet容器的启动器。 spring-boot-starter-tomcat的替代品</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-log4j2</td>
		<td>使用Log4j2进行日志记录的启动器。 spring-boot-starter-logging的替代方案</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-logging</td>
		<td>使用Logback进行日志记录的启动器。 默认日志启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-reactor-netty</td>
		<td>使用Reactor Netty作为嵌入式响应式HTTP服务器的启动器。</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-tomcat</td>
		<td>使用Tomcat作为嵌入式servlet容器的启动器。 spring-boot-starter-web使用的默认servlet容器启动器</td>
		<td>Pom</td>
	</tr>
	<tr>
		<td>spring-boot-starter-undertow</td>
		<td>使用Undertow作为嵌入式servlet容器的启动器。 spring-boot-starter-tomcat的替代品</td>
		<td>Pom</td>
	</tr>
</table>

>有关其他社区贡献启动器的列表，请参阅GitHub上spring-boot-starters模块中的README文件。

## **3.2 结构化您的代码**

&emsp;&emsp;Spring Boot不需要任何特定的代码布局即可工作。 但是，有一些最佳实践可以提供帮助。

### **3.2.1 使用“default”包**

&emsp;&emsp;当类不包含包声明时，它被认为是在“默认包”中。 通常不鼓励使用“默认包”，应该避免使用。 对于使用@ComponentScan，@EntityScan或@SpringBootApplication注释的Spring Boot应用程序，它可能会导致特定问题，因为每个jar中的每个类都被读取。

>我们建议您遵循Java推荐的包命名约定并使用反向域名（例如，com.example.project）

### **3.2.2 找到主应用程序类**

&emsp;&emsp;我们通常建议您将主应用程序类放在其他类之上的根包中。 @SpringBootApplication注释通常放在您的主类上，它隐式地为某些项定义了一个基础“搜索包”。 例如，如果您正在编写JPA应用程序，则使用@SpringBootApplication带注释类的包来搜索@Entity项。 使用根包还允许组件扫描仅应用于您的项目。

>如果您不想使用@SpringBootApplication，它导入的@EnableAutoConfiguration和@ComponentScan注释会定义该行为，因此您也可以使用它。

&emsp;&emsp;以下清单显示了典型的布局：

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

&emsp;&emsp;Application.java文件将声明main方法以及基本的@SpringBootApplication，如下所示：

``` 
package com.example.myapplication;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

}
```

## **3.3 配置类**

&emsp;&emsp;Spring Boot支持基于Java的配置。尽管与XML源一起使用SpringApplication是可能的，但我们通常建议您的主源是一个单一的@Configuration类。通常，定义主方法的类是一个很好的候选对象，可以作为主@Configuration。

>许多Spring配置示例已在Internet上发布，使用XML配置。 如果可能，请始终尝试使用等效的基于Java的配置。 搜索Enable *注释可能是一个很好的起点。

### **3.3.1 导入其他配置类**

&emsp;&emsp;您无需将所有@Configuration放入单个类中。 @Import注释可用于导入其他配置类。 或者，您可以使用@ComponentScan自动获取所有Spring组件，包括@Configuration类。

### **3.3.2 导入XML配置**

&emsp;&emsp;如果您必须使用基于XML的配置，我们建议您仍然使用@Configuration类。 然后，您可以使用@ImportResource注解来加载XML配置文件。

## **3.4 自动配置**

&emsp;&emsp;Spring Boot自动配置尝试根据您添加的jar依赖项自动配置Spring应用程序。 例如，如果HSQLDB在您的类路径上，并且您尚未手动配置任何数据库连接bean，则Spring Boot会自动配置内存数据库。

&emsp;&emsp;您需要通过将@EnableAutoConfiguration或@SpringBootApplication注解添加到其中一个@Configuration类来选择自动配置。

>您应该只添加一个@SpringBootApplication或@EnableAutoConfiguration注释。 我们通常建议您仅将一个或另一个添加到主@Configuration类中。

### **3.4.1 逐步更换自动配置**

&emsp;&emsp;自动配置是非侵入性的。 在任何时候，您都可以开始定义自己的配置以替换自动配置的特定部分。 例如，如果添加自己的DataSource bean，则默认的嵌入式数据库支持会退回。

&emsp;&emsp;如果您需要了解当前正在应用的自动配置以及原因，请使用--debug开关启动您的应用程序。 这样做可以为选择的核心记录器启用调试日志，并将条件报告记录到控制台。

### **3.4.2 禁用特定的自动配置类**

&emsp;&emsp;如果发现正在应用您不需要的特定自动配置类，则可以使用@EnableAutoConfiguration的exclude属性禁用它们，如以下示例所示：

``` 
import org.springframework.boot.autoconfigure.*;
import org.springframework.boot.autoconfigure.jdbc.*;
import org.springframework.context.annotation.*;

@Configuration
@EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class})
public class MyConfiguration {
}
```

&emsp;&emsp;如果类不在类路径中，则可以使用批注的excludeName属性，而是指定完全限定名称。 最后，您还可以使用spring.autoconfigure.exclude属性控制要排除的自动配置类列表。

>您可以在注解级别和使用属性定义排除项。

## **3.5 Spring Beans和依赖注入**

&emsp;&emsp;您可以自由地使用任何标准的Spring Framework技术来定义bean及其注入的依赖项。 为简单起见，我们经常发现使用@ComponentScan（找到你的bean）并使用@Autowired（做构造函数注入）效果很好。

&emsp;&emsp;如果按照上面的建议构建代码（在根包中定位应用程序类），则可以添加不带任何参数的@ComponentScan。 所有应用程序组件（@Component，@Service，@Repository，@Controller等）都会自动注册为Spring Beans。

&emsp;&emsp;以下示例显示了一个@Service Bean，它使用构造函数注入来获取所需的RiskAssessor bean：

``` 
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

&emsp;&emsp;如果bean有一个构造函数，则可以省略@Autowired，如以下示例所示：

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

>请注意如何使用构造函数注入将riskAssessor字段标记为final，表示无法随后更改它。

## **3.6 使用@SpringBootApplication注解**

&emsp;&emsp;许多Spring Boot开发人员喜欢他们的应用程序使用自动配置，组件扫描，并能够在他们的“应用程序类”上定义额外的配置。 单个@SpringBootApplication注释可用于启用这三个功能，即：

- @EnableAutoConfiguration: 启用Spring Boot的自动配置机制
- @ComponentScan: 在应用程序所在的包上启用@Component扫描（请参阅最佳实践）
- @Configuration: 允许在上下文中注册额外的bean或导入其他配置类


&emsp;&emsp;@SpringBootApplication注释等同于使用@Configuration，@EnableAutoConfiguration和@ComponentScan及其默认属性，如以下示例所示：

``` 
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

>@SpringBootApplication还提供别名来自定义@EnableAutoConfiguration和@ComponentScan的属性。

&emsp;
>这些功能都不是必需的，您可以选择通过它启用的任何功能替换此单个注释。 例如，您可能不希望在应用程序中使用组件扫描： 

>```
package com.example.myapplication;
>
import org.springframework.boot.SpringApplication;
import org.springframework.context.annotation.ComponentScan
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Import;
>
@Configuration
@EnableAutoConfiguration
@Import({ MyConfig.class, MyAnotherConfig.class })
public class Application {
>
	public static void main(String[] args) {
			SpringApplication.run(Application.class, args);
	}
>
} 
>```
>在此示例中，Application与任何其他Spring Boot应用程序一样，只是不会自动检测@Component-注解类，并且显式导入用户定义的bean（请参阅@Import）。

## **3.7 运行您的应用程序**

&emsp;&emsp;将应用程序打包为jar并使用嵌入式HTTP服务器的最大优势之一是，您可以像运行任何其他程序一样运行应用程序。 调试Spring Boot应用程序也很容易。 您不需要任何特殊的IDE插件或扩展。

>本节仅涉及基于JAR的包装。如果选择将应用程序打包为WAR文件，则应参考服务器和IDE文档。

### **3.7.1 从IDE运行**

&emsp;&emsp;您可以从IDE运行Spring Boot应用程序作为简单的Java应用程序。 但是，您首先需要导入项目。 导入步骤因IDE和构建系统而异。 大多数IDE可以直接导入Maven项目。 例如，Eclipse用户可以从“文件”菜单中选择“导入...”→“现有Maven项目”。

&emsp;&emsp;如果无法将项目直接导入IDE，则可以使用构建插件生成IDE元数据。 Maven包含Eclipse和IDEA的插件。 Gradle提供各种IDE的插件。

>如果您不小心运行了两次Web应用程序，则会看到“端口已在使用中”错误。 STS用户可以使用“重新启动”按钮而不是“运行”按钮来确保关闭任何现有实例。

### **3.7.2 作为打包应用程序运行**

&emsp;&emsp;如果使用Spring Boot Maven或Gradle插件创建可执行jar，则可以使用java -jar运行应用程序，如以下示例所示：

``` 
$ java -jar target/myapplication-0.0.1-SNAPSHOT.jar
```

&emsp;&emsp;也可以运行启用了远程调试支持的打包应用程序。 这样做可以将调试器附加到打包的应用程序，如以下示例所示：

``` 
$ java -Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n \
       -jar target/myapplication-0.0.1-SNAPSHOT.jar
```

### **3.7.3 使用Maven插件**

&emsp;&emsp;Spring Boot Maven插件包含一个可用于快速编译和运行应用程序的运行目标。 应用程序以分解形式运行，就像在IDE中一样。 以下示例显示了运行Spring Boot应用程序的典型Maven命令：

``` 
$ mvn spring-boot:run
```

&emsp;&emsp;您可能还想使用MAVEN_OPTS操作系统环境变量，如以下示例所示：

``` 
$ export MAVEN_OPTS=-Xmx1024m
```

### **3.7.4 使用Gradle插件**

&emsp;&emsp;Spring Boot Gradle插件还包含一个bootRun任务，可用于以分解形式运行应用程序。 每当您应用org.springframework.boot和java插件时都会添加bootRun任务，如以下示例所示：

``` 
$ gradle bootRun
```

&emsp;&emsp;您可能还想使用JAVA_OPTS操作系统环境变量，如以下示例所示：

``` 
$ export JAVA_OPTS=-Xmx1024m
```

### **3.7.5 热部署**

&emsp;&emsp;由于Spring Boot应用程序只是普通的Java应用程序，因此JVM热部署应该是开箱即用的。 JVM热部署换在某种程度上受限于它可以替换的字节码。 要获得更完整的解决方案，可以使用JRebel。

&emsp;&emsp;spring-boot-devtools模块还支持快速重启应用程序。 有关详细信息，请参阅本章后面的第3.8章“开发者工具”部分和热部署“操作方法”。

## **3.8 开发者工具**

&emsp;&emsp;Spring Boot包含一组额外的工具，可以使应用程序开发体验更加愉快。 spring-boot-devtools模块可以包含在任何项目中，以提供额外的开发时间功能。 要包含devtools支持，请将模块依赖项添加到您的构建中，如以下Maven和Gradle列表中所示：

``` 
<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-devtools</artifactId>
		<optional>true</optional>
	</dependency>
</dependencies>
```

``` 
configurations {
	developmentOnly
	runtimeClasspath {
		extendsFrom developmentOnly
	}
}
dependencies {
	developmentOnly("org.springframework.boot:spring-boot-devtools")
}
```

>运行完全打包的应用程序时会自动禁用开发人员工具。 如果您的应用程序是从java -jar启动的，或者它是从特殊的类加载器启动的，那么它将被视为“生产应用程序”。 将依赖项标记为Maven中的可选项或在Gradle中使用自定义“开发”配置（如上所示）是防止devtools传递应用于使用项目的其他模块的最佳实践。

&emsp;

>重新打包的归档默认情况下不包含devtools。 如果要使用某个远程devtools功能，则需要禁用excludeDevtoolsbuild属性以包含它。 该属性由Maven和Gradle插件支持。

### **3.8.1 默认属性**

&emsp;&emsp;Spring Boot支持的几个库使用缓存来提高性能。 例如，模板引擎缓存已编译的模板以避免重复解析模板文件。 此外，Spring MVC可以在提供静态资源时为响应添加HTTP缓存标头。

&emsp;&emsp;虽然缓存在生产中非常有用，但在开发过程中可能会适得其反，使您无法看到刚刚在应用程序中进行的更改。 因此，spring-boot-devtools默认禁用缓存选项。

&emsp;&emsp;缓存选项通常由application.properties文件中的设置配置。 例如，Thymeleaf提供了spring.thymeleaf.cache属性。 spring-boot-devtools模块不需要手动设置这些属性，而是自动应用合理的开发时配置。

&emsp;&emsp;因为在开发Spring MVC和Spring WebFlux应用程序时需要有关Web请求的更多信息，所以开发人员工具将为Web日志记录组启用DEBUG日志记录。 这将为您提供有关传入请求，处理程序正在处理它，响应结果等的信息。如果您希望记录所有请求详细信息（包括可能的敏感信息），您可以打开spring.http.log-request-details配置属性。

> 如果您不希望应用属性默认值，则可以在application.properties中将spring.devtools.add-properties设置为false。

&emsp;
>有关devtools应用的属性的完整列表，请参阅DevToolsPropertyDefaultsPostProcessor。

### **3.8.2 自动重启**

&emsp;&emsp;使用spring-boot-devtools的应用程序会在类路径上的文件发生更改时自动重新启动。 在IDE中工作时，这可能是一个有用的功能，因为它为代码更改提供了非常快速的反馈循环。 默认情况下，将监视类路径上指向文件夹的任何条目的更改。 请注意，某些资源（如静态资产和视图模板）无需重新启动应用程序。

>**触发重启** 
由于DevTools监视类路径资源，因此触发重新启动的唯一方法是更新类路径。导致更新类路径的方式取决于您使用的IDE。在Eclipse中，保存修改后的文件会导致更新类路径并触发重新启动。 在IntelliJ IDEA中，构建项目（Build - > Build Project）具有相同的效果。

&emsp;
>只要启用了forking，您也可以使用受支持的构建插件（Maven和Gradle）启动应用程序，因为DevTools需要一个独立的应用程序类加载器才能正常运行。 默认情况下，Gradle和Maven在类路径上检测到DevTools时会这样做

&emsp;
>与LiveReload一起使用时，自动重启非常有效。 有关详细信息，请参阅LiveReload部分。 如果使用JRebel，则禁用自动重新启动以支持动态类重新加载。 其他devtools功能（例如LiveReload和属性覆盖）仍然可以使用。

&emsp;
>DevTools依赖于应用程序上下文的关闭钩子来在重启期间关闭它。 如果禁用了关闭挂钩（SpringApplication.setRegisterShutdownHook(false)），它将无法正常工作。

&emsp;
>当决定类路径上的条目是否应该在更改时触发重新启动时，DevTools会自动忽略名为spring-boot，spring-boot-devtools，spring-boot-autoconfigure，spring-boot-actuator和spring-boot-starter的项目。

&emsp;
>DevTools需要自定义ApplicationContext使用的ResourceLoader。 如果您的应用程序已经提供了一个，它将被包装。 不支持在ApplicationContext上直接覆盖getResource方法。

&emsp;
>**Restart vs Reload Spring Boot**
提供的重启技术使用两个类加载器。 不更改的类（例如，来自第三方jar的类）将加载到基类加载器中。 您正在积极开发的类将加载到重新启动的类加载器中。重新启动应用程序时，将重新启动重新启动的类加载器并创建一个新的类加载器。这种方法意味着应用程序重新启动通常比“冷启动”快得多，因为基本类加载器已经可用并已填充。 
>
如果您发现重新启动对应用程序来说不够快，或者遇到类加载问题，您可以考虑重新加载JRebelfrom ZeroTurnaround等技术。 这些工作通过在加载类时重写类以使它们更适合重新加载。

**3.8.2.1 记录条件评估中的更改**

&emsp;&emsp;默认情况下，每次应用程序重新启动时，都会记录一个显示条件评估增量的报告。 该报告显示了在进行更改（例如添加或删除Bean以及设置配置属性）时应用程序自动配置的更改。

&emsp;&emsp;要禁用报告的日志记录，请设置以下属性：

``` 
spring.devtools.restart.log-condition-evaluation-delta=false
```

**3.8.2.2 过滤资源**

&emsp;&emsp;某些资源在更改时不一定需要触发重启。 例如，可以就地编辑Thymeleaf模板。 默认情况下，更改/META-INF/maven，/META-INF/resources，/resources，/static，/public或/templates中的资源不会触发重新启动，但会触发实时重新加载。 如果要自定义这些排除项，可以使用spring.devtools.restart.exclude属性。 例如，要仅排除/static和/public，您需要设置以下属性：

``` 
spring.devtools.restart.exclude=static/**,public/**
```

>如果要保留这些默认值并添加其他排除项，请改用spring.devtools.restart.additional-exclude属性。

**3.8.2.3 观察其他路径**

&emsp;&emsp;当您对不在类路径中的文件进行更改时，您可能希望重新启动或重新加载应用程序。 为此，请使用spring.devtools.restart.additional-paths属性配置其他路径以监视更改。 您可以使用前面描述的spring.devtools.restart.exclude属性来控制其他路径下的更改是触发完全重新启动还是实时重新加载。

**3.8.2.4 禁用重启**

&emsp;&emsp;如果需要完全禁用重新启动支持（例如，因为它不能与特定库一起使用），则需要在调用SpringApplication.ru(...)之前将spring.devtools.restart.enabled System属性设置为false，如下例所示：

``` 
public static void main(String[] args) {
	System.setProperty("spring.devtools.restart.enabled", "false");
	SpringApplication.run(MyApp.class, args);
}
```

**3.8.2.5 使用触发器文件**

&emsp;&emsp;如果使用不断编译已更改文件的IDE，则可能更喜欢仅在特定时间触发重新启动。 为此，您可以使用“触发器文件”，这是一个特殊文件，当您想要实际触发重新启动检查时，必须对其进行修改。 更改文件只会触发检查，只有在Devtools检测到必须执行某些操作时才会重新启动。 触发器文件可以手动更新，也可以使用IDE插件更新。

&emsp;&emsp;要使用触发器文件，请将spring.devtools.restart.trigger-file属性设置为触发器文件的路径。

>您可能希望将spring.devtools.restart.trigger文件设置为全局设置，以便所有项目的行为方式相同。

**3.8.2.6 自定义重新启动类加载器**

&emsp;&emsp;如前面在Restart vs Reload部分中所述，使用两个类加载器实现了重启功能。 对于大多数应用程序，这种方法很有效。 但是，它有时会导致类加载问题。

&emsp;&emsp;默认情况下，IDE中的任何打开项目都使用“restart”类加载器加载，并且任何常规.jar文件都使用“base”类加载器加载。 如果您处理多模块项目，并且并非每个模块都导入到IDE中，则可能需要自定义内容。 为此，您可以创建META-INF/spring-devtools.properties文件。

&emsp;&emsp;spring-devtools.properties文件可以包含以restart.exclude和restart.include为前缀的属性。 include元素是应该被提取到“restart”类加载器中的项，而exclude元素是应该被下推到“base”类加载器中的项。 属性的值是应用于类路径的正则表达式模式，如以下示例所示：

``` 
restart.exclude.companycommonlibs=/mycorp-common-[\\w-]+\.jar
restart.include.projectcommon=/mycorp-myproj-[\\w-]+\.jar
```

>所有属性键必须是唯一的。 只要属性以restart.include开头即可。 或者restart.exclude。 已经被考虑了。

&emsp;
>将加载类路径中的所有META-INF / spring-devtools.properties。 您可以将文件打包到项目中，也可以打包在项目使用的库中。

**3.8.2.7 已知限制**

&emsp;&emsp;对于使用标准ObjectInputStream反序列化的对象，重新启动功能不起作用。 如果需要反序列化数据，可能需要将Spring的ConfigurableObjectInputStream与Thread.currentThread()。getContextClassLoader()结合使用。

&emsp;&emsp;不幸的是，几个第三方库反序列化而不考虑上下文类加载器。 如果您发现此类问题，则需要向原作者请求修复。

### **3.8.3 LiveReload**

&emsp;&emsp;spring-boot-devtools模块包含一个嵌入式LiveReload服务器，可用于在更改资源时触发浏览器刷新。 LiveReload浏览器扩展程序可从livereload.com免费用于Chrome，Firefox和Safari。

>您一次只能运行一个LiveReload服务器。 在启动应用程序之前，请确保没有其他LiveReload服务器正在运行。 如果从IDE启动多个应用程序，则只有第一个具有LiveReload支持。<

### **3.8.4 全局设置**

&emsp;&emsp;您可以通过将名为.spring-boot-devtools.properties的文件添加到$ HOME文件夹来配置全局devtools设置（请注意，文件名以“.”开头）。 添加到此文件的任何属性都适用于计算机上使用devtools的所有Spring Boot应用程序。 例如，要将restart配置为始终使用触发器文件，您将添加以下属性：
```
~/.spring-boot-devtools.properties. 
```
``` 
spring.devtools.reload.trigger-file=.reloadtrigger
```

>在.spring-boot-devtools.properties中激活的配置文件不会影响特定于配置文件的配置文件的加载。

### **3.8.5 远程应用**

&emsp;&emsp;Spring Boot开发人员工具不仅限于本地开发。 远程运行应用程序时，您还可以使用多个功能。 远程支持是选择加入。 要启用它，您需要确保devtools包含在重新打包的存档中，如下面的清单所示：

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

&emsp;&emsp;然后，您需要设置spring.devtools.remote.secret属性，如以下示例所示：

``` 
spring.devtools.remote.secret=mysecret
```

>在远程应用程序上启用spring-boot-devtools存在安全风险。 您永远不应该在生产部署上启用支持。

&emsp;&emsp;远程devtools支持分为两部分：接受连接的服务器端端点和在IDE中运行的客户端应用程序。 设置spring.devtools.remote.secret属性时，将自动启用服务器组件。 必须手动启动客户端组件。

**3.8.5.1 运行远程客户端应用程序**

&emsp;&emsp;远程客户端应用程序旨在从IDE中运行。 您需要运行org.springframework.boot.devtools.RemoteSpringApplication，其类路径与您连接的远程项目相同。 应用程序的单个必需参数是它连接的远程URL。

例如，如果您使用的是Eclipse或STS，并且已经部署到Cloud Foundry的项目名为my-app，那么您将执行以下操作：

- 从“Run”菜单中选择“Run Configurations…”。
- 创建一个新的Java应用程序“launch configuration”。
- 浏览my-app程序项目。
- 使用org.springframework.boot.devtools.RemoteSpringApplication作为主类。
- 将https://myapp.cfapps.io添加到Program参数（或任何远程URL）。


&emsp;&emsp;正在运行的远程客户端可能类似于以下列表：

``` 
.   ____          _                                              __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _          ___               _      \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` |        | _ \___ _ __  ___| |_ ___ \ \ \ \
 \\/  ___)| |_)| | | | | || (_| []::::::[]   / -_) '  \/ _ \  _/ -_) ) ) ) )
  '  |____| .__|_| |_|_| |_\__, |        |_|_\___|_|_|_\___/\__\___|/ / / /
 =========|_|==============|___/===================================/_/_/_/
 :: Spring Boot Remote :: 2.1.3.RELEASE

2015-06-10 18:25:06.632  INFO 14938 --- [           main] o.s.b.devtools.RemoteSpringApplication   : Starting RemoteSpringApplication on pwmbp with PID 14938 (/Users/pwebb/projects/spring-boot/code/spring-boot-devtools/target/classes started by pwebb in /Users/pwebb/projects/spring-boot/code/spring-boot-samples/spring-boot-sample-devtools)
2015-06-10 18:25:06.671  INFO 14938 --- [           main] s.c.a.AnnotationConfigApplicationContext : Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext@2a17b7b6: startup date [Wed Jun 10 18:25:06 PDT 2015]; root of context hierarchy
2015-06-10 18:25:07.043  WARN 14938 --- [           main] o.s.b.d.r.c.RemoteClientConfiguration    : The connection to http://localhost:8080 is insecure. You should use a URL starting with 'https://'.
2015-06-10 18:25:07.074  INFO 14938 --- [           main] o.s.b.d.a.OptionalLiveReloadServer       : LiveReload server is running on port 35729
2015-06-10 18:25:07.130  INFO 14938 --- [           main] o.s.b.devtools.RemoteSpringApplication   : Started RemoteSpringApplication in 0.74 seconds (JVM running for 1.105)
```

>因为远程客户端使用与真实应用程序相同的类路径，所以它可以直接读取应用程序属性。 这是如何读取spring.devtools.remote.secret属性并将其传递给服务器进行身份验证的方法。

&emsp;
>始终建议使用https：//作为连接协议，以便加密流量并且不会截获密码。

&emsp;
>如果需要使用代理来访问远程应用程序，请配置spring.devtools.remote.proxy.host和spring.devtools.remote.proxy.port属性。

**3.8.5.2 远程更新**

&emsp;&emsp;远程客户端以与本地重新启动相同的方式监视应用程序类路径以进行更改。 任何更新的资源都会被推送到远程应用程序，并且（如果需要）会触发重新启动。 如果您迭代使用本地没有的云服务的功能，这将非常有用。 通常，远程更新和重新启动比完全重建和部署周期快得多。

>仅在远程客户端运行时监视文件。 如果在启动远程客户端之前更改文件，则不会将其推送到远程服务器。

## **3.9 打包用于生产中的应用**

&emsp;&emsp;可执行jar可用于生产部署。 由于它们是独立的，因此它们也非常适合基于云的部署。

&emsp;&emsp;对于其他“生产就绪”功能，例如运行状况，审计和度量REST或JMX端点，请考虑添加spring-boot-actuator。 有关详细信息，请参见第5章“spring boot启动执行器：生产就绪功能”。

## **3.10 接下来要阅读的内容**

&emsp;&emsp;您现在应该了解如何使用Spring Boot以及您应该遵循的一些最佳实践。 您现在可以继续深入了解特定的Spring Boot功能，或者您可以跳过并阅读Spring Boot的“生产就绪”方面。

# **4 Spring Boot功能**

&emsp;&emsp;本节深入介绍Spring Boot的详细信息。 在这里，您可以了解您可能想要使用和自定义的主要功能。 如果您还没有这样做，您可能需要阅读“第2章 入门”和“第3章 使用Spring Boot”部分，以便您掌握基础知识。

## **4.1 SpringApplication**

&emsp;&emsp;SpringApplication类提供了一种方便的方法来引导从main()方法启动的Spring应用程序。 在许多情况下，您可以委托静态SpringApplication.run方法，如以下示例所示：

``` 
public static void main(String[] args) {
	SpringApplication.run(MySpringConfiguration.class, args);
}
```

&emsp;&emsp;当您的应用程序启动时，您应该看到类似于以下输出的内容：

``` 
.   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::   v2.1.3.RELEASE

2013-07-31 00:08:16.117  INFO 56603 --- [           main] o.s.b.s.app.SampleApplication            : Starting SampleApplication v0.1.0 on mycomputer with PID 56603 (/apps/myapp.jar started by pwebb)
2013-07-31 00:08:16.166  INFO 56603 --- [           main] ationConfigServletWebServerApplicationContext : Refreshing org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@6e5a8246: startup date [Wed Jul 31 00:08:16 PDT 2013]; root of context hierarchy
2014-03-04 13:09:54.912  INFO 41370 --- [           main] .t.TomcatServletWebServerFactory : Server initialized with port: 8080
2014-03-04 13:09:56.501  INFO 41370 --- [           main] o.s.b.s.app.SampleApplication            : Started SampleApplication in 2.992 seconds (JVM running for 3.658)
```

&emsp;&emsp;默认情况下，会显示INFO日志记录消息，包括一些相关的启动详细信息，例如启动应用程序的用户。 如果需要INFO以外的日志级别，可以按照第4.4.4节“日志级别”中的说明进行设置。

### **4.1.1 启动失败**

&emsp;&emsp;如果您的应用程序无法启动，则已注册的FailureAnalyzers有机会提供专用错误消息和具体操作来解决问题。 例如，如果您在端口8080上启动Web应用程序并且该端口已在使用中，您应该会看到类似于以下消息的内容：

``` 
***************************
APPLICATION FAILED TO START
***************************

Description:

Embedded servlet container failed to start. Port 8080 was already in use.

Action:

Identify and stop the process that's listening on port 8080 or configure this application to listen on another port.
```

>Spring Boot提供了许多FailureAnalyzer实现，您可以添加自己的。

&emsp;&emsp;如果没有故障分析器能够处理异常，您仍然可以显示完整的条件报告，以便更好地了解出现了什么问题。 为此，您需要启用debug属性或为org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLoggingListener启用DEBUG日志记录。

例如，如果使用java -jar运行应用程序，则可以按如下方式启用debug属性：

``` 
$ java -jar myproject-0.0.1-SNAPSHOT.jar --debug
```

### **4.1.2 自定义Banner**

&emsp;&emsp;可以通过将banner.txt文件添加到类路径或将spring.banner.location属性设置为此类文件的位置来更改启动时打印的Banner。 如果文件的编码不是UTF-8，则可以设置spring.banner.charset。 除了文本文件，您还可以将banner.gif，banner.jpg或banner.png图像文件添加到类路径或设置spring.banner.image.location属性。 图像将转换为ASCII艺术表示，并打印在任何文本Banner上方。

&emsp;&emsp;在banner.txt文件中，您可以使用以下任何占位符：

表23.1 banner变量

<table>
	<tr>
		<th>变量</th>
		<th>描述</th>
	</tr>
	<tr>
		<td>\${application.version}</td>
		<td>应用程序的版本号，如MANIFEST.MF中声明的那样。例如，Implementation-Version:1.0打印为1.0。</td>
	</tr>
	<tr>
		<td>\${application.formatted-version}</td>
		<td>应用程序的版本号，在MANIFEST.MF中声明并格式化以供显示（用括号括起来并以v为前缀）。 例如（v1.0）。</td>
	</tr>
	<tr>
		<td>\${spring-boot.version}</td>
		<td>您正在使用的Spring Boot版本。 例如2.1.3.RELEASE。</td>
	</tr>
	<tr>
		<td>\${spring-boot.formatted-version}</td>
		<td>您正在使用的Spring Boot版本，格式化显示（用括号括起来并以v为前缀）。 例如（v2.1.3.RELEASE）。</td>
	</tr>
	<tr>
		<td>\${Ansi.NAME} (或\${AnsiColor.NAME},\${AnsiBackground.NAME}, \${AnsiStyle.NAME})</td>
		<td>其中NAME是ANSI转义码的名称。 有关详细信息，请参见AnsiPropertySource。</td>
	</tr>
	<tr>
		<td>\${application.title}</td>
		<td>应用程序的标题，在MANIFEST.MF中声明。 例如，标题：MyApp打印为MyApp。</td>
	</tr>
</table>

>如果要以编程方式生成横幅，可以使用SpringApplication.setBanner（...）方法。 使用org.springframework.boot.Banner接口并实现自己的printBanner（）方法。

&emsp;&emsp;您还可以使用spring.main.banner-mode属性来确定是否必须在System.out（控制台）上打印横幅，发送到配置的logger（日志），或者根本不生成横幅（关闭）。

&emsp;&emsp;打印的横幅在以下名称下注册为单例bean：springBootBanner。

>YAML映射为false，因此如果要在应用程序中禁用横幅，请务必添加引号，如以下示例所示： 

>```
spring:
	main:
		banner-mode: "off"
>```

### **4.1.3 自定义SpringApplication**

&emsp;&emsp;如果SpringApplication默认值不符合您的需要，您可以改为创建本地实例并对其进行自定义。 例如，要关闭横幅，您可以写：

``` 
public static void main(String[] args) {
	SpringApplication app = new SpringApplication(MySpringConfiguration.class);
	app.setBannerMode(Banner.Mode.OFF);
	app.run(args);
}
```

>传递给SpringApplication的构造函数参数是Spring bean的配置源。 在大多数情况下，这些是对@Configuration类的引用，但它们也可以是对XML配置或应扫描的包的引用。

&emsp;&emsp;也可以使用application.properties文件配置SpringApplication。 有关详细信息，请参见第4.2节 外部化配置。

&emsp;&emsp;有关配置选项的完整列表，请参阅SpringApplication Javadoc。

### **4.1.4 Fluent Builder API**

&emsp;&emsp;如果需要构建ApplicationContext层次结构（具有父/子关系的多个上下文），或者如果您更喜欢使用“Stream”构建器API，则可以使用SpringApplicationBuilder。

&emsp;&emsp;SpringApplicationBuilder允许您将多个方法调用链接在一起，并包含允许您创建层次结构的父方法和子方法，如以下示例所示：

``` 
new SpringApplicationBuilder()
		.sources(Parent.class)
		.child(Application.class)
		.bannerMode(Banner.Mode.OFF)
		.run(args);
```

>创建ApplicationContext层次结构时存在一些限制。 例如，Web组件必须包含在子上下文中，并且相同的Environment用于父上下文和子上下文。 有关完整的详细信息，请参阅SpringApplicationBuilder Javadoc。

### **4.1.5 应用程序事件和监听器**

&emsp;&emsp;除了通常的Spring Framework事件（例如ContextRefreshedEvent）之外，SpringApplication还会发送一些其他应用程序事件。

>某些事件实际上是在创建ApplicationContext之前触发的，因此您无法将这些事件的侦听器注册为@Bean。 您可以使用SpringApplication.addListeners(...)方法或SpringApplicationBuilder.listeners(...)方法注册它们。 如果您希望自动注册这些侦听器，无论应用程序的创建方式如何，您都可以将META-INF/spring.factories文件添加到项目中，并使用org.springframework.context.ApplicationListener 键引用侦听器。 如以下示例所示：

>```
org.springframework.context.ApplicationListener=com.example.project.MyListener
>```

&emsp;&emsp;

&emsp;&emsp;应用程序运行时，应按以下顺序发送应用程序事件：

1. ApplicationStartingEvent：开始运行但在任何处理之前，除了监听器和初始化器的注册。
2. ApplicationEnvironmentPreparedEvent：已经知道上下文的Environment，但还未创建上下文
3. ApplicationPreparedEvent：在刷新开始之前但是在加载bean定义之后。
4. ApplicationStartedEvent：在刷新上下文之后但在调用任何应用程序和命令行运行程序之前。
5. ApplicationReadyEvent：在调用任何应用程序和命令行运行程序之后。 它表示应用程序已准备好为请求提供服务。
6. ApplicationFailedEvent：如果启动时有异常。

>您通常不需要使用应用程序事件，但知道它们存在可能很方便。 在内部，Spring Boot使用事件来处理各种任务。

&emsp;&emsp;使用Spring Framework的事件发布机制发送应用程序事件。 此机制的一部分确保发布到子上下文中的侦听器的事件也发布到任何祖先上下文中的侦听器。 因此，如果您的应用程序使用SpringApplication实例的层次结构，则侦听器可能会收到相同类型的应用程序事件的多个实例。

&emsp;&emsp;为了允许侦听器区分其上下文的事件和后代上下文的事件，它应该请求注入其应用程序上下文，然后将注入的上下文与事件的上下文进行比较。 可以通过实现ApplicationContextAware来注入上下文，或者，如果监听器是bean，则使用@Autowired来注入。

### **4.1.6 网络环境**

&emsp;&emsp;SpringApplication尝试代表您创建正确类型的ApplicationContext。 用于确定WebApplicationType的算法非常简单：

- 如果存在Spring MVC，则使用AnnotationConfigServletWebServerApplicationContext
- 如果Spring MVC不存在且存在Spring WebFlux，则使用AnnotationConfigReactiveWebServerApplicationContext
- 否则，使用AnnotationConfigApplicationContext

&emsp;&emsp;这意味着如果您在同一个应用程序中使用Spring MVC和Spring WebFlux中的新WebClient，则默认情况下将使用Spring MVC。 您可以通过调用setWebApplicationType(WebApplicationType)轻松覆盖它。

&emsp;&emsp;也可以调用setApplicationContextClass(...)完全控制使用的ApplicationContext类型。

>在JUnit测试中使用SpringApplication时，通常需要调用setWebApplicationType(WebApplicationType.NONE)。

### **4.1.7 访问应用程序参数**

&emsp;&emsp;如果需要访问传递给SpringApplication.run(...)的应用程序参数，可以注入org.springframework.boot.ApplicationArguments bean。 ApplicationArguments接口提供对原始String []参数以及解析选项和非选项参数的访问，如以下示例所示：

``` 
import org.springframework.boot.*;
import org.springframework.beans.factory.annotation.*;
import org.springframework.stereotype.*;

@Component
public class MyBean {

	@Autowired
	public MyBean(ApplicationArguments args) {
		boolean debug = args.containsOption("debug");
		List<String> files = args.getNonOptionArgs();
		// if run with "--debug logfile.txt" debug=true, files=["logfile.txt"]
	}

}
```

>Spring Boot还在Spring Environment中注册了一个CommandLinePropertySource。 这使您还可以使用@Value注释注入单个应用程序参数。

### **4.1.8 使用ApplicationRunner或CommandLineRunner**

&emsp;&emsp;如果在SpringApplication启动后需要运行某些特定代码，则可以实现ApplicationRunner或CommandLineRunner接口。 两个接口以相同的方式工作，并提供单个run方法，该方法在SpringApplication.run(...)完成之前调用。

&emsp;&emsp;CommandLineRunner接口提供对应用程序参数的访问，作为简单的字符串数组，而ApplicationRunner使用前面讨论的ApplicationArguments接口。 以下示例显示了带有run方法的CommandLineRunner：

``` 
import org.springframework.boot.*;
import org.springframework.stereotype.*;

@Component
public class MyBean implements CommandLineRunner {

	public void run(String... args) {
		// Do something...
	}

}
```

&emsp;&emsp;如果定义了必须按特定顺序调用的多个CommandLineRunner或ApplicationRunner bean，则可以另外实现org.springframework.core.Ordered接口或使用org.springframework.core.annotation.Order注释。

### **4.1.9 退出应用**

&emsp;&emsp;每个SpringApplication都会向JVM注册一个关闭钩子，以确保ApplicationContext在退出时正常关闭。 可以使用所有标准的Spring生命周期回调（例如DisposableBean接口或@PreDestroy注释）。

&emsp;&emsp;此外，如果bean希望在调用SpringApplication.exit()时返回特定的退出代码，则bean可以实现org.springframework.boot.ExitCodeGenerator接口。 然后可以将此退出代码传递给System.exit()以将其作为状态代码返回，如以下示例所示：

``` 
@SpringBootApplication
public class ExitCodeApplication {

	@Bean
	public ExitCodeGenerator exitCodeGenerator() {
		return () -> 42;
	}

	public static void main(String[] args) {
		System.exit(SpringApplication
				.exit(SpringApplication.run(ExitCodeApplication.class, args)));
	}

}
```

&emsp;&emsp;此外，ExitCodeGenerator接口可以通过异常实现。 遇到这样的异常时，Spring Boot返回实现的getExitCode()方法提供的退出代码。

### **4.1.10 管理功能**

&emsp;&emsp;通过指定spring.application.admin.enabled属性，可以为应用程序启用与管理相关的功能。 这会在平台MBeanServer上公开SpringApplicationAdminMXBean。 您可以使用此功能远程管理Spring Boot应用程序。 此功能对于任何服务包装器实现也很有用。

>如果您想知道应用程序正在运行的HTTP端口，请使用local.server.port的键获取该属性。

&emsp;
>启用此功能时要小心，因为MBean公开了一种关闭应用程序的方法。

## **4.2 外部配置**

&emsp;&emsp;Spring Boot允许您外部化配置，以便您可以在不同的环境中使用相同的应用程序代码。 您可以使用属性文件，YAML文件，环境变量和命令行参数来外部化配置。 可以使用@Value注释将属性值直接注入到bean中，通过Spring的Environment抽象访问，或者通过@ConfigurationProperties绑定到结构化对象。

&emsp;&emsp;Spring Boot使用一个非常特殊的PropertySource命令，旨在允许合理地覆盖值。 按以下顺序考虑属性：

1. 在您的主目录上开发全局设置属性（当devtools处于活动状态时，〜/.spring-boot-devtools.properties）。
2. @TestPropertySource测试注释。
3. 测试中的properties属性。 可在@SpringBootTest上使用，以及用于测试应用程序特定片段的测试注释。
4. 命令行参数。
5. SPRING_APPLICATION_JSON中的属性（嵌入在环境变量或系统属性中的内联JSON）。
6. ServletConfig初始化参数。
7. ServletContext初始化参数。
8. 来自java:comp/env的JNDI属性。
9. Java系统属性（System.getProperties()）。
10. OS环境变量。
11. RandomValuePropertySource，只具有random.*.属性。
12. 特定于配置文件的应用程序属性在打包的jar之外（application-{profile}.properties和YAML变体）。
13. 打包在jar中的特定于配置文件的应用程序属性（application-{profile}.properties和YAML变体）。
14. 打包jar之外的应用程序属性（application.properties和YAML变体）。
15. 打包在jar中的应用程序属性（application.properties和YAML变体）。
16. @Configuration类上的@PropertySource注释。
17. 默认属性（通过设置SpringApplication.setDefaultProperties指定）。


&emsp;&emsp;要提供一个具体示例，假设您开发了一个使用name属性的@Component，如以下示例所示：

``` 
import org.springframework.stereotype.*;
import org.springframework.beans.factory.annotation.*;

@Component
public class MyBean {

    @Value("${name}")
    private String name;

    // ...

}
```

&emsp;&emsp;在应用程序类路径上（例如，在jar中），您可以拥有一个application.properties文件，该文件为name提供合理的默认属性值。 在新环境中运行时，可以在jar之外提供覆盖名称的application.properties文件。 对于一次性测试，您可以使用特定的命令行开关启动（例如，java -jar app.jar --name =“Spring”）。

>可以在命令行上使用环境变量提供SPRING_APPLICATION_JSON属性。 例如，您可以在UN * X shell中使用以下行： 

>```
$ SPRING_APPLICATION_JSON='{"acme":{"name":"test"}}' java -jar myapp.jar
>```

>在前面的示例中，您最终在Spring环境中使用了acme.name = test。您还可以在System属性中将JSON作为spring.application.json提供，如以下示例所示： 

>```
$ java -Dspring.application.json='{"name":"test"}' -jar myapp.jar
>```

>您还可以使用命令行参数提供JSON，如以下示例所示： 

>```
$ java -jar myapp.jar --spring.application.json='{"name":"test"}'
>```

>您还可以将JSON作为JNDI变量提供，如下所示：java:comp/env/spring.application.json。

### **4.2.1 配置随机值**

&emsp;&emsp;RandomValuePropertySource对于注入随机值非常有用（例如，注入密钥或测试用例）。 它可以生成整数，长整数，uuids或字符串，如以下示例所示：

``` 
my.secret=${random.value}
my.number=${random.int}
my.bignumber=${random.long}
my.uuid=${random.uuid}
my.number.less.than.ten=${random.int(10)}
my.number.in.range=${random.int[1024,65536]}
```

&emsp;&emsp;random.int *语法是OPEN值（，max）CLOSE，其中OPEN，CLOSE是任何字符和值，max是整数。 如果提供了max，则value是最小值，max是最大值（不包括）。

### **4.2.2 访问命令行属性**

&emsp;&emsp;默认情况下，SpringApplication将任何命令行选项参数（即以 - 开头的参数，例如--server.port = 9000）转换为属性，并将它们添加到Spring环境中。 如前所述，命令行属性始终优先于其他属性源。

&emsp;&emsp;如果您不希望将命令行属性添加到Environment，可以使用SpringApplication.setAddCommandLineProperties(false)禁用它们。

### **4.2.3 应用属性文件**

&emsp;&emsp;SpringApplication从以下位置的application.properties文件加载属性，并将它们添加到Spring环境中：

1. 一个当前目录的/config子目录
2. 当前目录
3. 一个classpath下的/config包
4. classpath根目录

&emsp;&emsp;列表按优先级排序（在列表中较高位置定义的属性将覆盖在较低位置中定义的属性）。

>您还可以使用YAML（'.yml'）文件替代'.properties'。

&emsp;&emsp;如果您不喜欢application.properties作为配置文件名，则可以通过指定spring.config.name环境属性来切换到另一个文件名。 您还可以使用spring.config.location环境属性（以逗号分隔的目录位置或文件路径列表）来引用显式位置。 以下示例显示如何指定其他文件名：

``` 
$ java -jar myproject.jar --spring.config.name=myproject
```

&emsp;&emsp;以下示例显示如何指定两个位置：

``` 
$ java -jar myproject.jar --spring.config.location=classpath:/default.properties,classpath:/override.properties
```

>spring.config.name和spring.config.location是最早用来确定必须加载哪些文件的属性， 因此必须将它们定义为环境属性（通常是OS环境变量，系统属性或命令行参数）。

&emsp;&emsp;如果spring.config.location包含目录（而不是文件），则它们应该以/结尾（并且在运行时，在加载之前附加从spring.config.name生成的名称，包括特定于配置文件的文件名）。 spring.config.location中指定的文件按原样使用，不支持特定于配置文件的变体，并且被任何特定于配置文件的属性覆盖。

&emsp;&emsp;以相反的顺序搜索配置位置。 默认情况下，配置的位置是classpath:/，classpath:/config/，file:./，file:./config/。 生成的搜索顺序如下：

1. file:./config/
2. file:./
3. classpath:/config/
4. classpath:/


&emsp;&emsp;使用spring.config.location配置自定义配置位置时，它们将替换默认位置。 例如，如果spring.config.location配置了值classpath:/custom-config/，file:./custom-config/，搜索顺序将变为以下内容：

1. file:./custom-config/
2. classpath:custom-config/


&emsp;&emsp;或者，当使用spring.config.additional-location配置自定义配置位置时，除默认位置外，还会使用它们。 在默认位置之前搜索其他位置。 例如，如果配置了classpath:/custom-config/，file:./custom-config/的其他位置，则搜索顺序将变为以下内容：

1. file:./custom-config/
2. classpath:custom-config/
3. file:./config/
4. file:./
5. classpath:/config/
6. classpath:/


&emsp;&emsp;此搜索顺序允许您在一个配置文件中指定默认值，然后有选择地覆盖另一个配置文件中的值。 您可以在其中一个默认位置的application.properties（或使用spring.config.name选择的任何其他基本名称）中为应用程序提供默认值。 然后，可以在运行时使用位于其中一个自定义位置的不同文件覆盖这些默认值。

>如果使用环境变量而不是系统属性，则大多数操作系统都不允许使用句点分隔的键名，但您可以使用下划线（例如，使用SPRING_CONFIG_NAME而不是spring.config.name）。

&emsp;
>如果应用程序在容器中运行，则可以使用JNDI属性（在java:comp/env中）或servlet上下文初始化参数来代替环境变量或系统属性。

### **4.2.4 特定于配置文件的属性**

&emsp;&emsp;除application.properties文件外，还可以使用以下命名约定定义特定于配置文件的属性：application-{profile} .properties。 环境具有一组默认配置文件（默认情况下为[default]），如果未设置活动配置文件，则使用这些配置文件。 换句话说，如果未显式激活任何配置文件，则会加载application-default.properties中的属性。

&emsp;&emsp;特定于配置文件的属性从与标准application.properties相同的位置加载，特定于配置文件的文件始终覆盖非特定文件，无论特定于配置文件的文件是在打包的jar内部还是外部。

&emsp;&emsp;如果指定了多个配置文件，则应用最后获胜策略。 例如，spring.profiles.active属性指定的配置文件是在通过SpringApplication API配置的配置文件之后添加的，因此优先。

>如果在spring.config.location中指定了任何文件，则不考虑这些文件的特定于配置文件的变体。 如果要使用特定于配置文件的属性，请使用spring.config.location中的目录。

### **4.2.5 属性中的占位符**

&emsp;&emsp;application.properties中的值在使用时通过现有环境进行过滤，因此您可以返回先前定义的值（例如，系统属性）。

``` 
app.name=MyApp
app.description=${app.name} is a Spring Boot application
```

>您还可以使用此技术创建现有Spring Boot属性的“简短”变体。 有关详细信息，请参见第9.3.4节“使用'短'命令行参数”操作方法。

### **4.2.6 加密属性**

&emsp;&emsp;Spring Boot没有为加密属性值提供任何内置支持，但是，它确实提供了修改Spring环境中包含的值所必需的钩子点。 EnvironmentPostProcessor接口允许您在应用程序启动之前操作Environment。 有关详细信息，请参见第9.1.3节“在开始之前自定义环境或ApplicationContext”。

&emsp;&emsp;如果您正在寻找一种存储凭据和密码的安全方法，Spring Cloud Vault项目支持在HashiCorp Vault中存储外部化配置。

### **4.2.7 使用YAML而不是properties**

&emsp;&emsp;YAML是JSON的超集，因此是用于指定分层配置数据的便捷格式。 只要在类路径上有SnakeYAML库，SpringApplication类就会自动支持YAML作为properties的替代。

>如果使用“Starters”，则Spring-boot-starter会自动提供SnakeYAML。

**4.2.7.1 读取YAML**

&emsp;&emsp;Spring Framework提供了两个方便的类，可用于加载YAML文档。 YamlPropertiesFactoryBean将YAML加载为Properties，YamlMapFactoryBean将YAML加载为Map。

例如，请考虑以下YAML文档：

``` 
environments:
	dev:
		url: http://dev.example.com
		name: Developer Setup
	prod:
		url: http://another.example.com
		name: My Cool App
```

&emsp;&emsp;前面的示例将转换为以下属性：

``` 
environments.dev.url=http://dev.example.com
environments.dev.name=Developer Setup
environments.prod.url=http://another.example.com
environments.prod.name=My Cool App
```

&emsp;&emsp;YAML列表表示为带有[index]解除引用的属性键。 例如，考虑以下YAML：

``` 
my:
servers:
	- dev.example.com
	- another.example.com
```

&emsp;&emsp;前面的示例将转换为这些属性：

``` 
my.servers[0]=dev.example.com
my.servers[1]=another.example.com
```

&emsp;&emsp;要使用Spring Boot的Binder实用程序（这是@ConfigurationProperties所做的）绑定到这样的属性，你需要在java.util.List（或Set）类型的目标bean中有一个属性，你需要提供一个setter 或者用可变值初始化它。 例如，以下示例绑定到前面显示的属性：

``` 
@ConfigurationProperties(prefix="my")
public class Config {

	private List<String> servers = new ArrayList<String>();

	public List<String> getServers() {
		return this.servers;
	}
}
```

**4.2.7.2 在Spring环境中将YAML公开为属性**

&emsp;&emsp;YamlPropertySourceLoader类可用于在Spring环境中将YAML公开为PropertySource。 这样做可以使用带占位符语法的@Value批注来访问YAML属性。

**4.2.7.3 多个YAML文件**

&emsp;&emsp;您可以使用spring.profiles键在单个文件中指定多个特定于配置文件的YAML文档，以指示文档何时应用，如以下示例所示：

``` 
server:
	address: 192.168.1.100
---
spring:
	profiles: development
server:
	address: 127.0.0.1
---
spring:
	profiles: production & eu-central
server:
	address: 192.168.1.120
```

&emsp;&emsp;在前面的示例中，如果development文件处于活动状态，则server.address属性为127.0.0.1。 同样，如果production和eu-central配置文件处于活动状态，则server.address属性为192.168.1.120。 如果未启用development，production和eu-central配置文件，则该属性的值为192.168.1.100。

>因此，spring.profiles可以包含简单的配置文件名称（例如production）或配置文件表达式。 表达式允许表达更复杂的逻辑，例如production＆(eu-central | eu-west)。 有关详细信息，请查阅参考指南.

&emsp;&emsp;如果在应用程序上下文启动时没有显式激活，则激活默认配置文件。 因此，在以下YAML中，我们为spring.security.user.password设置了一个值，该值仅在“默认”配置文件中可用：

``` 
server:
  port: 8000
---
spring:
  profiles: default
  security:
    user:
      password: weak
```

&emsp;&emsp;然而，在以下示例中，始终设置密码，因为它未附加到任何配置文件，并且必须根据需要在所有其他配置文件中显式重置密码：

``` 
server:
  port: 8000
spring:
  security:
    user:
      password: weak
```

&emsp;&emsp;使用spring.profiles元素指定的spring boot配置文件可以选择通过使用!字符。 如果为单个文档指定了否定和非否定的配置文件，则至少一个非否定的配置文件必须匹配，并且没有否定的配置文件可能匹配。

**4.2.7.4 YAML缺点**

&emsp;&emsp;无法使用@PropertySource批注加载YAML文件。 因此，如果您需要以这种方式加载值，则需要使用properties文件。

&emsp;&emsp;在特定于配置文件的YAML文件中使用多个YAML文档语法可能会导致意外行为。 例如，在名为application-dev.yml的文件中考虑以下配置，其中dev配置文件处于活动状态：

``` 
server:
  port: 8000
---
spring:
  profiles: !test
  security:
    user:
      password: weak
```

&emsp;&emsp;在上面的示例中，配置文件否定和配置文件表达式将不会按预期运行。 我们建议您不要将特定于配置文件的YAML文件和多个YAML文档组合在一起，并坚持只使用其中一个。

### **4.2.8 类型安全的配置属性**

&emsp;&emsp;使用@Value("${property}")注释来注入配置属性有时会很麻烦，特别是如果您使用多个属性或者您的数据本质上是分层的。 Spring Boot提供了一种使用属性的替代方法，该方法允许强类型bean管理和验证应用程序的配置，如以下示例所示：

``` 
package com.example;

import java.net.InetAddress;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

import org.springframework.boot.context.properties.ConfigurationProperties;

@ConfigurationProperties("acme")
public class AcmeProperties {

	private boolean enabled;

	private InetAddress remoteAddress;

	private final Security security = new Security();

	public boolean isEnabled() { ... }

	public void setEnabled(boolean enabled) { ... }

	public InetAddress getRemoteAddress() { ... }

	public void setRemoteAddress(InetAddress remoteAddress) { ... }

	public Security getSecurity() { ... }

	public static class Security {

		private String username;

		private String password;

		private List<String> roles = new ArrayList<>(Collections.singleton("USER"));

		public String getUsername() { ... }

		public void setUsername(String username) { ... }

		public String getPassword() { ... }

		public void setPassword(String password) { ... }

		public List<String> getRoles() { ... }

		public void setRoles(List<String> roles) { ... }

	}
}
```

&emsp;&emsp;前面的POJO定义了以下属性：

- acme.enabled，默认值为false。
- acme.remote-address，具有可以从String强制转换的类型。
- acme.security.username，带有嵌套的“security”对象，其名称由属性名称决定。 特别是，返回类型根本没有使用，可能是SecurityProperties。
- acme.security.password.
- acme.security.roles，带有String集合。


>getter和setter通常是必需的，因为绑定是通过标准的Java Beans属性描述符，就像在Spring MVC中一样。 在下列情况下可以省略setter： 

> - Maps, 只要它们被初始化，就需要一个getter但不一定是setter，因为它们可以被绑定器转变。 
> - 可以通过索引（通常使用YAML）或使用单个逗号分隔值（属性）访问集合和数组。 在后一种情况下，必须设置一个setter。 我们建议始终为这些类型添加setter。 如果初始化集合，请确保它不是不可变的（如上例所示）。 
> - 如果初始化嵌套的POJO属性（如前面示例中的“Security”字段），则不需要setter。 如果您希望绑定器使用其默认构造函数动态创建实例，则需要一个setter。 

>有些人使用Project Lombok自动添加getter和setter。 确保Lombok不为此类型生成任何特定构造函数，因为容器会自动使用它来实例化对象。 最后，仅考虑标准Java Bean属性，并且不支持对静态属性的绑定。

&emsp;
>另请参阅@Value和@ConfigurationProperties之间的差异。

&emsp;&emsp;您还需要列出要在@EnableConfigurationProperties注释中注册的属性类，如以下示例所示：

``` 
@Configuration
@EnableConfigurationProperties(AcmeProperties.class)
public class MyConfiguration {
}
```

>当以这种方式注册@ConfigurationProperties bean时，bean具有常规名称：<prefix> - <fqn>，其中<prefix>是@ConfigurationProperties注释中指定的环境键前缀，<fqn>是bean的完全限定名称。 如果注释未提供任何前缀，则仅使用bean的完全限定名称。 上例中的bean名称是acme-com.example.AcmeProperties。

&emsp;&emsp;即使前面的配置为AcmeProperties创建了一个常规bean，我们也建议@ConfigurationProperties只处理环境，特别是不从上下文中注入其他bean。 话虽如此，@EnableConfigurationProperties注释也会自动应用于您的项目，以便从Environment配置任何使用@ConfigurationProperties注释的现有bean。 您可以通过确保AcmeProperties已经是一个bean来快速创建MyConfiguration，如以下示例所示：

``` 
@Component
@ConfigurationProperties(prefix="acme")
public class AcmeProperties {

	// ... see the preceding example

}
```

&emsp;&emsp;这种配置样式在SpringApplication外部YAML配置中运行得特别好，如以下示例所示：

``` 
# application.yml

acme:
	remote-address: 192.168.1.1
	security:
		username: admin
		roles:
		  - USER
		  - ADMIN

# additional configuration as required
```

&emsp;&emsp;要使用@ConfigurationProperties bean，可以使用与任何其他bean相同的方式注入它们，如以下示例所示：

``` 
@Service
public class MyService {

	private final AcmeProperties properties;

	@Autowired
	public MyService(AcmeProperties properties) {
	    this.properties = properties;
	}

 	//...

	@PostConstruct
	public void openConnection() {
		Server server = new Server(this.properties.getRemoteAddress());
		// ...
	}

}
```

>使用@ConfigurationProperties还可以生成元数据文件，IDE可以使用这些文件为您自己的密钥提供自动完成功能。 有关详细信息，请参阅附录B，配置元数据附录。

**4.2.8.1 第三方配置**

&emsp;&emsp;除了使用@ConfigurationProperties注释类之外，您还可以在公共@Bean方法上使用它。 当您想要将属性绑定到控件之外的第三方组件时，这样做会特别有用。

&emsp;&emsp;要从Environment属性配置bean，请将@ConfigurationProperties添加到其bean注册中，如以下示例所示：

``` 
@ConfigurationProperties(prefix = "another")
@Bean
public AnotherComponent anotherComponent() {
	...
}
```

&emsp;&emsp;使用另一个前缀定义的任何属性都以与前面的AcmeProperties示例类似的方式映射到该AnotherComponent bean。

**4.2.8.2 轻松绑定**

&emsp;&emsp;Spring Boot使用一些宽松的规则将Environment属性绑定到@ConfigurationProperties bean，因此不需要在Environment属性名和bean属性名之间进行精确匹配。 这有用的常见示例包括破折号分隔的环境属性（例如，context-path绑定到contextPath）和大写环境属性（例如，PORT绑定到port）。

例如，请考虑以下@ConfigurationProperties类：

``` 
@ConfigurationProperties(prefix="acme.my-project.person")
public class OwnerProperties {

	private String firstName;

	public String getFirstName() {
		return this.firstName;
	}

	public void setFirstName(String firstName) {
		this.firstName = firstName;
	}

}
```

&emsp;&emsp;在前面的示例中，可以使用以下属性名称：

表24.1 宽松绑定

<table>
	<tr>
		<th>属性</th>
		<th>说明</th>
	</tr>
	<tr>
		<td>acme.my-project.person.first-name</td>
		<td>短横线命名，推荐在.properties和.yml文件中使用。</td>
	</tr>
	<tr>
		<td>acme.myProject.person.firstName</td>
		<td>标准驼峰式语法</td>
	</tr>
	<tr>
		<td>acme.my_project.person.first_name</td>
		<td>下划线表示法，它是在.properties和.yml文件中使用的替代格式。</td>
	</tr>
	<tr>
		<td>ACME_MYPROJECT_PERSON_FIRSTNAME</td>
		<td>大写格式，使用系统环境变量时建议使用。</td>
	</tr>
</table>

>注释的前缀值必须是短横线语法（小写并用 - 分隔，例如acme.my-project.person）。

表24.2 每个属性源宽松绑定规则

<table>
	<tr>
		<th>属性源</th>
		<th>Simple</th>
		<th>List</th>
	</tr>
	<tr>
		<td>Properties文件</td>
		<td>驼峰式、短横线式，下划线式</td>
		<td>使用[ ]或逗号分隔值的标准列表语法</td>
	</tr>
	<tr>
		<td>YAML文件</td>
		<td>驼峰式、短横线式，下划线式</td>
		<td>标准YAML列表语法或逗号分隔值</td>
	</tr>
	<tr>
		<td>环境变量</td>
		<td>大写格式，下划线作为分隔符。 _不应在属性名称中使用</td>
		<td>下划线包围的数字值，例如MY_ACME_1_OTHER = my.acme [1] .other</td>
	</tr>
	<tr>
		<td>系统属性</td>
		<td>驼峰式、短横线式，下划线式</td>
		<td>使用[ ]或逗号分隔值的标准列表语法</td>
	</tr>
</table>

>我们建议，在可能的情况下，属性以小写的短横线命名存储，例如my.property-name = acme。

&emsp;&emsp;绑定到Map属性时，如果键包含除小写字母数字字符以外的任何内容或 - ，则需要使用括号表示法以保留原始值。 如果键未被[]包围，则删除任何非字母数字或字符的字符。 例如，考虑将以下属性绑定到Map：

``` 
acme:
  map:
    "[/key1]": value1
    "[/key2]": value2
    /key3: value3
```

&emsp;&emsp;上面的属性将绑定到带有/key1，/key2和key3的Map作为Map中的键。

**4.2.8.3 合并复杂类型**

&emsp;&emsp;当列表在多个位置配置时，覆盖通过替换整个列表来工作。

例如，假设具有name和description属性的MyPojo对象默认为null。 以下示例公开了AcmeProperties中的MyPojo对象列表：

``` 
@ConfigurationProperties("acme")
public class AcmeProperties {

	private final List<MyPojo> list = new ArrayList<>();

	public List<MyPojo> getList() {
		return this.list;
	}

}
```

&emsp;&emsp;请考虑以下配置：

``` 
acme:
  list:
    - name: my name
      description: my description
---
spring:
  profiles: dev
acme:
  list:
    - name: my another name
```

&emsp;&emsp;如果dev配置文件未激活，则AcmeProperties.list包含一个MyPojo条目，如前所述。 但是，如果启用了dev配置文件，则列表仍然只包含一个条目（name为my another name，并且描述为null）。 此配置不会向列表中添加第二个MyPojo实例，也不会合并项目。

&emsp;&emsp;在多个配置文件中指定List时，将使用具有最高优先级（并且只有该一个）的列表。 请考虑以下示例：

``` 
acme:
  list:
    - name: my name
      description: my description
    - name: another name
      description: another description
---
spring:
  profiles: dev
acme:
  list:
    - name: my another name
```

&emsp;&emsp;在前面的示例中，如果dev配置文件处于活动状态，则AcmeProperties.list包含一个MyPojo条目（name为my another name，描述为null）。 对于YAML，逗号分隔列表和YAML列表都可用于完全覆盖列表的内容。

&emsp;&emsp;对于Map属性，您可以绑定从多个源中提取的属性值。 但是，对于多个源中的相同属性，使用具有最高优先级的属性。 以下示例从AcmeProperties公开Map &lt;String，MyPojo&gt;：

``` 
@ConfigurationProperties("acme")
public class AcmeProperties {

	private final Map<String, MyPojo> map = new HashMap<>();

	public Map<String, MyPojo> getMap() {
		return this.map;
	}

}
```

&emsp;&emsp;请考虑以下配置：

``` 
acme:
  map:
    key1:
      name: my name 1
      description: my description 1
---
spring:
  profiles: dev
acme:
  map:
    key1:
      name: dev name 1
    key2:
      name: dev name 2
      description: dev description 2
```

&emsp;&emsp;如果dev配置文件未激活，则AcmeProperties.map包含一个带键key1的条目（name为my name 1，description为my description 1）。 但是，如果启用了dev配置文件，则map包含两个条目，其中键key1（name为dev name 1和description为my description 1）和key2（name为dev name 2和description为dev description 2）。

>前面的合并规则适用于所有属性源的属性，而不仅仅适用于YAML文件。

**4.2.8.4 属性转换**

&emsp;&emsp;当Spring绑定到@ConfigurationProperties bean时，Spring Boot会尝试将外部应用程序属性强制转换为正确的类型。 如果需要自定义类型转换，则可以提供ConversionService bean（带有名为conversionService的bean）或自定义属性编辑器（通过CustomEditorConfigurer bean）或自定义转换器（带有注释为@ConfigurationPropertiesBinding的bean定义）。

>由于在应用程序生命周期中很早就请求了此bean，因此请确保限制ConversionService正在使用的依赖项。 通常，您在创建时可能无法完全初始化所需的任何依赖项。 如果配置密钥强制不需要，您可能希望重命名自定义ConversionService，并且只依赖于使用@ConfigurationPropertiesBinding限定的自定义转换器。

**1）转换durations**

&emsp;&emsp;Spring Boot专门支持表达持续时间。 如果公开java.time.Duration属性，则可以使用应用程序属性中的以下格式：

- 常规long表示（除非指定了@DurationUnit，否则使用毫秒作为默认单位）
- java.util.Duration使用的标准ISO-8601格式
- 一种更易读的格式，其中值和单位组合（例如10s表示10秒）


&emsp;&emsp;请考虑以下示例：

``` 
@ConfigurationProperties("app.system")
public class AppSystemProperties {

	@DurationUnit(ChronoUnit.SECONDS)
	private Duration sessionTimeout = Duration.ofSeconds(30);

	private Duration readTimeout = Duration.ofMillis(1000);

	public Duration getSessionTimeout() {
		return this.sessionTimeout;
	}

	public void setSessionTimeout(Duration sessionTimeout) {
		this.sessionTimeout = sessionTimeout;
	}

	public Duration getReadTimeout() {
		return this.readTimeout;
	}

	public void setReadTimeout(Duration readTimeout) {
		this.readTimeout = readTimeout;
	}

}
```

&emsp;&emsp;要指定会话超时30秒，30，PT30S和30s都是等效的。 读取超时为500ms可以采用以下任何一种形式指定：500，PT0.5S和500ms。

&emsp;&emsp;您也可以使用任何支持的单位。 如下所示：

- ns为纳秒
- us为微秒
- ms为毫秒
- s为秒
- m为分钟
- h为小时
- d为天

&emsp;&emsp;默认单位是毫秒，可以使用@DurationUnit覆盖，如上面的示例所示。

>如果要从仅使用Long表示持续时间的先前版本升级，如果它不是切换到的毫秒，请确保定义单位（使用@DurationUnit）。 这样做可以提供透明的升级路径，同时支持更丰富的格式。

**2）转换数据大小**

&emsp;&emsp;Spring Framework有一个DataSize值类型，允许以字节为单位表示大小。 如果公开DataSize属性，则可以使用应用程序属性中的以下格式：

- 常规long表示（使用byte作为默认单位，除非指定了@DataSizeUnit）
- 一种更易读的格式，其中值和单元组合（例如10MB表示10兆字节）


&emsp;&emsp;请考虑以下示例：

``` 
@ConfigurationProperties("app.io")
public class AppIoProperties {

	@DataSizeUnit(DataUnit.MEGABYTES)
	private DataSize bufferSize = DataSize.ofMegabytes(2);

	private DataSize sizeThreshold = DataSize.ofBytes(512);

	public DataSize getBufferSize() {
		return this.bufferSize;
	}

	public void setBufferSize(DataSize bufferSize) {
		this.bufferSize = bufferSize;
	}

	public DataSize getSizeThreshold() {
		return this.sizeThreshold;
	}

	public void setSizeThreshold(DataSize sizeThreshold) {
		this.sizeThreshold = sizeThreshold;
	}

}
```

&emsp;&emsp;要指定10兆字节的缓冲区大小，10和10MB是等效的。 可以将256字节的大小阈值指定为256或256B。

&emsp;&emsp;您也可以使用任何支持的单位。 如下所示：

- B
- KB
- MB
- TB


&emsp;&emsp;默认单位是字节，可以使用@DataSizeUnit覆盖，如上面的示例所示。

>如果要从仅使用Long表示大小的先前版本进行升级，如果它不是切换到DataSize字节，请确保定义单位（使用@DataSizeUnit）。 这样做可以提供透明的升级路径，同时支持更丰富的格式。

**4.2.8.5 @ConfigurationProperties验证**

&emsp;&emsp;只要使用Spring的@Validated注解注释，Spring Boot就会尝试验证@ConfigurationProperties类。 您可以直接在配置类上使用JSR-303 javax.validation约束注释。 为此，请确保符合条件的JSR-303实现位于类路径上，然后将约束注释添加到字段中，如以下示例所示：

``` 
@ConfigurationProperties(prefix="acme")
@Validated
public class AcmeProperties {

	@NotNull
	private InetAddress remoteAddress;

	// ... getters and setters

}
```

>您还可以通过使用@Validated注释来创建配置属性的@Bean方法来触发验证。

&emsp;&emsp;

&emsp;&emsp;尽管绑定时也会验证嵌套属性，但最好还是将关联字段注释为@Valid。 这确保即使没有找到嵌套属性也会触发验证。 以下示例基于前面的AcmeProperties示例构建：

``` 
@ConfigurationProperties(prefix="acme")
@Validated
public class AcmeProperties {

	@NotNull
	private InetAddress remoteAddress;

	@Valid
	private final Security security = new Security();

	// ... getters and setters

	public static class Security {

		@NotEmpty
		public String username;

		// ... getters and setters

	}
   
}
```

&emsp;&emsp;您还可以通过创建名为configurationPropertiesValidator的bean定义来添加自定义Spring Validator。 应该将@Bean方法声明为static。 配置属性验证器是在应用程序生命周期的早期创建的，并且将@Bean方法声明为static可以创建bean而无需实例化@Configuration类。 这样做可以避免早期实例化可能导致的任何问题。 有一个属性验证示例，显示如何设置。

>spring-boot-actuator模块包括一个暴露所有@ConfigurationProperties bean的端点。 将Web浏览器指向/actuator/configprops或使用等效的JMX端点。 有关详细信息，请参阅“生产就绪功能”部分。

**4.2.8.6 @ConfigurationProperties vs @Value**

&emsp;&emsp;@Value注释是核心容器功能，它不提供与类型安全配置属性相同的功能。 下表总结了@ConfigurationProperties和@Value支持的功能：

<table>
	<tr>
		<th>Feature</th>
		<th>@ConfigurationProperties</th>
		<th>@Value</th>
	</tr>
	<tr>
		<td>宽松绑定</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>元数据支持</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>SpEL 表达式</td>
		<td>No</td>
		<td>Yes</td>
	</tr>
</table>

&emsp;&emsp;如果为自己的组件定义一组配置键，我们建议您将它们分组到使用@ConfigurationProperties注释的POJO中。 您还应该知道，因为@Value不支持宽松绑定，所以如果您需要使用环境变量来提供值，则它不是一个好的候选者。

&emsp;&emsp;最后，虽然您可以在@Value中编写SpEL表达式，但不会从应用程序属性文件处理此类表达式。

## **4.3 Profiles**

&emsp;&emsp;Spring Profiles提供了一种隔离应用程序配置部分并使其仅在特定环境中可用的方法。 可以使用@Profile标记任何@Component或@Configuration以限制何时加载它，如以下示例所示：

``` 
@Configuration
@Profile("production")
public class ProductionConfiguration {

	// ...

}
```

&emsp;&emsp;您可以使用spring.profiles.active Environment属性指定哪些配置文件处于活动状态。 您可以使用本章前面介绍的任何方法指定属性。 例如，您可以将它包含在application.properties中，如以下示例所示：

``` 
spring.profiles.active=dev,hsqldb
```

&emsp;&emsp;您还可以使用以下开关在命令行上指定它： - spring.profiles.active = dev,hsqldb

### **4.3.1 添加活动的配置文件**

&emsp;&emsp;spring.profiles.active属性遵循与其他属性相同的排序规则：最高的PropertySource获胜。 这意味着您可以在application.properties中指定活动配置文件，然后使用命令行开关替换它们。

&emsp;&emsp;有时，将特定于配置文件的属性添加到活动配置文件而不是替换它们是有用的。 spring.profiles.include属性可用于无条件地添加活动配置文件。 SpringApplication入口点还有一个Java API，用于设置其他配置文件（即，在spring.profiles.active属性激活的配置文件之上）。 请参阅SpringApplication中的setAdditionalProfiles()方法。

例如，当使用开关--spring.profiles.active = prod运行具有以下属性的应用程序时，也会激活proddb和prodmq配置文件：

``` 
---
my.property: fromyamlfile
---
spring.profiles: prod
spring.profiles.include:
  - proddb
  - prodmq
```

>请记住，可以在YAML文档中定义spring.profiles属性，以确定此特定文档何时包含在配置中。 有关更多详细信息，请参见第9.2.7节“根据环境更改配置”。

### **4.3.2 以编程方式设置配置文件**

&emsp;&emsp;您可以通过在应用程序运行之前调用SpringApplication.setAdditionalProfiles(...)以编程方式设置活动配置文件。 也可以使用Spring的ConfigurableEnvironment接口激活配置文件

### **4.3.3 在配置文件中指定的配置文件**

&emsp;&emsp;通过@ConfigurationProperties引用的文件和通过@ConfigurationProperties引用的文件都被视为文件并加载。 有关详细信息，请参见“第4.2.4节 特定于配置文件的属性”。

## **4.4 日志**

&emsp;&emsp;Spring Boot使用Commons Logging进行所有内部日志记录，但保留底层日志实现。 为Java Util Logging，Log4J2和Logback提供了默认配置。 在每种情况下，记录器都预先配置为使用控制台输出，并且还提供可选的文件输出。

&emsp;&emsp;默认情况下，如果使用“Starters”，则使用Logback进行日志记录。 还包括适当的Logback路由，以确保使用Java Util Logging，Commons Logging，Log4J或SLF4J的依赖库都能正常工作。

>Java有很多日志框架可供使用。 如果以上列表看起来令人困惑，请不要担心。 通常，您不需要更改日志记录依赖项，并且Spring Boot默认值可以正常工作。

### **4.4.1 格式化日志**

&emsp;&emsp;Spring Boot的默认日志输出类似于以下示例：

``` 
2014-03-05 10:57:51.112  INFO 45469 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/7.0.52
2014-03-05 10:57:51.253  INFO 45469 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2014-03-05 10:57:51.253  INFO 45469 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1358 ms
2014-03-05 10:57:51.698  INFO 45469 --- [ost-startStop-1] o.s.b.c.e.ServletRegistrationBean        : Mapping servlet: 'dispatcherServlet' to [/]
2014-03-05 10:57:51.702  INFO 45469 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
```

&emsp;&emsp;输出以下项目：

- 日期和时间：毫秒精度，易于排序。
- 日志级别：ERROR，WARN，INFO，DEBUG或TRACE。
- 进程ID。
- ---分隔符，用于区分实际日志消息的开始。
- 线程名称：用方括号括起来（可能会截断控制台输出）。
- 记录器名称：这通常是源类名称（通常缩写）。
- 日志消息。

>Logback没有FATAL级别。 它映射到ERROR。

### **4.4.2 控制台输出**

&emsp;&emsp;默认日志配置会在写入时将消息回显到控制台。 默认情况下，会记录ERROR级别，WARN级别和INFO级别的消息。 您还可以通过使用--debug标志启动应用程序来启用“调试”模式。

``` 
$ java -jar myapp.jar --debug
```

>您还可以在application.properties中指定debug = true。

&emsp;&emsp;启用调试模式后，将选择一些核心记录器（嵌入式容器，Hibernate和Spring Boot）以输出更多信息。 启用调试模式不会将应用程序配置为使用DEBUG级别记录所有消息。

&emsp;&emsp;或者，您可以通过使用--trace标志（或application.properties中的trace = true）启动应用程序来启用“跟踪”模式。 这样做可以为选择的核心记录器（嵌入式容器，Hibernate模式生成和整个Spring组合）启用跟踪日志记录。

**4.4.2.1 彩色编码输出**

&emsp;&emsp;如果您的终端支持ANSI，则使用颜色输出来提高可读性。 您可以将spring.output.ansi.enabled设置为支持的值以覆盖自动检测。

&emsp;&emsp;使用％clr转换字配置颜色编码。 在最简单的形式中，转换器根据日志级别为输出着色，如以下示例所示：

``` 
%clr(%5p)
```

&emsp;&emsp;下表描述了日志级别到颜色的映射：

<table>
	<tr>
		<th>Level</th>
		<th>Color</th>
	</tr>
	<tr>
		<td>FATAL</td>
		<td>Red</td>
	</tr>
	<tr>
		<td>ERROR</td>
		<td>Red</td>
	</tr>
	<tr>
		<td>WARN</td>
		<td>Yellow</td>
	</tr>
	<tr>
		<td>INFO</td>
		<td>Green</td>
	</tr>
	<tr>
		<td>DEBUG</td>
		<td>Green</td>
	</tr>
	<tr>
		<td>TRACE</td>
		<td>Green</td>
	</tr>
</table>

&emsp;&emsp;或者，您可以通过将其作为转换选项指定应使用的颜色或样式。 例如，要使文本变为黄色，请使用以下设置：

``` 
%clr(%d{yyyy-MM-dd HH:mm:ss.SSS}){yellow}
```

&emsp;&emsp;支持以下颜色和样式：

- blue
- cyan
- faint
- green
- magenta
- red
- yellow

### **4.4.3 文件输出**

&emsp;&emsp;默认情况下，Spring Boot仅记录到控制台，不会写入日志文件。 如果除了控制台输出之外还要编写日志文件，则需要设置logging.file或logging.path属性（例如，在application.properties中）。

&emsp;&emsp;下表显示了logging.*属性如何一起使用：

表26.1 logging属性

<table>
	<tr>
		<th>logging.file</th>
		<th>logging.path</th>
		<th>Example</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>(none)</td>
		<td>(none)</td>
		<td></td>
		<td>仅在控制台显示日志</td>
	</tr>
	<tr>
		<td>特定文件</td>
		<td>(none)</td>
		<td>my.log</td>
		<td>写入指定的日志文件。 名称可以是精确位置或相对于当前目录。</td>
	</tr>
	<tr>
		<td>(none)</td>
		<td>特定目录</td>
		<td>/var/log</td>
		<td>将spring.log写入指定的目录。 名称可以是精确位置或相对于当前目录。</td>
	</tr>
</table>

&emsp;&emsp;日志文件在达到10 MB时会轮换，并且与控制台输出一样，默认情况下会记录ERROR级别，WARN级别和INFO级别的消息。 可以使用logging.file.max-size属性更改大小限制。 除非已设置logging.file.max-history属性，否则以前轮换的文件将无限期归档。

>日志记录系统在应用程序生命周期的早期初始化。 因此，在通过@PropertySource注释加载的属性文件中找不到日志记录属性。

&emsp;
>日志记录属性独立于实际的日志记录基础结构。 因此，spring Boot不管理特定的配置密钥（例如Logback的logback.configurationFile）。

### **4.4.4 日志级别**

&emsp;&emsp;所有受支持的日志记录系统都可以使用logging.level设置Spring环境中的记录器级别（例如，在application.properties中）。<logger-name> = <level>其中level是TRACE，DEBUG，INFO， WARN，ERROR，FATAL或OFF之一。 可以使用logging.level.root配置根记录器。

&emsp;&emsp;以下示例显示了application.properties中的潜在日志记录设置：

``` 
logging.level.root=WARN
logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate=ERROR
```

### **4.4.5 日志组**

&emsp;&emsp;能够将相关记录器组合在一起以便可以同时配置它们通常很有用。 例如，您通常可以更改所有Tomcat相关记录器的日志记录级别，但您无法轻松记住顶级软件包。

&emsp;&emsp;为了解决这个问题，Spring Boot允许您在Spring环境中定义日志记录组。 例如，以下是通过将“tomcat”组添加到application.properties来定义“tomcat”组的方法：

``` 
logging.group.tomcat=org.apache.catalina, org.apache.coyote, org.apache.tomcat
```

&emsp;&emsp;定义后，您可以使用一行更改组中所有记录器的级别：

``` 
logging.level.tomcat=TRACE
```

&emsp;&emsp;Spring Boot包含以下预定义的日志记录组，可以直接使用：

<table>
	<tr>
		<th>Name</th>
		<th>Loggers</th>
	</tr>
	<tr>
		<td>web</td>
		<td>org.springframework.core.codec, org.springframework.http, org.springframework.web</td>
	</tr>
	<tr>
		<td>sql</td>
		<td>org.springframework.jdbc.core, org.hibernate.SQL</td>
	</tr>
</table>

### **4.4.6 自定义日志配置**

&emsp;&emsp;可以通过在类路径中包含适当的库来激活各种日志记录系统，并且可以通过在类路径的根目录中或在以下Spring Environment属性指定的位置提供合适的配置文件来进一步自定义：logging.config。

&emsp;&emsp;您可以使用org.springframework.boot.logging.LoggingSystem系统属性强制Spring Boot使用特定的日志记录系统。 该值应该是LoggingSystem实现的完全限定类名。 您还可以使用none值完全禁用Spring Boot的日志记录配置。

>由于在创建ApplicationContext之前初始化日志记录，因此无法在Spring @Configuration文件中控制来自@PropertySources的日志记录。 更改日志记录系统或完全禁用它的唯一方法是通过系统属性。

&emsp;&emsp;根据您的日志记录系统，将加载以下文件：

<table>
	<tr>
		<th>Logging System</th>
		<th>Customization</th>
	</tr>
	<tr>
		<td>Logback</td>
		<td>logback-spring.xml, logback-spring.groovy, logback.xml, 或 logback.groovy</td>
	</tr>
	<tr>
		<td>Log4j2</td>
		<td>log4j2-spring.xml 或 log4j2.xml</td>
	</tr>
	<tr>
		<td>JDK (Java Util Logging)</td>
		<td>logging.properties</td>
	</tr>
</table>

>如果可能，我们建议您使用-spring变体进行日志记录配置（例如，logback-spring.xml而不是logback.xml）。 如果使用标准配置位置，Spring无法完全控制日志初始化。

&emsp;
>Java Util Logging存在已知的类加载问题，从“可执行jar”运行时会导致问题。 如果可能的话，我们建议您在从“可执行jar”运行时避免使用它。

&emsp;&emsp;为了帮助进行自定义，一些其他属性从Spring环境传输到System属性，如下表所述：

<table>
	<tr>
		<th>Spring Environment</th>
		<th>System Property</th>
		<th>Comments</th>
	</tr>
	<tr>
		<td>logging.exception-conversion-word</td>
		<td>LOG_EXCEPTION_CONVERSION_WORD</td>
		<td>记录异常时使用的转换字。</td>
	</tr>
	<tr>
		<td>logging.file</td>
		<td>LOG_FILE</td>
		<td>如果已定义，则在默认日志配置中使用它。</td>
	</tr>
	<tr>
		<td>logging.file.max-size</td>
		<td>LOG_FILE_MAX_SIZE</td>
		<td>最大日志文件大小（如果启用了LOG_FILE）。 （仅支持默认的Logback设置。）</td>
	</tr>
	<tr>
		<td>logging.file.max-history</td>
		<td>LOG_FILE_MAX_HISTORY</td>
		<td>要保留的最大归档日志文件数（如果启用了LOG_FILE）。 （仅支持默认的Logback设置。）</td>
	</tr>
	<tr>
		<td>logging.path</td>
		<td>LOG_PATH</td>
		<td>如果已定义，则在默认日志配置中使用它。</td>
	</tr>
	<tr>
		<td>logging.pattern.console</td>
		<td>CONSOLE_LOG_PATTERN</td>
		<td>要在控制台上使用的日志模式（stdout）。 （仅支持默认的Logback设置。）</td>
	</tr>
	<tr>
		<td>logging.pattern.dateformat</td>
		<td>LOG_DATEFORMAT_PATTERN</td>
		<td>日志日期格式的Appender模式。 （仅支持默认的Logback设置。）</td>
	</tr>
	<tr>
		<td>logging.pattern.file</td>
		<td>FILE_LOG_PATTERN</td>
		<td>要在文件中使用的日志模式（如果启用了LOG_FILE）。 （仅支持默认的Logback设置。）</td>
	</tr>
	<tr>
		<td>logging.pattern.level</td>
		<td>LOG_LEVEL_PATTERN</td>
		<td>The format to use when rendering the log level (default %5p). (Only supported with the default Logback setup.)</td>
	</tr>
	<tr>
		<td>PID</td>
		<td>PID</td>
		<td>当前进程ID（如果可能，则在未定义为OS环境变量时发现）。</td>
	</tr>
</table>

&emsp;&emsp;所有受支持的日志记录系统在分析其配置文件时都可以查阅系统属性。 有关示例，请参阅spring-boot.jar中的默认配置：

- Logback
- Log4j 2
- Java Util logging

>如果要在日志记录属性中使用占位符，则应使用Spring Boot的语法而不是底层框架的语法。 值得注意的是，如果使用Logback，则应使用:作为属性名称与其默认值之间的分隔符，而不是使用: - 。

&emsp;
>您可以通过仅覆盖LOG_LEVEL_PATTERN（或带Logback的logging.pattern.level）将MDC和其他临时内容添加到日志行。 例如，如果使用logging.pattern.level = user:％X{user}％5p，则默认日志格式包含“user”的MDC条目（如果存在），如以下示例所示。

>```
2015-09-30 12:30:04.031 user:someone INFO 22174 --- [  nio-8080-exec-0] demo.Controller
Handling authenticated request
>```

### **4.4.7 Logback扩充**

&emsp;&emsp;Spring Boot包含许多Logback扩展，可以帮助进行高级配置。 您可以在logback-spring.xml配置文件中使用这些扩展。

>由于标准logback.xml配置文件加载过早，因此无法在其中使用扩展。 您需要使用logback-spring.xml或定义logging.config属性。

&emsp;
>扩展不能与Logback的配置扫描一起使用。 如果您尝试这样做，更改配置文件会导致类似于以下记录之一的错误：

``` 
ERROR in ch.qos.logback.core.joran.spi.Interpreter@4:71 - no applicable action for [springProperty], current ElementPath is [[configuration][springProperty]]
ERROR in ch.qos.logback.core.joran.spi.Interpreter@4:71 - no applicable action for [springProfile], current ElementPath is [[configuration][springProfile]]
```

**4.4.7.1 特定于配置文件的配置**

&emsp;&emsp;<springProfile>标记允许您根据活动的Spring配置文件选择性地包含或排除配置部分。配置文件部分支持在<configuration>元素中的任何位置。使用name属性指定哪个配置文件接受配置。<springProfile>标记可以包含一个简单的概要文件名称(例如，staging)或配置文件表达式。配置文件表达式允许表达更复杂的配置文件逻辑，例如，production & (eu-central | eu-west)。有关详细信息，请参阅参考指南。下面的清单显示了三个示例配置文件：

``` 
<springProfile name="staging">
	<!-- configuration to be enabled when the "staging" profile is active -->
</springProfile>

<springProfile name="dev | staging">
	<!-- configuration to be enabled when the "dev" or "staging" profiles are active -->
</springProfile>

<springProfile name="!production">
	<!-- configuration to be enabled when the "production" profile is not active -->
</springProfile>
```

**4.4.7.2 环境属性**

&emsp;&emsp;<springProperty>标记允许您公开Spring环境中的属性，以便在Logback中使用。如果您想要访问您的Logback配置中的application.properties文件中的值，那么这样做可能很有用。标记的工作方式与Logback的标准<property>标记类似。但是，不是指定直接值，而是指定属性的来源(来自环境)。如果需要将属性存储在本地范围以外的其他地方，则可以使用范围属性。如果需要回退值(如果在环境中未设置属性)，则可以使用defaultValue属性。下面的示例演示如何公开在Logback中使用的属性：

``` 
<springProperty scope="context" name="fluentHost" source="myapp.fluentd.host"
		defaultValue="localhost"/>
<appender name="FLUENT" class="ch.qos.logback.more.appenders.DataFluentAppender">
	<remoteHost>${fluentHost}</remoteHost>
	...
</appender>
```

>必须短横线命名指定source（例如my.property-name）。 但是，可以使用宽松规则将属性添加到环境中。

## **4.5 国际化**

&emsp;&emsp;Spring Boot支持本地化消息，以便您的应用程序可以满足不同语言首选项的用户。 默认情况下，Spring Boot会在类路径的根目录中查找消息资源包的存在。

>当配置的资源包的默认属性文件可用时（默认情况下为messages.properties），将应用自动配置。 如果资源包仅包含特定于语言的属性文件，则需要添加默认值。

&emsp;&emsp;可以使用spring.messages命名空间配置资源包的基本名称以及其他几个属性，如以下示例所示：

``` 
spring.messages.basename=messages,config.i18n.messages
spring.messages.fallback-to-system-locale=false
```

>spring.messages.basename支持以逗号分隔的位置列表，包括限定符或从类路径根解析的资源。

&emsp;&emsp;有关更多支持的选项，请参阅MessageSourceProperties。

## **4.6 JSON**

&emsp;&emsp;Spring Boot提供了与三个JSON映射库的集成：

- Gson
- Jackson
- JSON-B

&emsp;&emsp;Jackson是首选的默认库。

### **4.6.1 Jackson**

&emsp;&emsp;提供了Jackson的自动配置，Jackson是spring-boot-starter-json的一部分。 当Jackson在类路径上时，会自动配置ObjectMapper bean。 提供了几个配置属性来自定义ObjectMapper的配置。

### **4.6.2 Gson**

&emsp;&emsp;提供Gson的自动配置。 当Gson在类路径上时，会自动配置Gson bean。 提供了几个spring.gson.*配置属性来自定义配置。 为了获得更多控制，可以使用一个或多个GsonBuilderCustomizer bean。

### **4.6.3 JSON-B**

&emsp;&emsp;提供了JSON-B的自动配置。 当JSON-B API和实现在类路径上时，将自动配置Jsonb bean。 首选的JSON-B实现是Apache Johnzon，它提供了依赖关系管理。

## **4.7 开发Web应用程序**

&emsp;&emsp;Spring Boot非常适合Web应用程序开发。 您可以使用嵌入式Tomcat，Jetty，Undertow或Netty创建自包含的HTTP服务器。 大多数Web应用程序使用spring-boot-starter-web模块快速启动和运行。 您还可以使用spring-boot-starter-webflux模块选择构建响应式Web应用程序。

&emsp;&emsp;如果您还没有开发Spring Boot Web应用程序，可以按照“Hello World！”进行操作。 “入门”部分中的示例。

### **4.7.1 “Spring Web MVC框架”**

&emsp;&emsp;Spring Web MVC框架（通常简称为“Spring MVC”）是一个丰富的“模型视图控制器”Web框架。 Spring MVC允许您创建特殊的@Controller或@RestController bean来处理传入的HTTP请求。 控制器中的方法通过使用@RequestMapping注释映射到HTTP。

&emsp;&emsp;以下代码显示了一个提供JSON数据的典型@RestController：

``` 
@RestController
@RequestMapping(value="/users")
public class MyRestController {

	@RequestMapping(value="/{user}", method=RequestMethod.GET)
	public User getUser(@PathVariable Long user) {
		// ...
	}

	@RequestMapping(value="/{user}/customers", method=RequestMethod.GET)
	List<Customer> getUserCustomers(@PathVariable Long user) {
		// ...
	}

	@RequestMapping(value="/{user}", method=RequestMethod.DELETE)
	public User deleteUser(@PathVariable Long user) {
		// ...
	}

}
```

&emsp;&emsp;Spring MVC是核心Spring Framework的一部分，详细信息可在参考文档中找到。 Spring.io/guides还提供了几个涵盖Spring MVC的指南。

**4.7.1.1 Spring MVC自动配置**

&emsp;&emsp;Spring Boot为Spring MVC提供自动配置，适用于大多数应用程序。

&emsp;&emsp;自动配置在Spring的默认值之上添加了以下功能：

- 包含ContentNegotiatingViewResolver和BeanNameViewResolver bean。
- 支持提供静态资源，包括对WebJars的支持（本文档稍后介绍））。
- 自动注册Converter，GenericConverter和Formatter bean。
- 支持HttpMessageConverters（本文档稍后介绍）。
- 自动注册MessageCodesResolver（本文档后面会介绍）。
- 静态index.html支持。
- 自定义Favicon支持（本文档稍后介绍）。
- 自动使用ConfigurableWebBindingInitializer bean（本文稍后介绍）。


&emsp;&emsp;如果要保留Spring Boot MVC功能并且想要添加其他MVC配置（拦截器，格式化器，视图控制器和其他功能），可以添加自己的类型为WebMvcConfigurer的@Configuration类但不使用@EnableWebMvc。 如果要提供RequestMappingHandlerMapping，RequestMappingHandlerAdapter或ExceptionHandlerExceptionResolver的自定义实例，可以声明WebMvcRegistrationsAdapter实例以提供此类组件。

&emsp;&emsp;如果您想完全控制Spring MVC，可以使用@EnableWebMvc添加自己的@Configuration注释。

**4.7.1.2 HttpMessageConverters**

&emsp;&emsp;Spring MVC使用HttpMessageConverter接口来转换HTTP请求和响应。 明智的默认设置包含在开箱即用中。 例如，对象可以自动转换为JSON（通过使用Jackson库）或XML（如果可用，则使用Jackson XML扩展，或者如果Jackson XML扩展不可用，则使用JAXB）。 默认情况下，字符串以UTF-8编码。

&emsp;&emsp;如果需要添加或自定义转换器，可以使用Spring Boot的HttpMessageConverters类，如下面的清单所示：

``` 
import org.springframework.boot.autoconfigure.web.HttpMessageConverters;
import org.springframework.context.annotation.*;
import org.springframework.http.converter.*;

@Configuration
public class MyConfiguration {

	@Bean
	public HttpMessageConverters customConverters() {
		HttpMessageConverter<?> additional = ...
		HttpMessageConverter<?> another = ...
		return new HttpMessageConverters(additional, another);
	}

}
```

&emsp;&emsp;上下文中存在的任何HttpMessageConverter bean都将添加到转换器列表中。 您也可以以相同的方式覆盖默认转换器。

**4.7.1.3 自定义JSON序列化程序和反序列化程序**

&emsp;&emsp;如果您使用Jackson序列化和反序列化JSON数据，您可能需要编写自己的JsonSerializer和JsonDeserializer类。 自定义序列化程序通常通过模块向Jackson注册，但Spring Boot提供了另一种@JsonComponent注释，可以更容易地直接注册Spring Beans。

&emsp;&emsp;您可以直接在JsonSerializer或JsonDeserializer实现上使用@JsonComponent注释。 您还可以在包含序列化程序/反序列化程序作为内部类的类上使用它，如以下示例所示：

``` 
import java.io.*;
import com.fasterxml.jackson.core.*;
import com.fasterxml.jackson.databind.*;
import org.springframework.boot.jackson.*;

@JsonComponent
public class Example {

	public static class Serializer extends JsonSerializer<SomeObject> {
		// ...
	}

	public static class Deserializer extends JsonDeserializer<SomeObject> {
		// ...
	}

}
```

&emsp;&emsp;ApplicationContext中的所有@JsonComponent bean都会自动注册到Jackson。 因为@JsonComponent是使用@Component进行元注释的，所以常规的组件扫描规则适用。

&emsp;&emsp;Spring Boot还提供了JsonObjectSerializer和JsonObjectDeserializer基类，它们在序列化对象时提供了标准Jackson版本的有用替代方法。 有关详细信息，请参阅Javadoc中的JsonObjectSerializer和JsonObjectDeserializer。

**4.7.1.4 MessageCodesResolver**

&emsp;&emsp;Spring MVC有一个生成错误代码的策略，用于从绑定错误中呈现错误消息：MessageCodesResolver。 如果设置spring.mvc.message-codes-resolver.format属性PREFIX_ERROR_CODE或POSTFIX_ERROR_CODE，Spring Boot会为您创建一个（请参阅DefaultMessageCodesResolver.Format中的枚举）。

**4.7.1.5 静态内容**

&emsp;&emsp;默认情况下，Spring Boot从类路径中的/static（或/public或/resources或/META-INF /resources）目录或ServletContext的根目录中提供静态内容。 它使用Spring MVC中的ResourceHttpRequestHandler，以便您可以通过添加自己的WebMvcConfigurer并覆盖addResourceHandlers方法来修改该行为。

&emsp;&emsp;在独立的Web应用程序中，容器中的默认servlet也被启用，并充当后盾，如果Spring决定不处理它，则从ServletContext根目录中提供内容。大多数情况下，这种情况不会发生(除非修改默认的MVC配置)，因为Spring总是可以通过DispatcherServlet处理请求。

&emsp;&emsp;默认情况下，资源映射到/**，但您可以使用spring.mvc.static-path-pattern属性对其进行调整。 例如，可以按如下方式将所有资源重新定位到/resources/**：

``` 
spring.mvc.static-path-pattern=/resources/**
```

&emsp;&emsp;您还可以使用spring.resources.static-locations属性（使用目录位置列表替换默认值）来自定义静态资源位置。 根Servlet上下文路径“/”也会自动添加为位置。

&emsp;&emsp;除了前面提到的“标准”静态资源位置之外，还为Webjars内容制作了一个特例。 在/webjars/**中具有路径的任何资源都是从jar文件提供的，如果它们以Webjars格式打包的话。

>如果您的应用程序打包为jar，请不要使用src/main/webapp目录。 虽然这个目录是一个通用标准，但它只适用于打包war，如果你生成一个jar，它会被大多数构建工具默默忽略。

&emsp;&emsp;Spring Boot还支持Spring MVC提供的高级资源处理功能，允许使用非缓存静态资源或使用与Webjars无关的URL。

&emsp;&emsp;要为Webjars使用版本无关的URL，请添加webjars-locator-core依赖项。 然后声明你的Webjar。 以jQuery为例，添加“/webjars/jquery/jquery.min.js”会产生“/webjars/jquery/x.y.z/jquery.min.js”。 其中x.y.z是Webjar版本。

>如果使用JBoss，则需要声明webjars-locator-jboss-vfs依赖项而不是webjars-locator-core。 否则，所有Webjars都将解析为404。

&emsp;&emsp;要使用缓存清除，以下配置为所有静态资源配置缓存清除解决方案，有效地在URL中添加内容哈希，例如<link href =“/css/spring2a2d595e6ed9a0b24f027f2b63b134d6.css”/>。

``` 
spring.resources.chain.strategy.content.enabled=true
spring.resources.chain.strategy.content.paths=/**
```

>由于为Thymeleaf和FreeMarker自动配置了ResourceUrlEncodingFilter，因此在运行时可以在模板中重写资源链接。 您应该在使用JSP时手动声明此过滤器。 目前不支持其他模板引擎，但可以使用自定义模板宏/帮助程序以及ResourceUrlProvider的使用。

&emsp;&emsp;使用（例如）JavaScript模块加载器动态加载资源时，不能重命名文件。 这就是为什么其他策略也得到支持并可以合并的原因。 “fixed”策略在URL中添加静态版本字符串而不更改文件名，如以下示例所示：

``` 
spring.resources.chain.strategy.content.enabled=true
spring.resources.chain.strategy.content.paths=/**
spring.resources.chain.strategy.fixed.enabled=true
spring.resources.chain.strategy.fixed.paths=/js/lib/
spring.resources.chain.strategy.fixed.version=v12
```

&emsp;&emsp;使用此配置，位于“/js/lib/”下的JavaScript模块使用固定版本控制策略（“/v12/js/lib/mymodule.js”），而其他资源仍使用content（<link href =“/css/spring-2a2d595e6ed9a0b24f027f2b63b134d6.css“/>）。

&emsp;&emsp;有关更多支持的选项，请参阅ResourceProperties。

>此功能已在专门的博客文章和Spring Framework的参考文档中进行了详细描述。

**4.7.1.6 欢迎页面**

&emsp;&emsp;Spring Boot支持静态和模板化欢迎页面。 它首先在配置的静态内容位置中查找index.html文件。 如果找不到，则查找索引模板。 如果找到任何一个，它将自动用作应用程序的欢迎页面。

**4.7.1.7 自定义Favicon**

&emsp;&emsp;Spring Boot在配置的静态内容位置和类路径的根（按此顺序）中查找favicon.ico。 如果存在这样的文件，它将自动用作应用程序的favicon。

**4.7.1.8 路径匹配和内容协商**

&emsp;&emsp;Spring MVC可以通过查看请求路径并将其与应用程序中定义的映射（例如Controller方法上的注释@GetMapping）相匹配，将传入的HTTP请求映射到处理程序。

&emsp;&emsp;Spring Boot默认选择禁用后缀模式匹配，这意味着像“GET /projects/spring-boot.json”这样的请求将不会与@GetMapping("/projects/ spring-boot")映射匹配。 这被认为是Spring MVC应用程序的最佳实践。 对于没有发送正确“接受”请求标头的HTTP客户端，此功能在过去主要有用; 我们需要确保将正确的内容类型发送给客户端。 如今，内容协商更加可靠。

&emsp;&emsp;还有其他方法可以处理不一致发送正确“接受”请求标头的HTTP客户端。 我们可以使用查询参数来确保像“GET /projects/spring-boot?format=json”这样的请求将映射到@GetMapping("/projects/spring-boot")，而不是使用后缀匹配：

``` 
spring.mvc.contentnegotiation.favor-parameter=true

# We can change the parameter name, which is "format" by default:
# spring.mvc.contentnegotiation.parameter-name=myparam

# We can also register additional file extensions/media types with:
spring.mvc.contentnegotiation.media-types.markdown=text/markdown
```

&emsp;&emsp;如果您了解警告并仍希望您的应用程序使用后缀模式匹配，则需要以下配置：

``` 
spring.mvc.contentnegotiation.favor-path-extension=true
spring.mvc.pathmatch.use-suffix-pattern=true
```

&emsp;&emsp;或者，不是打开所有后缀模式，而是仅支持已注册的后缀模式更安全：

``` 
spring.mvc.contentnegotiation.favor-path-extension=true
spring.mvc.pathmatch.use-registered-suffix-pattern=true

# You can also register additional file extensions/media types with:
# spring.mvc.contentnegotiation.media-types.adoc=text/asciidoc
```

**4.7.1.9 ConfigurableWebBindingInitializer**

&emsp;&emsp;Spring MVC使用WebBindingInitializer为特定请求初始化WebDataBinder。 如果您创建自己的ConfigurableWebBindingInitializer @Bean，Spring Boot会自动配置Spring MVC以使用它。

**4.7.1.10 模板引擎**

&emsp;&emsp;除REST Web服务外，您还可以使用Spring MVC来提供动态HTML内容。 Spring MVC支持各种模板技术，包括Thymeleaf，FreeMarker和JSP。 此外，许多其他模板引擎包括他们自己的Spring MVC集成。

&emsp;&emsp;Spring Boot包括对以下模板引擎的自动配置支持：

- FreeMarker
- Groovy
- Thymeleaf
- Mustache

>如果可能，应该避免使用JSP。 将它们与嵌入式servlet容器一起使用时有几个已知的限制。

&emsp;&emsp;当您使用其中一个模板引擎和默认配置时，您的模板将自动从src/main/resources/templates中获取。

>根据您运行应用程序的方式，IntelliJ IDEA以不同方式对类路径进行排序。 从主方法在IDE中运行应用程序会导致与使用Maven或Gradle或其打包的jar运行应用程序时的顺序不同。 这可能导致Spring Boot无法在类路径中找到模板。 如果遇到此问题，可以在IDE中重新排序类路径，以便首先放置模块的类和资源。 或者，您可以配置模板前缀以搜索类路径上的每个模板目录，如下所示：classpath*:/templates/。

**4.7.1.11 错误处理**

&emsp;&emsp;默认情况下，Spring Boot提供/error映射，以合理的方式处理所有错误，并在servlet容器中注册为“全局”错误页面。 对于计算机客户端，它会生成一个JSON响应，其中包含错误，HTTP状态和异常消息的详细信息。 对于浏览器客户端，有一个“whitelabel”错误视图，以HTML格式呈现相同的数据（要自定义它，添加解析为错误的View）。 要完全替换默认行为，可以实现ErrorController并注册该类型的bean定义，或者添加ErrorAttributes类型的bean以使用现有机制但替换内容。

>BasicErrorController可以用作自定义ErrorController的基类。 如果要为新内容类型添加处理程序，则此功能特别有用（默认情况下是专门处理text / html并为其他所有内容提供后备）。 为此，请扩展BasicErrorController，使用具有produce属性的@RequestMapping添加公共方法，并创建新类型的bean。

&emsp;&emsp;您还可以定义一个使用@ControllerAdvice注释的类，以自定义JSON文档以返回特定控制器和/或异常类型，如以下示例所示：

``` 
@ControllerAdvice(basePackageClasses = AcmeController.class)
public class AcmeControllerAdvice extends ResponseEntityExceptionHandler {

	@ExceptionHandler(YourException.class)
	@ResponseBody
	ResponseEntity<?> handleControllerException(HttpServletRequest request, Throwable ex) {
		HttpStatus status = getStatus(request);
		return new ResponseEntity<>(new CustomErrorType(status.value(), ex.getMessage()), status);
	}

	private HttpStatus getStatus(HttpServletRequest request) {
		Integer statusCode = (Integer) request.getAttribute("javax.servlet.error.status_code");
		if (statusCode == null) {
			return HttpStatus.INTERNAL_SERVER_ERROR;
		}
		return HttpStatus.valueOf(statusCode);
	}

}
```

&emsp;&emsp;在前面的示例中，如果在与AcmeController相同的包中定义的控制器抛出YourException，则使用CustomErrorType POJO的JSON表示而不是ErrorAttributes表示。

**1）自定义错误页面**

&emsp;&emsp;如果要显示给定状态代码的自定义HTML错误页面，可以将文件添加到/error文件夹。 错误页面可以是静态HTML（即，添加到任何静态资源文件夹下），也可以使用模板构建。 文件名应该是确切的状态代码或系列掩码。

例如，要将404映射到静态HTML文件，您的文件夹结构将如下所示：

``` 
src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- public/
             +- error/
             |   +- 404.html
             +- <other public assets>
```

&emsp;&emsp;要使用FreeMarker模板映射所有5xx错误，您的文件夹结构如下：

``` 
src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- templates/
             +- error/
             |   +- 5xx.ftl
             +- <other templates>
```

&emsp;&emsp;对于更复杂的映射，您还可以添加实现ErrorViewResolver接口的bean，如以下示例所示：

``` 
public class MyErrorViewResolver implements ErrorViewResolver {

	@Override
	public ModelAndView resolveErrorView(HttpServletRequest request,
			HttpStatus status, Map<String, Object> model) {
		// Use the request or status to optionally return a ModelAndView
		return ...
	}

}
```

&emsp;&emsp;您还可以使用常规的Spring MVC功能，例如@ExceptionHandler方法和@ControllerAdvice。 然后，ErrorController将获取任何未处理的异常。

**2）映射Spring MVC之外的错误页面**

&emsp;&emsp;对于不使用Spring MVC的应用程序，可以使用ErrorPageRegistrar接口直接注册ErrorPages。 这种抽象直接与底层嵌入式servlet容器一起工作，即使你没有Spring MVC DispatcherServlet也可以工作。

``` 
@Bean
public ErrorPageRegistrar errorPageRegistrar(){
	return new MyErrorPageRegistrar();
}

// ...

private static class MyErrorPageRegistrar implements ErrorPageRegistrar {

	@Override
	public void registerErrorPages(ErrorPageRegistry registry) {
		registry.addErrorPages(new ErrorPage(HttpStatus.BAD_REQUEST, "/400"));
	}

}
```

>如果您注册一个ErrorPage，其路径最终由Filter处理（这与一些非Spring Web框架（如Jersey和Wicket）一样），则Filter必须显式注册为ERROR调度程序，如 以下示例：

``` 
@Bean
public FilterRegistrationBean myFilter() {
	FilterRegistrationBean registration = new FilterRegistrationBean();
	registration.setFilter(new MyFilter());
	...
	registration.setDispatcherTypes(EnumSet.allOf(DispatcherType.class));
	return registration;
}
```

&emsp;&emsp;请注意，默认的FilterRegistrationBean不包含ERROR调度程序类型。

&emsp;&emsp;小心：当部署到servlet容器时，Spring Boot使用其错误页面过滤器将具有错误状态的请求转发到相应的错误页面。 如果尚未提交响应，则只能将请求转发到正确的错误页面。 缺省情况下，WebSphere Application Server 8.0及更高版本在成功完成servlet的服务方法后提交响应。 您应该通过将com.ibm.ws.webcontainer.invokeFlushAfterService设置为false来禁用此行为。

**4.7.1.12 Spring HATEOAS**

&emsp;&emsp;如果您开发使用超媒体的RESTful API，Spring Boot为Spring HATEOAS提供自动配置，适用于大多数应用程序。 自动配置取代了使用@EnableHypermediaSupport的需要，并注册了许多bean以简化构建基于超媒体的应用程序，包括LinkDiscoverers（用于客户端支持）和配置为正确地将响应编组到所需表示中的ObjectMapper。 ObjectMapper是通过设置各种spring.jackson.*属性或者如果存在的话，通过设置Jackson2ObjectMapperBuilder bean来定制的。

&emsp;&emsp;您可以使用@EnableHypermediaSupport控制Spring HATEOAS的配置。 请注意，这样做会禁用前面描述的ObjectMapper自定义。

**4.7.1.13 支持CORS**

&emsp;&emsp;跨源资源共享（CORS）是大多数浏览器实现的W3C规范，允许您以灵活的方式指定授权何种跨域请求，而不是使用一些安全性较低且功能较弱的方法，如IFRAME或JSONP。

&emsp;&emsp;从版本4.2开始，Spring MVC支持CORS。 在Spring Boot应用程序中使用带有@CrossOrigin注释的控制器方法CORS配置不需要任何特定配置。 可以通过使用自定义的addCorsMappings(CorsRegistry)方法注册WebMvcConfigurer bean来定义全局CORS配置，如以下示例所示：

``` 
@Configuration
public class MyConfiguration {

	@Bean
	public WebMvcConfigurer corsConfigurer() {
		return new WebMvcConfigurer() {
			@Override
			public void addCorsMappings(CorsRegistry registry) {
				registry.addMapping("/api/**");
			}
		};
	}
}
```

### **4.7.2 “Spring WebFlux框架”**

&emsp;&emsp;Spring WebFlux是Spring Framework 5.0中引入的新的响应式Web框架。 与Spring MVC不同，它不需要Servlet API，完全异步且无阻塞，并通过Reactor项目实现Reactive Streams规范。

&emsp;&emsp;Spring WebFlux有两种版本：基于方法和注释。 基于注释的注释非常接近Spring MVC模型，如以下示例所示：

``` 
@RestController
@RequestMapping("/users")
public class MyRestController {

	@GetMapping("/{user}")
	public Mono<User> getUser(@PathVariable Long user) {
		// ...
	}

	@GetMapping("/{user}/customers")
	public Flux<Customer> getUserCustomers(@PathVariable Long user) {
		// ...
	}

	@DeleteMapping("/{user}")
	public Mono<User> deleteUser(@PathVariable Long user) {
		// ...
	}

}
```

&emsp;&emsp;“WebFlux.fn”是函数变体，它将路由配置与请求的实际处理分开，如以下示例所示：

``` 
@Configuration
public class RoutingConfiguration {

	@Bean
	public RouterFunction<ServerResponse> monoRouterFunction(UserHandler userHandler) {
		return route(GET("/{user}").and(accept(APPLICATION_JSON)), userHandler::getUser)
				.andRoute(GET("/{user}/customers").and(accept(APPLICATION_JSON)), userHandler::getUserCustomers)
				.andRoute(DELETE("/{user}").and(accept(APPLICATION_JSON)), userHandler::deleteUser);
	}

}

@Component
public class UserHandler {

	public Mono<ServerResponse> getUser(ServerRequest request) {
		// ...
	}

	public Mono<ServerResponse> getUserCustomers(ServerRequest request) {
		// ...
	}

	public Mono<ServerResponse> deleteUser(ServerRequest request) {
		// ...
	}
}
```

&emsp;&emsp;WebFlux是Spring Framework的一部分，详细信息可在其参考文档中找到。

>您可以根据需要定义尽可能多的RouterFunction bean来模块化路由器的定义。 如果需要应用优先级，可以排序Bean。

&emsp;&emsp;首先，将spring-boot-starter-webflux模块添加到您的应用程序中。

>在应用程序中添加spring-boot-starter-web和spring-boot-starter-webflux模块会导致Spring Boot自动配置Spring MVC，而不是WebFlux。 选择此行为是因为许多Spring开发人员将spring-boot-starter-webflux添加到他们的Spring MVC应用程序中以使用反应式WebClient。 您仍然可以通过将所选应用程序类型设置为SpringApplication.setWebApplicationType（WebApplicationType.REACTIVE）来强制执行您的选择。

**4.7.2.1 Spring WebFlux自动配置**

&emsp;&emsp;Spring Boot为Spring WebFlux提供自动配置，适用于大多数应用程序。

&emsp;&emsp;自动配置在Spring的默认值之上添加了以下功能：

- 为HttpMessageReader和HttpMessageWriter实例配置编解码器（本文档稍后将介绍）。
- 支持提供静态资源，包括对WebJars的支持（在本文档后面介绍）。


&emsp;&emsp;如果你想保留Spring Boot WebFlux功能，并且想要添加额外的WebFlux配置，你可以添加自己的@Configuration类，类型为WebFluxConfigurer，但没有@EnableWebFlux。

&emsp;&emsp;如果您想完全控制Spring WebFlux，可以添加自己的@Configuration注释@EnableWebFlux。

**4.7.2.2 带有HttpMessageReaders和HttpMessageWriters的HTTP编解码器**

&emsp;&emsp;Spring WebFlux使用HttpMessageReader和HttpMessageWriter接口来转换HTTP请求和响应。 通过查看类路径中可用的库，它们配置了CodecConfigurer以具有合理的默认值。

&emsp;&emsp;Spring Boot通过使用CodecCustomizer实例进一步自定义。 例如，spring.jackson.*配置键应用于Jackson编解码器。

&emsp;&emsp;如果需要添加或自定义编解码器，可以创建自定义CodecCustomizer组件，如以下示例所示：

``` 
import org.springframework.boot.web.codec.CodecCustomizer;

@Configuration
public class MyConfiguration {

	@Bean
	public CodecCustomizer myCodecCustomizer() {
		return codecConfigurer -> {
			// ...
		}
	}

}
```

&emsp;&emsp;您还可以利用Spring Boot的自定义JSON序列化程序和反序列化程序。

**4.7.2.3 静态内容**

&emsp;&emsp;默认情况下，Spring Boot从类路径中名为/static（或/public或/resources或/META-INF/resources）的目录中提供静态内容。 它使用Spring WebFlux中的ResourceWebHandler，以便您可以通过添加自己的WebFluxConfigurer并覆盖addResourceHandlers方法来修改该行为。

&emsp;&emsp;默认情况下，资源映射到/**，但您可以通过设置spring.webflux.static-path-pattern属性来调整它。 例如，可以按如下方式将所有资源重新定位到/resources/**：

``` 
spring.webflux.static-path-pattern=/resources/**
```

&emsp;&emsp;您还可以使用spring.resources.static-locations自定义静态资源位置。 这样做会将默认值替换为目录位置列表。 如果这样做，默认的欢迎页面检测将切换到您的自定义位置。 因此，如果启动时您的任何位置都有index.html，那么它就是应用程序的主页。

&emsp;&emsp;除了前面列出的“标准”静态资源位置之外，还为Webjars内容制作了一个特例。 在/webjars/**中具有路径的任何资源都是从jar文件提供的，如果它们以Webjars格式打包的话。

>Spring WebFlux应用程序并不严格依赖于Servlet API，因此它们不能作为war文件部署，也不能使用src/main/webapp目录。

**4.7.2.4 模板引擎**

&emsp;&emsp;除REST Web服务外，您还可以使用Spring WebFlux来提供动态HTML内容。 Spring WebFlux支持各种模板技术，包括Thymeleaf，FreeMarker和Mustache。

&emsp;&emsp;Spring Boot包括对以下模板引擎的自动配置支持：

- FreeMarker
- Thymeleaf
- Mustache


&emsp;&emsp;当您使用其中一个模板引擎和默认配置时，您的模板将自动从src/main/resources/templates中获取。

**4.7.2.5 错误处理**

&emsp;&emsp;Spring Boot提供了一个WebExceptionHandler，它以合理的方式处理所有错误。 它在处理顺序中的位置紧接在WebFlux提供的处理程序之前，这些处理程序被认为是最后一个。 对于计算机客户端，它会生成一个JSON响应，其中包含错误，HTTP状态和异常消息的详细信息。 对于浏览器客户端，有一个“whitelabel”错误处理程序，它以HTML格式呈现相同的数据。 您还可以提供自己的HTML模板来显示错误（请参阅下一节）。

&emsp;&emsp;自定义此功能的第一步通常涉及使用现有机制，但替换或扩充错误内容。 为此，您可以添加ErrorAttributes类型的bean。

&emsp;&emsp;要更改错误处理行为，可以实现ErrorWebExceptionHandler并注册该类型的bean定义。 因为WebExceptionHandler是一个非常低级的，所以Spring Boot还提供了一个方便的AbstractErrorWebExceptionHandler来让你以WebFlux函数方式处理错误，如下例所示：

``` 
public class CustomErrorWebExceptionHandler extends AbstractErrorWebExceptionHandler {

	// Define constructor here

	@Override
	protected RouterFunction<ServerResponse> getRoutingFunction(ErrorAttributes errorAttributes) {

		return RouterFunctions
				.route(aPredicate, aHandler)
				.andRoute(anotherPredicate, anotherHandler);
	}

}
```

&emsp;&emsp;要获得更完整的片段，您还可以直接继承DefaultErrorWebExceptionHandler并覆盖特定方法。

**1）自定义错误页面**

&emsp;&emsp;如果要显示给定状态代码的自定义HTML错误页面，可以将文件添加到/error文件夹。 错误页面可以是静态HTML（即，添加到任何静态资源文件夹下）或使用模板构建。 文件名应该是确切的状态代码或系列掩码。

例如，要将404映射到静态HTML文件，您的文件夹结构将如下所示：

``` 
src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- public/
             +- error/
             |   +- 404.html
             +- <other public assets>
```

&emsp;&emsp;要使用Mustache模板映射所有5xx错误，您的文件夹结构如下：

``` 
src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- templates/
             +- error/
             |   +- 5xx.mustache
             +- <other templates>
```

**4.7.2.6 Web过滤器**

&emsp;&emsp;Spring WebFlux提供了一个WebFilter接口，可以实现该接口来过滤HTTP请求 - 响应交换。 在应用程序上下文中找到的WebFilter bean将自动用于过滤每个交换。

&emsp;&emsp;如果过滤器的顺序很重要，则可以实现Ordered或使用@Order进行注释。 Spring Boot自动配置可以为您配置Web过滤器。 执行此操作时，将使用下表中显示的顺序：

<table>
	<tr>
		<th>Web Filter</th>
		<th>Order</th>
	</tr>
	<tr>
		<td>MetricsWebFilter</td>
		<td>Ordered.HIGHEST_PRECEDENCE + 1</td>
	</tr>
	<tr>
		<td>WebFilterChainProxy (Spring Security)</td>
		<td>-100</td>
	</tr>
	<tr>
		<td>HttpTraceWebFilter</td>
		<td>Ordered.LOWEST_PRECEDENCE - 10</td>
	</tr>
</table>

### **4.7.3 JAX-RS 和 Jersey**

&emsp;&emsp;如果您更喜欢REST端点的JAX-RS编程模型，则可以使用其中一个可用的实现而不是Spring MVC。 Jersey和Apache CXF开箱即用。 CXF要求您在应用程序上下文中将其Servlet或Filter注册为@Bean。 Jersey有一些原生的Spring支持，因此我们还在Spring Boot中为它提供了自动配置支持以及启动器。

&emsp;&emsp;要开始使用Jersey，请将spring-boot-starter-jersey作为依赖项包含在内，然后您需要一个类型为ResourceConfig的@Bean，您可以在其中注册所有端点，如以下示例所示：

``` 
@Component
public class JerseyConfig extends ResourceConfig {

	public JerseyConfig() {
		register(Endpoint.class);
	}

}
```

>Jersey对扫描可执行档案的支持相当有限。 例如，在运行可执行war文件时，它无法扫描完全可执行jar文件或WEB-INF/classes中找到的包中的端点。 为避免此限制，不应使用packages方法，并且应使用register方法单独注册端点，如上例所示。

&emsp;&emsp;对于更高级的自定义，您还可以注册实现ResourceConfigCustomizer的任意数量的bean。

&emsp;&emsp;所有已注册的端点都应该是具有HTTP资源注释的@Components（@GET和其他），如以下示例所示：

``` 
@Component
@Path("/hello")
public class Endpoint {

	@GET
	public String message() {
		return "Hello";
	}

}
```

&emsp;&emsp;默认情况下，Jersey在名为jerseyServletRegistration的ServletRegistrationBean类型的@Bean中设置为Servlet。 默认情况下，servlet是懒惰地初始化的，但您可以通过设置spring.jersey.servlet.load-on-startup来自定义该行为。 您可以通过创建具有相同名称的bean来禁用或覆盖该bean。 您还可以通过设置spring.jersey.type = filter来使用过滤器而不是servlet（在这种情况下，要替换或覆盖的@Bean是jerseyFilterRegistration）。 过滤器有一个@Order，可以使用spring.jersey.filter.order设置。 通过使用spring.jersey.init.*指定属性映射，可以为servlet和过滤器注册提供init参数。

&emsp;&emsp;有一个Jersey样本，以便您可以看到如何设置。

### **4.7.4 嵌入式Servlet容器支持**

&emsp;&emsp;Spring Boot包括对嵌入式Tomcat，Jetty和Undertow服务器的支持。 大多数开发人员使用适当的“Starter”来获取完全配置的实例。 默认情况下，嵌入式服务器在端口8080上侦听HTTP请求。

>如果您选择在CentOS上使用Tomcat，请注意，默认情况下，临时目录用于存储已编译的JSP，文件上载等。 应用程序运行时，tmpwatch可能会删除此目录，从而导致失败。 要避免此行为，您可能希望自定义tmpwatch配置，以便不删除tomcat.*目录或配置server.tomcat.basedir，以便嵌入式Tomcat使用不同的位置。

**4.7.4.1 Servlets, Filters, 和 listeners**

&emsp;&emsp;使用嵌入式servlet容器时，可以通过使用Spring bean或扫描Servlet组件，从Servlet规范中注册servlet，过滤器和所有侦听器（如HttpSessionListener）。

**1）注册Servlets, Filters, 和 Listeners 作为 Spring Beans**

&emsp;&emsp;任何Servlet，Filter或servlet *作为Spring bean的监听器实例都是在嵌入式容器中注册的。 如果要在配置期间引用application.properties中的值，这可能特别方便。

&emsp;&emsp;默认情况下，如果上下文仅包含一个Servlet，则将其映射到/。 在多个servlet bean的情况下，bean名称用作路径前缀。 过滤器映射到/*。

&emsp;&emsp;如果基于约定的映射不够灵活，则可以使用ServletRegistrationBean，FilterRegistrationBean和ServletListenerRegistrationBean类进行完全控制。

&emsp;&emsp;Spring Boot附带了许多可以定义Filter bean的自动配置。 以下是过滤器及其各自顺序的一些示例（较低的顺序值表示较高的优先级）：

<table>
	<tr>
		<th>Servlet Filter</th>
		<th>Order</th>
	</tr>
	<tr>
		<td>OrderedCharacterEncodingFilter</td>
		<td>Ordered.HIGHEST_PRECEDENCE</td>
	</tr>
	<tr>
		<td>WebMvcMetricsFilter</td>
		<td>Ordered.HIGHEST_PRECEDENCE + 1</td>
	</tr>
	<tr>
		<td>ErrorPageFilter</td>
		<td>Ordered.HIGHEST_PRECEDENCE + 1</td>
	</tr>
	<tr>
		<td>HttpTraceFilter</td>
		<td>Ordered.LOWEST_PRECEDENCE - 10</td>
	</tr>
</table>

&emsp;&emsp;将过滤器无序放置通常是安全的。

&emsp;&emsp;如果需要特定的顺序，则应避免在Ordered.HIGHEST_PRECEDENCE中配置读取请求主体的过滤器，因为它可能违反应用程序的字符编码配置。 如果Servlet过滤器包装请求，则应使用小于或等于OrderedFilter.REQUEST_WRAPPER_FILTER_MAX_ORDER的顺序对其进行配置。

**4.7.4.2 初始化Servlet Context**

&emsp;&emsp;嵌入式servlet容器不直接执行Servlet 3.0+ javax.servlet.ServletContainerInitializer接口或Spring的org.springframework.web.WebApplicationInitializer接口。 这是一个有意的设计决策，旨在降低设计在war中运行的第三方库可能会破坏Spring Boot应用程序的风险。

&emsp;&emsp;如果需要在Spring Boot应用程序中执行servlet上下文初始化，则应注册实现org.springframework.boot.web.servlet.ServletContextInitializer接口的bean。 单个onStartup方法提供对ServletContext的访问，如果需要，可以轻松地用作现有WebApplicationInitializer的适配器。

**1）扫描Servlets, Filters, 和 listeners**

&emsp;&emsp;使用嵌入式容器时，可以使用@ServletComponentScan启用使用@WebServlet，@WebFilter和@WebListener注释的类的自动注册。

>@ServletComponentScan对独立容器没有影响，其中使用容器的内置发现机制。

**4.7.4.3 ServletWebServerApplicationContext**

&emsp;&emsp;在内部，Spring Boot使用不同类型的ApplicationContext来支持嵌入式servlet容器。 ServletWebServerApplicationContext是一种特殊类型的WebApplicationContext，它通过搜索单个ServletWebServerFactory bean来引导自身。 通常已自动配置TomcatServletWebServerFactory，JettyServletWebServerFactory或UndertowServletWebServerFactory。

>您通常不需要了解这些实现类。 大多数应用程序都是自动配置的，并且代表您创建了相应的ApplicationContext和ServletWebServerFactory。

**4.7.4.4 自定义嵌入式Servlet容器**

&emsp;&emsp;可以使用Spring Environment属性配置公共servlet容器设置。 通常，您将在application.properties文件中定义属性。

&emsp;&emsp;常用服务器设置包括：

- 网络设置：侦听传入HTTP请求的端口（server.port），绑定到server.address的接口地址，等等。
- 会话设置：会话是持久的（server.servlet.session.persistence），会话超时（server.servlet.session.timeout），会话数据的位置（server.servlet.session.store-dir）和会话cookie 配置（server.servlet.session.cookie.*）。
- 错误管理：错误页面的位置（server.error.path）等。
- SSL
- HTTP压缩

&emsp;&emsp;Spring Boot尽可能尝试共用常见设置，但这并不总是可行。 对于这些情况，专用命名空间提供特定于服务器的自定义（请参阅server.tomcat和server.undertow）。 例如，可以使用嵌入式servlet容器的特定功能配置访问日志。

>有关完整列表，请参阅ServerProperties类。

**1）程序化定制**

&emsp;&emsp;如果需要以编程方式配置嵌入式servlet容器，可以注册实现WebServerFactoryCustomizer接口的Spring bean。 WebServerFactoryCustomizer提供对ConfigurableServletWebServerFactory的访问，其中包括许多自定义setter方法。 以下示例以编程方式设置端口：

``` 
import org.springframework.boot.web.server.WebServerFactoryCustomizer;
import org.springframework.boot.web.servlet.server.ConfigurableServletWebServerFactory;
import org.springframework.stereotype.Component;

@Component
public class CustomizationBean implements WebServerFactoryCustomizer<ConfigurableServletWebServerFactory> {

	@Override
	public void customize(ConfigurableServletWebServerFactory server) {
		server.setPort(9000);
	}

}
```

>TomcatServletWebServerFactory，JettyServletWebServerFactory和UndertowServletWebServerFactory是ConfigurableServletWebServerFactory的专用变体，它们分别为Tomcat，Jetty和Undertow提供了其他自定义setter方法。

**2）直接自定义ConfigurableServletWebServerFactory**

&emsp;&emsp;如果前面的自定义技术太有限，您可以自己注册TomcatServletWebServerFactory，JettyServletWebServerFactory或UndertowServletWebServerFactory bean。

``` 
@Bean
public ConfigurableServletWebServerFactory webServerFactory() {
	TomcatServletWebServerFactory factory = new TomcatServletWebServerFactory();
	factory.setPort(9000);
	factory.setSessionTimeout(10, TimeUnit.MINUTES);
	factory.addErrorPages(new ErrorPage(HttpStatus.NOT_FOUND, "/notfound.html"));
	return factory;
}
```

&emsp;&emsp;为许多配置选项提供了Setter。 如果您需要做一些更具异国情调的事情，还会提供一些受保护的方法“挂钩”。 有关详细信息，请参阅源代码文档。

**4.7.4.5 JSP限制**

&emsp;&emsp;运行使用嵌入式servlet容器的Spring Boot应用程序（并打包为可执行存档）时，JSP支持存在一些限制。

- 使用Jetty和Tomcat，如果使用war包装，它应该可以工作。 使用java -jar启动时，可执行的war将起作用，并且还可以部署到任何标准容器。 使用可执行jar时不支持JSP。
- Undertow不支持JSP。
- 创建自定义error.jsp页面不会覆盖错误处理的默认视图。 应该使用自定义错误页面。


&emsp;&emsp;有一个JSP示例，以便您可以看到如何设置。

### **4.7.5 嵌入式Reactive Server支持**

&emsp;&emsp;Spring Boot包括对以下嵌入式响应式Web服务器的支持：Reactor Netty，Tomcat，Jetty和Undertow。 大多数开发人员使用适当的“Starter”来获取完全配置的实例。 默认情况下，嵌入式服务器在端口8080上侦听HTTP请求。

### **4.7.6 Reactive Server资源配置**

&emsp;&emsp;在自动配置Reactor Netty或Jetty服务器时，Spring Boot将创建特定的bean，为服务器实例提供HTTP资源：ReactorResourceFactory或JettyResourceFactory。

&emsp;&emsp;默认情况下，这些资源也将与Reactor Netty和Jetty客户端共享，以获得最佳性能，具体如下：

- 相同的技术用于服务器和客户端
- 客户端实例是使用Spring Boot自动配置的WebClient.Builder bean构建的


&emsp;&emsp;开发人员可以通过提供自定义的ReactorResourceFactory或JettyResourceFactory bean来覆盖Jetty和Reactor Netty的资源配置 - 这将应用于客户端和服务器。

&emsp;&emsp;您可以在4.14.1 运行时WebClient部分中了解有关客户端资源配置的更多信息。

## **4.8 安全**

&emsp;&emsp;如果Spring Security位于类路径上，则默认情况下Web应用程序是安全的。 Spring Boot依赖于Spring Security的内容协商策略来确定是使用httpBasic还是formLogin。 要向Web应用程序添加方法级安全性，还可以使用所需设置添加@EnableGlobalMethodSecurity。 其他信息可以在Spring Security Reference Guide中找到。

&emsp;&emsp;默认的UserDetailsService只有一个用户。 用户名是user，密码是随机的，在应用程序启动时以INFO级别打印，如以下示例所示：

``` 
Using generated security password: 78fa095d-3f4c-48b1-ad50-e24c31d5cf35
```

>如果您对日志记录配置进行微调，请确保将org.springframework.boot.autoconfigure.security类别设置为记录INFO级别的消息。 否则，不会打印默认密码。

&emsp;&emsp;您可以通过提供spring.security.user.name和spring.security.user.password来更改用户名和密码。

&emsp;&emsp;您在Web应用程序中默认获得的基本功能包括：

- UserDetailsService（或WebFlux应用程序中的ReactiveUserDetailsService）具有内存存储的bean和具有生成密码的单个用户（有关用户属性，请参阅SecurityProperties.User）。
- 基于表单的登录或HTTP基本安全性（取决于Content-Type）用于整个应用程序（如果执行器在类路径上，则包括执行器端点）。
- 用于发布身份验证事件的DefaultAuthenticationEventPublisher。


&emsp;&emsp;您可以通过为其添加bean来提供不同的AuthenticationEventPublisher。

### **4.8.1 MVC安全**

&emsp;&emsp;默认安全配置在SecurityAutoConfiguration和UserDetailsServiceAutoConfiguration中实现。 SecurityAutoConfiguration导入用于Web安全的SpringBootWebSecurityConfiguration和UserDetailsServiceAutoConfiguration配置身份验证，这也适用于非Web应用程序。 要完全关闭默认Web应用程序安全性配置，可以添加WebSecurityConfigurerAdapter类型的bean（这样做不会禁用UserDetailsService配置或Actuator的安全性）。

&emsp;&emsp;要关闭UserDetailsService配置，您可以添加UserDetailsService，AuthenticationProvider或AuthenticationManager类型的bean。 Spring Boot示例中有几个安全的应用程序可以帮助您开始使用常见的用例。

&emsp;&emsp;可以通过添加自定义WebSecurityConfigurerAdapter来覆盖访问规则。 Spring Boot提供了便捷方法，可用于覆盖执行器端点和静态资源的访问规则。 EndpointRequest可用于创建基于management.endpoints.web.base-path属性的RequestMatcher。 PathRequest可用于为常用位置中的资源创建RequestMatcher。

### **4.8.2 WebFlux安全**

&emsp;&emsp;与Spring MVC应用程序类似，您可以通过添加spring-boot-starter-security依赖项来保护WebFlux应用程序。 默认安全配置在ReactiveSecurityAutoConfiguration和UserDetailsServiceAutoConfiguration中实现。 ReactiveSecurityAutoConfiguration导入WebFluxSecurityConfiguration以实现Web安全性，UserDetailsServiceAutoConfiguration配置身份验证，这也适用于非Web应用程序。 要完全关闭默认Web应用程序安全配置，可以添加WebFilterChainProxy类型的bean（这样做不会禁用UserDetailsService配置或Actuator的安全性）。

&emsp;&emsp;要关闭UserDetailsService配置，您可以添加ReactiveUserDetailsService或ReactiveAuthenticationManager类型的bean。

&emsp;&emsp;可以通过添加自定义SecurityWebFilterChain来配置访问规则。 Spring Boot提供了便捷方法，可用于覆盖执行器端点和静态资源的访问规则。 EndpointRequest可用于创建基于management.endpoints.web.base-path属性的ServerWebExchangeMatcher。

&emsp;&emsp;PathRequest可用于为常用位置中的资源创建ServerWebExchangeMatcher。

例如，您可以通过添加以下内容来自定义安全配置：

``` 
@Bean
public SecurityWebFilterChain springSecurityFilterChain(ServerHttpSecurity http) {
	return http
		.authorizeExchange()
			.matchers(PathRequest.toStaticResources().atCommonLocations()).permitAll()
			.pathMatchers("/foo", "/bar")
				.authenticated().and()
			.formLogin().and()
		.build();
}
```

### **4.8.3 OAuth2**

&emsp;&emsp;OAuth2是Spring支持的一种广泛使用的授权框架。

**4.8.3.1 客户端**

&emsp;&emsp;如果在类路径中有spring-security-oauth2-client，则可以利用一些自动配置来轻松设置OAuth2 / Open ID Connect客户端。 此配置使用OAuth2ClientProperties下的属性。 相同的属性适用于servlet和反应式应用程序。

&emsp;&emsp;您可以在spring.security.oauth2.client前缀下注册多个OAuth2客户端和提供程序，如以下示例所示：

``` 
spring.security.oauth2.client.registration.my-client-1.client-id=abcd
spring.security.oauth2.client.registration.my-client-1.client-secret=password
spring.security.oauth2.client.registration.my-client-1.client-name=Client for user scope
spring.security.oauth2.client.registration.my-client-1.provider=my-oauth-provider
spring.security.oauth2.client.registration.my-client-1.scope=user
spring.security.oauth2.client.registration.my-client-1.redirect-uri-template=http://my-redirect-uri.com
spring.security.oauth2.client.registration.my-client-1.client-authentication-method=basic
spring.security.oauth2.client.registration.my-client-1.authorization-grant-type=authorization_code

spring.security.oauth2.client.registration.my-client-2.client-id=abcd
spring.security.oauth2.client.registration.my-client-2.client-secret=password
spring.security.oauth2.client.registration.my-client-2.client-name=Client for email scope
spring.security.oauth2.client.registration.my-client-2.provider=my-oauth-provider
spring.security.oauth2.client.registration.my-client-2.scope=email
spring.security.oauth2.client.registration.my-client-2.redirect-uri-template=http://my-redirect-uri.com
spring.security.oauth2.client.registration.my-client-2.client-authentication-method=basic
spring.security.oauth2.client.registration.my-client-2.authorization-grant-type=authorization_code

spring.security.oauth2.client.provider.my-oauth-provider.authorization-uri=http://my-auth-server/oauth/authorize
spring.security.oauth2.client.provider.my-oauth-provider.token-uri=http://my-auth-server/oauth/token
spring.security.oauth2.client.provider.my-oauth-provider.user-info-uri=http://my-auth-server/userinfo
spring.security.oauth2.client.provider.my-oauth-provider.user-info-authentication-method=header
spring.security.oauth2.client.provider.my-oauth-provider.jwk-set-uri=http://my-auth-server/token_keys
spring.security.oauth2.client.provider.my-oauth-provider.user-name-attribute=name
```

&emsp;&emsp;对于支持OpenID Connect发现的OpenID Connect提供程序，可以进一步简化配置。 提供程序需要配置issuer-uri，它是它声明为其颁发者标识符的URI。 例如，如果提供的issuer-uri是“https://example.com”，则将对“https://example.com/.well-known/openid-configuration”进行OpenID提供商配置请求。 结果预计将是OpenID提供程序配置响应。 以下示例显示如何使用issuer-uri配置OpenID Connect Provider：

``` 
spring.security.oauth2.client.provider.oidc-provider.issuer-uri=https://dev-123456.oktapreview.com/oauth2/default/
```

&emsp;&emsp;默认情况下，Spring Security的OAuth2LoginAuthenticationFilter仅处理与/login/oauth2/code/*匹配的URL。 如果要自定义redirect-uri以使用其他模式，则需要提供配置以处理该自定义模式。 例如，对于servlet应用程序，您可以添加类似于以下内容的WebSecurityConfigurerAdapter：

``` 
public class OAuth2LoginSecurityConfig extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		http
			.authorizeRequests()
				.anyRequest().authenticated()
				.and()
			.oauth2Login()
				.redirectionEndpoint()
					.baseUri("/custom-callback");
	}
}
```

**1）OAuth2客户端注册常见提供商**

&emsp;&emsp;对于常见的OAuth2和OpenID提供商，包括Google，Github，Facebook和Okta，我们提供了一组提供商默认设置（分别为google，github，facebook和okta）。

&emsp;&emsp;如果不需要自定义这些提供程序，则可以将Provider属性设置为需要推断默认值的提供程序属性。此外，如果客户端注册的键与默认支持的提供程序匹配，SpringBoot也会推断这一点。

&emsp;&emsp;换句话说，以下示例中的两个配置使用Google提供程序：

``` 
spring.security.oauth2.client.registration.my-client.client-id=abcd
spring.security.oauth2.client.registration.my-client.client-secret=password
spring.security.oauth2.client.registration.my-client.provider=google

spring.security.oauth2.client.registration.google.client-id=abcd
spring.security.oauth2.client.registration.google.client-secret=password
```

**4.8.3.2 资源服务器**

&emsp;&emsp;如果在类路径上有spring-security-oauth2-resource-server，只要指定了JWK Set URI或OIDC Issuer URI，Spring Boot就可以设置OAuth2资源服务器，如以下示例所示：

``` 
spring.security.oauth2.resourceserver.jwt.jwk-set-uri=https://example.com/oauth2/default/v1/keys
```

``` 
spring.security.oauth2.resourceserver.jwt.issuer-uri=https://dev-123456.oktapreview.com/oauth2/default/
```

&emsp;&emsp;相同的属性适用于servlet和反应应用程序。

&emsp;&emsp;或者，您可以为servlet应用程序定义自己的JwtDecoder bean，或者为响应式应用程序定义ReactiveJwtDecoder。

**4.8.3.3 授权服务器**

&emsp;&emsp;目前，Spring Security不支持实施OAuth 2.0授权服务器。 但是，此功能可从Spring Security OAuth项目获得，该项目最终将完全被Spring Security取代。 在此之前，您可以使用spring-security-oauth2-autoconfigure模块轻松设置OAuth 2.0授权服务器; 请参阅其文档以获取说明

### **4.8.4 执行器安全**

&emsp;&emsp;出于安全考虑，默认情况下禁用除/health和/info之外的所有执行器。 management.endpoints.web.exposure.include属性可用于启用执行器。

&emsp;&emsp;如果Spring Security位于类路径上且没有其他WebSecurityConfigurerAdapter，则除了/health和/info之外的所有执行程序都由Spring Boot自动配置保护。 如果您定义了自定义WebSecurityConfigurerAdapter，则Spring Boot自动配置将退回，您将完全控制执行器访问规则。

>在设置management.endpoints.web.exposure.include之前，请确保暴露的执行器不包含敏感信息和（或）通过将它们放在防火墙后面或通过Spring Security之类的东西来保护。

**4.8.4.1 伪造跨域请求保护**

&emsp;&emsp;由于Spring Boot依赖于Spring Security的默认值，因此默认情况下会启用CSRF保护。 这意味着当使用默认安全配置时，需要POST（关闭和记录器端点），PUT或DELETE的执行器端点将获得403禁止错误。

>我们建议仅在创建非浏览器客户端使用的服务时才完全禁用CSRF保护。

## **4.9 使用SQL数据库**

&emsp;&emsp;Spring Framework为使用SQL数据库提供了广泛的支持，从使用JdbcTemplate的直接JDBC访问到完成“对象关系映射”技术（如Hibernate）。 Spring Data提供了更多级别的功能：直接从接口创建存储库实现，并使用约定从方法名称生成查询。

### **4.9.1 配置数据源**

&emsp;&emsp;Java的javax.sql.DataSource接口提供了一种处理数据库连接的标准方法。 传统上，“DataSource”使用URL和一些凭据来建立数据库连接。

>有关更多高级示例，请参阅“操作方法”部分，通常可以完全控制DataSource的配置。

**4.9.1.1 嵌入式数据库支持**

&emsp;&emsp;通过使用内存中的嵌入式数据库来开发应用程序通常很方便。 显然，内存数据库不提供持久存储。 您需要在应用程序启动时填充数据库，并准备在应用程序结束时丢弃数据。

>“操作方法”部分包含有关如何初始化数据库的部分。

&emsp;&emsp;Spring Boot可以自动配置嵌入式H2，HSQL和Derby数据库。 您无需提供任何连接URL。 您只需要包含要使用的嵌入式数据库的构建依赖项。

>如果您在测试中使用此功能，您可能会注意到整个测试套件都会重复使用相同的数据库，而不管您使用的应用程序上下文的数量。 如果要确保每个上下文都有一个单独的嵌入式数据库，则应将spring.datasource.generate-unique-name设置为true。

例如，典型的POM依赖关系如下：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<dependency>
	<groupId>org.hsqldb</groupId>
	<artifactId>hsqldb</artifactId>
	<scope>runtime</scope>
</dependency>
```

>您需要依赖spring-jdbc才能自动配置嵌入式数据库。 在这个例子中，它通过spring-boot-starter-data-jpa传递。

&emsp;
>如果由于某种原因，您确实为嵌入式数据库配置了连接URL，请注意确保禁用数据库的自动关闭。 如果使用H2，则应使用DB_CLOSE_ON_EXIT = FALSE来执行此操作。 如果使用HSQLDB，则应确保不使用shutdown = true。 禁用数据库的自动关闭可以在数据库关闭时进行Spring Boot控制，从而确保在不再需要访问数据库时发生。

**4.9.1.2 连接到生产数据库**

&emsp;&emsp;还可以使用池化DataSource自动配置生产数据库连接。 Spring Boot使用以下算法来选择特定的实现：

1. 我们更喜欢HikariCP的性能和并发性。 如果HikariCP可用，我们总是选择它。
2. 否则，如果Tomcat池化DataSource可用，我们将使用它。
3. 如果HikariCP和Tomcat池化数据源都不可用，并且Commons DBCP2可用，我们就会使用它。

&emsp;&emsp;如果使用spring-boot-starter-jdbc或spring-boot-starter-data-jpa“starters”，则会自动获得对HikariCP的依赖。

>您可以完全绕过该算法，并通过设置spring.datasource.type属性指定要使用的连接池。 如果您在Tomcat容器中运行应用程序，这一点尤为重要，因为默认情况下会提供tomcat-jdbc。

&emsp;
>始终可以手动配置其他连接池。 如果您定义自己的DataSource bean，则不会进行自动配置。

&emsp;&emsp;DataSource配置由spring.datasource.*中的外部配置属性控制。 例如，您可以在application.properties中声明以下部分：

``` 
spring.datasource.url=jdbc:mysql://localhost/test
spring.datasource.username=dbuser
spring.datasource.password=dbpass
spring.datasource.driver-class-name=com.mysql.jdbc.Driver
```

>您至少应该通过设置spring.datasource.url属性来指定URL。 否则，Spring Boot会尝试自动配置嵌入式数据库。

&emsp;
>您通常不需要指定driver-class-name，因为Spring Boot可以从url中为大多数数据库推断出它。

&emsp;
>对于要创建的DataSource池，我们需要能够验证有效的Driver类是否可用，因此我们在执行任何操作之前检查它。 换句话说，如果设置spring.datasource.driver-class-name = com.mysql.jdbc.Driver，那么该类必须是可加载的。

&emsp;&emsp;有关更多受支持的选项，请参阅DataSourceProperties。 无论实际实施如何，这些都是标准选项。 也可以使用各自的前缀（spring.datasource.hikari.*，spring.datasource.tomcat.*和spring.datasource.dbcp2.*）来微调特定于实现的设置。 有关更多详细信息，请参阅您正在使用的连接池实现的文档。

例如，如果使用Tomcat连接池，则可以自定义许多其他设置，如以下示例所示：

``` 
# Number of ms to wait before throwing an exception if no connection is available.
spring.datasource.tomcat.max-wait=10000

# Maximum number of active connections that can be allocated from this pool at the same time.
spring.datasource.tomcat.max-active=50

# Validate the connection before borrowing it from the pool.
spring.datasource.tomcat.test-on-borrow=true
```

**4.9.1.3 连接到JNDI数据源**

&emsp;&emsp;如果将Spring Boot应用程序部署到Application Server，则可能需要使用Application Server的内置功能配置和管理DataSource，并使用JNDI访问它。

&emsp;&emsp;spring.datasource.jndi-name属性可用作spring.datasource.url，spring.datasource.username和spring.datasource.password属性的替代，以从特定JNDI位置访问DataSource。 例如，application.properties中的以下部分显示了如何访问JBoss AS定义的DataSource：

``` 
spring.datasource.jndi-name=java:jboss/datasources/customers
```

### **4.9.2 使用JdbcTemplate**

&emsp;&emsp;Spring的JdbcTemplate和NamedParameterJdbcTemplate类是自动配置的，您可以将它们直接@Autowire到您自己的bean中，如以下示例所示：

``` 
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final JdbcTemplate jdbcTemplate;

	@Autowired
	public MyBean(JdbcTemplate jdbcTemplate) {
		this.jdbcTemplate = jdbcTemplate;
	}

	// ...

}
```

&emsp;&emsp;您可以使用spring.jdbc.template.*属性自定义模板的某些属性，如以下示例所示：

``` 
spring.jdbc.template.max-rows=500
```

>NamedParameterJdbcTemplate在后台重用相同的JdbcTemplate实例。 如果定义了多个JdbcTemplate且不存在主要候选项，则不会自动配置NamedParameterJdbcTemplate。

### **4.9.3 JPA 和 Spring Data JPA**

&emsp;&emsp;Java Persistence API是一种标准技术，可让您将对象“映射”到关系数据库。 spring-boot-starter-data-jpa POM提供了一种快速入门方式。 它提供以下关键依赖项：

- Hibernate：最受欢迎的JPA实现之一。
- Spring Data JPA：使实现基于JPA的存储库变得容易。
- Spring ORMs：Spring Framework的核心ORM支持。

>我们不会在这里详细介绍JPA或Spring Data。 您可以按照spring.io中的“使用JPA访问数据”指南阅读Spring Data JPA和Hibernate参考文档。

**4.9.3.1 实体类**

&emsp;&emsp;传统上，JPA“Entity”类在persistence.xml文件中指定。 使用Spring Boot，此文件不是必需的，而是使用“实体扫描”。 默认情况下，将搜索主配置类（使用@EnableAutoConfiguration或@SpringBootApplication注释的那个）下的所有包。

&emsp;&emsp;任何使用@Entity，@Embeddable或@MappedSuperclass注释的类都被考虑在内。 典型的实体类类似于以下示例：

``` 
package com.example.myapp.domain;

import java.io.Serializable;
import javax.persistence.*;

@Entity
public class City implements Serializable {

	@Id
	@GeneratedValue
	private Long id;

	@Column(nullable = false)
	private String name;

	@Column(nullable = false)
	private String state;

	// ... additional members, often include @OneToMany mappings

	protected City() {
		// no-args constructor required by JPA spec
		// this one is protected since it shouldn't be used directly
	}

	public City(String name, String state) {
		this.name = name;
		this.state = state;
	}

	public String getName() {
		return this.name;
	}

	public String getState() {
		return this.state;
	}

	// ... etc

}
```

>您可以使用@EntityScan批注自定义实体扫描位置。 请参阅“9.9.4 从Spring配置中分离@Entity定义”。

**4.9.3.2 Spring Data JPA Repositories**

&emsp;&emsp;Spring Data JPA存储库是您可以定义以访问数据的接口。 JPA查询是从您的方法名称自动创建的。 例如，CityRepository接口可能会声明findAllByState(String state)方法以查找给定状态中的所有城市。

&emsp;&emsp;对于更复杂的查询，可以使用Spring Data Query批注对方法进行批注。

&emsp;&emsp;Spring Data存储库通常从Repository或CrudRepository接口扩展。 如果使用自动配置，则会从包含主配置类（使用@EnableAutoConfiguration或@SpringBootApplication注释的那个）的包中搜索存储库。

&emsp;&emsp;以下示例显示了典型的Spring Data存储库接口定义：

``` 
package com.example.myapp.domain;

import org.springframework.data.domain.*;
import org.springframework.data.repository.*;

public interface CityRepository extends Repository<City, Long> {

	Page<City> findAll(Pageable pageable);

	City findByNameAndStateAllIgnoringCase(String name, String state);

}
```

&emsp;&emsp;Spring Data JPA存储库支持三种不同的引导模式：default，deferred和lazy。 要启用延迟或延迟引导，请将spring.data.jpa.repositories.bootstrap-mode分别设置为deferred或lazy。 使用延迟或延迟引导时，自动配置的EntityManagerFactoryBuilder将使用上下文的AsyncTaskExecutor（如果有）作为引导程序执行程序。 如果存在多个，则将使用名为applicationTaskExecutor的那个。

>我们几乎没有涉及Spring Data JPA的皮毛。 有关完整的详细信息，请参阅Spring Data JPA参考文档。

**4.9.3.3 创建和删除JPA数据库**

&emsp;&emsp;默认情况下，仅当您使用嵌入式数据库（H2，HSQL或Derby）时，才会自动创建JPA数据库。 您可以使用spring.jpa.*属性显式配置JPA设置。 例如，要创建和删除表，可以将以下行添加到application.properties：

``` 
spring.jpa.hibernate.ddl-auto=create-drop
```

>Hibernate自己的内部属性名称（如果你碰巧记得更好）是hibernate.hbm2ddl.auto。 您可以使用spring.jpa.properties.*（在将它们添加到实体管理器之前剥离前缀）来设置它以及其他Hibernate本机属性。 以下行显示了为Hibernate设置JPA属性的示例：

``` 
spring.jpa.properties.hibernate.globally_quoted_identifiers=true
```

&emsp;&emsp;前面示例中的行将hibernate.globally_quoted_identifiers属性的值传递给Hibernate实体管理器。

&emsp;&emsp;默认情况下，DDL执行（或验证）将延迟到ApplicationContext启动。 还有一个spring.jpa.generate-ddl标志，但如果Hibernate自动配置处于活动状态，则不会使用它，因为ddl-auto设置更精细。

**4.9.3.4 在View中打开EntityManager**

&emsp;&emsp;如果您正在运行Web应用程序，Spring Boot默认会注册OpenEntityManagerInViewInterceptor以应用“在视图中打开EntityManager”模式，以允许在Web视图中进行延迟加载。 如果您不想要此行为，则应在application.properties中将spring.jpa.open-in-view设置为false。

### **4.9.4 Spring Data JDBC**

&emsp;&emsp;Spring Data包含对JDBC的存储库支持，并将自动为CrudRepository上的方法生成SQL。 对于更高级的查询，提供了@Query注释。

&emsp;&emsp;当必要的依赖项在类路径上时，Spring Boot将自动配置Spring Data的JDBC存储库。 它们可以通过spring-boot-starter-data-jdbc的单一依赖项添加到项目中。 如有必要，可以通过将@EnableJdbcRepositories批注或JdbcConfiguration子类添加到应用程序来控制Spring Data JDBC的配置。

<table>
	<tr>
		<td></td>
	</tr>
	<tr>
		<td>有关Spring Data JDBC的完整详细信息，请参阅参考文档。</td>
	</tr>
</table>

### **4.9.5 使用 H2’s Web控制台**

&emsp;&emsp;H2数据库提供了一个基于浏览器的控制台，Spring Boot可以为您自动配置。 满足以下条件时，将自动配置控制台：

- 您正在开发基于servlet的Web应用程序。
- com.h2database：h2在类路径上。
- 您正在使用Spring Boot的开发人员工具。

>如果您没有使用Spring Boot的开发人员工具但仍想使用H2的控制台，则可以使用值true配置spring.h2.console.enabled属性。

&emsp;
>H2控制台仅用于开发期间，因此您应该注意确保spring.h2.console.enabled在生产中未设置为true。

**4.9.5.1 更改H2控制台的路径**

&emsp;&emsp;默认情况下，控制台位于/h2-console。 您可以使用spring.h2.console.path属性自定义控制台的路径。

### **4.9.6 使用jOOQ**

&emsp;&emsp;Java面向对象查询（jOOQ）是Data Geekery的一个流行产品，它从您的数据库生成Java代码，并允许您通过其Stream的API构建类型安全的SQL查询。 商业版和开源版都可以与Spring Boot一起使用。

**4.9.6.1 代码生成**

&emsp;&emsp;为了使用jOOQ类型安全查询，您需要从数据库模式生成Java类。 您可以按照jOOQ用户手册中的说明进行操作。 如果您使用jooq-codegen-maven插件并且还使用spring-boot-starter-parent“父POM”，则可以安全地省略插件的<version>标记。 您还可以使用Spring Boot定义的版本变量（例如h2.version）来声明插件的数据库依赖性。 以下清单显示了一个示例：

``` 
<plugin>
	<groupId>org.jooq</groupId>
	<artifactId>jooq-codegen-maven</artifactId>
	<executions>
		...
	</executions>
	<dependencies>
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<version>${h2.version}</version>
		</dependency>
	</dependencies>
	<configuration>
		<jdbc>
			<driver>org.h2.Driver</driver>
			<url>jdbc:h2:~/yourdatabase</url>
		</jdbc>
		<generator>
			...
		</generator>
	</configuration>
</plugin>
```

**4.9.6.2 使用DSLContext**

&emsp;&emsp;jOOQ提供的Stream API通过org.jooq.DSLContext接口启动。 Spring Boot将DSLContext自动配置为Spring Bean并将其连接到您的应用程序DataSource。 要使用DSLContext，您可以@Autowire它，如以下示例所示：

``` 
@Component
public class JooqExample implements CommandLineRunner {

	private final DSLContext create;

	@Autowired
	public JooqExample(DSLContext dslContext) {
		this.create = dslContext;
	}

}
```

>jOOQ手册倾向于使用名为create的变量来保存DSLContext。

&emsp;&emsp;然后，您可以使用DSLContext构建查询，如以下示例所示：

``` 
public List<GregorianCalendar> authorsBornAfter1980() {
	return this.create.selectFrom(AUTHOR)
		.where(AUTHOR.DATE_OF_BIRTH.greaterThan(new GregorianCalendar(1980, 0, 1)))
		.fetch(AUTHOR.DATE_OF_BIRTH);
}
```

**4.9.6.3 jOOQ数据库方言**

&emsp;&emsp;除非已配置spring.jooq.sql-dialect属性，否则Spring Boot会确定要用于数据源的SQL方言。 如果Spring Boot无法检测到方言，则使用DEFAULT。

>Spring Boot只能自动配置开源版本的jOOQ支持的方言.

**4.9.6.4 自定义jOOQ**

&emsp;&emsp;通过定义自己的@Bean定义可以实现更高级的自定义，这些定义在创建jOOQ配置时使用。 您可以为以下jOOQ类型定义bean：

- ConnectionProvider
- ExecutorProvider
- TransactionProvider
- RecordMapperProvider
- RecordUnmapperProvider
- RecordListenerProvider
- ExecuteListenerProvider
- VisitListenerProvider
- TransactionListenerProvider

&emsp;&emsp;如果要完全控制jOOQ配置，还可以创建自己的org.jooq.Configuration @Bean。

## **4.10 使用NoSQL技术**

&emsp;&emsp;Spring Data提供了其他项目，可帮助您访问各种NoSQL技术，包括：MongoDB，Neo4J，Elasticsearch，Solr，Redis，Gemfire，Cassandra，Couchbase和LDAP。 Spring Boot为Redis，MongoDB，Neo4j，Elasticsearch，Solr Cassandra，Couchbase和LDAP提供自动配置。 您可以使用其他项目，但必须自己配置它们。 请参阅projects.spring.io/spring-data上的相应参考文档。

### **4.10.1 Redis**

&emsp;&emsp;Redis是一个缓存，消息代理和功能丰富的键值存储。 Spring Boot为Lettuce和Jedis客户端库提供了基本的自动配置，并为Spring Data Redis提供了它们之外的抽象。

&emsp;&emsp;有一个spring-boot-starter-data-redis的“Starter”用于以方便的方式收集依赖项。 默认情况下，它使用Lettuce。 该启动器处理传统和反应应用程序。

>我们还提供了一个spring-boot-starter-data-redis-reactive的“Starter”，以便与其他具有反应支持的存储保持一致。

**4.10.1.1 连接到Redis**

&emsp;&emsp;您可以像注入任何其他Spring Bean一样注入自动配置的RedisConnectionFactory，StringRedisTemplate或vanilla RedisTemplate实例。 默认情况下，实例尝试连接到localhost:6379上的Redis服务器。 以下清单显示了这样一个bean的示例：

``` 
@Component
public class MyBean {

	private StringRedisTemplate template;

	@Autowired
	public MyBean(StringRedisTemplate template) {
		this.template = template;
	}

	// ...

}
```

>您还可以注册实现LettuceClientConfigurationBuilderCustomizer的任意数量的bean，以进行更高级的自定义。 如果使用Jedis，JedisClientConfigurationBuilderCustomizer也可用。

&emsp;&emsp;如果添加任何自动配置类型的@Bean，它将替换默认值（RedisTemplate除外，当排除基于bean名称时，redisTemplate，而不是其类型）。 默认情况下，如果commons-pool2在类路径上，则会获得池化连接工厂。

### **4.10.2 MongoDB**

&emsp;&emsp;MongoDB是一个开源的NoSQL文档数据库，它使用类似JSON的模式而不是传统的基于表的关系数据。 Spring Boot提供了几种使用MongoDB的便利，包括spring-boot-starter-data-mongodb和spring-boot-starter-data-mongodb-reactive“Starters”。

**4.10.2.1 连接到MongoDB数据库**

&emsp;&emsp;要访问Mongo数据库，您可以注入自动配置的org.springframework.data.mongodb.MongoDbFactory。 默认情况下，实例尝试通过mongodb:localhost/test连接到MongoDB服务器以下示例显示如何连接到MongoDB数据库：

``` 
import org.springframework.data.mongodb.MongoDbFactory;
import com.mongodb.DB;

@Component
public class MyBean {

	private final MongoDbFactory mongo;

	@Autowired
	public MyBean(MongoDbFactory mongo) {
		this.mongo = mongo;
	}

	// ...

	public void example() {
		DB db = mongo.getDb();
		// ...
	}

}
```

&emsp;&emsp;您可以设置spring.data.mongodb.uri属性以更改URL并配置其他设置，例如副本集合，如以下示例所示：

``` 
spring.data.mongodb.uri=mongodb://user:secret@mongo1.example.com:12345,mongo2.example.com:23456/test
```

&emsp;&emsp;或者，只要您使用Mongo 2.x，就可以指定主机/端口。 例如，您可以在application.properties中声明以下设置：

``` 
spring.data.mongodb.host=mongoserver
spring.data.mongodb.port=27017
```

&emsp;&emsp;如果您已经定义了自己的MongoClient，它将用于自动配置合适的MongoDbFactory。 com.mongodb.MongoClient和com.mongodb.client.MongoClient都受支持。

&emsp;
>如果使用Mongo 3.0 Java驱动程序，则不支持spring.data.mongodb.host和spring.data.mongodb.port。 在这种情况下，应使用spring.data.mongodb.uri来提供所有配置。

&emsp;
>如果未指定spring.data.mongodb.port，则使用默认值27017。 您可以从前面显示的示例中删除此行。

&emsp;
>如果你不使用Spring Data Mongo，你可以注入com.mongodb.MongoClient bean而不是使用MongoDbFactory。 如果要完全控制建立MongoDB连接，还可以声明自己的MongoDbFactory或MongoClient bean。

&emsp;
>如果您使用的是反应式驱动程序，则SSL需要Netty。 如果Netty可用并且尚未自定义要使用的工厂，则自动配置会自动配置此工厂。

**4.10.2.2 MongoTemplate**

&emsp;&emsp;Spring Data MongoDB提供了一个MongoTemplate类，它的设计与Spring的JdbcTemplate非常相似。 与JdbcTemplate一样，Spring Boot会自动为您配置一个bean来注入模板，如下所示：

``` 
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.data.mongodb.core.MongoTemplate;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final MongoTemplate mongoTemplate;

	@Autowired
	public MyBean(MongoTemplate mongoTemplate) {
		this.mongoTemplate = mongoTemplate;
	}

	// ...

}
```

&emsp;&emsp;有关完整的详细信息，请参阅MongoOperations Javadoc。

**4.10.2.3 Spring Data MongoDB Repositories**

&emsp;&emsp;Spring Data包括MongoDB的存储库支持。 与前面讨论的JPA存储库一样，基本原则是基于方法名称自动构造查询。

&emsp;&emsp;事实上，Spring Data JPA和Spring Data MongoDB共享相同的通用基础架构。 您可以从之前的JPA示例中获取，假设City现在是Mongo数据类而不是JPA @Entity，它的工作方式相同，如下例所示：

``` 
package com.example.myapp.domain;

import org.springframework.data.domain.*;
import org.springframework.data.repository.*;

public interface CityRepository extends Repository<City, Long> {

	Page<City> findAll(Pageable pageable);

	City findByNameAndStateAllIgnoringCase(String name, String state);

}
```

>您可以使用@EntityScan批注自定义文档扫描位置。

&emsp;
>有关Spring Data MongoDB的完整详细信息，包括其丰富的对象映射技术，请参阅其参考文档。

**4.10.2.4 嵌入式Mongo**

&emsp;&emsp;Spring Boot为Embedded Mongo提供自动配置。 要在Spring Boot应用程序中使用它，请添加依赖项 de.flapdoodle.embed:de.flapdoodle.embed.mongo。

&emsp;&emsp;可以通过设置spring.data.mongodb.port属性来配置Mongo侦听的端口。 要使用随机分配的空闲端口，请使用值0。MongoAutoConfiguration创建的MongoClient会自动配置为使用随机分配的端口。

>如果未配置自定义端口，则默认情况下，嵌入式支持使用随机端口（而不是27017）。

&emsp;&emsp;如果类路径上有SLF4J，则Mongo生成的输出将自动路由到名为org.springframework.boot.autoconfigure.mongo.embedded.EmbeddedMongo的记录器。

&emsp;&emsp;您可以声明自己的IMongodConfig和IRuntimeConfig bean来控制Mongo实例的配置和日志路由。

### **4.10.3 Neo4j**

&emsp;&emsp;Neo4j是一个开源的NoSQL图形数据库，它使用由一级关系连接的节点的丰富数据模型，与传统的RDBMS方法相比，它更适合于连接大数据。 Spring Boot为使用Neo4j提供了一些便利，包括spring-boot-starter-data-neo4j“的Starter”。

**4.10.3.1 连接到Neo4j数据库**

&emsp;&emsp;要访问Neo4j服务器，您可以注入自动配置的org.neo4j.ogm.session.Session。 默认情况下，实例尝试使用Bolt协议连接到localhost:7687上的Neo4j服务器。 以下示例显示了如何注入Neo4j会话：

``` 
@Component
public class MyBean {

	private final Session session;

	@Autowired
	public MyBean(Session session) {
		this.session = session;
	}

	// ...

}
```

&emsp;&emsp;您可以通过设置spring.data.neo4j.*属性来配置要使用的URI和凭据，如以下示例所示：

``` 
spring.data.neo4j.uri=bolt://my-server:7687
spring.data.neo4j.username=neo4j
spring.data.neo4j.password=secret
```

&emsp;&emsp;您可以通过添加org.neo4j.ogm.config.Configuration @Bean来完全控制会话创建。 此外，添加类型为SessionFactory的@Bean会禁用自动配置并为您提供完全控制。

**4.10.3.2 使用嵌入模式**

&emsp;&emsp;如果将org.neo4j:neo4j-ogm-embedded-driver添加到应用程序的依赖项中，Spring Boot会自动配置Neo4j的进程内嵌入式实例，该应用程序在应用程序关闭时不会保留任何数据。

>由于嵌入式Neo4j OGM驱动程序本身不提供Neo4j内核，因此您必须自己声明org.neo4j:neo4j作为依赖项。 有关兼容版本的列表，请参阅Neo4j OGM文档。

&emsp;&emsp;当类路径上有多个驱动程序时，嵌入式驱动程序优先于其他驱动程序。 您可以通过设置spring.data.neo4j.embedded.enabled = false来显式禁用嵌入模式。

&emsp;&emsp;如果嵌入式驱动程序和Neo4j内核如上所述位于类路径上，则数据Neo4j测试会自动使用嵌入式Neo4j实例。

>您可以通过在配置中提供数据库文件的路径来为嵌入模式启用持久性，例如：
spring.data.neo4j.uri=file://var/tmp/graph.db。

**4.10.3.3 Neo4jSession**

&emsp;&emsp;默认情况下，如果您正在运行Web应用程序，则会话将绑定到线程以进行整个请求处理（即，它使用“在视图中打开会话”模式）。 如果您不想要此行为，请将以下行添加到application.properties文件中：

``` 
spring.data.neo4j.open-in-view=false
```

**4.10.3.4 Spring Data Neo4j Repositories**

&emsp;&emsp;Spring Data包含对Neo4j的存储库支持。

&emsp;&emsp;Spring Data Neo4j与Spring Data JPA共享通用基础架构，就像许多其他Spring Data模块一样。 您可以从之前的JPA示例中将City定义为Neo4j OGM @NodeEntity而不是JPA @Entity，并且存储库抽象以相同的方式工作，如以下示例所示：

``` 
package com.example.myapp.domain;

import java.util.Optional;

import org.springframework.data.neo4j.repository.*;

public interface CityRepository extends Neo4jRepository<City, Long> {

	Optional<City> findOneByNameAndState(String name, String state);

}
```

&emsp;&emsp;spring-boot-starter-data-neo4j的“Starter”支持存储库支持和事务管理。 您可以在@Configuration-bean上分别使用@EnableNeo4jRepositories和@EntityScan来自定义位置以查找存储库和实体。

>有关Spring Data Neo4j的完整详细信息，包括其对象映射技术，请参阅参考文档。

### **4.10.4 Gemfire**

&emsp;&emsp;Spring Data Gemfire为访问Pivotal Gemfire数据管理平台提供了方便的Spring友好工具。 有一个spring-boot-starter-data-gemfire的“Starter”用于以方便的方式收集依赖项。 目前没有对Gemfire的自动配置支持，但您可以使用单个注释启用Spring Data Repositories:@EnableGemfireRepositories。

### **4.10.5 Solr**

&emsp;&emsp;Apache Solr是一个搜索引擎。 Spring Boot为Solr 5客户端库提供了基本的自动配置，并为Spring Data Solr提供了它的抽象。 有一个spring-boot-starter-data-solr的“Starter”用于以方便的方式收集依赖项。

**4.10.5.1 连接到Solr**

&emsp;&emsp;您可以像任何其他Spring bean一样注入自动配置的SolrClient实例。 默认情况下，实例尝试连接到localhost:8983/solr上的服务器。 以下示例显示如何注入Solr bean：

``` 
@Component
public class MyBean {

	private SolrClient solr;

	@Autowired
	public MyBean(SolrClient solr) {
		this.solr = solr;
	}

	// ...

}
```

&emsp;&emsp;如果添加自己的SolrClient类型的@Bean，它将替换默认值。

**4.10.5.2 Spring Data Solr Repositories**

&emsp;&emsp;Spring Data包括Apache Solr的存储库支持。 与前面讨论的JPA存储库一样，基本原则是根据方法名称自动构造查询。

&emsp;&emsp;事实上，Spring Data JPA和Spring Data Solr共享相同的通用基础架构。 您可以从之前获取JPA示例，假设City现在是@SolrDocument类而不是JPA @Entity，它的工作方式相同。

>有关Spring Data Solr的完整详细信息，请参阅参考文档。

### **4.10.6 Elasticsearch**

&emsp;&emsp;Elasticsearch是一个开源，分布式，RESTful搜索和分析引擎。 Spring Boot为Elasticsearch提供基本的自动配置。

&emsp;&emsp;Spring Boot支持多个HTTP客户端：

- 官方Java“低级”和“高级”REST客户端
- Jest


&emsp;&emsp;Spring Data Elasticsearch仍在使用传输客户端，您可以使用spring-boot-starter-data-elasticsearch的“Starter”开始使用它。

**4.10.6.1 使用REST客户端连接到Elasticsearch**

&emsp;&emsp;Elasticsearch提供了两个可用于查询集群的REST客户端：“低级”客户端和“高级”客户端。

&emsp;&emsp;如果您对类路径具有org.elasticsearch.client:elasticsearch-rest-client依赖关系，则Spring Boot将自动配置并注册默认情况下为localhost:9200的RestClient bean。 您可以进一步调整RestClient的配置方式，如以下示例所示：

``` 
spring.elasticsearch.rest.uris=http://search.example.com:9200
spring.elasticsearch.rest.username=user
spring.elasticsearch.rest.password=secret
```

&emsp;&emsp;您还可以注册实现RestClientBuilderCustomizer的任意数量的bean，以进行更高级的自定义。 要完全控制注册，请定义RestClient bean。

&emsp;&emsp;如果你对类路径有org.elasticsearch.client:elasticsearch-rest-high-level-client依赖关系，Spring Boot将自动配置一个RestHighLevelClient，它包装任何现有的RestClient bean，重用其HTTP配置。

**4.10.6.2 使用Jest连接到Elasticsearch**

&emsp;&emsp;如果你在类路径上有Jest，你可以注入一个自动配置的JestClient，默认情况下是localhost:9200。 您可以进一步调整客户端的配置方式，如以下示例所示：

``` 
spring.elasticsearch.jest.uris=http://search.example.com:9200
spring.elasticsearch.jest.read-timeout=10000
spring.elasticsearch.jest.username=user
spring.elasticsearch.jest.password=secret
```

&emsp;&emsp;您还可以注册实现HttpClientConfigBuilderCustomizer的任意数量的bean，以进行更高级的自定义。 以下示例调整其他HTTP设置：

``` 
static class HttpSettingsCustomizer implements HttpClientConfigBuilderCustomizer {

	@Override
	public void customize(HttpClientConfig.Builder builder) {
		builder.maxTotalConnection(100).defaultMaxTotalConnectionPerRoute(5);
	}

}
```

&emsp;&emsp;要完全控制注册，请定义JestClient bean。

**4.10.6.3 使用Spring Data连接到Elasticsearch**

&emsp;&emsp;要连接到Elasticsearch，您必须提供一个或多个群集节点的地址。 可以通过将spring.data.elasticsearch.cluster-nodes属性设置为以逗号分隔的host:port列表来指定地址。 使用此配置，可以像任何其他Spring bean一样注入ElasticsearchTemplate或TransportClient，如以下示例所示：

``` 
spring.data.elasticsearch.cluster-nodes=localhost:9300
```

``` 
@Component
public class MyBean {

	private final ElasticsearchTemplate template;

	public MyBean(ElasticsearchTemplate template) {
		this.template = template;
	}

	// ...

}
```

&emsp;&emsp;如果添加自己的ElasticsearchTemplate或TransportClient @Bean，它将替换默认值。

**4.10.6.4 Spring Data Elasticsearch Repositories**

&emsp;&emsp;Spring Data包括对Elasticsearch的存储库支持。 与前面讨论的JPA存储库一样，基本原则是根据方法名称自动为您构建查询。

&emsp;&emsp;事实上，Spring Data JPA和Spring Data Elasticsearch共享相同的通用基础架构。 您可以从之前的JPA示例中获取，假设City现在是Elasticsearch @Document类而不是JPA @Entity，它的工作方式相同。

>有关Spring Data Elasticsearch的完整详细信息，请参阅参考文档。

### **4.10.7 Cassandra**

&emsp;&emsp;Cassandra是一个开源的分布式数据库管理系统，旨在处理许多商用服务器上的大量数据。 Spring Boot提供了Cassandra的自动配置以及Spring Data Cassandra提供的抽象。 有一个spring-boot-starter-data-cassandra的“Starter”用于以方便的方式收集依赖项。

**4.10.7.1 连接到Cassandra**

&emsp;&emsp;您可以像使用任何其他Spring Bean一样注入自动配置的CassandraTemplate或Cassandra Session实例。 spring.data.cassandra.*属性可用于自定义连接。 通常，您提供keyspace-name和contact-points属性，如以下示例所示：

``` 
spring.data.cassandra.keyspace-name=mykeyspace
spring.data.cassandra.contact-points=cassandrahost1,cassandrahost2
```

&emsp;&emsp;您还可以注册实现ClusterBuilderCustomizer的任意数量的bean，以进行更高级的自定义。

&emsp;&emsp;以下代码清单显示了如何注入Cassandra bean：

``` 
@Component
public class MyBean {

	private CassandraTemplate template;

	@Autowired
	public MyBean(CassandraTemplate template) {
		this.template = template;
	}

	// ...

}
```

&emsp;&emsp;如果添加自己的CassandraTemplate类型的@Bean，它将替换默认值。

**4.10.7.2 Spring Data Cassandra Repositories**

&emsp;&emsp;Spring Data包含对Cassandra的基本存储库支持。 目前，这比前面讨论的JPA存储库更有限，需要使用@Query注释finder方法。

>有关Spring Data Cassandra的完整详细信息，请参阅参考文档.

### **4.10.8 Couchbase**

&emsp;&emsp;Couchbase是一个开源的，分布式的，多模型的NoSQL面向文档的数据库，针对交互式应用程序进行了优化。 Spring Boot提供了Couchbase的自动配置以及Spring Data Couchbase提供的抽象。 有spring-boot-starter-data-couchbase和spring-boot-starter-data-couchbase-reactive的“Starters”，用于以方便的方式收集依赖项。

**4.10.8.1 连接到Couchbase**

&emsp;&emsp;您可以通过添加Couchbase SDK和一些配置来获取Bucket和Cluster。 spring.couchbase.*属性可用于自定义连接。 通常，您提供引导主机，存储桶名称和密码，如以下示例所示：

``` 
spring.couchbase.bootstrap-hosts=my-host-1,192.168.1.123
spring.couchbase.bucket.name=my-bucket
spring.couchbase.bucket.password=secret
```

>您至少需要提供引导主机，在这种情况下，bucket名是默认的，密码是空字符串。或者，您可以定义自己的org.springframework.data.couchbase.config.CouchbaseConfigurer@Bean来控制整个配置。

&emsp;&emsp;也可以自定义一些CouchbaseEnvironment设置。 例如，以下配置更改用于打开新Bucket的超时并启用SSL支持：

``` 
spring.couchbase.env.timeouts.connect=3000
spring.couchbase.env.ssl.key-store=/location/of/keystore.jks
spring.couchbase.env.ssl.key-store-password=secret
```

&emsp;&emsp;有关更多详细信息，请查看spring.couchbase.env.*属性。

**4.10.8.2 Spring Data Couchbase Repositories**

&emsp;&emsp;Spring Data包括对Couchbase的存储库支持。 有关Spring Data Couchbase的完整详细信息，请参阅参考文档。

&emsp;&emsp;您可以像使用任何其他Spring Bean一样注入自动配置的CouchbaseTemplate实例，前提是可以使用默认的CouchbaseConfigurer（当您启用Couchbase支持时会发生这种情况，如前所述）。

&emsp;&emsp;以下示例显示了如何注入Couchbase bean：

``` 
@Component
public class MyBean {

	private final CouchbaseTemplate template;

	@Autowired
	public MyBean(CouchbaseTemplate template) {
		this.template = template;
	}

	// ...

}
```

&emsp;&emsp;您可以在自己的配置中定义一些bean来覆盖自动配置提供的bean：

- CouchbaseTemplate @Bean，名称为couchbaseTemplate。
- 一个名为couchbaseIndexManager的IndexManager @Bean。
- CustomConversions @Bean，名称为couchbaseCustomConversions。


&emsp;&emsp;为避免在您自己的配置中对这些名称进行硬编码，您可以重用Spring Data Couchbase提供的BeanNames。 例如，您可以自定义要使用的转换器，如下所示：

``` 
@Configuration
public class SomeConfiguration {

	@Bean(BeanNames.COUCHBASE_CUSTOM_CONVERSIONS)
	public CustomConversions myCustomConversions() {
		return new CustomConversions(...);
	}

	// ...

}
```

>如果要完全绕过Spring Data Couchbase的自动配置，请提供您自己的实现.org.springframework.data.couchbase.config.AbstractCouchbaseDataConfiguration.

### **4.10.9 LDAP**

&emsp;&emsp;LDAP（轻量级目录访问协议）是一种开放的，与供应商无关的行业标准应用程序协议，用于通过IP网络访问和维护分布式目录信息服务。 Spring Boot为任何兼容的LDAP服务器提供自动配置，并为UnboundID支持嵌入式内存中LDAP服务器。

&emsp;&emsp;LDAP抽象由Spring Data LDAP提供。 有一个spring-boot-starter-data-ldap的“Starter”用于以方便的方式收集依赖项。

**4.10.9.1 连接到LDAP服务器**

&emsp;&emsp;要连接到LDAP服务器，请确保声明对spring-boot-starter-data-ldap的“Starter”或spring-ldap-core的依赖关系，然后在application.properties中声明服务器的URL，如下所示：

``` 
spring.ldap.urls=ldap://myserver:1235
spring.ldap.username=admin
spring.ldap.password=secret
```

&emsp;&emsp;如果需要自定义连接设置，可以使用spring.ldap.base和spring.ldap.base-environment属性。

&emsp;&emsp;根据这些设置自动配置LdapContextSource。 如果您需要自定义它，例如使用PooledContextSource，您仍然可以注入自动配置的LdapContextSource。 确保将自定义的ContextSource标记为@Primary，以便自动配置的LdapTemplate使用它。

**4.10.9.2 Spring Data LDAP Repositories**

&emsp;&emsp;Spring Data包括对LDAP的存储库支持。 有关Spring Data LDAP的完整详细信息，请参阅参考文档。

&emsp;&emsp;您也可以像使用任何其他Spring Bean一样注入自动配置的LdapTemplate实例，如以下示例所示：

``` 
@Component
public class MyBean {

	private final LdapTemplate template;

	@Autowired
	public MyBean(LdapTemplate template) {
		this.template = template;
	}

	// ...

}
```

**4.10.9.3 嵌入式内存LDAP服务器**

&emsp;&emsp;出于测试目的，Spring Boot支持从UnboundID自动配置内存中的LDAP服务器。 要配置服务器，请向com.unboundid:unboundid-ldapsdk添加依赖项并声明base-dn属性，如下所示：

``` 
spring.ldap.embedded.base-dn=dc=spring,dc=io
```

>可以定义多个base-dn值，但是，由于可分辨名称通常包含逗号，因此必须使用正确的表示法定义它们。 在yaml文件中，您可以使用yaml列表表示法： 

>```
spring.ldap.embedded.base-dn:
  - dc=spring,dc=io
  - dc=pivotal,dc=io 
>```

>在属性文件中，必须包含索引作为属性名称的一部分：

>```
spring.ldap.embedded.base-dn[0]=dc=spring,dc=io
spring.ldap.embedded.base-dn[1]=dc=pivotal,dc=io
>```

&emsp;&emsp;默认情况下，服务器在随机端口上启动并触发常规LDAP支持。 无需指定spring.ldap.urls属性。

&emsp;&emsp;如果类路径上有schema.ldif文件，则它用于初始化服务器。 如果要从其他资源加载初始化脚本，还可以使用spring.ldap.embedded.ldif属性。

&emsp;&emsp;默认情况下，标准模式用于验证LDIF文件。 您可以通过设置spring.ldap.embedded.validation.enabled属性来完全关闭验证。 如果您有自定义属性，则可以使用spring.ldap.embedded.validation.schema来定义自定义属性类型或对象类。

### **4.10.10 InfluxDB**

&emsp;&emsp;InfluxDB是一个开源时间序列数据库，针对运营监控，应用程序指标，物联网传感器数据和实时分析等领域中的时间序列数据的快速，高可用性存储和检索进行了优化。

### **4.10.10.1 连接到InfluxDB**

&emsp;&emsp;Spring Boot自动配置InfluxDB实例，前提是Influxdb-java客户端在类路径上并且设置了数据库的URL，如以下示例所示：

``` 
spring.influx.url=http://172.0.0.1:8086
```

&emsp;&emsp;如果与InfluxDB的连接需要用户和密码，则可以相应地设置spring.influx.user和spring.influx.password属性。

&emsp;&emsp;InfluxDB依赖于OkHttp。 如果你需要调整InfluxDB在幕后使用的http客户端，你可以注册一个InfluxDbOkHttpClientBuilderProvider bean。

## **4.11 缓存**

&emsp;&emsp;Spring Framework支持透明地向应用程序添加缓存。 从本质上讲，抽象将缓存应用于方法，从而根据缓存中可用的信息减少执行次数。 缓存逻辑是透明应用的，不会对调用者造成任何干扰。 只要通过@EnableCaching批注启用了缓存支持，Spring Boot就会自动配置缓存基础结构。

>有关更多详细信息，请查看Spring Framework参考的相关部分.

&emsp;&emsp;简而言之，将缓存添加到服务操作就像在其方法中添加相关注释一样简单，如以下示例所示：

``` 
import org.springframework.cache.annotation.Cacheable;
import org.springframework.stereotype.Component;

@Component
public class MathService {

	@Cacheable("piDecimals")
	public int computePiDecimal(int i) {
		// ...
	}

}
```

&emsp;&emsp;此示例演示了如何在可能代价高昂的操作上使用缓存。 在调用computePiDecimal之前，抽象在piDecimals缓存中查找与i参数匹配的条目。 如果找到条目，则缓存中的内容会立即返回给调用者，并且不会调用该方法。 否则，将调用该方法，并在返回值之前更新缓存。

>您还可以透明地使用标准JSR-107（JCache）注释（例如@CacheResult）。 但是，我们强烈建议您不要混淆和匹配Spring Cache和JCache注释.

&emsp;&emsp;如果您不添加任何特定的缓存库，Spring Boot会自动配置一个在内存中使用并发映射的简单提供程序。 当需要缓存时（例如前面示例中的piDecimals），此提供程序会为您创建缓存。 简单的提供程序并不是真正推荐用于生产用途，但它非常适合入门并确保您了解这些功能。 当您决定使用缓存提供程序时，请务必阅读其文档以了解如何配置应用程序使用的缓存。 几乎所有提供程序都要求您显式配置在应用程序中使用的每个缓存。 有些提供了一种自定义spring.cache.cache-names属性定义的默认缓存的方法。

>还可以透明地更新或逐出缓存中的数据.

### **4.11.1 支持的缓存提供程序**

&emsp;&emsp;缓存抽象不提供实际存储，而是依赖于org.springframework.cache.Cache和org.springframework.cache.CacheManager接口实现的抽象。

&emsp;&emsp;如果您尚未定义CacheManager类型的bean或名为cacheResolver的CacheResolver（请参阅CachingConfigurer），则Spring Boot会尝试检测以下提供程序（按指示的顺序）：

1. Generic
2. JCache (JSR-107) (EhCache 3, Hazelcast, Infinispan, 和其他)
3. EhCache 2.x
4. Hazelcast
5. Infinispan
6. Couchbase
7. Redis
8. Caffeine
9. Simple

>也可以通过设置spring.cache.type属性来强制特定的缓存提供程序。 如果需要在某些环境（例如测试）中完全禁用缓存，请使用此属性.

&emsp;
>使用spring-boot-starter-cache“Starter”快速添加基本缓存依赖项。 Starter带来了spring环境支持。 如果手动添加依赖项，则必须包含spring-context-support才能使用JCache，EhCache 2.x或Guava支持.

&emsp;&emsp;如果通过Spring Boot自动配置CacheManager，则可以通过公开实现CacheManagerCustomizer接口的bean，在完全初始化之前进一步调整其配置。 以下示例设置一个标志，表示应将null值传递给底层映射：

``` 
@Bean
public CacheManagerCustomizer<ConcurrentMapCacheManager> cacheManagerCustomizer() {
	return new CacheManagerCustomizer<ConcurrentMapCacheManager>() {
		@Override
		public void customize(ConcurrentMapCacheManager cacheManager) {
			cacheManager.setAllowNullValues(false);
		}
	};
}
```

>在前面的示例中，需要自动配置的ConcurrentMapCacheManager。 如果不是这种情况（您提供了自己的配置或自动配置了不同的缓存提供程序），则根本不会调用自定义程序。 您可以拥有任意数量的自定义程序，也可以使用@Order或Ordered排序它们.

**4.11.1.1 Generic**

&emsp;&emsp;如果上下文定义了至少一个org.springframework.cache.Cache bean，则使用通用缓存。 将创建一个包装该类型所有bean的CacheManager。

**4.11.1.2 JCache (JSR-107)**

&emsp;&emsp;JCache是通过类路径上的javax.cache.spi.CachingProvider（即类路径上存在JSR-107兼容的缓存库）来引导的，而JCacheCacheManager是由spring-boot-starter-cache提供的“ Starter”。 可以使用各种兼容库，Spring Boot为Ehcache 3，Hazelcast和Infinispan提供依赖管理。 还可以添加任何其他兼容库。

&emsp;&emsp;可能会出现多个提供程序，在这种情况下，必须明确指定提供程序。 即使JSR-107标准没有强制执行定义配置文件位置的标准化方法，Spring Boot也会尽力满足设置缓存的实现细节，如下例所示：

``` 
# Only necessary if more than one provider is present
spring.cache.jcache.provider=com.acme.MyCachingProvider
spring.cache.jcache.config=classpath:acme.xml
```

>当缓存库同时提供本机实现和JSR-107支持时，Spring Boot更喜欢JSR-107支持，因此如果切换到不同的JSR-107实现，则可以使用相同的功能.

&emsp;
>Spring Boot对Hazelcast有一般支持。 如果单个HazelcastInstance可用，它也会自动重用于CacheManager，除非指定了spring.cache.jcache.config属性.

&emsp;&emsp;有两种方法可以自定义底层的javax.cache.cacheManager：

- 可以通过设置spring.cache.cache-names属性在启动时创建缓存。 如果定义了自定义javax.cache.configuration.Configuration bean，则会使用它来自定义它们。
- 使用CacheManager的引用调用org.springframework.boot.autoconfigure.cache.JCacheManagerCustomizer bean以进行完全自定义。

>如果定义了标准的javax.cache.CacheManager bean，它将自动包装在抽象所需的org.springframework.cache.CacheManagerimplementation中。 没有对其应用的进一步自定义.

**4.11.1.3 EhCache 2.x**

&emsp;&emsp;如果可以在类路径的根目录中找到名为ehcache.xml的文件，则使用EhCache 2.x. 如果找到EhCache 2.x，则使用spring-boot-starter-cache“Starter”提供的EhCacheCacheManager来引导缓存管理器。 还可以提供备用配置文件，如以下示例所示：

``` 
spring.cache.ehcache.config=classpath:config/another-config.xml
```

**4.11.1.4 Hazelcast**

&emsp;&emsp;Spring Boot对Hazelcast有一般支持。 如果已自动配置HazelcastInstance，则会自动将其包装在CacheManager中。

**4.11.1.5 Infinispan**

&emsp;&emsp;Infinispan没有默认配置文件位置，因此必须明确指定。 否则，使用默认引导程序。

``` 
spring.cache.infinispan.config=infinispan.xml
```

&emsp;&emsp;可以通过设置spring.cache.cache-names属性在启动时创建缓存。 如果定义了自定义ConfigurationBuilder bean，则它用于自定义缓存。

>Infinispan在Spring Boot中的支持仅限于嵌入式模式，非常基础。 如果你想要更多选项，你应该使用官方的Infinispan Spring Boot启动器。 有关更多详细信息，请参阅Infinispan的文档.

**4.11.1.6 Couchbase**

&emsp;&emsp;如果Couchbase Java客户端和couchbase-spring-cache实现可用且配置了Couchbase，则会自动配置CouchbaseCacheManager。 也可以通过设置spring.cache.cache-names属性在启动时创建其他缓存。 这些缓存在自动配置的Bucket上运行。 您还可以使用自定义程序在另一个Bucket上创建其他缓存。 假设您需要在“主”Bucket和一个（cache3）缓存上使用两个缓存（cache1和cache2），并在“另一个”Bucket上生成2秒的自定义时间。 您可以通过配置创建前两个缓存，如下所示：

``` 
spring.cache.cache-names=cache1,cache2
```

&emsp;&emsp;然后，您可以定义一个@Configuration类来配置额外的Bucket和cache3缓存，如下所示：

``` 
@Configuration
public class CouchbaseCacheConfiguration {

	private final Cluster cluster;

	public CouchbaseCacheConfiguration(Cluster cluster) {
		this.cluster = cluster;
	}

	@Bean
	public Bucket anotherBucket() {
		return this.cluster.openBucket("another", "secret");
	}

	@Bean
	public CacheManagerCustomizer<CouchbaseCacheManager> cacheManagerCustomizer() {
		return c -> {
			c.prepareCache("cache3", CacheBuilder.newInstance(anotherBucket())
					.withExpiration(2));
		};
	}

}
```

&emsp;&emsp;此示例配置重用通过自动配置创建的群集。

**4.11.1.7 Redis**

&emsp;&emsp;如果Redis可用并已配置，则会自动配置RedisCacheManager。 通过设置spring.cache.cache-names属性可以在启动时创建其他缓存，并且可以使用spring.cache.redis.*属性配置缓存默认值。 例如，以下配置创建cache1和cache2缓存，其生存时间为10分钟：

``` 
spring.cache.cache-names=cache1,cache2
spring.cache.redis.time-to-live=600000
```

>默认情况下，会添加一个键前缀，这样，如果两个单独的缓存使用相同的键，则Redis没有重叠键，也不能返回无效值。 如果您创建自己的RedisCacheManager，我们强烈建议您启用此设置.

&emsp;
>您可以通过添加自己的RedisCacheConfiguration @Bean来完全控制配置。 如果您正在寻找自定义序列化策略，这可能很有用.

**4.11.1.8 Caffeine**

&emsp;&emsp;Caffeine是Java 8重写的Guava缓存，取代了对Guava的支持。 如果存在Caffeine，则会自动配置CaffeineCacheManager（由spring-boot-starter-cache“Starter”提供）。 可以通过设置spring.cache.cache-names属性在启动时创建缓存，并且可以通过以下之一（按指示的顺序）自定义缓存：

1. 由spring.cache.caffeine.spec定义的缓存规范
2. 定义了com.github.benmanes.caffeine.cache.CaffeineSpec bean
3. 定义了com.github.benmanes.caffeine.cache.Caffeine bean


例如，以下配置创建cache1和cache2缓存，最大大小为500，生存时间为10分钟

``` 
spring.cache.cache-names=cache1,cache2
spring.cache.caffeine.spec=maximumSize=500,expireAfterAccess=600s
```

&emsp;&emsp;如果定义了com.github.benmanes.caffeine.cache.CacheLoader bean，它将自动与CaffeineCacheManager关联。 由于CacheLoader将与缓存管理器管理的所有缓存相关联，因此必须将其定义为CacheLoader &lt;Object，Object&gt;。 自动配置忽略任何其他泛型类型。

**4.11.1.9 Simple**

&emsp;&emsp;如果找不到其他提供程序，则配置使用ConcurrentHashMap作为缓存存储的简单实现。 如果应用程序中不存在缓存库，则这是默认值。 默认情况下，会根据需要创建高速缓存，但您可以通过设置cache-names属性来限制可用高速缓存的列表。 例如，如果只需要cache1和cache2缓存，请按如下所示设置cache-names属性：

``` 
spring.cache.cache-names=cache1,cache2
```

&emsp;&emsp;如果这样做并且您的应用程序使用未列出的缓存，则在需要缓存时它会在运行时失败，但在启动时则不会。 这类似于“real”缓存提供程序在使用未声明的缓存时的行为方式。

**4.11.1.10 None**

&emsp;&emsp;当配置中存在@EnableCaching时，也需要合适的缓存配置。 如果需要在某些环境中完全禁用缓存，请将缓存类型强制为none以使用no-op实现，如以下示例所示：

``` 
spring.cache.type=none
```

## **4.12 消息**

&emsp;&emsp;Spring Framework为与消息传递系统的集成提供了广泛的支持，从使用JmsTemplate的JMS API的简化使用到异步接收消息的完整基础结构。 Spring AMQP为高级消息队列协议提供了类似的功能集。 Spring Boot还为RabbitTemplate和RabbitMQ提供自动配置选项。 Spring WebSocket本身包含对STOMP消息传递的支持，Spring Boot通过启动器和少量自动配置支持它。 Spring Boot也支持Apache Kafka。

### **4.12.1 JMS**

&emsp;&emsp;javax.jms.ConnectionFactory接口提供了一种创建javax.jms.Connection的标准方法，用于与JMS代理进行交互。 虽然Spring需要一个ConnectionFactory来与JMS一起工作，但是你通常不需要自己直接使用它，而是可以依赖于更高级别的消息传递抽象。 （有关详细信息，请参阅Spring Framework参考文档的相关部分。）Spring Boot还会自动配置发送和接收消息所需的基础结构。

**4.12.1.1 ActiveMQ支持**

&emsp;&emsp;当ActiveMQ在类路径上可用时，Spring Boot也可以配置ConnectionFactory。 如果代理存在，则会自动启动并配置嵌入式代理（前提是未通过配置指定代理URL）。

>如果使用spring-boot-starter-activemq，则提供连接或嵌入ActiveMQ实例的必要依赖项，以及与JMS集成的Spring基础结构.

&emsp;&emsp;ActiveMQ配置由spring.activemq.*中的外部配置属性控制。 例如，您可以在application.properties中声明以下部分：

``` 
spring.activemq.broker-url=tcp://192.168.1.210:9876
spring.activemq.user=admin
spring.activemq.password=secret
```

&emsp;&emsp;默认情况下，CachingConnectionFactory使用合理设置包装本机ConnectionFactory，您可以通过spring.jms.*中的外部配置属性控制这些设置：

``` 
spring.jms.cache.session-cache-size=5
```

&emsp;&emsp;如果您更愿意使用本机池，则可以通过向org.messaginghub:pooled-jms添加依赖项并相应地配置JmsPoolConnectionFactory来实现，如以下示例所示：

``` 
spring.activemq.pool.enabled=true
spring.activemq.pool.max-connections=50
```

>有关更多支持的选项，请参阅ActiveMQProperties。 您还可以注册实现ActiveMQConnectionFactoryCustomizer的任意数量的bean，以进行更高级的自定义.

&emsp;&emsp;默认情况下，ActiveMQ会创建一个目标（如果它尚不存在），以便根据提供的名称解析目标。

**4.12.1.2 Artemis支持**

&emsp;&emsp;Spring Boot可以在检测到Artemis在类路径上可用时自动配置ConnectionFactory。 如果代理存在，则会自动启动并配置嵌入式代理（除非已明确设置mode属性）。 嵌入支持的模式（明确表示需要嵌入式代理，如果代理在类路径上不可用则发生错误）和本机（使用netty传输协议连接到代理）。 配置后者后，Spring Boot会使用默认设置配置连接到本地计算机上运行的代理的ConnectionFactory。

>如果使用spring-boot-starter-artemis，则会提供连接到现有Artemis实例的必要依赖项，以及与JMS集成的Spring基础结构。 将org.apache.activemq:artemis-jms-server添加到您的应用程序可让您使用嵌入模式.

&emsp;&emsp;Artemis配置由spring.artemis.*中的外部配置属性控制。 例如，您可以在application.properties中声明以下部分：

``` 
spring.artemis.mode=native
spring.artemis.host=192.168.1.210
spring.artemis.port=9876
spring.artemis.user=admin
spring.artemis.password=secret
```

&emsp;&emsp;嵌入代理时，您可以选择是否要启用持久性并列出应该可用的目标。 可以将这些指定为以逗号分隔的列表，以使用默认选项创建它们，也可以定义类型为org.apache.activemq.artemis.jms.server.config.JMSQueueConfiguration或org.apache.activemq的bean。 artemis.jms.server.config.TopicConfiguration，分别用于高级队列和主题配置。

&emsp;&emsp;默认情况下，CachingConnectionFactory使用合理设置包装本机ConnectionFactory，您可以通过spring.jms.*中的外部配置属性控制这些设置：

``` 
spring.jms.cache.session-cache-size=5
```

&emsp;&emsp;如果您更愿意使用本机池，则可以通过向org.messaginghub:pooled-jms添加依赖项并相应地配置JmsPoolConnectionFactory来实现，如以下示例所示：

``` 
spring.artemis.pool.enabled=true
spring.artemis.pool.max-connections=50
```

&emsp;&emsp;有关更多支持的选项，请参阅ArtemisProperties。

&emsp;&emsp;不涉及JNDI查找，并使用Artemis配置中的name属性或通过配置提供的名称来解析目标名称。

**4.12.1.3 使用JNDI ConnectionFactory**

&emsp;&emsp;如果您在应用程序服务器中运行应用程序，Spring Boot会尝试使用JNDI找到JMS ConnectionFactory。 默认情况下，将检查java:/JmsXA和java:/XAConnectionFactory位置。 如果需要指定备用位置，可以使用spring.jms.jndi-name属性，如以下示例所示：

``` 
spring.jms.jndi-name=java:/MyConnectionFactory
```

**4.12.1.4 发送消息**

&emsp;&emsp;Spring的JmsTemplate是自动配置的，你可以直接将它自动装入自己的bean中，如下例所示：

``` 
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jms.core.JmsTemplate;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final JmsTemplate jmsTemplate;

	@Autowired
	public MyBean(JmsTemplate jmsTemplate) {
		this.jmsTemplate = jmsTemplate;
	}

	// ...

}
```

>可以以类似的方式注入JmsMessagingTemplate。 如果定义了DestinationResolver或MessageConverter bean，它将自动关联到自动配置的JmsTemplate.

**4.12.1.5 接收消息**

&emsp;&emsp;当存在JMS基础结构时，可以使用@JmsListener对任何bean进行批注以创建侦听器端点。 如果未定义JmsListenerContainerFactory，则会自动配置默认值。 如果定义了DestinationResolver或MessageConverter bean，它将自动关联到默认工厂。

&emsp;&emsp;默认情况下，默认工厂是事务性的。 如果您在存在JtaTransactionManager的基础结构中运行，则默认情况下它与侦听器容器相关联。 如果不是，则启用sessionTransacted标志。 在后一种情况下，您可以通过在侦听器方法（或其委托）上添加@Transactional，将本地数据存储事务与传入消息的处理相关联。 这确保了在本地事务完成后确认传入消息。 这还包括发送已在同一JMS会话上执行的响应消息。

&emsp;&emsp;以下组件在someQueue目标上创建一个侦听器端点：

``` 
@Component
public class MyBean {

	@JmsListener(destination = "someQueue")
	public void processMessage(String content) {
		// ...
	}

}
```

>有关更多详细信息，请参阅@EnableJms的Javadoc.

&emsp;&emsp;如果需要创建更多JmsListenerContainerFactory实例，或者如果要覆盖缺省值，Spring Boot会提供一个DefaultJmsListenerContainerFactoryConfigurer，您可以使用它来初始化DefaultJmsListenerContainerFactory，其设置与自动配置的设置相同。

例如，以下示例公开了另一个使用特定MessageConverter的工厂：

``` 
@Configuration
static class JmsConfiguration {

	@Bean
	public DefaultJmsListenerContainerFactory myFactory(
			DefaultJmsListenerContainerFactoryConfigurer configurer) {
		DefaultJmsListenerContainerFactory factory =
				new DefaultJmsListenerContainerFactory();
		configurer.configure(factory, connectionFactory());
		factory.setMessageConverter(myMessageConverter());
		return factory;
	}

}
```

&emsp;&emsp;然后您可以在任何@JmsListener-annotated方法中使用工厂，如下所示：

``` 
@Component
public class MyBean {

	@JmsListener(destination = "someQueue", containerFactory="myFactory")
	public void processMessage(String content) {
		// ...
	}

}
```

### **4.12.2 AMQP**

&emsp;&emsp;高级消息队列协议（AMQP）是面向消息的中间件的平台中立的线级协议。 Spring AMQP项目将核心Spring概念应用于基于AMQP的消息传递解决方案的开发。 Spring Boot为通过RabbitMQ使用AMQP提供了一些便利，包括spring-boot-starter-amqp的“Starter”。

**4.12.2.1 RabbitMQ支持**

&emsp;&emsp;RabbitMQ是一个基于AMQP协议的轻量级，可靠，可扩展且可移植的消息代理。 Spring使用RabbitMQ通过AMQP协议进行通信。

&emsp;&emsp;RabbitMQ配置由spring.rabbitmq.*中的外部配置属性控制。 例如，您可以在application.properties中声明以下部分：

``` 
spring.rabbitmq.host=localhost
spring.rabbitmq.port=5672
spring.rabbitmq.username=admin
spring.rabbitmq.password=secret
```

&emsp;&emsp;如果上下文中存在ConnectionNameStrategy bean，它将自动用于命名由自动配置的ConnectionFactory创建的连接。 有关更多支持的选项，请参阅RabbitProperties。

>有关详细信息，请参阅了解RabbitMQ, AMQP使用的协议。

**4.12.2.2 发送消息**

&emsp;&emsp;Spring的AmqpTemplate和AmqpAdmin是自动配置的，您可以将它们直接自动装入自己的bean中，如下例所示：

``` 
import org.springframework.amqp.core.AmqpAdmin;
import org.springframework.amqp.core.AmqpTemplate;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final AmqpAdmin amqpAdmin;
	private final AmqpTemplate amqpTemplate;

	@Autowired
	public MyBean(AmqpAdmin amqpAdmin, AmqpTemplate amqpTemplate) {
		this.amqpAdmin = amqpAdmin;
		this.amqpTemplate = amqpTemplate;
	}

	// ...

}
```

>RabbitMessagingTemplate可以以类似的方式注入。 如果定义了MessageConverter bean，它将自动关联到自动配置的AmqpTemplate.

&emsp;&emsp;如有必要，任何定义为bean的org.springframework.amqp.core.Queue都会自动用于在RabbitMQ实例上声明相应的队列。

&emsp;&emsp;要重试操作，可以在AmqpTemplate上启用重试（例如，在代理连接丢失的情况下）：

``` 
spring.rabbitmq.template.retry.enabled=true
spring.rabbitmq.template.retry.initial-interval=2s
```

&emsp;&emsp;默认情况下禁用重试。 您还可以通过声明RabbitRetryTemplateCustomizer bean以编程方式自定义RetryTemplate。

**4.12.2.3 接收消息**

&emsp;&emsp;当Rabbit基础结构存在时，可以使用@RabbitListener注释任何bean以创建侦听器端点。 如果未定义RabbitListenerContainerFactory，则会自动配置默认的SimpleRabbitListenerContainerFactory，您可以使用spring.rabbitmq.listener.type属性切换到直接容器。 如果定义了MessageConverter或MessageRecoverer bean，它将自动与默认工厂关联。

&emsp;&emsp;以下示例组件在someQueue队列上创建一个侦听器端点：

``` 
@Component
public class MyBean {

	@RabbitListener(queues = "someQueue")
	public void processMessage(String content) {
		// ...
	}

}
```

>有关更多详细信息，请参阅@EnableRabbit的Javadoc.

&emsp;&emsp;如果您需要创建更多RabbitListenerContainerFactory实例或者如果要覆盖默认值，Spring Boot提供了一个SimpleRabbitListenerContainerFactoryConfigurer和一个DirectRabbitListenerContainerFactoryConfigurer，您可以使用它来初始化SimpleRabbitListenerContainerFactory和DirectRabbitListenerContainerFactory，其设置与自动配置使用的工厂相同。

>您选择的容器类型无关紧要。 这两个bean通过自动配置公开.

例如，以下配置类公开了另一个使用特定MessageConverter的工厂：

``` 
@Configuration
static class RabbitConfiguration {

	@Bean
	public SimpleRabbitListenerContainerFactory myFactory(
			SimpleRabbitListenerContainerFactoryConfigurer configurer) {
		SimpleRabbitListenerContainerFactory factory =
				new SimpleRabbitListenerContainerFactory();
		configurer.configure(factory, connectionFactory);
		factory.setMessageConverter(myMessageConverter());
		return factory;
	}

}
```

&emsp;&emsp;然后您可以在任何@RabbitListener注解方法中使用工厂，如下所示：

``` 
@Component
public class MyBean {

	@RabbitListener(queues = "someQueue", containerFactory="myFactory")
	public void processMessage(String content) {
		// ...
	}

}
```

&emsp;&emsp;您可以启用重试来处理侦听器抛出异常的情况。 默认情况下，使用RejectAndDontRequeueRecoverer，但您可以定义自己的MessageRecoverer。 当重试耗尽时，如果代理配置了这样做，则拒绝该消息并将其丢弃或路由到死信交换。 默认情况下，禁用重试。 您还可以通过声明RabbitRetryTemplateCustomizer bean以编程方式自定义RetryTemplate。

>默认情况下，如果禁用重试并且侦听器抛出异常，则会无限期地重试传递。 您可以通过两种方式修改此行为：将thedefaultRequeueRejected属性设置为false，以便尝试零重新传递或抛出AmqpRejectAndDontRequeueException以指示应拒绝该消息。 后者是启用重试并且达到最大传递尝试次数时使用的机制.

### **4.12.3 Apache Kafka**

&emsp;&emsp;通过提供spring-kafka项目的自动配置来支持Apache Kafka。

&emsp;&emsp;Kafka配置由spring.kafka.*中的外部配置属性控制。 例如，您可以在application.properties中声明以下部分：

``` 
spring.kafka.bootstrap-servers=localhost:9092
spring.kafka.consumer.group-id=myGroup
```

>要在启动时创建topic，请添加NewTopic类型的Bean。 如果topic已存在，则忽略该bean.

&emsp;&emsp;有关更多支持的选项，请参阅KafkaProperties。

**4.12.3.1 发送消息**

&emsp;&emsp;Spring的KafkaTemplate是自动配置的，您可以直接在自己的bean中自动装配它，如以下示例所示：

``` 
@Component
public class MyBean {

	private final KafkaTemplate kafkaTemplate;

	@Autowired
	public MyBean(KafkaTemplate kafkaTemplate) {
		this.kafkaTemplate = kafkaTemplate;
	}

	// ...

}
```

>如果定义了属性spring.kafka.producer.transaction-id-prefix，则会自动配置KafkaTransactionManager。 此外，如果定义了RecordMessageConverter bean，它将自动关联到自动配置的KafkaTemplate.

**4.12.3.2 接收消息**

&emsp;&emsp;当存在Apache Kafka基础结构时，可以使用@KafkaListener注释任何bean以创建侦听器端点。 如果未定义KafkaListenerContainerFactory，则会使用spring.kafka.listener.*中定义的键自动配置默认值。

&emsp;&emsp;以下组件在someTopic topics上创建一个侦听器端点：

``` 
@Component
public class MyBean {

	@KafkaListener(topics = "someTopic")
	public void processMessage(String content) {
		// ...
	}

}
```

&emsp;&emsp;如果定义了KafkaTransactionManager bean，它将自动关联到容器工厂。 同样，如果定义了RecordMessageConverter，ErrorHandler或AfterRollbackProcessor bean，它将自动关联到默认工厂。

>自定义ChainedKafkaTransactionManager必须标记为@Primary，因为它通常引用自动配置的KafkaTransactionManagerbean.

**4.12.3.3 Kafka流**

&emsp;&emsp;Spring for Apache Kafka提供了一个工厂bean来创建StreamsBuilder对象并管理其流的生命周期。 只要kafka-streams在类路径上并且通过@EnableKafkaStreams注释启用Kafka Streams，Spring Boot就会自动配置所需的KafkaStreamsConfiguration bean。

&emsp;&emsp;启用Kafka Streams意味着必须设置应用程序ID和引导服务器。 可以使用spring.kafka.streams.application-id配置前者，如果未设置则默认为spring.application.name。 后者可以全局设置或专门为流而重写。

&emsp;&emsp;使用专用属性可以使用其他几个属性; 可以使用spring.kafka.streams.properties命名空间设置其他任意Kafka属性。 有关更多信息，另请参见第4.11.3.4节“其他Kafka属性”。

&emsp;&emsp;要使用工厂bean，只需将StreamsBuilder连接到@Bean，如以下示例所示：

``` 
@Configuration
@EnableKafkaStreams
static class KafkaStreamsExampleConfiguration {

	@Bean
	public KStream<Integer, String> kStream(StreamsBuilder streamsBuilder) {
		KStream<Integer, String> stream = streamsBuilder.stream("ks1In");
		stream.map((k, v) -> new KeyValue<>(k, v.toUpperCase())).to("ks1Out",
				Produced.with(Serdes.Integer(), new JsonSerde<>()));
		return stream;
	}

}
```

&emsp;&emsp;默认情况下，由其创建的StreamBuilder对象管理的流将自动启动。 您可以使用spring.kafka.streams.auto-startup属性自定义此行为。

**4.12.3.4 其他Kafka属性**

&emsp;&emsp;自动配置支持的属性显示在附录A，常见应用程序属性中。 请注意，在大多数情况下，这些属性（连字符或驼峰式）直接映射到Apache Kafka点状属性。 有关详细信息，请参阅Apache Kafka文档。

&emsp;&emsp;这些属性中的前几个适用于所有组件（producers, consumers, admins, 和 streams），但如果您希望使用不同的值，则可以在组件级别指定。 Apache Kafka指定重要性为HIGH，MEDIUM或LOW的属性。 Spring Boot自动配置支持所有HIGH重要性属性，一些选定的MEDIUM和LOW属性，以及任何没有默认值的属性。

&emsp;&emsp;只有Kafka支持的属性的子集可以直接通过KafkaProperties类获得。 如果您希望使用不直接支持的其他属性配置生产者或使用者，请使用以下属性：

``` 
spring.kafka.properties.prop.one=first
spring.kafka.admin.properties.prop.two=second
spring.kafka.consumer.properties.prop.three=third
spring.kafka.producer.properties.prop.four=fourth
spring.kafka.streams.properties.prop.five=fifth
```

&emsp;&emsp;这将常见的prop.one Kafka属性设置为第一个（适用于producers, consumers 和 admins），prop.two管理员属性为第二个，prop.three消费者属性为第三个，prop.four生产者属性为第四个和prop.five streams属性为第五。

&emsp;&emsp;您还可以按如下方式配置Spring Kafka JsonDeserializer：

``` 
spring.kafka.consumer.value-deserializer=org.springframework.kafka.support.serializer.JsonDeserializer
spring.kafka.consumer.properties.spring.json.value.default.type=com.example.Invoice
spring.kafka.consumer.properties.spring.json.trusted.packages=com.example,org.acme
```

&emsp;&emsp;同样，您可以禁用JSONSerializer在标头中发送类型信息的默认行为：

``` 
spring.kafka.producer.value-serializer=org.springframework.kafka.support.serializer.JsonSerializer
spring.kafka.producer.properties.spring.json.add.type.headers=false
```

>以这种方式设置的属性将覆盖Spring Boot明确支持的任何配置项.

## **4.13 使用RestTemplate调用REST服务**

&emsp;&emsp;如果需要从应用程序调用远程REST服务，可以使用Spring Framework的RestTemplate类。 由于RestTemplate实例在使用之前通常需要进行自定义，因此Spring Boot不提供任何单个自动配置的RestTemplate bean。 但是，它会自动配置RestTemplateBuilder，可用于在需要时创建RestTemplate实例。 自动配置的RestTemplateBuilder确保将合理的HttpMessageConverters应用于RestTemplate实例。

&emsp;&emsp;以下代码显示了一个典型示例：

``` 
@Service
public class MyService {

	private final RestTemplate restTemplate;

	public MyService(RestTemplateBuilder restTemplateBuilder) {
		this.restTemplate = restTemplateBuilder.build();
	}

	public Details someRestCall(String name) {
		return this.restTemplate.getForObject("/{name}/details", Details.class, name);
	}

}
```

>RestTemplateBuilder包含许多可用于快速配置RestTemplate的有用方法。 例如，要添加BASIC auth支持，可以使用builder.basicAuthentication("user","password").build()

### **4.13.1 自定义RestTemplate**

&emsp;&emsp;RestTemplate自定义有三种主要方法，具体取决于您希望自定义应用的广泛程度。

&emsp;&emsp;要使任何自定义的范围尽可能窄，请注入自动配置的RestTemplateBuilder，然后根据需要调用其方法。 每个方法调用都返回一个新的RestTemplateBuilder实例，因此自定义只会影响构建器的这种使用。

&emsp;&emsp;要进行应用程序范围的附加自定义，请使用RestTemplateCustomizer bean。 所有这些bean都自动注册到自动配置的RestTemplateBuilder，并应用于使用它构建的任何模板。

&emsp;&emsp;以下示例显示了一个自定义程序，它为除192.168.0.5之外的所有主机配置代理的使用：

``` 
static class ProxyCustomizer implements RestTemplateCustomizer {

	@Override
	public void customize(RestTemplate restTemplate) {
		HttpHost proxy = new HttpHost("proxy.example.com");
		HttpClient httpClient = HttpClientBuilder.create()
				.setRoutePlanner(new DefaultProxyRoutePlanner(proxy) {

					@Override
					public HttpHost determineProxy(HttpHost target,
							HttpRequest request, HttpContext context)
							throws HttpException {
						if (target.getHostName().equals("192.168.0.5")) {
							return null;
						}
						return super.determineProxy(target, request, context);
					}

				}).build();
		restTemplate.setRequestFactory(
				new HttpComponentsClientHttpRequestFactory(httpClient));
	}

}
```

&emsp;&emsp;最后，最极端（也很少使用）的选项是创建自己的RestTemplateBuilder bean。 这样做会关闭RestTemplateBuilder的自动配置，并防止使用任何RestTemplateCustomizer bean。

## **4.14 使用WebClient调用REST服务**

&emsp;&emsp;如果类路径上有SpringWebFlux，还可以选择使用WebClient调用远程REST服务。与RestTemplate相比，这个客户端具有更多的功能感和完全的反应性。您可以在SpringFrameworkdocs中的专用部分中了解更多关于WebClient的信息。

&emsp;&emsp;Spring Boot为您创建并预配置WebClient.Builder; 强烈建议将其注入组件并使用它来创建WebClient实例。 Spring Boot正在配置该构建器以共享HTTP资源，以与服务器相同的方式反映编解码器设置（请参阅WebFlux HTTP编解码器自动配置）等。

&emsp;&emsp;以下代码显示了一个典型示例：

``` 
@Service
public class MyService {

	private final WebClient webClient;

	public MyService(WebClient.Builder webClientBuilder) {
		this.webClient = webClientBuilder.baseUrl("http://example.org").build();
	}

	public Mono<Details> someRestCall(String name) {
		return this.webClient.get().uri("/{name}/details", name)
						.retrieve().bodyToMono(Details.class);
	}

}
```

### **4.14.1 运行时WebClient**

&emsp;&emsp;Spring Boot将自动检测用于驱动WebClient的ClientHttpConnector，具体取决于应用程序类路径上可用的库。 目前，支持Reactor Netty和Jetty RS客户端。

&emsp;&emsp;默认情况下spring-boot-starter-webflux启动程序依赖于io.projectreactor.netty:reactor-netty，它带来了服务器和客户端实现。 如果您选择将Jetty用作反应式服务器，则应在Jetty Reactive HTTP客户端库org.eclipse.jetty:jetty-reactive-httpclient上添加依赖项。 对服务器和客户端使用相同的技术具有优势，因为它将自动在客户端和服务器之间共享HTTP资源。

&emsp;&emsp;开发人员可以通过提供自定义的ReactorResourceFactory或JettyResourceFactory bean来覆盖Jetty和Reactor Netty的资源配置 - 这将应用于客户端和服务器。

&emsp;&emsp;如果您希望覆盖客户端的该选项，则可以定义自己的ClientHttpConnector bean并完全控制客户端配置。

&emsp;&emsp;您可以在Spring Framework参考文档中了解有关WebClient配置选项的更多信息。

### **4.14.2 自定义WebClient**

&emsp;&emsp;WebClient自定义有三种主要方法，具体取决于您希望自定义应用的广泛程度。

&emsp;&emsp;要使任何自定义的范围尽可能窄，请注入自动配置的WebClient.Builder，然后根据需要调用其方法。 WebClient.Builder实例是有状态的：构建器上的任何更改都会反映在随后使用它创建的所有客户端中。 如果要使用相同的构建器创建多个客户端，还可以考虑使用WebClient.Builder other = builder.clone();克隆构建器。

&emsp;&emsp;最后，您可以回退到原始API并使用WebClient.create()。 在这种情况下，不应用自动配置或WebClientCustomizer。

## **4.15 校验**

&emsp;&emsp;只要JSR-303实现（例如Hibernate验证器）在类路径上，就会自动启用Bean Validation 1.1支持的方法验证功能。 这允许bean方法在其参数和/或返回值上使用javax.validation约束进行注释。 具有这种带注释方法的目标类需要在类型级别使用@Validated注释进行注释，以便搜索内联约束注释的方法。

例如，以下服务触发第一个参数的验证，确保其大小在8到10之间：

``` 
@Service
@Validated
public class MyBean {

	public Archive findByCodeAndAuthor(@Size(min = 8, max = 10) String code,
			Author author) {
		...
	}

}
```

## **4.16 发送邮件**

&emsp;&emsp;Spring Framework提供了一个使用JavaMailSender接口发送电子邮件的简单抽象，Spring Boot为它提供了自动配置以及启动器模块。

>有关如何使用JavaMailSender的详细说明，请参阅参考文档.

&emsp;&emsp;如果spring.mail.host和相关库（由spring-boot-starter-mail定义）可用，则创建默认JavaMailSender（如果不存在）。 可以通过spring.mail命名空间中的配置项进一步自定义发件人。 有关详细信息，请参阅MailProperties。

&emsp;&emsp;特别是，某些默认超时值是无限的，您可能希望更改它以避免线程被无响应的邮件服务器阻塞，如以下示例所示：

``` 
spring.mail.properties.mail.smtp.connectiontimeout=5000
spring.mail.properties.mail.smtp.timeout=3000
spring.mail.properties.mail.smtp.writetimeout=5000
```

&emsp;&emsp;也可以使用JNDI中的现有会话配置JavaMailSender：

``` 
spring.mail.jndi-name=mail/Session
```

&emsp;&emsp;设置jndi-name时，它优先于所有其他与Session相关的设置。

## **4.17 使用JTA的分布式事务**

&emsp;&emsp;Spring Boot通过使用Atomikos或Bitronix嵌入式事务管理器支持跨多个XA资源的分布式JTA事务。 部署到合适的Java EE Application Server时，也支持JTA事务。

&emsp;&emsp;检测到JTA环境时，Spring的JtaTransactionManager用于管理事务。 自动配置的JMS，DataSource和JPA bean已升级为支持XA事务。 您可以使用标准的Spring惯用语（例如@Transactional）来参与分布式事务。 如果您在JTA环境中并且仍想使用本地事务，则可以将spring.jta.enabled属性设置为false以禁用JTA自动配置。

### **4.17.1 使用Atomikos事务管理器**

&emsp;&emsp;Atomikos是一个流行的开源事务管理器，可以嵌入到Spring Boot应用程序中。 您可以使用spring-boot-starter-jta-atomikos Starter来获取相应的Atomikos库。 Spring Boot自动配置Atomikos并确保将适当的依赖设置应用于Spring bean，以便正确启动和关闭顺序。

&emsp;&emsp;默认情况下，Atomikos事务日志将写入应用程序主目录（应用程序jar文件所在的目录）中的transaction-logs目录。 您可以通过在application.properties文件中设置spring.jta.log-dir属性来自定义此目录的位置。 以spring.jta.atomikos.properties开头的属性也可用于自定义Atomikos UserTransactionServiceImp。 有关完整的详细信息，请参阅AtomikosProperties Javadoc。

>为确保多个事务管理器可以安全地协调相同的资源管理器，必须使用唯一ID配置每个Atomikos实例。 默认情况下，此ID是运行Atomikos的计算机的IP地址。 要确保生产中的唯一性，您应该为应用程序的每个实例配置spring.jta.transaction-manager-id属性，并使用不同的值.

### **4.17.2 使用Bitronix事务管理器**

&emsp;&emsp;Bitronix是一种流行的开源JTA事务管理器实现。 您可以使用spring-boot-starter-jta-bitronix starter为您的项目添加适当的Bitronix依赖项。 与Atomikos一样，Spring Boot会自动配置Bitronix并对bean进行后处理，以确保启动和关闭顺序正确。

&emsp;&emsp;默认情况下，Bitronix事务日志文件（part1.btm和part2.btm）将写入应用程序主目录中的transaction-logs目录。 您可以通过设置spring.jta.log-dir属性来自定义此目录的位置。 以spring.jta.bitronix.properties开头的属性也绑定到bitronix.tm.Configuration bean，允许完全自定义。 有关详细信息，请参阅Bitronix文档。

>为确保多个事务管理器可以安全地协调相同的资源管理器，必须为每个Bitronix实例配置唯一ID。 默认情况下，此ID是运行Bitronix的计算机的IP地址。 要确保生产中的唯一性，应为应用程序的每个实例配置spring.jta.transaction-manager-id属性，并使用不同的值。

### **4.17.3 使用Java EE托管事务管理器**

&emsp;&emsp;如果将Spring Boot应用程序打包为war或ear文件并将其部署到Java EE应用程序服务器，则可以使用应用程序服务器的内置事务管理器。 Spring Boot尝试通过查看常见的JNDI位置（java:comp/UserTransaction，java:comp/TransactionManager等）来自动配置事务管理器。 如果使用应用程序服务器提供的事务服务，通常还需要确保所有资源都由服务器管理并通过JNDI公开。 Spring Boot尝试通过在JNDI路径（java:/JmsXA或java:/XAConnectionFactory）中查找ConnectionFactory来自动配置JMS，并且可以使用spring.datasource.jndi-name属性来配置DataSource。

### **4.17.4 混合XA和非XA JMS连接**

&emsp;&emsp;使用JTA时，主JMS ConnectionFactory bean可识别XA并参与分布式事务。 在某些情况下，您可能希望使用非XA ConnectionFactory处理某些JMS消息。 例如，您的JMS处理逻辑可能需要比XA超时更长的时间。

&emsp;&emsp;如果要使用非XA ConnectionFactory，可以注入nonXaJmsConnectionFactory bean而不是@Primary jmsConnectionFactory bean。 为了保持一致性，还使用bean别名xaJmsConnectionFactory提供了jmsConnectionFactory bean。

&emsp;&emsp;以下示例显示如何注入ConnectionFactory实例：

``` 
// Inject the primary (XA aware) ConnectionFactory
@Autowired
private ConnectionFactory defaultConnectionFactory;

// Inject the XA aware ConnectionFactory (uses the alias and injects the same as above)
@Autowired
@Qualifier("xaJmsConnectionFactory")
private ConnectionFactory xaConnectionFactory;

// Inject the non-XA aware ConnectionFactory
@Autowired
@Qualifier("nonXaJmsConnectionFactory")
private ConnectionFactory nonXaConnectionFactory;
```

### **4.17.5 支持替代嵌入式事务管理器**

&emsp;&emsp;XAConnectionFactoryWrapper和XADataSourceWrapper接口可用于支持备用嵌入式事务管理器。 接口负责包装XAConnectionFactory和XADataSource bean，并将它们公开为常规ConnectionFactory和DataSource bean，它们透明地注册分布式事务。 DataSource和JMS自动配置使用JTA变体，前提是您有一个JtaTransactionManager bean和在ApplicationContext中注册的相应XA包装bean。

&emsp;&emsp;BitronixXAConnectionFactoryWrapper和BitronixXADataSourceWrapper提供了如何编写XA包装器的很好示例。

## **4.18 Hazelcast**

&emsp;&emsp;如果Hazelcast位于类路径上并找到合适的配置，则Spring Boot会自动配置您可以在应用程序中注入的HazelcastInstance。

&emsp;&emsp;如果定义com.hazelcast.config.Config bean，Spring Boot会使用它。 如果您的配置定义了实例名称，Spring Boot会尝试查找现有实例，而不是创建新实例。

&emsp;&emsp;您还可以指定要通过配置使用的hazelcast.xml配置文件，如以下示例所示：

``` 
spring.hazelcast.config=classpath:config/my-hazelcast.xml
```

&emsp;&emsp;否则，Spring Boot会尝试从默认位置查找Hazelcast配置：工作目录中的hazelcast.xml或类路径的根目录。 我们还检查是否设置了hazelcast.config系统属性。 有关更多详细信息，请参阅Hazelcast文档。

&emsp;&emsp;如果类路径中存在hazelcast-client，则Spring Boot首先尝试通过检查以下配置选项来创建客户端：

- 存在com.hazelcast.client.config.ClientConfig bean。
- 由spring.hazelcast.config属性定义的配置文件。
- hazelcast.client.config系统属性的存在。
- 工作目录中或类路径根目录下的hazelcast-client.xml。

>Spring Boot还为Hazelcast提供了明确的缓存支持。 如果启用了缓存，HazelcastInstance将自动包装在CacheManagerimplementation中.

## **4.19 Quartz Scheduler**

&emsp;&emsp;Spring Boot提供了几种使用Quartz调度程序的便利，包括spring-boot-starter-quartz的“Starter”。 如果Quartz可用，则自动配置Scheduler（通过SchedulerFactoryBean抽象）。

&emsp;&emsp;自动选取以下类型的Bean并将其与Scheduler程序关联：

- JobDetail：定义一个特定的Job。 可以使用JobBuilder API构建JobDetail实例。
- Calendar
- Trigger：定义何时触发特定作业。


&emsp;&emsp;默认情况下，使用内存中的JobStore。 但是，如果应用程序中有DataSource bean，并且相应地配置了spring.quartz.job-store-type属性，则可以配置基于JDBC的存储，如以下示例所示：

``` 
spring.quartz.job-store-type=jdbc
```

&emsp;&emsp;使用JDBC存储时，可以在启动时初始化模式，如以下示例所示：

``` 
spring.quartz.jdbc.initialize-schema=always
```

>默认情况下，使用Quartz库提供的标准脚本检测并初始化数据库。 这些脚本删除现有表，在每次重启时删除所有触发器。 也可以通过设置spring.quartz.jdbc.schema属性来提供自定义脚本.

&emsp;&emsp;要让Quartz使用除应用程序主DataSource之外的DataSource，请声明一个DataSource bean，使用@QuartzDataSource注释其@Bean方法。 这样做可确保SchedulerFactoryBean和架构初始化都使用特定于Quartz的DataSource。

&emsp;&emsp;默认情况下，配置创建的作业不会覆盖已从永久性作业存储读取的已注册作业。 要启用覆盖现有作业定义，请设置spring.quartz.overwrite-existing-jobs属性。

&emsp;&emsp;Quartz Scheduler配置可以使用spring.quartz属性和SchedulerFactoryBeanCustomizer bean进行自定义，它们允许程序化的SchedulerFactoryBean自定义。 可以使用spring.quartz.properties.*定制高级Quartz配置属性。

>特别是，Executor bean与调度程序没有关联，因为Quartz提供了一种通过spring.quartz.properties配置调度程序的方法。 如果需要自定义任务执行程序，请考虑实现SchedulerFactoryBeanCustomizer.

&emsp;&emsp;Job可以定义setter以注入数据映射属性。 也可以以类似的方式注入常规bean，如以下示例所示：

``` 
public class SampleJob extends QuartzJobBean {

	private MyService myService;

	private String name;

	// Inject "MyService" bean
	public void setMyService(MyService myService) { ... }

	// Inject the "name" job data property
	public void setName(String name) { ... }

	@Override
	protected void executeInternal(JobExecutionContext context)
			throws JobExecutionException {
		...
	}

}
```

## **4.20 任务执行和调度**

&emsp;&emsp;在上下文中没有Executor bean的情况下，Spring Boot会自动配置一个具有合理默认值的ThreadPoolTaskExecutor，这些默认值可以自动与异步任务执行（@EnableAsync）和Spring MVC异步请求处理相关联。

>如果您在上下文中定义了自定义Executor，则常规任务执行（即@EnableAsync）将透明地使用它，但不会配置Spring MVC支持，因为它需要AsyncTaskExecutor实现（名为applicationTaskExecutor）。 根据您的目标安排，您可以将Executor更改为ThreadPoolTaskExecutor，或者定义包装自定义Executor的ThreadPoolTaskExecutor和AsyncConfigurer。 自动配置的TaskExecutorBuilder允许您轻松创建实例，以再现默认情况下自动配置的功能

&emsp;&emsp;线程池使用8个核心线程，可根据负载增长和缩小。 可以使用spring.task.execution命名空间对这些默认设置进行微调，如以下示例所示：

``` 
spring.task.execution.pool.max-threads=16
spring.task.execution.pool.queue-capacity=100
spring.task.execution.pool.keep-alive=10s
```

&emsp;&emsp;这会将线程池更改为使用有界队列，以便在队列满（100个任务）时，线程池增加到最多16个线程。 当线程在闲置10秒（而不是默认为60秒）时回收线程时，池的收缩会更加激进。

&emsp;&emsp;如果需要与计划任务执行（@EnableScheduling）相关联，还可以自动配置ThreadPoolTaskScheduler。 默认情况下，线程池使用一个线程，并且可以使用spring.task.scheduling命名空间对这些设置进行微调。

&emsp;&emsp;如果需要创建自定义执行程序或调度程序，则在上下文中可以使用TaskExecutorBuilder bean和TaskSchedulerBuilder bean。

## **4.21 Spring Integration**

&emsp;&emsp;Spring Boot提供了一些使用Spring Integration的便利，包括spring-boot-starter-integration的“Starter”。 Spring Integration提供了有关消息传递以及其他传输（如HTTP，TCP等）的抽象。 如果类路径上有Spring Integration，则通过@EnableIntegration批注对其进行初始化。

&emsp;&emsp;Spring Boot还配置了一些由于存在其他Spring Integration模块而触发的功能。 如果spring-integration-jmx也在类路径上，则消息处理统计信息将通过JMX发布。 如果spring-integration-jdbc可用，则可以在启动时创建默认数据库模式，如以下行所示：

``` 
spring.integration.jdbc.initialize-schema=always
```

&emsp;&emsp;有关更多详细信息，请参阅IntegrationAutoConfiguration和IntegrationProperties类。

&emsp;&emsp;默认情况下，如果存在Micrometer meterRegistry bean，则Micro Integration将管理Spring Integration指标。 如果您希望使用旧版Spring Integration度量标准，请将DefaultMetricsFactory bean添加到应用程序上下文中。

## **4.22 Spring Session**

&emsp;&emsp;Spring Boot为各种数据存储提供Spring Session自动配置。 构建Servlet Web应用程序时，可以自动配置以下存储：

- JDBC
- Redis
- Hazelcast
- MongoDB

&emsp;&emsp;构建响应式Web应用程序时，可以自动配置以下存储：

- Redis
- MongoDB

&emsp;&emsp;如果类路径上存在单个Spring Session模块，则Spring Boot会自动使用该存储实现。 如果您有多个实现，则必须选择要用于存储会话的StoreType。 例如，要使用JDBC作为后端存储，您可以按如下方式配置应用程序：

``` 
spring.session.store-type=jdbc
```

>您可以通过将store-type设置为none来禁用Spring Session.

&emsp;&emsp;每个存储都有特定的附加设置。 例如，可以为JDBC存储定制表的名称，如以下示例所示：

``` 
spring.session.jdbc.table-name=SESSIONS
```

&emsp;&emsp;要设置会话的超时，可以使用spring.session.timeout属性。 如果未设置该属性，则自动配置将回退到server.servlet.session.timeout的值。

## **4.23 JMX的监控和管理**

&emsp;&emsp;Java Management Extensions（JMX）提供了一种监视和管理应用程序的标准机制。 默认情况下，Spring Boot会创建一个ID为mbeanServer的MBeanServer bean，并公开使用Spring JMX注释（@ManagedResource，@ ManagedAttribute或@ManagedOperation）注释的任何bean。

&emsp;&emsp;如果您的平台提供标准MBeanServer，Spring Boot将使用它，并在必要时默认使用VM MBeanServer。 如果全部失败，将创建一个新的MBeanServer。

&emsp;&emsp;有关更多详细信息，请参阅JmxAutoConfiguration类。

## **4.23 测试**

&emsp;&emsp;Spring Boot提供了许多实用程序和注释来帮助您测试应用程序。 测试支持由两个模块提供：spring-boot-test包含核心项，spring-boot-test-autoconfigure支持测试的自动配置。

&emsp;&emsp;大多数开发人员使用spring-boot-starter-test的“Starter”，它导入Spring Boot测试模块以及JUnit，AssertJ，Hamcrest和许多其他有用的库。

### **4.24.1 测试范围依赖项**

&emsp;&emsp;spring-boot-starter-test“Starter”（在测试范围内）包含以下提供的库：

- JUnit：单元测试Java应用程序的事实上的标准。
- Spring Test和Spring Boot测试：Spring Boot应用程序的实用程序和集成测试支持。
- AssertJ：一个Stream的断言库。
- Hamcrest：匹配器对象库（也称为约束或谓词）。
- Mockito：一个Java模拟框架。
- JSONassert：JSON的断言库。
- JsonPath：JSON的XPath。

&emsp;&emsp;我们通常发现这些常用库在编写测试时很有用。 如果这些库不符合您的需求，您可以添加自己的其他测试依赖项。

### **4.24.2 测试Spring应用程序**

&emsp;&emsp;依赖注入的一个主要优点是它应该使您的代码更容易进行单元测试。 您可以使用new运算符实例化对象，甚至不涉及Spring。 您还可以使用模拟对象而不是真正的依赖项。

&emsp;&emsp;通常，您需要越过单元测试并开始集成测试（使用Spring ApplicationContext）。 能够在不需要部署应用程序或需要连接到其他基础架构的情况下执行集成测试非常有用。

&emsp;&emsp;Spring Framework包含一个用于此类集成测试的专用测试模块。 您可以直接向org.springframework声明一个依赖项：spring-test或使用spring-boot-starter-test“Starter”来传递它。

&emsp;&emsp;如果您之前没有使用过spring-test模块，那么首先应阅读Spring Framework参考文档的相关部分。

### **4.24.3 测试Spring Boot应用程序**

&emsp;&emsp;Spring Boot应用程序是一个Spring ApplicationContext，因此除了通常使用的Spring上下文之外，还没有什么特别的东西可以用来测试它。

>只有在使用SpringApplication创建Spring Boot的外部属性，日志记录和其他功能时，才会默认安装在上下文中.

&emsp;&emsp;Spring Boot提供了一个@SpringBootTest注释，当您需要Spring Boot功能时，它可以用作标准spring-test @ContextConfiguration注释的替代方法。 注释通过SpringApplication创建测试中使用的ApplicationContext来工作。 除了@SpringBootTest之外，还提供了许多其他注释来测试应用程序的更具体的切片。

>如果您使用的是JUnit 4，请不要忘记将@RunWith(SpringRunner.class)添加到测试中，否则将忽略注释。 如果您使用的是JUnit 5，则无需将等效的@ExtendWith(SpringExtension)添加为@SpringBootTest而另一个@ ...Test注释已经使用它进行了注释.

&emsp;&emsp;默认情况下，@ SpringBootTest不会启动服务器。 您可以使用@SpringBootTest的webEnvironment属性来进一步优化测试的运行方式：

- MOCK（默认）：加载Web ApplicationContext并提供模拟Web环境。 使用此批注时，不会启动嵌入式服务器。 如果类路径上没有Web环境，则此模式将透明地回退到创建常规非Web ApplicationContext。 它可以与@AutoConfigureMockMvc或@AutoConfigureWebTestClient结合使用，以进行基于模拟的Web应用程序测试。
- RANDOM_PORT：加载WebServerApplicationContext并提供真实的Web环境。 嵌入式服务器启动并在随机端口上侦听。
- DEFINED_PORT：加载WebServerApplicationContext并提供真实的Web环境。 嵌入式服务器启动并侦听定义的端口（来自您的application.properties）或默认端口8080。
- NONE：使用SpringApplication加载ApplicationContext，但不提供任何Web环境（模拟或其他）。

>如果您的测试是@Transactional，则默认情况下会在每个测试方法的末尾回滚事务。 但是，由于使用RANDOM_PORT或DEFINED_PORT这种安排隐式提供了一个真正的servlet环境，因此HTTP客户端和服务器在不同的线程中运行，因此在单独的事务中运行。 在这种情况下，在服务器上启动的任何事务都不会回滚.

&emsp;
>带有webEnvironment = WebEnvironment.RANDOM_PORT的@SpringBootTest也将在一个单独的随机端口上启动管理服务器，如果您的应用程序使用不同的管理服务器端口.

**4.24.3.1 检测Web应用程序类型**

&emsp;&emsp;如果Spring MVC可用，则配置基于MVC的常规应用程序上下文。 如果您只有Spring WebFlux，我们会检测到并配置基于WebFlux的应用程序上下文。

&emsp;&emsp;如果两者都存在，则Spring MVC优先。 如果要在此方案中测试响应式Web应用程序，则必须设置spring.main.web-application-type属性：

``` 
@RunWith(SpringRunner.class)
@SpringBootTest(properties = "spring.main.web-application-type=reactive")
public class MyWebFluxTests { ... }
```

**4.24.3.2 检测测试配置**

&emsp;&emsp;如果您熟悉Spring Test Framework，则可能习惯使用@ContextConfiguration(classes = ...)来指定要加载的Spring @Configuration。 或者，您可能经常在测试中使用嵌套的@Configuration类。

&emsp;&emsp;在测试Spring Boot应用程序时，通常不需要这样做。 Spring Boot的@*Test注解会在您未明确定义主要配置时自动搜索主要配置。

&emsp;&emsp;搜索算法从包含测试的包开始工作，直到找到使用@SpringBootApplication或@SpringBootConfiguration注释的类。 只要您以合理的方式构建代码，通常就会找到主要配置。

>如果使用测试批注来测试应用程序的更具体的片段，则应避免在main方法的应用程序类中添加特定于特定区域的配置设置。. @SpringBootApplication的基础组件扫描配置定义了排除过滤器，用于确保切片按预期工作。 如果在@SpringBootApplication注释的类上使用显式的@ComponentScan指令，请注意将禁用这些过滤器。 如果您正在使用切片，则应再次定义它们.

&emsp;&emsp;如果要自定义主要配置，可以使用嵌套的@TestConfiguration类。 与嵌套的@Configuration类不同，它将用于代替应用程序的主要配置，除了应用程序的主要配置之外，还使用嵌套的@TestConfiguration类。

>Spring的测试框架在测试之间缓存应用程序上下文。 因此，只要您的测试共享相同的配置（无论如何发现），加载上下文的潜在耗时过程只会发生一次.

**4.24.3.3 排除测试配置**

&emsp;&emsp;如果您的应用程序使用组件扫描（例如，如果您使用@SpringBootApplication或@ComponentScan），您可能会发现仅为特定测试创建的顶级配置类偶然会在任何地方被拾取。

&emsp;&emsp;正如我们之前所见，@TestConfiguration可用于测试的内部类以自定义主要配置。 当置于顶级类时，@TestConfiguration指示不应通过扫描拾取src/test/java中的类。 然后，您可以在需要的位置显式导入该类，如以下示例所示：

``` 
@RunWith(SpringRunner.class)
@SpringBootTest
@Import(MyTestsConfiguration.class)
public class MyTests {

	@Test
	public void exampleTest() {
		...
	}

}
```

>如果直接使用@ComponentScan（即不通过@SpringBootApplication），则需要使用它注册TypeExcludeFilter。 有关详细信息，请参阅Javadoc.

**4.24.3.4 使用模拟环境进行测试**

&emsp;&emsp;默认情况下，@SpringBootTest不会启动服务器。 如果您要针对此模拟环境测试Web端点，则可以另外配置MockMvc，如以下示例所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.servlet.AutoConfigureMockMvc;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.web.servlet.MockMvc;

import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.content;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.status;

@RunWith(SpringRunner.class)
@SpringBootTest
@AutoConfigureMockMvc
public class MockMvcExampleTests {

	@Autowired
	private MockMvc mvc;

	@Test
	public void exampleTest() throws Exception {
		this.mvc.perform(get("/")).andExpect(status().isOk())
				.andExpect(content().string("Hello World"));
	}

}
```

>如果您只想关注Web层而不是启动完整的ApplicationContext，请考虑使用@WebMvcTest.

&emsp;&emsp;或者，您可以配置WebTestClient，如以下示例所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.reactive.AutoConfigureWebTestClient;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.web.reactive.server.WebTestClient;

@RunWith(SpringRunner.class)
@SpringBootTest
@AutoConfigureWebTestClient
public class MockWebTestClientExampleTests {

	@Autowired
	private WebTestClient webClient;

	@Test
	public void exampleTest() {
		this.webClient.get().uri("/").exchange().expectStatus().isOk()
				.expectBody(String.class).isEqualTo("Hello World");
	}

}
```

**4.24.3.5 使用正在运行的服务器进行测试**

&emsp;&emsp;如果您需要启动一个完整运行的服务器，我们建议您使用随机端口。 如果使用@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)，则每次运行测试时都会随机选取一个可用端口。

&emsp;&emsp;@LocalServerPort注释可用于注入测试中使用的实际端口。 为方便起见，需要对启动的服务器进行REST调用的测试还可以@Autowire WebTestClient，它解析与正在运行的服务器的相对链接，并附带用于验证响应的专用API，如以下示例所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.boot.test.context.SpringBootTest.WebEnvironment;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.web.reactive.server.WebTestClient;

@RunWith(SpringRunner.class)
@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
public class RandomPortWebTestClientExampleTests {

	@Autowired
	private WebTestClient webClient;

	@Test
	public void exampleTest() {
		this.webClient.get().uri("/").exchange().expectStatus().isOk()
				.expectBody(String.class).isEqualTo("Hello World");
	}

}
```

&emsp;&emsp;此设置需要类路径上的spring-webflux。 如果你不能或不会添加webflux，Spring Boot还提供了一个TestRestTemplate工具：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.boot.test.context.SpringBootTest.WebEnvironment;
import org.springframework.boot.test.web.client.TestRestTemplate;
import org.springframework.test.context.junit4.SpringRunner;

import static org.assertj.core.api.Assertions.assertThat;

@RunWith(SpringRunner.class)
@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
public class RandomPortTestRestTemplateExampleTests {

	@Autowired
	private TestRestTemplate restTemplate;

	@Test
	public void exampleTest() {
		String body = this.restTemplate.getForObject("/", String.class);
		assertThat(body).isEqualTo("Hello World");
	}

}
```

**4.24.3.6 使用JMX**

&emsp;&emsp;当测试上下文框架缓存上下文时，默认情况下禁用JMX以防止相同的组件在同一域上注册。 如果此类测试需要访问MBeanServer，请考虑将其标记为dirty：

``` 
@RunWith(SpringRunner.class)
@SpringBootTest(properties = "spring.jmx.enabled=true")
@DirtiesContext
public class SampleJmxTests {

	@Autowired
	private MBeanServer mBeanServer;

	@Test
	public void exampleTest() {
		// ...
	}

}
```

**4.24.3.7 Mocking和Spying Beans**

&emsp;&emsp;运行测试时，有时需要在应用程序上下文中模拟某些组件。 例如，您可能拥有在开发期间不可用的某些远程服务的外观。 当您想要模拟在真实环境中难以触发的故障时，模拟也很有用。

&emsp;&emsp;Spring Boot包含一个@MockBean注释，可用于为ApplicationContext中的bean定义Mockito模拟。 您可以使用批注添加新bean或替换单个现有bean定义。 注释可以直接用于测试类，测试中的字段或@Configuration类和字段。 在字段上使用时，也会注入创建的模拟的实例。 每种测试方法后，模拟Bean都会自动重置。

>如果您的测试使用Spring Boot的测试注释之一（例如@SpringBootTest），则会自动启用此功能。 要使用不同排列的此功能，必须显式添加侦听器，如以下示例所示: @TestExecutionListeners(MockitoTestExecutionListener.class)

&emsp;&emsp;以下示例使用模拟实现替换现有的RemoteService bean：

``` 
import org.junit.*;
import org.junit.runner.*;
import org.springframework.beans.factory.annotation.*;
import org.springframework.boot.test.context.*;
import org.springframework.boot.test.mock.mockito.*;
import org.springframework.test.context.junit4.*;

import static org.assertj.core.api.Assertions.*;
import static org.mockito.BDDMockito.*;

@RunWith(SpringRunner.class)
@SpringBootTest
public class MyTests {

	@MockBean
	private RemoteService remoteService;

	@Autowired
	private Reverser reverser;

	@Test
	public void exampleTest() {
		// RemoteService has been injected into the reverser bean
		given(this.remoteService.someCall()).willReturn("mock");
		String reverse = reverser.reverseSomeCall();
		assertThat(reverse).isEqualTo("kcom");
	}

}
```

&emsp;&emsp;此外，您可以使用@SpyBean将任何现有bean包装为Mockito间谍。 有关详细信息，请参阅Javadoc。

>虽然Spring的测试框架在测试之间缓存应用程序上下文并重用共享相同配置的测试的上下文，但使用@MockBean或@SpyBean会影响缓存键，这很可能会增加上下文的数量.

&emsp;
>如果您使用@SpyBean监视具有按名称引用参数的@Cacheable方法的bean，则必须使用-parameters编译应用程序。 这确保了一旦bean被监视，参数名称可用于缓存基础结构.

**4.24.3.8 自动配置测试**

&emsp;&emsp;Spring Boot的自动配置系统适用于应用程序，但有时对于测试来说有点太多了。 通常有助于仅加载测试应用程序“切片”所需的配置部分。 例如，您可能希望测试Spring MVC控制器是否正确映射URL，并且您不希望在这些测试中涉及数据库调用，或者您可能想要测试运行JPA实体，并且您对Web层不感兴趣 。

&emsp;&emsp;spring-boot-test-autoconfigure模块包括许多可用于自动配置这种“切片”的注释。 它们中的每一个都以类似的方式工作，提供一个@...Test注释，用于加载ApplicationContext和一个或多个@AutoConfigure...注释，可用于自定义自动配置设置。

>每个切片将组件扫描限制为适当的组件，并加载一组非常有限的自动配置类。 如果您需要排除其中一个，大多数@...Test注释提供excludeAutoConfiguration属性。 或者，您可以使用@ImportAutoConfiguration＃exclude.

&emsp;
>不支持在一个测试中使用通过使用多个@...Test注释包括多个“切片”。 如果您需要多个“切片”，请选择其中一个@...Testannotations并手动包含@ AutoConfigure...其他“切片”的注释.

&emsp;
>也可以将@AutoConfigure...注释与标准@SpringBootTest注释一起使用。 如果您对“切片”应用程序不感兴趣但想要一些自动配置的测试bean，则可以使用此组合.

**4.24.3.9 自动配置的JSON测试**

&emsp;&emsp;要测试该对象JSON序列化和反序列化是否按预期工作，您可以使用@JsonTest批注。 @JsonTest自动配置可用的受支持JSON映射器，它可以是以下库之一：

- Jackson ObjectMapper，任何@JsonComponent bean和任何Jackson Modules
- Gson
- Jsonb

>可以在附录中找到由@JsonTest启用的自动配置列表。

&emsp;&emsp;如果需要配置自动配置的元素，可以使用@AutoConfigureJsonTesters注释。

&emsp;&emsp;Spring Boot包括基于AssertJ的助手，它们与JSONAssert和JsonPath库一起使用，以检查JSON是否按预期显示。 JacksonTester，GsonTester，JsonbTester和BasicJsonTester类可分别用于Jackson，Gson，Jsonb和Strings。 使用@JsonTest时，测试类上的任何辅助字段都可以是@Autowired。 以下示例显示了Jackson的测试类：

``` 
import org.junit.*;
import org.junit.runner.*;
import org.springframework.beans.factory.annotation.*;
import org.springframework.boot.test.autoconfigure.json.*;
import org.springframework.boot.test.context.*;
import org.springframework.boot.test.json.*;
import org.springframework.test.context.junit4.*;

import static org.assertj.core.api.Assertions.*;

@RunWith(SpringRunner.class)
@JsonTest
public class MyJsonTests {

	@Autowired
	private JacksonTester<VehicleDetails> json;

	@Test
	public void testSerialize() throws Exception {
		VehicleDetails details = new VehicleDetails("Honda", "Civic");
		// Assert against a `.json` file in the same package as the test
		assertThat(this.json.write(details)).isEqualToJson("expected.json");
		// Or use JSON path based assertions
		assertThat(this.json.write(details)).hasJsonPathStringValue("@.make");
		assertThat(this.json.write(details)).extractingJsonPathStringValue("@.make")
				.isEqualTo("Honda");
	}

	@Test
	public void testDeserialize() throws Exception {
		String content = "{\"make\":\"Ford\",\"model\":\"Focus\"}";
		assertThat(this.json.parse(content))
				.isEqualTo(new VehicleDetails("Ford", "Focus"));
		assertThat(this.json.parseObject(content).getMake()).isEqualTo("Ford");
	}

}
```

>JSON帮助程序类也可以直接在标准单元测试中使用。 为此，如果不使用@JsonTest，请在@Before方法中调用助手的initFields方法。

**4.24.3.10 自动配置的Spring MVC测试**

&emsp;&emsp;要测试Spring MVC控制器是否按预期工作，请使用@WebMvcTest注释。 @WebMvcTest自动配置Spring MVC基础结构并将扫描的bean限制为@Controller，@ControllerAdvice，@JsonComponent，Converter，GenericConverter，Filter，WebMvcConfigurer和HandlerMethodArgumentResolver。 使用此批注时，不会扫描常规@Component bean。

>可以在附录中找到由@WebMvcTest启用的自动配置设置列表。

&emsp;
>如果需要注册额外的组件，例如Jackson Module，则可以在测试中使用@Import导入其他配置类。

&emsp;&emsp;通常，@WebMvcTest仅限于单个控制器，并与@MockBean结合使用，为所需的协作者提供模拟实现。

&emsp;&emsp;@WebMvcTest还自动配置MockMvc。 Mock MVC提供了一种快速测试MVC控制器的强大方法，无需启动完整的HTTP服务器。

>您还可以通过使用@AutoConfigureMockMvc对其进行注释，在非@WebMvcTest（例如@SpringBootTest）中自动配置MockMvc。 以下示例使用MockMvc：

``` 
import org.junit.*;
import org.junit.runner.*;
import org.springframework.beans.factory.annotation.*;
import org.springframework.boot.test.autoconfigure.web.servlet.*;
import org.springframework.boot.test.mock.mockito.*;

import static org.assertj.core.api.Assertions.*;
import static org.mockito.BDDMockito.*;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.*;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringRunner.class)
@WebMvcTest(UserVehicleController.class)
public class MyControllerTests {

	@Autowired
	private MockMvc mvc;

	@MockBean
	private UserVehicleService userVehicleService;

	@Test
	public void testExample() throws Exception {
		given(this.userVehicleService.getVehicleDetails("sboot"))
				.willReturn(new VehicleDetails("Honda", "Civic"));
		this.mvc.perform(get("/sboot/vehicle").accept(MediaType.TEXT_PLAIN))
				.andExpect(status().isOk()).andExpect(content().string("Honda Civic"));
	}

}
```

>如果需要配置自动配置的元素（例如，应该应用servlet过滤器时），可以使用@AutoConfigureMockMvc注释中的属性。

&emsp;&emsp;如果使用HtmlUnit或Selenium，则自动配置还提供HTMLUnit WebClient bean和/或WebDriver bean。 以下示例使用HtmlUnit：

``` 
import com.gargoylesoftware.htmlunit.*;
import org.junit.*;
import org.junit.runner.*;
import org.springframework.beans.factory.annotation.*;
import org.springframework.boot.test.autoconfigure.web.servlet.*;
import org.springframework.boot.test.mock.mockito.*;

import static org.assertj.core.api.Assertions.*;
import static org.mockito.BDDMockito.*;

@RunWith(SpringRunner.class)
@WebMvcTest(UserVehicleController.class)
public class MyHtmlUnitTests {

	@Autowired
	private WebClient webClient;

	@MockBean
	private UserVehicleService userVehicleService;

	@Test
	public void testExample() throws Exception {
		given(this.userVehicleService.getVehicleDetails("sboot"))
				.willReturn(new VehicleDetails("Honda", "Civic"));
		HtmlPage page = this.webClient.getPage("/sboot/vehicle.html");
		assertThat(page.getBody().getTextContent()).isEqualTo("Honda Civic");
	}

}
```

>默认情况下，Spring Boot将WebDriver bean放在一个特殊的“scope”中，以确保驱动程序在每次测试后退出并注入新实例。 如果您不想要此行为，可以将@Scope("singleton")添加到WebDriver @Bean定义中。

&emsp;
>Spring Boot创建的webDriver范围将替换任何用户定义的同名范围。 如果您定义自己的webDriver范围，则可能会在使用@WebMvcTest时发现它停止工作。

&emsp;&emsp;如果在类路径上有Spring Security，@ WebMvcTest也将扫描WebSecurityConfigurer bean。 您可以使用Spring Security的测试支持，而不是完全禁用此类测试的安全性。 有关如何使用Spring Security的MockMvc支持的更多详细信息，请参见第9.5 “使用Spring Security测试操作方法”部分。

>有时编写Spring MVC测试是不够的; Spring Boot可以帮助您使用实际服务器运行完整的端到端测试。

**4.24.3.11 自动配置的Spring WebFlux测试**

&emsp;&emsp;要测试Spring WebFlux控制器是否按预期工作，可以使用@WebFluxTest批注。 @WebFluxTest自动配置Spring WebFlux基础结构并将扫描的bean限制为@Controller，@ControllerAdvice，@JsonComponent，Converter，GenericConverter和WebFluxConfigurer。 使用@WebFluxTest批注时，不会扫描常规@Component bean。

>可以在附录中找到由@WebFluxTest启用的自动配置列表。

&emsp;
>如果需要注册额外的组件，例如Jackson Module，则可以在测试中使用@Import导入其他配置类。<

&emsp;&emsp;通常，@WebFluxTest仅限于单个控制器，并与@MockBean批注结合使用，为所需的协作者提供模拟实现。

&emsp;&emsp;@WebFluxTest还自动配置WebTestClient，它提供了一种快速测试WebFlux控制器的强大方法，无需启动完整的HTTP服务器。

>您还可以通过使用@AutoConfigureWebTestClient对其进行注释，在非@WebFluxTest（例如@SpringBootTest）中自动配置WebTestClient。 以下示例显示了一个同时使用@WebFluxTest和WebTestClient的类：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.reactive.WebFluxTest;
import org.springframework.http.MediaType;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.web.reactive.server.WebTestClient;

@RunWith(SpringRunner.class)
@WebFluxTest(UserVehicleController.class)
public class MyControllerTests {

	@Autowired
	private WebTestClient webClient;

	@MockBean
	private UserVehicleService userVehicleService;

	@Test
	public void testExample() throws Exception {
		given(this.userVehicleService.getVehicleDetails("sboot"))
				.willReturn(new VehicleDetails("Honda", "Civic"));
		this.webClient.get().uri("/sboot/vehicle").accept(MediaType.TEXT_PLAIN)
				.exchange()
				.expectStatus().isOk()
				.expectBody(String.class).isEqualTo("Honda Civic");
	}

}
```

>此设置仅由WebFlux应用程序支持，因为在模拟的Web应用程序中使用WebTestClient仅适用于WebFlux。

&emsp;
>@WebFluxTest无法检测通过功能Web框架注册的路由。 要在上下文中测试RouterFunction bean，请考虑通过@Import或使用@SpringBootTest自行导入RouterFunction。

&emsp;
>有时编写Spring WebFlux测试是不够的; Spring Boot可以帮助您使用实际服务器运行完整的端到端测试。

**4.24.3.12 自动配置的Data JPA测试**

&emsp;&emsp;您可以使用@DataJpaTest批注来测试JPA应用程序。 默认情况下，它配置内存中的嵌入式数据库，扫描@Entity类，并配置Spring Data JPA存储库。 常规@Component bean未加载到ApplicationContext中。

>可以在附录中找到由@DataJpaTest启用的自动配置设置列表。

&emsp;&emsp;默认情况下，数据JPA测试是事务性的，并在每次测试结束时回滚。 有关更多详细信息，请参阅Spring Framework Reference Documentation中的相关部分。 如果这不是您想要的，您可以为测试或整个类禁用事务管理，如下所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.transaction.annotation.Propagation;
import org.springframework.transaction.annotation.Transactional;

@RunWith(SpringRunner.class)
@DataJpaTest
@Transactional(propagation = Propagation.NOT_SUPPORTED)
public class ExampleNonTransactionalTests {

}
```

&emsp;&emsp;数据JPA测试还可以注入TestEntityManager bean，它提供了专门为测试设计的标准JPA EntityManager的替代方法。 如果要在@DataJpaTest实例之外使用TestEntityManager，还可以使用@AutoConfigureTestEntityManager注释。 如果需要，还可以使用JdbcTemplate。 以下示例显示正在使用的@DataJpaTest批注：

``` 
import org.junit.*;
import org.junit.runner.*;
import org.springframework.boot.test.autoconfigure.orm.jpa.*;

import static org.assertj.core.api.Assertions.*;

@RunWith(SpringRunner.class)
@DataJpaTest
public class ExampleRepositoryTests {

	@Autowired
	private TestEntityManager entityManager;

	@Autowired
	private UserRepository repository;

	@Test
	public void testExample() throws Exception {
		this.entityManager.persist(new User("sboot", "1234"));
		User user = this.repository.findByUsername("sboot");
		assertThat(user.getUsername()).isEqualTo("sboot");
		assertThat(user.getVin()).isEqualTo("1234");
	}

}
```

&emsp;&emsp;内存中的嵌入式数据库通常可以很好地用于测试，因为它们很快并且不需要任何安装。 但是，如果您更喜欢对真实数据库运行测试，则可以使用@AutoConfigureTestDatabase批注，如以下示例所示：

``` 
@RunWith(SpringRunner.class)
@DataJpaTest
@AutoConfigureTestDatabase(replace=Replace.NONE)
public class ExampleRepositoryTests {

	// ...

}
```

**4.24.3.13 自动配置的JDBC测试**

&emsp;&emsp;@JdbcTest类似于@DataJpaTest，但适用于仅需要DataSource且不使用Spring Data JDBC的测试。 默认情况下，它配置内存中的嵌入式数据库和JdbcTemplate。 常规@Component bean未加载到ApplicationContext中。

>可以在附录中找到由@JdbcTest启用的自动配置列表。

&emsp;&emsp;默认情况下，JDBC测试是事务性的，并在每次测试结束时回滚。 有关更多详细信息，请参阅Spring Framework Reference Documentation中的相关部分。 如果这不是您想要的，您可以禁用测试或整个类的事务管理，如下所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.boot.test.autoconfigure.jdbc.JdbcTest;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.transaction.annotation.Propagation;
import org.springframework.transaction.annotation.Transactional;

@RunWith(SpringRunner.class)
@JdbcTest
@Transactional(propagation = Propagation.NOT_SUPPORTED)
public class ExampleNonTransactionalTests {

}
```

&emsp;&emsp;如果您希望测试针对真实数据库运行，则可以使用与DataJpaTest相同的方式使用@AutoConfigureTestDatabase批注。 （参见“第4.24.3.12节”，“自动配置的数据JPA测试”。）

**4.24.3.14 自动配置的Data JDBC测试**

&emsp;&emsp;@DataJdbcTest类似于@JdbcTest，但适用于使用Spring Data JDBC存储库的测试。 默认情况下，它配置内存中嵌入式数据库，JdbcTemplate和Spring Data JDBC存储库。 常规@Component bean未加载到ApplicationContext中。

>可以在附录中找到由@DataJdbcTest启用的自动配置列表。

&emsp;&emsp;默认情况下，数据JDBC测试是事务性的，并在每次测试结束时回滚。 有关更多详细信息，请参阅Spring Framework Reference Documentation中的相关部分。 如果这不是您想要的，您可以禁用测试或整个测试类的事务管理，如JDBC示例中所示。

&emsp;&emsp;如果您希望测试针对真实数据库运行，则可以使用与DataJpaTest相同的方式使用@AutoConfigureTestDatabase批注。 （参见“第4.24.3.12节”，“自动配置的数据JPA测试”。）

**4.24.3.15 自动配置的jOOQ测试**

&emsp;&emsp;你可以像@JdbcTest一样使用@JooqTest，但是用于与jOOQ相关的测试。 由于jOOQ严重依赖于与数据库模式相对应的基于Java的模式，因此使用现有的DataSource。 如果要将其替换为内存数据库，可以使用@AutoConfigureTestDatabase覆盖这些设置。 （有关在Spring Boot中使用jOOQ的更多信息，请参阅本章前面的“第4.8.6节”，“使用jOOQ”。）常规@Component bean未加载到ApplicationContext中。

>可以在附录中找到由@JooqTest启用的自动配置列表。

&emsp;&emsp;@JooqTest配置DSLContext。 常规@Component bean未加载到ApplicationContext中。 以下示例显示了正在使用的@JooqTest批注：

``` 
import org.jooq.DSLContext;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.boot.test.autoconfigure.jooq.JooqTest;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@JooqTest
public class ExampleJooqTests {

	@Autowired
	private DSLContext dslContext;
}
```

&emsp;&emsp;JOOQ测试是事务性的，默认情况下在每次测试结束时回滚。 如果这不是您想要的，您可以禁用测试或整个测试类的事务管理，如JDBC示例中所示。

**4.24.3.16 自动配置的Data MongoDB测试**

&emsp;&emsp;您可以使用@DataMongoTest来测试MongoDB应用程序。 默认情况下，它配置内存中嵌入的MongoDB（如果可用），配置MongoTemplate，扫描@Document类，以及配置Spring Data MongoDB存储库。 常规@Component bean未加载到ApplicationContext中。 （有关将MongoDB与Spring Boot一起使用的更多信息，请参阅本章前面的“第4.9.2节”，“MongoDB”。）

>可以在附录中找到由@DataMongoTest启用的自动配置设置列表。

&emsp;&emsp;以下类显示正在使用的@DataMongoTest批注：

``` 
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.data.mongo.DataMongoTest;
import org.springframework.data.mongodb.core.MongoTemplate;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@DataMongoTest
public class ExampleDataMongoTests {

	@Autowired
	private MongoTemplate mongoTemplate;

	//
}
```

&emsp;&emsp;内存中嵌入式MongoDB通常适用于测试，因为它速度快，不需要任何开发人员安装。 但是，如果您更喜欢对真正的MongoDB服务器运行测试，则应排除嵌入式MongoDB自动配置，如以下示例所示：

``` 
import org.junit.runner.RunWith;
 import org.springframework.boot.autoconfigure.mongo.embedded.EmbeddedMongoAutoConfiguration;
import org.springframework.boot.test.autoconfigure.data.mongo.DataMongoTest;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@DataMongoTest(excludeAutoConfiguration = EmbeddedMongoAutoConfiguration.class)
public class ExampleDataMongoNonEmbeddedTests {

}
```

**4.24.3.17 自动配置的Data Neo4j测试**

&emsp;&emsp;您可以使用@DataNeo4jTest来测试Neo4j应用程序。 默认情况下，它使用内存中嵌入式Neo4j（如果嵌入式驱动程序可用），扫描@NodeEntity类，并配置Spring Data Neo4j存储库。 常规@Component bean未加载到ApplicationContext中。 （有关使用带有Spring Boot的Neo4J的更多信息，请参阅本章前面的“第4.9.3节”，“Neo4j”。）

>可以在附录中找到由@ DataNeo4jTest启用的自动配置设置列表。

&emsp;&emsp;以下示例显示了在Spring Boot中使用Neo4J测试的典型设置：

``` 
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.data.neo4j.DataNeo4jTest;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@DataNeo4jTest
public class ExampleDataNeo4jTests {

	@Autowired
	private YourRepository repository;

	//
}
```

&emsp;&emsp;默认情况下，Data Neo4j测试是事务性的，并在每次测试结束时回滚。 有关更多详细信息，请参阅Spring Framework Reference Documentation中的相关部分。 如果这不是您想要的，您可以禁用测试或整个类的事务管理，如下所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.boot.test.autoconfigure.data.neo4j.DataNeo4jTest;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.transaction.annotation.Propagation;
import org.springframework.transaction.annotation.Transactional;

@RunWith(SpringRunner.class)
@DataNeo4jTest
@Transactional(propagation = Propagation.NOT_SUPPORTED)
public class ExampleNonTransactionalTests {

}
```

**4.24.3.18 自动配置的Data Redis测试**

&emsp;&emsp;您可以使用@DataRedisTest来测试Redis应用程序。 默认情况下，它会扫描@RedisHash类并配置Spring Data Redis存储库。 常规@Component bean未加载到ApplicationContext中。（有关使用带有Spring Boot的Redis的更多信息，请参阅本章前面的“第4.9.1节”，“Redis”。）

>可以在附录中找到由@DataRedisTest启用的自动配置设置列表。

&emsp;&emsp;以下示例显示正在使用的@DataRedisTest批注：

``` 
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.data.redis.DataRedisTest;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@DataRedisTest
public class ExampleDataRedisTests {

	@Autowired
	private YourRepository repository;

	//
}
```

**4.24.3.19 自动配置的Data LDAP测试**

&emsp;&emsp;您可以使用@DataLdapTest来测试LDAP应用程序。 默认情况下，它配置内存中嵌入式LDAP（如果可用），配置LdapTemplate，扫描@Entry类，以及配置Spring Data LDAP存储库。 常规@Component bean未加载到ApplicationContext中。 （有关在Spring Boot中使用LDAP的更多信息，请参阅本章前面的“第4.9.9节”，“LDAP”。）

>可以在附录中找到由@DataLdapTest启用的自动配置设置列表。

&emsp;&emsp;以下示例显示正在使用的@DataLdapTest批注：

``` 
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.data.ldap.DataLdapTest;
import org.springframework.ldap.core.LdapTemplate;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@DataLdapTest
public class ExampleDataLdapTests {

	@Autowired
	private LdapTemplate ldapTemplate;

	//
}
```

&emsp;&emsp;内存中嵌入式LDAP通常适用于测试，因为它速度快，不需要任何开发人员安装。 但是，如果您更喜欢针对真实LDAP服务器运行测试，则应排除嵌入式LDAP自动配置，如以下示例所示：

``` 
import org.junit.runner.RunWith;
import org.springframework.boot.autoconfigure.ldap.embedded.EmbeddedLdapAutoConfiguration;
import org.springframework.boot.test.autoconfigure.data.ldap.DataLdapTest;
import org.springframework.test.context.junit4.SpringRunner;

@RunWith(SpringRunner.class)
@DataLdapTest(excludeAutoConfiguration = EmbeddedLdapAutoConfiguration.class)
public class ExampleDataLdapNonEmbeddedTests {

}
```

**4.24.3.20 自动配置的REST Clients 测试**

&emsp;&emsp;您可以使用@RestClientTest批注来测试REST客户端。 默认情况下，它会自动配置Jackson，GSON和Jsonb支持，配置RestTemplateBuilder，并添加对MockRestServiceServer的支持。 常规@Component bean未加载到ApplicationContext中。

>可以在附录中找到由@RestClientTest启用的自动配置设置列表。

&emsp;&emsp;应使用@RestClientTest的value或components属性指定要测试的特定bean，如以下示例所示：

``` 
@RunWith(SpringRunner.class)
@RestClientTest(RemoteVehicleDetailsService.class)
public class ExampleRestClientTest {

	@Autowired
	private RemoteVehicleDetailsService service;

	@Autowired
	private MockRestServiceServer server;

	@Test
	public void getVehicleDetailsWhenResultIsSuccessShouldReturnDetails()
			throws Exception {
		this.server.expect(requestTo("/greet/details"))
				.andRespond(withSuccess("hello", MediaType.TEXT_PLAIN));
		String greeting = this.service.callRestService();
		assertThat(greeting).isEqualTo("hello");
	}

}
```

**4.24.3.21 自动配置的Spring REST Docs测试**

&emsp;&emsp;您可以使用@AutoConfigureRestDocs批注在Mock MVC，REST Assured或WebTestClient的测试中使用Spring REST Docs。 它消除了对Spring REST Docs中JUnit规则的需求。

&emsp;&emsp;@AutoConfigureRestDocs可用于覆盖默认输出目录（如果您使用的是Maven，则使用target/generated-snippets，如果使用Gradle，则使用build/generated-snippets）。 它还可用于配置出现在任何已记录的URI中的主机，方案和端口。

**1）使用Mock MVC测试自动配置的Spring REST Docs**

&emsp;&emsp;@AutoConfigureRestDocs自定义MockMvc bean以使用Spring REST Docs。 您可以使用@Autowired注入它，并像在使用Mock MVC和Spring REST Docs时一样在测试中使用它，如以下示例所示：

``` 
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.servlet.WebMvcTest;
import org.springframework.http.MediaType;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.web.servlet.MockMvc;

import static org.springframework.restdocs.mockmvc.MockMvcRestDocumentation.document;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringRunner.class)
@WebMvcTest(UserController.class)
@AutoConfigureRestDocs
public class UserDocumentationTests {

	@Autowired
	private MockMvc mvc;

	@Test
	public void listUsers() throws Exception {
		this.mvc.perform(get("/users").accept(MediaType.TEXT_PLAIN))
				.andExpect(status().isOk())
				.andDo(document("list-users"));
	}

}
```

&emsp;&emsp;如果您需要对Spring REST Docs配置的更多控制，而不是@AutoConfigureRestDocs的属性，则可以使用RestDocsMockMvcConfigurationCustomizer bean，如以下示例所示：

``` 
@TestConfiguration
static class CustomizationConfiguration
		implements RestDocsMockMvcConfigurationCustomizer {

	@Override
	public void customize(MockMvcRestDocumentationConfigurer configurer) {
		configurer.snippets().withTemplateFormat(TemplateFormats.markdown());
	}

}
```

&emsp;&emsp;如果要对参数化输出目录使用Spring REST Docs支持，可以创建RestDocumentationResultHandler bean。 自动配置使用此结果处理程序调用alwaysDo，从而使每个MockMvc调用自动生成默认代码段。 以下示例显示正在定义的RestDocumentationResultHandler：

``` 
@TestConfiguration
static class ResultHandlerConfiguration {

	@Bean
	public RestDocumentationResultHandler restDocumentation() {
		return MockMvcRestDocumentation.document("{method-name}");
	}

}
```

**2）使用REST Assured测试自动配置的Spring REST Docs**

&emsp;&emsp;@AutoConfigureRestDocs生成一个RequestSpecification bean，预先配置为使用Spring REST Docs，可用于您的测试。 您可以使用@Autowired注入它并在测试中使用它，就像使用REST Assured和Spring REST Doc时一样，如下例所示：

``` 
import io.restassured.specification.RequestSpecification;
import org.junit.Test;
import org.junit.runner.RunWith;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.restdocs.AutoConfigureRestDocs;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.boot.test.context.SpringBootTest.WebEnvironment;
import org.springframework.boot.web.server.LocalServerPort;
import org.springframework.test.context.junit4.SpringRunner;

import static io.restassured.RestAssured.given;
import static org.hamcrest.CoreMatchers.is;
import static org.springframework.restdocs.restassured3.RestAssuredRestDocumentation.document;

@RunWith(SpringRunner.class)
@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
@AutoConfigureRestDocs
public class UserDocumentationTests {

	@LocalServerPort
	private int port;

	@Autowired
	private RequestSpecification documentationSpec;

	@Test
	public void listUsers() {
		given(this.documentationSpec).filter(document("list-users")).when()
				.port(this.port).get("/").then().assertThat().statusCode(is(200));
	}

}
```

&emsp;&emsp;如果您需要对Spring REST Docs配置的更多控制，而不是@AutoConfigureRestDocs的属性，则可以使用RestDocsRestAssuredConfigurationCustomizer bean，如以下示例所示：

``` 
@TestConfiguration
public static class CustomizationConfiguration
		implements RestDocsRestAssuredConfigurationCustomizer {

	@Override
	public void customize(RestAssuredRestDocumentationConfigurer configurer) {
		configurer.snippets().withTemplateFormat(TemplateFormats.markdown());
	}

}
```

**4.24.3.22 额外的自动配置和切片**

&emsp;&emsp;每个切片提供一个或多个@AutoConfigure ...注释，即定义应作为切片的一部分包含的自动配置。 可以通过创建自定义@AutoConfigure...注释或仅通过将@ImportAutoConfiguration添加到测试来添加其他自动配置，如以下示例所示：

``` 
@RunWith(SpringRunner.class)
@JdbcTest
@ImportAutoConfiguration(IntegrationAutoConfiguration.class)
public class ExampleJdbcTests {

}
```

>确保不使用常规的@Import批注来导入自动配置，因为Spring Boot会以特定的方式处理它们。

**4.24.3.23 用户配置和切片**

&emsp;&emsp;如果以合理的方式构建代码，则默认情况下会使用@SpringBootApplication类作为测试的配置。

&emsp;&emsp;然后，重要的是不要使用特定于其功能的特定区域的配置设置来丢弃应用程序的主类。

&emsp;&emsp;假设您正在使用Spring Batch并依赖于它的自动配置。 您可以按如下方式定义@SpringBootApplication：

``` 
@SpringBootApplication
@EnableBatchProcessing
public class SampleApplication { ... }
```

&emsp;&emsp;因为此类是测试的源配置，所以任何切片测试实际上都会尝试启动Spring Batch，这绝对不是您想要做的。 建议的方法是将特定于区域的配置移动到与应用程序相同级别的单独@Configuration类，如以下示例所示：

``` 
@Configuration
@EnableBatchProcessing
public class BatchConfiguration { ... }
```

>根据应用程序的复杂程度，您可能只有一个用于自定义的@Configuration类，或者每个域区域有一个类。 后一种方法允许您在必要时使用@Import注释在其中一个测试中启用它。

&emsp;&emsp;混淆的另一个原因是类路径扫描。 假设您以合理的方式构建代码，则需要扫描其他包。 您的应用程序可能类似于以下代码：

``` 
@SpringBootApplication
@ComponentScan({ "com.example.app", "org.acme.another" })
public class SampleApplication { ... }
```

&emsp;&emsp;这样做会有效地覆盖默认组件扫描指令，并且无论您选择哪个切片，都会扫描这两个包。 例如，@DataJpaTest似乎突然扫描了应用程序的组件和用户配置。 同样，将自定义指令移动到单独的类是解决此问题的好方法。

>如果这不是您的选项，您可以在测试的层次结构中的某处创建@SpringBootConfiguration，以便使用它。 或者，您可以为测试指定源，这会禁用查找默认源的行为。

**4.24.3.24 使用Spock来测试Spring Boot应用程序**

&emsp;&emsp;如果您希望使用Spock来测试Spring Boot应用程序，您应该将Spock的spock-spring模块的依赖项添加到您的应用程序的构建中。 spock-spring将Spring的测试框架集成到Spock中。 建议您使用Spock 1.2或更高版本从Spock的Spring Framework和Spring Boot集成的许多改进中受益。 有关更多详细信息，请参阅Spock Spring模块的文档。

### **4.24.4 测试工具包**

&emsp;&emsp;在测试应用程序时通常有用的一些测试实用程序类被打包为spring-boot的一部分。

**4.24.4.1 ConfigFileApplicationContextInitializer**

&emsp;&emsp;ConfigFileApplicationContextInitializer是一个ApplicationContextInitializer，您可以将其应用于测试以加载Spring Boot application.properties文件。 当您不需要@SpringBootTest提供的全套功能时，可以使用它，如以下示例所示：

``` 
@ContextConfiguration(classes = Config.class,
	initializers = ConfigFileApplicationContextInitializer.class)
```

>仅使用ConfigFileApplicationContextInitializer不支持@Value("${...}")注入。 它唯一的工作是确保将application.properties文件加载到Spring的环境中。 对于@Value支持，您需要另外配置PropertySourcesPlaceholderConfigurer或使用@SpringBootTest，它会自动为您配置一个。

**4.24.4.2 TestPropertyValues**

&emsp;&emsp;TestPropertyValues允许您快速向ConfigurableEnvironment或ConfigurableApplicationContext添加属性。 您可以使用key = value字符串调用它，如下所示：

``` 
TestPropertyValues.of("org=Spring", "name=Boot").applyTo(env);
```

**4.24.4.3 OutputCapture**

&emsp;&emsp;OutputCapture是一个JUnit规则，可用于捕获System.out和System.err输出。 您可以将捕获声明为@Rule，然后使用toString()进行断言，如下所示：

``` 
import org.junit.Rule;
import org.junit.Test;
import org.springframework.boot.test.rule.OutputCapture;

import static org.hamcrest.Matchers.*;
import static org.junit.Assert.*;

public class MyTest {

	@Rule
	public OutputCapture capture = new OutputCapture();

	@Test
	public void testName() throws Exception {
		System.out.println("Hello World!");
		assertThat(capture.toString(), containsString("World"));
	}

}
```

**4.24.4.4 TestRestTemplate**

>Spring Framework 5.0提供了一个新的WebTestClient，适用于WebFlux集成测试以及WebFlux和MVC端到端测试。 与TestRestTemplate不同，它为断言提供了Stream的API。

&emsp;&emsp;TestRestTemplate是Spring的RestTemplate的一种便利替代品，可用于集成测试。 您可以获得一个vanilla模板或一个发送基本HTTP身份验证（使用用户名和密码）的模板。 在任何一种情况下，模板都以一种测试友好的方式运行，不会在服务器端错误上抛出异常。 建议（但不是强制性的）使用Apache HTTP Client（版本4.3.2或更高版本）。 如果在类路径上有这个，则TestRestTemplate通过适当地配置客户端来响应。 如果您确实使用Apache的HTTP客户端，则启用一些其他测试友好功能：

- 不遵循重定向（因此您可以断言响应位置）。
- Cookie被忽略（因此模板是无状态的）。

&emsp;&emsp;TestRestTemplate可以直接在集成测试中实例化，如以下示例所示：

``` 
public class MyTest {

	private TestRestTemplate template = new TestRestTemplate();

	@Test
	public void testRequest() throws Exception {
		HttpHeaders headers = this.template.getForEntity(
				"http://myhost.example.com/example", String.class).getHeaders();
		assertThat(headers.getLocation()).hasHost("other.example.com");
	}

}
```

## **4.25 WebSockets**

&emsp;&emsp;Spring Boot为嵌入式Tomcat，Jetty和Undertow提供WebSockets自动配置。 如果将war文件部署到独立容器，则Spring Boot假定容器负责其WebSocket支持的配置。

&emsp;&emsp;Spring Framework为MVC Web应用程序提供了丰富的WebSocket支持，可以通过spring-boot-starter-websocket模块轻松访问。

&emsp;&emsp;WebSocket支持也可用于响应式Web应用程序，并且需要包含WebSocket API以及spring-boot-starter-webflux：

``` 
<dependency>
	<groupId>javax.websocket</groupId>
	<artifactId>javax.websocket-api</artifactId>
</dependency>
```

## **4.26 Web Service**

&emsp;&emsp;Spring Boot提供Web服务自动配置，因此您必须做的就是定义端点。

&emsp;&emsp;可以使用spring-boot-starter-webservices模块轻松访问Spring Web Services功能。

&emsp;&emsp;可以分别为WSDL和XSD自动创建SimpleWsdl11Definition和SimpleXsdSchema bean。 为此，请配置其位置，如以下示例所示：

``` 
spring.webservices.wsdl-locations=classpath:/wsdl
```

### **4.26.1 使用WebServiceTemplate调用Web服务**

&emsp;&emsp;如果需要从应用程序调用远程Web服务，则可以使用WebServiceTemplate类。 由于WebServiceTemplate实例在使用之前通常需要进行自定义，因此Spring Boot不提供任何单个自动配置的WebServiceTemplate bean。 但是，它会自动配置WebServiceTemplateBuilder，可用于在需要时创建WebServiceTemplate实例。

&emsp;&emsp;以下代码显示了一个典型示例：

``` 
@Service
public class MyService {

	private final WebServiceTemplate webServiceTemplate;

	public MyService(WebServiceTemplateBuilder webServiceTemplateBuilder) {
		this.webServiceTemplate = webServiceTemplateBuilder.build();
	}

	public DetailsResp someWsCall(DetailsReq detailsReq) {
		 return (DetailsResp) this.webServiceTemplate.marshalSendAndReceive(detailsReq, new SoapActionCallback(ACTION));

	}

}
```

&emsp;&emsp;默认情况下，WebServiceTemplateBuilder使用类路径上的可用HTTP客户端库检测合适的基于HTTP的WebServiceMessageSender。 您还可以按如下方式自定义读取和连接超时：

``` 
@Bean
public WebServiceTemplate webServiceTemplate(WebServiceTemplateBuilder builder) {
	return builder.messageSenders(new HttpWebServiceMessageSenderBuilder()
			.setConnectTimeout(5000).setReadTimeout(2000).build()).build();
}
```

## **4.27 创建自己的自动配置**

&emsp;&emsp;如果您在开发共享库的公司工作，或者您在开源或商业库中工作，则可能需要开发自己的自动配置。 自动配置类可以捆绑在外部jar中，仍然可以通过Spring Boot获取。

&emsp;&emsp;自动配置可以与“启动器”相关联，该“启动器”提供自动配置代码以及您将使用它的典型库。 我们首先介绍了构建自己的自动配置需要了解的内容，然后我们将继续介绍创建自定义启动器所需的典型步骤。

>可以使用演示项目来展示如何逐步创建启动器。

### **4.27.1 了解自动配置的Bean**

&emsp;&emsp;在幕后，使用标准的@Configuration类实现自动配置。 额外的@Conditional注释用于约束何时应用自动配置。 通常，自动配置类使用@ConditionalOnClass和@ConditionalOnMissingBean注释。 这可确保仅在找到相关类时以及未声明自己的@Configuration时才应用自动配置。

&emsp;&emsp;您可以浏览spring-boot-autoconfigure的源代码，以查看Spring提供的@Configuration类（请参阅META-INF/spring.factories文件）

### **4.27.2 匹配自动配置候选人**

&emsp;&emsp;Spring Boot会检查已发布jar中是否存在META-INF/spring.factories文件。 该文件应列出EnableAutoConfiguration键下的配置类，如以下示例所示：

``` 
org.springframework.boot.autoconfigure.EnableAutoConfiguration=\
com.mycorp.libx.autoconfigure.LibXAutoConfiguration,\
com.mycorp.libx.autoconfigure.LibXWebAutoConfiguration
```

>必须以这种方式加载自动配置。 确保它们在特定的包空间中定义，并且它们永远不是组件扫描的目标。 此外，自动配置类不应启用组件扫描以查找其他组件。 应该使用特定的`@Import`代替。

&emsp;&emsp;如果需要按特定顺序应用配置，则可以使用@AutoConfigureAfter或@AutoConfigureBefore注释。 例如，如果您提供特定于Web的配置，则可能需要在WebMvcAutoConfiguration之后应用您的类。

&emsp;&emsp;如果您想排序某些不应该彼此直接了解的自动配置，您也可以使用@AutoConfigureOrder。 该注释与常规@Order注释具有相同的语义，但为自动配置类提供了专用顺序。

### **4.27.3 条件注解**

&emsp;&emsp;您几乎总是希望在自动配置类中包含一个或多个@Conditional注释。 @ConditionalOnMissingBean注释是一个常见示例，用于允许开发人员如果对您的默认值不满意，则覆盖自动配置。

&emsp;&emsp;Spring Boot包含许多@Conditional注释，您可以通过注释@Configuration类或单独的@Bean方法在您自己的代码中重用它们。 这些注释包括：

- Class条件
- Bean条件
- Property条件
- Resource条件
- Web Application条件
- SpEL表达式条件


**4.27.3.1 Class条件**

&emsp;&emsp;@ConditionalOnClass和@ConditionalOnMissingClass注释允许根据特定类的存在与否来包含@Configuration类。 由于使用ASM解析注释元数据这一事实，您可以使用value属性来引用真实类，即使该类实际上可能不会出现在正在运行的应用程序类路径中。 如果您希望使用String值指定类名，也可以使用name属性。

&emsp;&emsp;这种机制不适用于@Bean方法，在这种方法中，返回类型通常是条件的目标：在应用该方法的条件之前，JVM将加载类和可能处理的方法引用，如果类不存在，这些引用将失败。

&emsp;&emsp;要处理这种情况，可以使用单独的@Configuration类来隔离条件，如以下示例所示：

``` 
@Configuration
// Some conditions
public class MyAutoConfiguration {

	// Auto-configured beans

	@Configuration
	@ConditionalOnClass(EmbeddedAcmeService.class)
	static class EmbeddedConfiguration {

		@Bean
		@ConditionalOnMissingBean
		public EmbeddedAcmeService embeddedAcmeService() { ... }

	}

}
```

>如果使用@ConditionalOnClass或@ConditionalOnMissingClass作为元注释的一部分来组成自己的组合注释，则必须使用name作为引用类，在这种情况下不处理。

**4.27.3.2 Bean条件**

&emsp;&emsp;@ConditionalOnBean和@ConditionalOnMissingBean注释允许根据特定bean的存在与否包含bean。可以使用value属性按类型指定bean或按名称指定bean。Search属性允许您限制在搜索bean时应该考虑的ApplicationContext层次结构。

&emsp;&emsp;放置在@Bean方法上时，目标类型默认为方法的返回类型，如以下示例所示：

``` 
@Configuration
public class MyAutoConfiguration {

	@Bean
	@ConditionalOnMissingBean
	public MyService myService() { ... }

}
```

&emsp;&emsp;在前面的示例中，如果ApplicationContext中不包含MyService类型的bean，则将创建myService bean。

>您需要非常小心添加bean定义的顺序，因为这些条件是根据到目前为止已处理的内容进行评估的。 因此，我们建议在自动配置类上仅使用@ConditionalOnBean和@ConditionalOnMissingBean注释（因为这些注释保证在添加任何用户定义的bean定义后加载）。

&emsp;
>@ConditionalOnBean和@ConditionalOnMissingBean不会阻止创建@Configuration类。 在类级别使用这些条件并使用注释标记每个包含@Bean方法的唯一区别是，如果条件不匹配，前者会阻止将@Configuration类注册为bean。

**4.27.3.3 Property条件**

&emsp;&emsp;@ConditionalOnProperty注释允许基于Spring Environment属性包含配置。 使用prefix和name属性指定应检查的属性。 默认情况下，匹配存在且不等于false的任何属性。 您还可以使用havingValue和matchIfMissing属性创建更高级的检查。

**4.27.3.4 Resource条件**

&emsp;&emsp;@ConditionalOnResource注释仅允许在存在特定资源时包含配置。 可以使用常用的Spring约定来指定资源，如以下示例所示：file:/home/user/test.dat。

**4.27.3.5 Web Application条件**

&emsp;&emsp;@ConditionalOnWebApplication和@ConditionalOnNotWebApplication注释允许包含配置，具体取决于应用程序是否为“Web应用程序”。 Web应用程序是使用Spring WebApplicationContext，定义会话范围或具有StandardServletEnvironment的任何应用程序。

**4.26.3.6 SpEL表达式条件**

&emsp;&emsp;@ConditionalOnExpression批注允许根据SpEL表达式的结果包含配置。

### **4.27.4 测试您的自动配置**

&emsp;&emsp;自动配置可能受许多因素的影响：用户配置（@Bean定义和环境定制），条件评估（存在特定库）等。 具体而言，每个测试都应该创建一个定义良好的ApplicationContext，它表示这些自定义的组合。 ApplicationContextRunner提供了一种实现它的好方法。

&emsp;&emsp;ApplicationContextRunner通常被定义为测试类的一个字段，用于收集基本的通用配置。 以下示例确保始终调用UserServiceAutoConfiguration：

``` 
private final ApplicationContextRunner contextRunner = new ApplicationContextRunner()
		.withConfiguration(AutoConfigurations.of(UserServiceAutoConfiguration.class));
```

>如果必须定义多个自动配置，则无需按照与运行应用程序时完全相同的顺序调用它们的声明。

&emsp;&emsp;每个测试都可以使用运行器来表示特定的用例。 例如，下面的示例调用用户配置（UserConfiguration）并检查自动配置是否正确退回。 调用run提供了一个可以与Assert4J一起使用的回调上下文。

``` 
@Test
public void defaultServiceBacksOff() {
	this.contextRunner.withUserConfiguration(UserConfiguration.class)
			.run((context) -> {
				assertThat(context).hasSingleBean(UserService.class);
				assertThat(context.getBean(UserService.class)).isSameAs(
						context.getBean(UserConfiguration.class).myUserService());
			});
}

@Configuration
static class UserConfiguration {

	@Bean
	public UserService myUserService() {
		return new UserService("mine");
	}

}
```

&emsp;&emsp;也可以轻松自定义环境，如以下示例所示：

``` 
@Test
public void serviceNameCanBeConfigured() {
	this.contextRunner.withPropertyValues("user.name=test123").run((context) -> {
		assertThat(context).hasSingleBean(UserService.class);
		assertThat(context.getBean(UserService.class).getName()).isEqualTo("test123");
	});
}
```

&emsp;&emsp;启动器还可用于显示ConditionEvaluationReport。 报告可以在INFO或DEBUG级别打印。 以下示例显示如何使用ConditionEvaluationReportLoggingListener在自动配置测试中打印报表。

``` 
@Test
public void autoConfigTest {
	ConditionEvaluationReportLoggingListener initializer = new ConditionEvaluationReportLoggingListener(
			LogLevel.INFO);
	ApplicationContextRunner contextRunner = new ApplicationContextRunner()
			.withInitializer(initializer).run((context) -> {
					// Do something...
			});
}
```

**4.27.4.1 模拟Web上下文**

&emsp;&emsp;如果需要测试仅在Servlet或Reactive Web应用程序上下文中运行的自动配置，请分别使用WebApplicationContextRunner或ReactiveWebApplicationContextRunner。

**4.27.4.2 覆盖Classpath**

&emsp;&emsp;还可以测试在运行时不存在特定类和/或包时发生的情况。 Spring Boot附带了一个可以由Runner轻松使用的FilteredClassLoader。 在以下示例中，我们声明如果UserService不存在，则会正确禁用自动配置：

``` 
@Test
public void serviceIsIgnoredIfLibraryIsNotPresent() {
	this.contextRunner.withClassLoader(new FilteredClassLoader(UserService.class))
			.run((context) -> assertThat(context).doesNotHaveBean("userService"));
}
```

### **4.27.5 创建您自己的Starter**

&emsp;&emsp;库的完整Spring Boot启动程序可能包含以下组件：

- 自动配置模块，包含自动配置代码。
- 启动器模块，它提供对autoconfigure模块以及库的依赖关系以及通常有用的任何其他依赖关系。 简而言之，添加启动器应该提供开始使用该库所需的一切。

>如果您不需要将这两个问题分开，则可以将自动配置代码和依赖关系管理组合在一个模块中。

**4.27.5.1 命名**

&emsp;&emsp;您应该确保为您的启动器提供适当的命名空间。 即使您使用其他Maven groupId，也不要使用spring-boot启动模块名称。 我们可能会为您将来自动配置的内容提供官方支持。

&emsp;&emsp;根据经验，您应该在启动器后命名组合模块。 例如，假设您正在为“acme”创建启动器，并且您将自动配置模块命名为acme-spring-boot-autoconfigure和starter acme-spring-boot-starter。 如果您只有一个组合两者的模块，请将其命名为acme-spring-boot-starter。

&emsp;&emsp;此外，如果您的启动器提供配置密钥，请为它们使用唯一的命名空间。 特别是，不要将您的密钥包含在Spring Boot使用的命名空间中（例如server, management, spring等）。 如果您使用相同的命名空间，我们将来可能会以破坏您的模块的方式修改这些命名空间。

&emsp;&emsp;确保触发元数据生成，以便为您的密钥提供IDE帮助。 您可能希望查看生成的元数据（META-INF/spring-configuration-metadata.json）以确保正确记录您的密钥。

**4.27.5.2 自动配置模块**

&emsp;&emsp;autoconfigure模块包含开始使用库所需的所有内容。 它还可以包含配置键定义（例如@ConfigurationProperties）和任何可用于进一步自定义组件初始化方式的回调接口。

>您应该将库的依赖项标记为可选，以便您可以更轻松地在项目中包含autoconfigure模块。 如果以这种方式执行，则不提供库，默认情况下，Spring Boot会退出。

&emsp;&emsp;Spring Boot使用注释处理器来收集元数据文件（META-INF / spring-autoconfigure-metadata.properties）中自动配置的条件。 如果该文件存在，则用于热切过滤不匹配的自动配置，这将缩短启动时间。 建议在包含自动配置的模块中添加以下依赖项：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-autoconfigure-processor</artifactId>
	<optional>true</optional>
</dependency>
```

&emsp;&emsp;使用Gradle 4.5及更早版本时，应在compileOnly配置中声明依赖项，如以下示例所示：

``` 
dependencies {
	compileOnly "org.springframework.boot:spring-boot-autoconfigure-processor"
}
```

&emsp;&emsp;使用Gradle 4.6及更高版本时，应在annotationProcessor配置中声明依赖项，如以下示例所示：

``` 
dependencies {
	annotationProcessor "org.springframework.boot:spring-boot-autoconfigure-processor"
}
```

**4.27.5.3 Starter模块**

&emsp;&emsp;起动器真的是一个空jar。 它的唯一目的是提供必要的依赖项来使用库。 您可以将其视为对入门所需内容的一种看法。

&emsp;&emsp;不要对添加启动器的项目做出假设。 如果您自动配置的库通常需要其他启动器，请同时提及它们。 如果可选依赖项的数量很高，则提供一组适当的默认依赖项可能很难，因为您应该避免包含对典型库的使用不必要的依赖项。 换句话说，您不应该包含可选的依赖项。

>无论哪种方式，您的启动器必须直接或间接引用核心Spring Boot启动器（spring-boot-starter）（即如果您的启动器依赖于另一个启动器，则无需添加它）。 如果只使用自定义启动器创建项目，则Spring Boot的核心功能将通过核心启动器的存在来实现。

## **4.28 Kotlin支持**

&emsp;&emsp;Kotlin是一种针对JVM（和其他平台）的静态类型语言，它允许编写简洁而优雅的代码，同时提供与Java编写的现有库的互操作性。

&emsp;&emsp;Spring Boot通过利用其他Spring项目（如Spring Framework，Spring Data和Reactor）的支持来提供Kotlin支持。 有关更多信息，请参阅Spring Framework Kotlin支持文档。

&emsp;&emsp;从Spring Boot和Kotlin开始的最简单方法是遵循这个全面的教程。 您可以通过start.spring.io创建新的Kotlin项目。 如果您需要支持，请随意加入Kotlin Slack的#spring频道或使用Stack Overflow上的spring和kotlin标签提问。

### **4.28.1 Requirements**

&emsp;&emsp;Spring Boot支持Kotlin 1.2.x. 要使用Kotlin，org.jetbrains.kotlin:kotlin-stdlib和org.jetbrains.kotlin:kotlin-reflect必须存在于类路径中。 也可以使用kotlin-stdlib变体kotlin-stdlib-jdk7和kotlin-stdlib-jdk8。

&emsp;&emsp;由于Kotlin类默认为final，因此您可能需要配置kotlin-spring插件以自动打开Spring-annotated类，以便可以代理它们。

&emsp;&emsp;在Kotlin中序列化/反序列化JSON数据需要Jackson的Kotlin模块。 在类路径中找到它时会自动注册。 如果Jackson和Kotlin存在但Jackson Kotlin模块不存在，则会记录警告消息。

>如果在start.spring.io上引导Kotlin项目，则默认提供这些依赖项和插件。

### **4.28.2 Null-safety**

&emsp;&emsp;Kotlin的一个关键特性是null安全。 它在编译时处理空值，而不是将问题推迟到运行时并遇到NullPointerException。 这有助于消除常见的错误来源，而无需支付像Optional这样的包装器的成本。 Kotlin还允许使用具有可空值的功能构造，如本Kotlin中关于null安全性的综合指南中所述。

&emsp;&emsp;虽然Java不允许在其类型系统中表示null安全性，但Spring Framework，Spring Data和Reactor现在通过易于使用工具的注释提供其API的安全性。 默认情况下，Kotlin中使用的Java API类型被识别为放宽空检查的平台类型。 Kotlin对JSR 305注释的支持与可空性注释相结合，为Kotlin中的相关Spring API提供了空安全性。

&emsp;&emsp;可以通过使用以下选项添加-Xjsr305编译器标志来配置JSR 305检查：-Xjsr305 = {strict | warn | ignore}。 默认行为与-Xjsr305 = warn相同。 在从Spring API推断出的Kotlin类型中需要考虑null安全性的严格值，但是应该使用Spring API可空性声明甚至可以在次要版本之间发展并且将来可能添加更多检查的知识。

>尚不支持泛型类型参数，varargs和数组元素可空性。 有关最新信息，请参见SPR-15942。 另请注意，Spring Boot自己的API尚未注释。

### **4.28.3 Kotlin API**

**4.28.3.1 运行应用程序**

&emsp;&emsp;Spring Boot提供了一种使用runApplication<MyApplication>(*args)运行应用程序的惯用方法，如以下示例所示：

``` 
import org.springframework.boot.autoconfigure.SpringBootApplication
import org.springframework.boot.runApplication

@SpringBootApplication
class MyApplication

fun main(args: Array<String>) {
	runApplication<MyApplication>(*args)
}
```

&emsp;&emsp;这是SpringApplication.run(MyApplication::class.java，*args)的替代品。 它还允许自定义应用程序，如以下示例所示：

``` 
runApplication<MyApplication>(*args) {
	setBannerMode(OFF)
}
```

**4.28.3.2 扩展**

&emsp;&emsp;Kotlin扩展提供了使用附加功能扩展现有类的能力。 Spring Boot Kotlin API利用这些扩展为现有API添加新的Kotlin特定便利。

&emsp;&emsp;提供了类似于Spring Framework中的Spring Framework for RestOperations提供的TestRestTemplate扩展。 除此之外，扩展使得可以利用Kotlin reified类型参数。

### **4.28.4 依赖管理**

&emsp;&emsp;为了避免在类路径上混合不同版本的Kotlin依赖项，提供了以下Kotlin依赖项的依赖项管理：

- kotlin-reflect
- kotlin-runtime
- kotlin-stdlib
- kotlin-stdlib-jdk7
- kotlin-stdlib-jdk8
- kotlin-stdlib-jre7
- kotlin-stdlib-jre8


&emsp;&emsp;使用Maven，可以通过kotlin.version属性自定义Kotlin版本，并为kotlin-maven-plugin提供插件管理。 使用Gradle，Spring Boot插件会自动将kotlin.version与Kotlin插件的版本对齐。

### **4.28.5 @ConfigurationProperties**

&emsp;&emsp;@ConfigurationProperties目前仅适用于lateinit或nullable var属性（建议使用前者），因为尚不支持由构造函数初始化的不可变类。

``` 
@ConfigurationProperties("example.kotlin")
class KotlinExampleProperties {

	lateinit var name: String

	lateinit var description: String

	val myService = MyService()

	class MyService {

		lateinit var apiToken: String

		lateinit var uri: URI

	}

}
```

>要使用注释处理器生成您自己的元数据，应使用spring-boot-configuration-processordependency配置kapt。

### **4.28.6 测试**

&emsp;&emsp;虽然可以使用JUnit 4（spring-boot-starter-test提供的默认值）来测试Kotlin代码，但建议使用JUnit 5。 JUnit 5允许测试类实例化一次，并重用于所有类的测试。 这使得可以在非静态方法上使用@BeforeAll和@AfterAll注释，这非常适合Kotlin。

&emsp;&emsp;要使用JUnit 5，请从spring-boot-starter-test中排除junit：junit依赖项，添加JUnit 5依赖项，并相应地配置Maven或Gradle插件。 有关更多详细信息，请参阅JUnit 5文档。 您还需要将测试实例生命周期切换为“per-class”。

&emsp;&emsp;为了模拟Kotlin类，建议使用Mockk。 如果需要Mockk等效的Mockito特定的@MockBean和@SpyBean注释，则可以使用SpringMockK，它提供类似的@MockkBean和@SpykBean注释。

### **4.28.7 资源**

**4.28.7.1 进一步阅读**

- Kotlin语言参考
- Kotlin Slack（带有专用的#spring频道）
- Stackoverflow与spring和kotlin标签
- 在浏览器中试用Kotlin
- Kotlin博客
- 很棒的Kotlin
- 教程：使用Spring Boot和Kotlin构建Web应用程序
- 使用Kotlin开发Spring Boot应用程序
- 带有Kotlin，Spring Boot和PostgreSQL的地理空间信使
- 在Spring Framework 5.0中引入Kotlin支持
- Spring Framework 5 Kotlin API，函数式


**4.28.7.2 示例**

- spring-boot-kotlin-demo：常规Spring Boot + Spring Data JPA项目
- mixit：Spring Boot 2 + WebFlux + Reactive Spring Data MongoDB
- spring-kotlin-fullstack：WebFlux Kotlin fullstack示例，其中Kotlin2js用于前端而不是JavaScript或TypeScript
- spring-petclinic-kotlin：Spring PetClinic简单应用的Kotlin版本
- spring-kotlin-deepdive：将Boot 1.0 + Java逐步迁移到Boot 2.0 + Kotlin


## **4.29 接下来要阅读的内容**

&emsp;&emsp;如果您想了解本节中讨论的任何类的更多信息，可以查看Spring Boot API文档，也可以直接浏览源代码。 如果您有具体问题，请查看操作方法部分。

&emsp;&emsp;如果您对Spring Boot的核心功能感到满意，可以继续阅读有关生产就绪功能的内容。

# **5 Spring Boot Actuator: 生产就绪功能**

&emsp;&emsp;Spring Boot包含许多其他功能，可帮助您在将应用程序推送到生产环境时监视和管理应用程序。 您可以选择使用HTTP端点或JMX来管理和监视应用程序。 审核，运行状况和指标收集也可以自动应用于您的应用程序。

## **5.1 启用生产就绪功能**

&emsp;&emsp;spring-boot-actuator模块提供Spring Boot的所有生产就绪功能。 启用这些功能的最简单方法是添加一个spring-boot-starter-actuator'Starter'依赖项。

&emsp;&emsp;执行器的定义 执行器是指用于移动或控制某物的机械装置的制造术语。执行器可以从一个小的变化中产生大量的运动。

&emsp;&emsp;要将执行器添加到基于Maven的项目，请添加以下“Starter”依赖项：

``` 
<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-actuator</artifactId>
	</dependency>
</dependencies>
```

&emsp;&emsp;对于Gradle，请使用以下声明：

``` 
dependencies {
	compile("org.springframework.boot:spring-boot-starter-actuator")
}
```

## **5.2 Endpoints**

&emsp;&emsp;执行器端点允许您监视应用程序并与其交互。SpringBoot包含许多内置端点，并允许您添加自己的端点。例如，health端点提供了基本的应用程序健康信息。

&emsp;&emsp;可以启用或禁用每个端点。 它控制是否创建端点并且其bean存在于应用程序上下文中。 要进行远程访问，还必须通过JMX或HTTP公开端点。 大多数应用程序选择HTTP，其中端点的ID以及/actuator的前缀映射到URL。 例如，默认情况下，运行状况端点映射到/actuator/health。

&emsp;&emsp;有以下与技术无关的端点：

<table>
	<tr>
		<th>ID</th>
		<th>描述</th>
		<th>默认情况下是否启用</th>
	</tr>
	<tr>
		<td>auditevents</td>
		<td>公开当前应用程序的审核事件信息。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>beans</td>
		<td>显示应用程序中所有Spring bean的完整列表。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>caches</td>
		<td>公开可用的缓存</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>conditions</td>
		<td>显示在配置和自动配置类上评估的条件以及它们匹配或不匹配的原因。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>configprops</td>
		<td>显示所有@ConfigurationProperties的有序列表。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>env</td>
		<td>公开Spring的ConfigurableEnvironment中的属性</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>flyway</td>
		<td>显示已应用的任何Flyway数据库迁移。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>health</td>
		<td>显示应用健康信息。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>httptrace</td>
		<td>显示HTTP跟踪信息（默认情况下，最后100个HTTP请求 - 响应交换）。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>info</td>
		<td>显示任意应用信息。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>integrationgraph</td>
		<td>显示Spring集成图。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>loggers</td>
		<td>显示和修改应用程序中日志记录器的配置。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>liquibase</td>
		<td>显示已应用的任何Liquibase数据库迁移。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>metrics</td>
		<td>显示当前应用程序的“指标”信息。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>mappings</td>
		<td>显示所有@RequestMapping路径的有序列表。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>scheduledtasks</td>
		<td>显示应用程序中的计划任务。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>sessions</td>
		<td>允许从Spring Session支持的会话存储中检索和删除用户会话。 使用Spring Session对响应式Web应用程序的支持时不可用。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>shutdown</td>
		<td>允许应用程序正常关闭。</td>
		<td>No</td>
	</tr>
	<tr>
		<td>threaddump</td>
		<td>执行线程转储。</td>
		<td>Yes</td>
	</tr>
</table>

&emsp;&emsp;如果您的应用程序是Web应用程序（Spring MVC，Spring WebFlux或Jersey），则可以使用以下附加端点：

<table>
	<tr>
		<th>ID</th>
		<th>描述</th>
		<th>默认情况下是否启用</th>
	</tr>
	<tr>
		<td>heapdump</td>
		<td>返回一个hprof堆转储文件。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>jolokia</td>
		<td>通过HTTP公开JMX bean（当Jolokia在类路径上时，不适用于WebFlux）。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>logfile</td>
		<td>返回日志文件的内容（如果已设置logging.file或logging.path属性）。 支持使用HTTP Range标头来检索部分日志文件的内容。</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>prometheus</td>
		<td>以Prometheus服务器可以抓取的格式公开指标。</td>
		<td>Yes</td>
	</tr>
</table>

### **5.2.1 启用Endpoints**

&emsp;&emsp;默认情况下，启用除关闭之外的所有端点。 要配置端点的启用，请使用其management.endpoint.<id>.enabled属性。 以下示例启用关闭端点：

``` 
management.endpoint.shutdown.enabled=true
```

&emsp;&emsp;如果您希望端点启用是选择加入而不是选择退出，请将management.endpoints.enabled-by-default属性设置为false，并使用启用了各个端点的属性重新加入。以下示例启用info端点并禁用所有其他端点：

``` 
management.endpoints.enabled-by-default=false
management.endpoint.info.enabled=true
```

>已完全从应用程序上下文中删除已禁用的端点。 如果只想更改端点所暴露的技术，请改用include和exclude属性。

### **5.2.2 暴露Endpoints**

&emsp;&emsp;由于端点可能包含敏感信息，因此应仔细考虑何时公开它们。 下表显示了内置端点的默认暴露规则：

<table>
	<tr>
		<th>ID</th>
		<th>JMX</th>
		<th>Web</th>
	</tr>
	<tr>
		<td>auditevents</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>beans</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>caches</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>conditions</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>configprops</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>env</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>flyway</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>health</td>
		<td>Yes</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>heapdump</td>
		<td>N/A</td>
		<td>No</td>
	</tr>
	<tr>
		<td>httptrace</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>info</td>
		<td>Yes</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>integrationgraph</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>jolokia</td>
		<td>N/A</td>
		<td>No</td>
	</tr>
	<tr>
		<td>logfile</td>
		<td>N/A</td>
		<td>No</td>
	</tr>
	<tr>
		<td>loggers</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>liquibase</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>metrics</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>mappings</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>prometheus</td>
		<td>N/A</td>
		<td>No</td>
	</tr>
	<tr>
		<td>scheduledtasks</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>sessions</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>shutdown</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
	<tr>
		<td>threaddump</td>
		<td>Yes</td>
		<td>No</td>
	</tr>
</table>

&emsp;&emsp;要更改公开的端点，请使用以下特定于技术的包含和排除属性：

<table>
	<tr>
		<th>Property</th>
		<th>Default</th>
	</tr>
	<tr>
		<td>management.endpoints.jmx.exposure.exclude</td>
		<td></td>
	</tr>
	<tr>
		<td>management.endpoints.jmx.exposure.include</td>
		<td>*</td>
	</tr>
	<tr>
		<td>management.endpoints.web.exposure.exclude</td>
		<td></td>
	</tr>
	<tr>
		<td>management.endpoints.web.exposure.include</td>
		<td>info, health</td>
	</tr>
</table>

&emsp;&emsp;include属性列出了公开的端点的ID。 exclude属性列出了不应公开的端点的ID。 exclude属性优先于include属性。 可以使用端点ID列表配置include和exclude属性。

例如，要停止通过JMX公开所有端点并仅显示运行状况和信息端点，请使用以下属性：

``` 
management.endpoints.jmx.exposure.include=health,info
```

&emsp;&emsp;*可用于选择所有端点。 例如，要通过HTTP公开除env和beans端点之外的所有内容，请使用以下属性：

``` 
management.endpoints.web.exposure.include=*
management.endpoints.web.exposure.exclude=env,beans
```

>*在YAML中具有特殊含义，因此如果要包含（或排除）所有端点，请务必添加引号，如以下示例所示： 

>```
management:
  endpoints:
    web:
      exposure:
        include: "*"
>```

&emsp;
>如果您的应用是公开的，我们强烈建议您也保护您的端点。

&emsp;
>如果要在公开端点时实现自己的策略，可以注册EndpointFilter bean。

### **5.2.3 保护HTTP Endpoints**

&emsp;&emsp;您应该像使用任何其他敏感URL一样注意保护HTTP端点。 如果存在Spring Security，则默认使用Spring Security的内容协商策略来保护端点。 例如，如果您希望为HTTP端点配置自定义安全性，只允许具有特定角色的用户访问它们，Spring Boot提供了一些方便的RequestMatcher对象，可以与Spring Security结合使用。

&emsp;&emsp;典型的Spring Security配置可能类似于以下示例：

``` 
@Configuration
public class ActuatorSecurity extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		http.requestMatcher(EndpointRequest.toAnyEndpoint()).authorizeRequests()
				.anyRequest().hasRole("ENDPOINT_ADMIN")
				.and()
			.httpBasic();
	}

}
```

&emsp;&emsp;上面的示例使用EndpointRequest.toAnyEndpoint()将请求与任何端点进行匹配，然后确保所有端点都具有ENDPOINT_ADMIN角色。 EndpointRequest上还提供了其他几种匹配器方法。 有关详细信息，请参阅API文档（HTML或PDF）。

&emsp;&emsp;如果在防火墙后面部署应用程序，您可能希望无需身份验证即可访问所有执行器端点。 您可以通过更改management.endpoints.web.exposure.include属性来执行此操作，如下所示：

``` 
management.endpoints.web.exposure.include=*
```

&emsp;&emsp;此外，如果存在Spring Security，则需要添加自定义安全配置，以允许对端点进行未经身份验证的访问，如以下示例所示：

``` 
@Configuration
public class ActuatorSecurity extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		http.requestMatcher(EndpointRequest.toAnyEndpoint()).authorizeRequests()
			.anyRequest().permitAll();
	}

}
```

### **5.2.4 配置Endpoints**

&emsp;&emsp;端点自动缓存对不带任何参数的读取操作的响应。 要配置端点缓存响应的时间量，请使用其cache.time-to-live属性。 以下示例将beans端点缓存的生存时间设置为10秒：

``` 
management.endpoint.beans.cache.time-to-live=10s
```

>前缀management.endpoint.<name>用于唯一标识正在配置的端点。

&emsp;
>在进行经过身份验证的HTTP请求时，Principal被视为端点的输入，因此不会缓存响应。

### **5.2.5 用于Actuator Web Endpoints的Hypermedia**

&emsp;&emsp;添加了“门户页面”，其中包含指向所有端点的链接。 默认情况下，“门户页面”在/actuator上。

&emsp;&emsp;配置自定义管理上下文路径时，“门户页面”会自动从/actuator移动到管理上下文的根目录。 例如，如果管理上下文路径是/management，则可以从/ management获取门户页面。 当管理上下文路径设置为/时，将禁用门户页面以防止与其他映射冲突的可能性。

### **5.2.6 CORS支持**

&emsp;&emsp;跨源资源共享（CORS）是一种W3C规范，允许您以灵活的方式指定授权的跨域请求类型。 如果您使用Spring MVC或Spring WebFlux，则可以配置Actuator的Web端点以支持此类方案。

&emsp;&emsp;默认情况下禁用CORS支持，仅在设置了management.endpoints.web.cors.allowed-origins属性后才启用CORS支持。 以下配置允许来自example.com域的GET和POST调用：

``` 
management.endpoints.web.cors.allowed-origins=http://example.com
management.endpoints.web.cors.allowed-methods=GET,POST
```

>有关选项的完整列表，请参阅CorsEndpointProperties。

### **5.2.7 实现自定义Endpoints**

&emsp;&emsp;如果添加使用@Endpoint注释的@Bean，则使用@ReadOperation，@WritOperation或@DeleteOperation注释的任何方法都将通过JMX自动公开，并且在Web应用程序中也通过HTTP公开。 可以使用Jersey，Spring MVC或Spring WebFlux通过HTTP公开端点。

&emsp;&emsp;您还可以使用@JmxEndpoint或@WebEndpoint编写特定于技术的端点。 这些端点仅限于各自的技术。 例如，@WebEndpoint仅通过HTTP而不是通过JMX公开。

&emsp;&emsp;您可以使用@EndpointWebExtension和@EndpointJmxExtension编写特定于技术的扩展。 通过这些注释，您可以提供特定于技术的操作来扩充现有端点。

&emsp;&emsp;最后，如果您需要访问特定于Web框架的功能，则可以实现Servlet或Spring @Controller和@RestController端点，但代价是它们无法通过JMX或使用其他Web框架。

**5.2.7.1 接收输入**

&emsp;&emsp;端点上的操作通过其参数接收输入。 通过Web公开时，这些参数的值取自URL的查询参数和JSON请求体。 通过JMX公开时，参数将映射到MBean操作的参数。 默认情况下需要参数。 可以使用@ org.springframework.lang.Nullable对它们进行注释，使它们成为可选项。

&emsp;&emsp;JSON请求正文中的每个根属性都可以映射到端点的参数。 考虑以下JSON请求正文：

``` 
{
	"name": "test",
	"counter": 42
}
```

&emsp;&emsp;这可用于调用带有String name和int counter参数的写操作。


>由于端点与技术无关，因此只能在方法签名中指定简单类型。 特别是不支持使用定义名称和计数器属性的自定义类型声明单个参数。

&emsp;
>要允许将输入映射到操作方法的参数，应使用-parameters编译实现端点的Java代码，并且应使用-java-parameters编译实现端点的Kotlin代码。 如果您使用的是Spring Boot的Gradle插件，或者您使用的是Maven和spring-boot-starter-parent，则会自动执行此操作。

**1）输入类型转换**

&emsp;&emsp;如有必要，传递给端点操作方法的参数将自动转换为所需类型。 在调用操作方法之前，使用ApplicationConversionService实例将通过JMX或HTTP请求接收的输入转换为所需类型。

**5.2.7.2 自定义Web Endpoints**

&emsp;&emsp;@Endpoint，@WebEndpoint或@EndpointWebExtension上的操作将使用Jersey，Spring MVC或Spring WebFlux通过HTTP自动公开。

**1）Web Endpoint请求谓词**

&emsp;&emsp;为Web暴露的端点上的每个操作自动生成请求谓词。

**2）路径**

&emsp;&emsp;谓词的路径由端点的ID和Web暴露的端点的基本路径确定。 默认基本路径是/actuator。 例如，具有ID会话的端点将使用/actuator/sessions作为其在谓词中的路径。

&emsp;&emsp;通过使用@Selector注释操作方法的一个或多个参数，可以进一步定制路径。 这样的参数作为路径变量添加到路径谓词中。 调用端点操作时，变量的值将传递给操作方法。

**3）HTTP方法**

&emsp;&emsp;谓词的HTTP方法由操作类型决定，如下表所示：

<table>
	<tr>
		<th>Operation</th>
		<th>HTTP method</th>
	</tr>
	<tr>
		<td>@ReadOperation</td>
		<td>GET</td>
	</tr>
	<tr>
		<td>@WriteOperation</td>
		<td>POST</td>
	</tr>
	<tr>
		<td>@DeleteOperation</td>
		<td>DELETE</td>
	</tr>
</table>

**3）Consumes**

&emsp;&emsp;对于使用请求主体的@WriteOperation(HTTP POST)，谓词的consumes子句是application/vnd.spring-boot.actuator.v2 + json，application/json。 对于所有其他操作，consumemes子句为空。

**4）Produces**

&emsp;&emsp;谓词的produce子句可以由@DeleteOperation，@ReadOperation和@WriteOperation注释的produce属性确定。 该属性是可选的。 如果未使用，则自动确定produce子句。

&emsp;&emsp;如果操作方法返回void或Void，则produce子句为空。 如果操作方法返回org.springframework.core.io.Resource，则produce子句为application/octet-stream。 对于所有其他操作，produce子句是application/vnd.spring-boot.actuator.v2 + json，application/json。

**5）Web Endpoint响应状态**

&emsp;&emsp;端点操作的默认响应状态取决于操作类型（读取，写入或删除）以及操作返回的内容（如果有）。

&emsp;&emsp;@ReadOperation返回一个值，响应状态为200（OK）。 如果它未返回值，则响应状态将为404（未找到）。

&emsp;&emsp;如果@WriteOperation或@DeleteOperation返回值，则响应状态将为200（OK）。 如果它没有返回值，则响应状态将为204（无内容）。

&emsp;&emsp;如果在没有必需参数的情况下调用操作，或者使用无法转换为所需类型的参数，则不会调用操作方法，并且响应状态将为400（错误请求）。

**6）Web Endpoint范围请求**

&emsp;&emsp;HTTP范围请求可用于请求部分HTTP资源。 使用Spring MVC或Spring Web Flux时，返回org.springframework.core.io.Resource的操作会自动支持范围请求。

>使用Jersey时不支持范围请求。

**7）Web Endpoint安全**

&emsp;&emsp;Web端点或特定于Web的端点扩展上的操作可以接收当前的java.security.Principal或org.springframework.boot.actuate.endpoint.SecurityContext作为方法参数。 前者通常与@Nullable结合使用，为经过身份验证和未经身份验证的用户提供不同的行为。 后者通常用于使用其isUserInRole(String)方法执行授权检查。

**5.2.7.3 Servlet endpoints**

&emsp;&emsp;通过实现一个带有@ServletEndpoint注释的类，Servlet可以作为端点公开，该类也实现了Supplier<EndpointServlet>。 Servlet端点提供与Servlet容器更深层次的集成，但代价是可移植性。 它们旨在用于将现有Servlet作为端点公开。 对于新端点，应尽可能首选@Endpoint和@WebEndpoint注释。

**5.2.7.4 Controller endpoints**

&emsp;&emsp;@ControllerEndpoint和@RestControllerEndpoint可用于实现仅由Spring MVC或Spring WebFlux公开的端点。 使用Spring MVC和Spring WebFlux的标准注释（如@RequestMapping和@GetMapping）映射方法，并将端点的ID用作路径的前缀。 控制器端点提供与Spring的Web框架更深层次的集成，但代价是可移植性。 应尽可能首选@Endpoint和@WebEndpoint注释。

### **5.2.8 健康信息**

&emsp;&emsp;您可以使用运行状况信息来检查正在运行的应用程序的状态。 监视软件经常使用它在生产系统出现故障时提醒某人。 运行状况端点公开的信息取决于management.endpoint.health.show-details属性，该属性可以使用以下值之一进行配置：

<table>
	<tr>
		<th>Name</th>
		<th>描述</th>
	</tr>
	<tr>
		<td>never</td>
		<td>细节永远不会显示。</td>
	</tr>
	<tr>
		<td>when-authorized</td>
		<td>详细信息仅向授权用户显示。 可以使用management.endpoint.health.roles配置授权角色。</td>
	</tr>
	<tr>
		<td>always</td>
		<td>向所有用户显示详细信息。</td>
	</tr>
</table>

&emsp;&emsp;永远不会是默认值。 当用户处于一个或多个端点的角色时，将被视为已获得授权。 如果端点没有配置角色（默认值），则认为所有经过身份验证的用户都已获得授权。 可以使用management.endpoint.health.roles属性配置角色。

>如果您已保护应用程序并希望始终使用，则安全配置必须允许对经过身份验证和未经身份验证的用户访问运行状况终结点。

&emsp;&emsp;健康信息是从HealthIndicatorRegistry的内容中收集的（默认情况下，ApplicationContext中定义的所有HealthIndicator实例。Spring Boot包含许多自动配置的HealthIndicators，您也可以自己编写。默认情况下，最终系统状态由 HealthAggregator根据状态的有序列表对每个HealthIndicator的状态进行排序。排序列表中的第一个状态用作整体健康状态。如果没有HealthIndicator返回HealthAggregator已知的状态，则使用UNKNOWN状态。

>HealthIndicatorRegistry可用于在运行时注册和注销健康指示器。

**5.2.8.1 自动配置的HealthIndicators**

&emsp;&emsp;适当时，Spring Boot会自动配置以下HealthIndicator：

<table>
	<tr>
		<th>Name</th>
		<th>描述</th>
	</tr>
	<tr>
		<td>CassandraHealthIndicator</td>
		<td>检查Cassandra数据库是否已启动。</td>
	</tr>
	<tr>
		<td>CouchbaseHealthIndicator</td>
		<td>检查Couchbase群集是否已启动。</td>
	</tr>
	<tr>
		<td>DiskSpaceHealthIndicator</td>
		<td>检查磁盘空间不足。</td>
	</tr>
	<tr>
		<td>DataSourceHealthIndicator</td>
		<td>检查是否可以获得与DataSource的连接。</td>
	</tr>
	<tr>
		<td>ElasticsearchHealthIndicator</td>
		<td>检查Elasticsearch集群是否已启动。</td>
	</tr>
	<tr>
		<td>InfluxDbHealthIndicator</td>
		<td>检查InfluxDB服务器是否已启动。</td>
	</tr>
	<tr>
		<td>JmsHealthIndicator</td>
		<td>检查JMS代理是否已启动。</td>
	</tr>
	<tr>
		<td>MailHealthIndicator</td>
		<td>检查邮件服务器是否已启动。</td>
	</tr>
	<tr>
		<td>MongoHealthIndicator</td>
		<td>检查Mongo数据库是否已启动。</td>
	</tr>
	<tr>
		<td>Neo4jHealthIndicator</td>
		<td>检查Neo4j服务器是否已启动。</td>
	</tr>
	<tr>
		<td>RabbitHealthIndicator</td>
		<td>检查Rabbit服务器是否已启动。</td>
	</tr>
	<tr>
		<td>RedisHealthIndicator</td>
		<td>检查Redis服务器是否已启动。</td>
	</tr>
	<tr>
		<td>SolrHealthIndicator</td>
		<td>检查Solr服务器是否已启动。</td>
	</tr>
</table>

>您可以通过设置management.health.defaults.enabled属性来禁用它们。

**5.2.8.2 编写自定义HealthIndicators**

&emsp;&emsp;要提供自定义运行状况信息，可以注册实现HealthIndicator接口的Spring bean。 您需要提供health()方法的实现并返回Health响应。 运行状况响应应包括状态，并且可以选择包括要显示的其他详细信息。 以下代码显示了一个示例HealthIndicator实现：

``` 
import org.springframework.boot.actuate.health.Health;
import org.springframework.boot.actuate.health.HealthIndicator;
import org.springframework.stereotype.Component;

@Component
public class MyHealthIndicator implements HealthIndicator {

	@Override
	public Health health() {
		int errorCode = check(); // perform some specific health check
		if (errorCode != 0) {
			return Health.down().withDetail("Error Code", errorCode).build();
		}
		return Health.up().build();
	}

}
```

>给定HealthIndicator的标识符是没有HealthIndicator后缀的bean的名称（如果存在）。 在前面的示例中，健康信息在名为my的条目中可用。

&emsp;&emsp;除了Spring Boot的预定义状态类型之外，Health还可以返回表示新系统状态的自定义状态。 在这种情况下，还需要提供HealthAggregator接口的自定义实现，或者必须使用management.health.status.order配置属性配置默认实现。

例如，假设在您的一个HealthIndicator实现中使用了具有代码FATAL的新状态。 要配置严重性顺序，请将以下属性添加到应用程序属性：

``` 
management.health.status.order=FATAL, DOWN, OUT_OF_SERVICE, UNKNOWN, UP
```

&emsp;&emsp;响应中的HTTP状态代码反映了整体运行状况（例如，UP映射到200，而OUT_OF_SERVICE和DOWN映射到503）。 如果通过HTTP访问运行状况端点，则可能还需要注册自定义状态映射。 例如，以下属性将FATAL映射到503（服务不可用）：

``` 
management.health.status.http-mapping.FATAL=503
```

>如果需要更多控制，可以定义自己的HealthStatusHttpMapper bean。

&emsp;&emsp;下表显示了内置状态的默认状态映射：

<table>
	<tr>
		<th>Status</th>
		<th>Mapping</th>
	</tr>
	<tr>
		<td>DOWN</td>
		<td>SERVICE_UNAVAILABLE (503)</td>
	</tr>
	<tr>
		<td>OUT_OF_SERVICE</td>
		<td>SERVICE_UNAVAILABLE (503)</td>
	</tr>
	<tr>
		<td>UP</td>
		<td>No mapping by default, so http status is 200</td>
	</tr>
	<tr>
		<td>UNKNOWN</td>
		<td>No mapping by default, so http status is 200</td>
	</tr>
</table>

**5.2.8.3 反应健康指标**

&emsp;&emsp;对于反应式应用程序，例如使用Spring WebFlux的应用程序，ReactiveHealthIndicator提供了一个非阻塞的类来获取应用程序运行状况。 与传统的HealthIndicator类似，健康信息从ReactiveHealthIndicatorRegistry的内容中收集（默认情况下，ApplicationContext中定义的所有HealthIndicator和ReactiveHealthIndicator实例。不检查反应API的Regular HealthIndicator在弹性调度程序上执行。

>在响应式应用程序中，ReactiveHealthIndicatorRegistry可用于在运行时注册和取消注册运行状况指示器。

&emsp;&emsp;要从反应式API提供自定义运行状况信息，可以注册实现ReactiveHealthIndicator接口的Spring bean。 以下代码显示了ReactiveHealthIndicator实现的示例：

``` 
@Component
public class MyReactiveHealthIndicator implements ReactiveHealthIndicator {

	@Override
	public Mono<Health> health() {
		return doHealthCheck() //perform some specific health check that returns a Mono<Health>
			.onErrorResume(ex -> Mono.just(new Health.Builder().down(ex).build())));
	}

}
```

>要自动处理错误，请考虑从AbstractReactiveHealthIndicator进行扩展。

**5.2.8.4 自动配置的ReactiveHealthIndicators**

&emsp;&emsp;适当时，Spring Boot会自动配置以下ReactiveHealthIndicator：

<table>
	<tr>
		<th>Name</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>CassandraReactiveHealthIndicator</td>
		<td>检查Cassandra数据库是否已启动。</td>
	</tr>
	<tr>
		<td>CouchbaseReactiveHealthIndicator</td>
		<td>检查Couchbase群集是否已启动。</td>
	</tr>
	<tr>
		<td>MongoReactiveHealthIndicator</td>
		<td>检查Mongo数据库是否已启动。</td>
	</tr>
	<tr>
		<td>RedisReactiveHealthIndicator</td>
		<td>检查Redis服务器是否已启动。</td>
	</tr>
</table>

>如有必要，应采用反应性指标取代常规指标。此外，未显式处理的任何HealthIndicator都会自动包装。

### **5.2.9 应用信息**

&emsp;&emsp;应用程序信息公开从ApplicationContext中定义的所有InfoContributor bean收集的各种信息。 Spring Boot包含许多自动配置的InfoContributor bean，您可以编写自己的bean。

**5.2.9.1 自动配置的InfoContributors**

&emsp;&emsp;适当时，Spring Boot会自动配置以下InfoContributor bean：

<table>
	<tr>
		<th>Name</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>EnvironmentInfoContributor</td>
		<td>在信息键下显示环境中的任何键。</td>
	</tr>
	<tr>
		<td>GitInfoContributor</td>
		<td>如果git.properties文件可用，则公开git信息。</td>
	</tr>
	<tr>
		<td>BuildInfoContributor</td>
		<td>如果META-INF/build-info.properties文件可用，则公开构建信息。</td>
	</tr>
</table>

>可以通过设置management.info.defaults.enabled属性来禁用它们。

**5.2.9.2 定制应用信息**

&emsp;&emsp;您可以通过设置info.* Spring属性来自定义信息端点公开的数据。 信息键下的所有环境属性都会自动公开。 例如，您可以将以下设置添加到application.properties文件中：

``` 
info.app.encoding=UTF-8
info.app.java.source=1.8
info.app.java.target=1.8
```

>您可以在构建时扩展信息属性，而不是对这些值进行硬编码。 假设您使用Maven，您可以按如下方式重写前面的示例：

>```
info.app.encoding=@project.build.sourceEncoding@
info.app.java.source=@java.version@
info.app.java.target=@java.version@
>```

**5.2.9.3 Git提交信息**

&emsp;&emsp;nfo端点的另一个有用功能是它能够在构建项目时发布有关git源代码存储库状态的信息。 如果GitProperties bean可用，则公开git.branch，git.commit.id和git.commit.time属性。

>果git.properties文件在类路径的根目录中可用，则会自动配置GitProperties bean。 有关更多详细信息，请参阅“生成git信息”。

&emsp;&emsp;如果要显示完整的git信息（即git.properties的完整内容），请使用management.info.git.mode属性，如下所示：

``` 
management.info.git.mode=full
```

**5.2.9.4 构建信息**

&emsp;&emsp;如果BuildProperties bean可用，则信息端点还可以发布有关构建的信息。 如果类路径中有META-INF/build-info.properties文件，则会发生这种情况。

>Maven和Gradle插件都可以生成该文件。 有关更多详细信息，请参阅“生成构建信息”。

**5.2.9.5 编写自定义InfoContributors**

&emsp;&emsp;要提供自定义应用程序信息，可以注册实现InfoContributor接口的Spring bean。

&emsp;&emsp;以下示例提供了具有单个值的示例条目：

``` 
import java.util.Collections;

import org.springframework.boot.actuate.info.Info;
import org.springframework.boot.actuate.info.InfoContributor;
import org.springframework.stereotype.Component;

@Component
public class ExampleInfoContributor implements InfoContributor {

	@Override
	public void contribute(Info.Builder builder) {
		builder.withDetail("example",
				Collections.singletonMap("key", "value"));
	}

}
```

&emsp;&emsp;如果到达信息端点，您应该看到包含以下附加条目的响应：

``` 
{
	"example": {
		"key" : "value"
	}
}
```

## **5.3 通过HTTP进行监控和管理**

&emsp;&emsp;如果您正在开发Web应用程序，则Spring Boot Actuator会自动配置所有已启用的端点以通过HTTP公开。 默认约定是使用前缀为/ actuator的端点的id作为URL路径。 例如，健康作为/actuator/health暴露。 提示：Spring MVC，Spring WebFlux和Jersey本身支持Actuator。

### **5.3.1 自定义管理Endpoint路径**

&emsp;&emsp;有时，定制管理端点的前缀很有用。 例如，您的应用程序可能已将/actuator用于其他目的。 您可以使用management.endpoints.web.base-path属性更改管理端点的前缀，如以下示例所示：

``` 
management.endpoints.web.base-path=/manage
```

&emsp;&emsp;前面的application.properties示例将端点从/actuator/{id}更改为/manage/{id}（例如，/manage/info）。

>除非已将管理端口配置为使用其他HTTP端口公开端点，否则management.endpoints.web.base-path与server.servlet.context-path相关。 如果配置了management.server.port，则management.endpoints.web.base-path与manager.server.servlet.context-path相关。

&emsp;&emsp;如果要将端点映射到其他路径，可以使用management.endpoints.web.path-mapping属性。

&emsp;&emsp;以下示例将/actuator/health重新映射到/healthcheck：

``` 
management.endpoints.web.base-path=/
management.endpoints.web.path-mapping.health=healthcheck
```

### **5.3.2 自定义管理服务器端口**

&emsp;&emsp;使用默认HTTP端口公开管理端点是基于云的部署的明智选择。 但是，如果您的应用程序在您自己的数据中心内运行，您可能更喜欢使用不同的HTTP端口公开端点。

&emsp;&emsp;您可以设置management.server.port属性以更改HTTP端口，如以下示例所示：

``` 
management.server.port=8081
```

### **5.3.3 配置特定于管理的SSL**

&emsp;&emsp;配置为使用自定义端口时，还可以使用各种management.server.ssl.*属性为管理服务器配置自己的SSL。 例如，这样做可以在主应用程序使用HTTPS时通过HTTP使管理服务器可用，如以下属性设置所示：

``` 
server.port=8443
server.ssl.enabled=true
server.ssl.key-store=classpath:store.jks
server.ssl.key-password=secret
management.server.port=8080
management.server.ssl.enabled=false
```

&emsp;&emsp;或者，主服务器和管理服务器都可以使用SSL但具有不同的密钥库，如下所示：

``` 
server.port=8443
server.ssl.enabled=true
server.ssl.key-store=classpath:main.jks
server.ssl.key-password=secret
management.server.port=8080
management.server.ssl.enabled=true
management.server.ssl.key-store=classpath:management.jks
management.server.ssl.key-password=secret
```

### **5.3.4 自定义管理服务器地址**

&emsp;&emsp;您可以通过设置management.server.address属性来自定义管理端点可用的地址。 如果您只想在内部或面向操作的网络上侦听或仅侦听来自localhost的连接，那么这样做会非常有用。

>仅当端口与主服务器端口不同时，才能侦听不同的地址。

&emsp;&emsp;以下示例application.properties不允许远程管理连接：

``` 
management.server.port=8081
management.server.address=127.0.0.1
```

### **5.3.5 禁用HTTP Endpoints**

&emsp;&emsp;如果您不希望通过HTTP公开端点，则可以将管理端口设置为-1，如以下示例所示：

``` 
management.server.port=-1
```

&emsp;&emsp;这也可以使用management.endpoints.web.exposure.exclude属性来实现，如以下示例所示：

``` 
management.endpoints.web.exposure.exclude=*
```

## **5.4 JMX的监控和管理**

&emsp;&emsp;Java Management Extensions（JMX）提供了一种监视和管理应用程序的标准机制。 默认情况下，Spring Boot将管理端点公开为org.springframework.boot域下的JMX MBean。

### **5.4.1 自定义MBean名称**

&emsp;&emsp;MBean的名称通常是从端点的id生成的。 例如，运行状况端点公开为org.springframework.boot:type = Endpoint, name = Health。

&emsp;&emsp;如果您的应用程序包含多个Spring ApplicationContext，您可能会发现名称发生冲突。 要解决此问题，可以将spring.jmx.unique-names属性设置为true，以便MBean名称始终是唯一的。

&emsp;&emsp;您还可以自定义公开端点的JMX域。 以下设置显示了在application.properties中执行此操作的示例：

``` 
spring.jmx.unique-names=true
management.endpoints.jmx.domain=com.example.myapp
```

### **5.4.2 禁用JMX Endpoints**

&emsp;&emsp;如果您不想通过JMX公开端点，可以将management.endpoints.jmx.exposure.exclude属性设置为*，如以下示例所示：

``` 
management.endpoints.jmx.exposure.exclude=*
```

### **5.4.3 在HTTP上使用Jolokia实现JMX**

&emsp;&emsp;Jolokia是一个JMX-HTTP桥，它提供了一种访问JMX bean的替代方法。 要使用Jolokia，请包含对org.jolokia的依赖：jolokia-core。 例如，使用Maven，您将添加以下依赖项：

``` 
<dependency>
	<groupId>org.jolokia</groupId>
	<artifactId>jolokia-core</artifactId>
</dependency>
```

&emsp;&emsp;然后可以通过将jolokia或*添加到management.endpoints.web.exposure.include属性来公开Jolokia端点。 然后，您可以在管理HTTP服务器上使用/actuator/jolokia访问它。

**5.4.3.1 自定义Jolokia**

&emsp;&emsp;Jolokia有许多设置，您可以通过设置servlet参数来进行传统配置。 使用Spring Boot，您可以使用application.properties文件。 为此，请在参数前加上management.endpoint.jolokia.config. ，如以下示例所示：

``` 
management.endpoint.jolokia.config.debug=true
```

**5.4.3.2 禁用Jolokia**

&emsp;&emsp;如果您使用Jolokia但不希望Spring Boot配置它，请将management.endpoint.jolokia.enabled属性设置为false，如下所示：

``` 
management.endpoint.jolokia.enabled=false
```

## **5.5 Loggers**

&emsp;&emsp;Spring Boot Actuator包括在运行时查看和配置应用程序日志级别的功能。 您可以查看整个列表或单个记录器的配置，该配置由显式配置的日志记录级别以及日志记录框架为其提供的有效日志记录级别组成。 这些级别可以是以下之一：

- TRACE
- DEBUG
- INFO
- WARN
- ERROR
- FATAL
- OFF
- null


&emsp;&emsp;null表示没有显式配置。

### **5.5.1 配置Logger**

&emsp;&emsp;要配置给定的记录器，请将部分实体POST到资源的URI，如以下示例所示：

``` 
{
	"configuredLevel": "DEBUG"
}
```

>要“重置”记录器的特定级别（并使用默认配置），可以将null值作为configuredLevel传递。

## **5.6 Metrics**

&emsp;&emsp;Spring Boot Actuator为Micrometer提供依赖关系管理和自动配置，Micrometer是一个支持众多监控系统的应用程序指标外观，包括：

- AppOptics
- Atlas
- Datadog
- Dynatrace
- Elastic
- Ganglia
- Graphite
- Humio
- Influx
- JMX
- KairosDB
- New Relic
- Prometheus
- SignalFx
- Simple (in-memory)
- StatsD
- Wavefront

>要了解有关Micrometer功能的更多信息，请参阅其参考文档，特别是概念部分。

### **5.6.1 入门**

&emsp;&emsp;Spring Boot自动配置复合MeterRegistry，并为组合路径中找到的每个受支持的实现添加一个注册表。 在运行时类路径中依赖micrometer-registry- {system}足以让Spring Boot配置注册表。

&emsp;&emsp;大多数注册管理机构都有共同点。例如，即使Micrometer注册表实现位于类路径上，您也可以禁用特定的注册表。 例如，要禁用Datadog：

``` 
management.metrics.export.datadog.enabled=false
```

&emsp;&emsp;Spring Boot还会将任何自动配置的注册表添加到Metrics类的全局静态复合注册表中，除非您明确告诉它不要：

``` 
management.metrics.use-global-registry=false
```

&emsp;&emsp;在注册表中注册任何仪表之前，您可以注册任意数量的MeterRegistryCustomizer bean以进一步配置注册表，例如应用通用标记：

``` 
@Bean
MeterRegistryCustomizer<MeterRegistry> metricsCommonTags() {
	return registry -> registry.config().commonTags("region", "us-east-1");
}
```

&emsp;&emsp;您可以通过更具体地说明泛型类型，将自定义应用于特定的注册表实现：

``` 
@Bean
MeterRegistryCustomizer<GraphiteMeterRegistry> graphiteMetricsNamingConvention() {
	return registry -> registry.config().namingConvention(MY_CUSTOM_CONVENTION);
}
```

&emsp;&emsp;使用该设置，您可以在组件中注入MeterRegistry并注册指标：

``` 
@Component
public class SampleBean {

	private final Counter counter;

	public SampleBean(MeterRegistry registry) {
		this.counter = registry.counter("received.messages");
	}

	public void handleMessage(String message) {
		this.counter.increment();
		// handle message implementation
	}

}
```

&emsp;&emsp;Spring Boot还配置内置仪器（即MeterBinder实现），您可以通过配置或专用注释标记来控制。

### **5.6.2 支持的监控系统**

**5.6.2.1 AppOptics**

&emsp;&emsp;默认情况下，AppOptics注册表会定期将指标推送到api.appoptics.com/v1/measurements。 要将指标导出到SaaS AppOptics，必须提供您的API令牌：

``` 
management.metrics.export.appoptics.api-token=YOUR_TOKEN
```

**5.6.2.2 Atlas**

&emsp;&emsp;默认情况下，度量标准将导出到在本地计算机上运行的Atlas。 可以使用以下方式提供要使用的Atlas服务器的位置：

``` 
management.metrics.export.atlas.uri=http://atlas.example.com:7101/api/v1/publish
```

**5.6.2.3 Datadog**

&emsp;&emsp;Datadog注册表会定期将指标推送到datadoghq。 要将指标导出到Datadog，必须提供您的API密钥：

``` 
management.metrics.export.datadog.api-key=YOUR_KEY
```

&emsp;&emsp;您还可以更改度量标准发送到Datadog的时间间隔：

``` 
management.metrics.export.datadog.step=30s
```

**5.6.2.4 Dynatrace**

&emsp;&emsp;Dynatrace注册表定期将指标推送到配置的URI。 要将指标导出到Dynatrace，必须提供API令牌，设备ID和URI：

``` 
management.metrics.export.dynatrace.api-token=YOUR_TOKEN
management.metrics.export.dynatrace.device-id=YOUR_DEVICE_ID
management.metrics.export.dynatrace.uri=YOUR_URI
```

&emsp;&emsp;您还可以更改度量标准发送到Dynatrace的时间间隔：

``` 
management.metrics.export.dynatrace.step=30s
```

**5.6.2.5 Elastic**

&emsp;&emsp;默认情况下，度量标准将导出到本地计算机上运行的Elastic。 可以使用以下属性提供要使用的弹性服务器的位置：

``` 
management.metrics.export.elastic.host=http://elastic.example.com:8086
```

**5.6.2.6 Ganglia**

&emsp;&emsp;默认情况下，度量标准将导出到本地计算机上运行的Ganglia。 可以使用以下方式提供要使用的Ganglia服务器主机和端口：

``` 
management.metrics.export.ganglia.host=ganglia.example.com
management.metrics.export.ganglia.port=9649
```

**5.6.2.7 Graphite**

&emsp;&emsp;默认情况下，度量标准将导出到在本地计算机上运行的Graphite。 可以使用以下方式提供要使用的Graphite服务器主机和端口：

``` 
management.metrics.export.graphite.host=graphite.example.com
management.metrics.export.graphite.port=9004
```

&emsp;&emsp;Micrometer提供了一个默认的HierarchicalNameMapper，它管理维度计数器id如何映射到平面分层名称。

>要控制此行为，请定义GraphiteMeterRegistry并提供自己的HierarchicalNameMapper。 除非您自己定义，否则提供自动配置的GraphiteConfig和Clock bean：

``` 
@Bean
public GraphiteMeterRegistry graphiteMeterRegistry(GraphiteConfig config, Clock clock) {
	return new GraphiteMeterRegistry(config, clock, MY_HIERARCHICAL_MAPPER);
}
```

**5.6.2.8 Humio**

&emsp;&emsp;默认情况下，Humio注册表会定期将指标推送到cloud.humio.com。 要将指标导出到SaaS Humio，必须提供您的API令牌：

``` 
management.metrics.export.humio.api-token=YOUR_TOKEN
```

&emsp;&emsp;您还应配置一个或多个标记，以标识要推送指标的数据源：

``` 
management.metrics.export.humio.tags.alpha=a
management.metrics.export.humio.tags.bravo=b
```

**5.6.2.9 Influx**

&emsp;&emsp;默认情况下，度量标准将导出到本地计算机上运行的Influx。 要使用的Influx服务器的位置可以使用：

``` 
management.metrics.export.influx.uri=http://influx.example.com:8086
```

**5.6.2.10 JMX**

&emsp;&emsp;Micrometer提供了与JMX的分层映射，主要是作为在本地查看指标的便宜且可移植的方式。 默认情况下，度量标准将导出到度量标准JMX域。 可以使用以下方式提供要使用的域：

``` 
management.metrics.export.jmx.domain=com.example.app.metrics
```

&emsp;&emsp;Micrometer提供了一个默认的HierarchicalNameMapper，它管理维度计数器id如何映射到平面分层名称。

>要控制此行为，请定义JmxMeterRegistry并提供自己的HierarchicalNameMapper。 除非您定义自己的bean，否则会提供自动配置的JmxConfigand Clock bean：

``` 
@Bean
public JmxMeterRegistry jmxMeterRegistry(JmxConfig config, Clock clock) {
	return new JmxMeterRegistry(config, clock, MY_HIERARCHICAL_MAPPER);
}
```

**5.6.2.11 KairosDB**

&emsp;&emsp;默认情况下，度量标准将导出到本地计算机上运行的KairosDB。 可以使用以下方式提供要使用的KairosDB服务器的位置：

``` 
management.metrics.export.kairos.uri=http://kairosdb.example.com:8080/api/v1/datapoints
```

**5.6.2.12 New Relic**

&emsp;&emsp;New Relic注册表定期将指标推送到New Relic。 要将指标导出到New Relic，必须提供您的API密钥和帐户ID：

``` 
management.metrics.export.newrelic.api-key=YOUR_KEY
management.metrics.export.newrelic.account-id=YOUR_ACCOUNT_ID
```

&emsp;&emsp;您还可以更改将度量标准发送到New Relic的时间间隔：

``` 
management.metrics.export.newrelic.step=30s
```

**5.6.2.13 Prometheus**

&emsp;&emsp;Prometheus希望抓取或轮询各个应用实例以获取指标。 Spring Boot在/actuator/prometheus提供执行器端点，以适当的格式呈现Prometheus刮擦。

>默认情况下端点不可用，必须公开，请参阅公开端点以获取更多详细信息。

&emsp;&emsp;以下是要添加到prometheus.yml的示例scrape_config：

``` 
scrape_configs:
  - job_name: 'spring'
	metrics_path: '/actuator/prometheus'
	static_configs:
	  - targets: ['HOST:PORT']
```

**5.6.2.14 SignalFx**

&emsp;&emsp;SignalFx注册表定期将指标推送到SignalFx。 要将指标导出到SignalFx，必须提供您的访问令牌：

``` 
management.metrics.export.signalfx.access-token=YOUR_ACCESS_TOKEN
```

&emsp;&emsp;您还可以更改将指标发送到SignalFx的时间间隔：

``` 
management.metrics.export.signalfx.step=30s
```

**5.6.2.15 Simple**

&emsp;&emsp;Micrometer附带一个简单的内存后端，如果没有配置其他注册表，它将自动用作后备。 这使您可以查看度量标准终结点中收集的度量标准。

&emsp;&emsp;只要您使用任何其他可用后端，内存后端就会自动禁用。 您也可以显式禁用它：

``` 
management.metrics.export.simple.enabled=false
```

**5.6.2.16 StatsD**

&emsp;&emsp;StatsD注册表急切地将UDP上的指标推送到StatsD代理。 默认情况下，度量标准将导出到本地计算机上运行的StatsD代理。 可以使用以下方式提供要使用的StatsD代理主机和端口：

``` 
management.metrics.export.statsd.host=statsd.example.com
management.metrics.export.statsd.port=9125
```

&emsp;&emsp;您还可以更改要使用的StatsD线路协议（默认为Datadog）：

``` 
management.metrics.export.statsd.flavor=etsy
```

**5.6.2.17 Wavefront**

&emsp;&emsp;Wavefront注册表定期将指标推送到Wavefront。 如果要将指标直接导出到Wavefront，则必须提供您的API令牌：

``` 
management.metrics.export.wavefront.api-token=YOUR_API_TOKEN
```

&emsp;&emsp;或者，您可以在环境中使用Wavefront边线或内部代理设置，将指标数据转发到Wavefront API主机：

``` 
management.metrics.export.wavefront.uri=proxy://localhost:2878
```

>如果将度量标准发布到Wavefront代理（如文档中所述），则主机必须采用proxy://HOST:PORT格式。

&emsp;&emsp;您还可以更改将指标发送到Wavefront的时间间隔：

``` 
management.metrics.export.wavefront.step=30s
```

### **5.6.3 支持的指标**

&emsp;&emsp;Spring Boot在适用时注册以下核心指标：

- JVM指标，报告利用率： 各种内存和缓冲池 与垃圾收集有关的统计 线程利用率 加载/卸载的类数
- CPU指标
- 文件描述符指标
- Kafka消费者指标
- Log4j2指标：记录每个级别记录到Log4j2的事件数
- Logback指标：记录每个级别记录到Logback的事件数
- 正常运行时间指标：报告正常运行时间表和表示应用程序绝对启动时间的固定计量表
- Tomcat指标
- Spring集成指标


**5.6.3.1 Spring MVC指标**

&emsp;&emsp;自动配置启用Spring MVC处理的请求的检测。 当management.metrics.web.server.auto-time-requests为true时，将对所有请求进行此检测。 或者，当设置为false时，您可以通过将@Timed添加到请求处理方法来启用检测：

``` 
@RestController
@Timed 
public class MyController {

	@GetMapping("/api/people")
	@Timed(extraTags = { "region", "us-east-1" }) 
	@Timed(value = "all.people", longTask = true) 
	public List<Person> listPeople() { ... }

}
```

1. 一个控制器类，用于在控制器中的每个请求处理程序上启用计时。
2. 一种启用单个端点的方法。 如果您在类上拥有它，则不需要这样做，但可以用于进一步自定义此特定端点的计时器。
3. 使用longTask = true的方法为该方法启用长任务计时器。 长任务计时器需要单独的度量标准名称，并且可以使用短任务计时器进行堆叠。


&emsp;&emsp;默认情况下，使用名称http.server.requests生成度量标准。 可以通过设置management.metrics.web.server.requests-metric-name属性来自定义名称。

&emsp;&emsp;默认情况下，Spring MVC相关指标标有以下信息：

<table>
	<tr>
		<th>Tag</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>exception</td>
		<td>处理请求时抛出的任何异常的简单类名。</td>
	</tr>
	<tr>
		<td>method</td>
		<td>请求的方法（例如，GET或POST）</td>
	</tr>
	<tr>
		<td>outcome</td>
		<td>根据响应的状态代码请求结果。 1xx是INFORMATIONAL，2xx是SUCCESS，3xx是REDIRECTION，4xx CLIENT_ERROR，5xx是SERVER_ERROR</td>
	</tr>
	<tr>
		<td>status</td>
		<td>响应的HTTP状态代码（例如，200或500）</td>
	</tr>
	<tr>
		<td>uri</td>
		<td>如果可能，在变量替换之前请求URI模板（例如，/api/person/{id}）</td>
	</tr>
</table>

&emsp;&emsp;要自定义标记，请提供实现WebMvcTagsProvider的@Bean。

**5.6.3.2 Spring WebFlux指标**

&emsp;&emsp;自动配置可以检测WebFlux控制器和功能处理程序处理的所有请求。

&emsp;&emsp;默认情况下，使用名称http.server.requests生成度量标准。 您可以通过设置management.metrics.web.server.requests-metric-name属性来自定义名称。

&emsp;&emsp;默认情况下，与WebFlux相关的指标标记有以下信息：

<table>
	<tr>
		<th>Tag</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>exception</td>
		<td>处理请求时抛出的任何异常的简单类名。</td>
	</tr>
	<tr>
		<td>method</td>
		<td>请求的方法（例如，GET或POST）</td>
	</tr>
	<tr>
		<td>outcome</td>
		<td>根据响应的状态代码请求结果。 1xx是INFORMATIONAL，2xx是SUCCESS，3xx是REDIRECTION，4xx CLIENT_ERROR，5xx是SERVER_ERROR</td>
	</tr>
	<tr>
		<td>status</td>
		<td>响应的HTTP状态代码（例如，200或500）</td>
	</tr>
	<tr>
		<td>uri</td>
		<td>如果可能，在变量替换之前请求URI模板（例如，/api/person/{id}）</td>
	</tr>
</table>

&emsp;&emsp;要自定义标记，请提供实现WebFluxTagsProvider的@Bean。

**5.6.3.3 Jersey Server指标**

&emsp;&emsp;自动配置可以对Jersey JAX-RS实现处理的请求进行检测。 当management.metrics.web.server.auto-time-requests为true时，将对所有请求进行此检测。 或者，当设置为false时，您可以通过将@Timed添加到请求处理方法来启用检测：

``` 
@Component
@Path("/api/people")
@Timed 
public class Endpoint {
	@GET
	@Timed(extraTags = { "region", "us-east-1" }) 
	@Timed(value = "all.people", longTask = true) 
	public List<Person> listPeople() { ... }
}
```

1. 在资源类上，为资源中的每个请求处理程序启用计时。
2. 在启用单个端点的方法上。 如果您在类上拥有它，则不需要这样做，但可以用于进一步自定义此特定端点的计时器。
3. 在具有longTask = true的方法上，为该方法启用长任务计时器。 长任务计时器需要单独的度量标准名称，并且可以使用短任务计时器进行堆叠。


&emsp;&emsp;默认情况下，使用名称http.server.requests生成度量标准。 可以通过设置management.metrics.web.server.requests-metric-name属性来自定义名称。

&emsp;&emsp;默认情况下，Jersey服务器指标标记有以下信息：

<table>
	<tr>
		<th>Tag</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>exception</td>
		<td>处理请求时抛出的任何异常的简单类名。</td>
	</tr>
	<tr>
		<td>method</td>
		<td>请求的方法（例如，GET或POST）</td>
	</tr>
	<tr>
		<td>outcome</td>
		<td>根据响应的状态代码请求结果。 1xx是INFORMATIONAL，2xx是SUCCESS，3xx是REDIRECTION，4xx CLIENT_ERROR，5xx是SERVER_ERROR</td>
	</tr>
	<tr>
		<td>status</td>
		<td>响应的HTTP状态代码（例如，200或500）</td>
	</tr>
	<tr>
		<td>uri</td>
		<td>如果可能，在变量替换之前请求URI模板（例如，/api/person/{id}）</td>
	</tr>
</table>

&emsp;&emsp;要自定义标记，请提供实现JerseyTagsProvider的@Bean。

**5.6.3.4 HTTP Client指标**

&emsp;&emsp;Spring Boot Actuator管理RestTemplate和WebClient的工具。 为此，您必须注入一个自动配置的构建器并使用它来创建实例：

- 用于RestTemplate的RestTemplateBuilder
- 用于WebClient的WebClient.Builder


&emsp;&emsp;也可以手动应用负责此检测的定制程序，即MetricsRestTemplateCustomizer和MetricsWebClientCustomizer。

&emsp;&emsp;默认情况下，使用名称http.client.requests生成度量标准。 可以通过设置management.metrics.web.client.requests-metric-name属性来自定义名称。

&emsp;&emsp;默认情况下，已检测客户端生成的度量标准使用以下信息进行标记：

- method，请求的方法（例如，GET或POST）。
- uri，变量替换之前的请求URI模板（如果可能）（例如，/api/person/{id}）。
- status，响应的HTTP状态代码（例如，200或500）。
- clientName，URI的主机部分。


&emsp;&emsp;要自定义标记，并根据您选择的客户端，您可以提供实现RestTemplateExchangeTagsProvider或WebClientExchangeTagsProvider的@Bean。 RestTemplateExchangeTags和WebClientExchangeTags中有方便的静态函数。

**5.6.3.5 Cache指标**

&emsp;&emsp;自动配置允许启动时所有可用缓存的检测，其中指标以缓存为前缀。 缓存检测针对一组基本指标进行了标准化。 此外，还提供了特定于缓存的指标。

&emsp;&emsp;支持以下缓存库：

- Caffeine
- EhCache 2
- Hazelcast
- 任何兼容的JCache（JSR-107）实现


&emsp;&emsp;度量标准由缓存的名称和从bean名称派生的CacheManager的名称标记。

>只有启动时可用的缓存才会绑定到注册表。 对于在启动阶段后即时或以编程方式创建的缓存，需要显式注册。 CacheMetricsRegistrar bean可用于简化该过程。

**5.6.3.6 DataSource指标**

&emsp;&emsp;自动配置使用名为jdbc的度量标准启用所有可用DataSource对象的检测。 数据源检测会生成表示池中当前活动，最大允许和最小允许连接的计量器。 这些仪表中的每一个都有一个以jdbc为前缀的名称。

&emsp;&emsp;度量标准也由基于bean名称计算的DataSource的名称标记。

>默认情况下，Spring Boot为所有支持的数据源提供元数据; 如果开箱即用不支持您喜欢的数据源，则可以添加其他DataSourcePoolMetadataProvider bean。 有关示例，请参阅DataSourcePoolMetadataProvidersConfiguration。

&emsp;&emsp;此外，Hikari特定的指标用hikaricp前缀公开。 每个度量标准都由池的名称标记（可以使用spring.datasource.name控制）。

**5.6.3.7 Hibernate指标**

&emsp;&emsp;自动配置启用所有可用Hibernate EntityManagerFactory实例的检测，这些实例使用名为hibernate的度量标准启用统计信息。

&emsp;&emsp;度量标准也由从bean名称派生的EntityManagerFactory的名称标记。

&emsp;&emsp;要启用统计信息，必须将标准JPA属性hibernate.generate_statistics设置为true。 您可以在自动配置的EntityManagerFactory上启用它，如以下示例所示：

``` 
spring.jpa.properties.hibernate.generate_statistics=true
```

**5.6.3.8 RabbitMQ指标**

&emsp;&emsp;自动配置将使用名为rabbitmq的度量标准启用所有可用RabbitMQ连接工厂的检测。

### **5.6.4 注册自定义指标**

&emsp;&emsp;要注册自定义指标，请将MeterRegistry注入组件，如以下示例所示：

``` 
class Dictionary {

	private final List<String> words = new CopyOnWriteArrayList<>();

	Dictionary(MeterRegistry registry) {
		registry.gaugeCollectionSize("dictionary.size", Tags.empty(), this.words);
	}

	// …

}
```

&emsp;&emsp;如果您发现跨组件或应用程序重复检测一套度量标准，则可以将此套件封装在MeterBinder实现中。 默认情况下，所有MeterBinder bean的指标都将自动绑定到Spring管理的MeterRegistry。

### **5.6.5 定制个人指标**

&emsp;&emsp;如果需要将自定义应用于特定的Meter实例，可以使用io.micrometer.core.instrument.config.MeterFilter接口。 默认情况下，所有MeterFilter bean都将自动应用于MeterRegistry.Config。

例如，如果要将mytag.region标记重命名为mytag.area以获取以com.example开头的所有仪表ID，则可以执行以下操作：

``` 
@Bean
public MeterFilter renameRegionTagMeterFilter() {
	return MeterFilter.renameTag("com.example", "mytag.region", "mytag.area");
}
```

**5.6.5.1 常用标签**

&emsp;&emsp;通用标签通常用于操作环境中的维度向下钻取，例如主机，实例，区域，堆栈等。共用标签应用于所有仪表，并且可以按照以下示例所示进行配置：

``` 
management.metrics.tags.region=us-east-1
management.metrics.tags.stack=prod
```

&emsp;&emsp;上面的示例将region和stack标签添加到所有仪表，其值分别为us-east-1和prod。

>如果您使用Graphite，常用标签的顺序很重要。 由于使用此方法无法保证常用标记的顺序，因此建议Graphite用户定义自定义MeterFilter。

**5.6.5.2 单位属性**

&emsp;&emsp;除了MeterFilter bean之外，还可以使用属性在每米的基础上应用一组有限的自定义。 单位自定义适用于以给定名称开头的所有仪表ID。 例如，以下将禁用任何具有以example.remote开头的ID的仪表

``` 
management.metrics.enable.example.remote=false
```

&emsp;&emsp;以下属性允许单位定制：

<table>
	<tr>
		<th>Property</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>management.metrics.enable</td>
		<td>是否拒绝仪表发射任何指标。</td>
	</tr>
	<tr>
		<td>management.metrics.distribution.percentiles-histogram</td>
		<td>是否发布适合于计算聚合(跨维度)百分位数近似的直方图。</td>
	</tr>
	<tr>
		<td>management.metrics.distribution.minimum-expected-value,management.metrics.distribution.maximum-expected-value</td>
		<td>通过限制预期值的范围来发布较少的直方图桶。</td>
	</tr>
	<tr>
		<td>management.metrics.distribution.percentiles</td>
		<td>发布应用程序中计算的百分位数</td>
	</tr>
	<tr>
		<td>management.metrics.distribution.sla</td>
		<td>使用SLA定义的桶发布累积直方图。</td>
	</tr>
</table>

&emsp;&emsp;有关百分位数 - 直方图，百分位数和斜率背后的概念的更多详细信息，请参阅micrometer文档的“直方图和百分位数”部分。

### **5.6.6 指标端点**

&emsp;&emsp;Spring Boot提供了一个度量端点，可以在诊断中用于检查应用程序收集的度量标准。 默认情况下端点不可用，必须公开，请参阅公开端点以获取更多详细信息。

&emsp;&emsp;导航到/actuator/metrics会显示可用的仪表名称列表。 您可以向下钻取以查看有关特定仪表的信息，方法是将其名称作为选择器，例如，/actuator/metrics/jvm.memory.max。

>您在这里使用的名称应该与代码中使用的名称相匹配，而不是在命名之后使用的名称。换句话说，如果jvm.memory.max在Prometheus中以jvm_memory_max的形式出现，因为它的下划线式命名约定，那么在检查度量端点中的仪表时，仍然应该使用jvm.memory.max作为选择器。

&emsp;&emsp;您还可以在URL的末尾添加任意数量的tag = KEY:VALUE查询参数，以便按比例向下钻取仪表，例如/actuator/metrics/jvm.memory.max?tag=area:nonheap。

>报告的测量值是与仪表名称和已应用的任何标签匹配的所有仪表的统计数据的总和。 因此，在上面的示例中，返回的“Value”统计信息是堆的“Code Cache”，“Compressed Class Space”和“Metaspace”区域的最大内存占用量的总和。 如果您只想查看“Metaspace”的最大大小，可以添加一个额外的tag = id:Metaspace，即/actuator/metrics/jvm.memory.max?tag=area:nonheap&tag=id:Metaspace。

## **5.7 审计**

&emsp;&emsp;一旦Spring Security发挥作用，Spring Boot Actuator就有一个灵活的审计框架，可以发布事件（默认情况下，“身份验证成功”，“失败”和“访问被拒绝”例外）。 此功能对于报告和基于身份验证失败实施锁定策略非常有用。 要自定义已发布的安全事件，您可以提供自己的AbstractAuthenticationAuditListener和AbstractAuthorizationAuditListener实现。

&emsp;&emsp;您还可以将审计服务用于您自己的业务事件。 为此，请将现有的AuditEventRepository注入您自己的组件并直接使用它或使用Spring ApplicationEventPublisher（通过实现ApplicationEventPublisherAware）发布AuditApplicationEvent。

## **5.8 HTTP跟踪**

&emsp;&emsp;将自动为所有HTTP请求启用跟踪。 您可以查看httptrace端点并获取有关最近100次请求 - 响应交换的基本信息。

### **5.8.1 自定义HTTP跟踪**

&emsp;&emsp;要自定义每个跟踪中包含的项，请使用management.trace.http.include配置属性。 对于高级自定义，请考虑注册自己的HttpExchangeTracer实现。

&emsp;&emsp;默认情况下，使用存储最后100个请求 - 响应交换的跟踪的InMemoryHttpTraceRepository。 如果需要扩展容量，可以定义自己的InMemoryHttpTraceRepository bean实例。 您还可以创建自己的替代HttpTraceRepository实现。

## **5.9 进程监控**

&emsp;&emsp;在spring-boot模块中，您可以找到两个类来创建通常对进程监视有用的文件：

- ApplicationPidFileWriter创建一个包含应用程序PID的文件（默认情况下，在应用程序目录中，文件名为application.pid）。
- WebServerPortFileWriter创建一个或多个文件，其中包含正在运行的Web服务器的端口（默认情况下，在应用程序目录中，文件名为application.port）。


&emsp;&emsp;默认情况下，这些编写器未激活，但您可以启用：

- 通过扩展配置
- 通过编程控制


### **5.9.1 扩展配置**

&emsp;&emsp;在META-INF/spring.factories文件中，您可以激活写入PID文件的侦听器，如以下示例所示：

``` 
org.springframework.context.ApplicationListener=\
org.springframework.boot.context.ApplicationPidFileWriter,\
org.springframework.boot.web.context.WebServerPortFileWriter
```

### **5.9.2 编程**

&emsp;&emsp;您还可以通过调用SpringApplication.addListeners(...)方法并传递相应的Writer对象来激活侦听器。 此方法还允许您在Writer构造函数中自定义文件名和路径。

## **5.10 Cloud Foundry支持**

&emsp;&emsp;Spring Boot的执行器模块包括在部署到兼容的Cloud Foundry实例时激活的其他支持。 /cloudfoundryapplication路径为所有@Endpoint bean提供了另一种安全路由。

&emsp;&emsp;扩展支持允许使用Spring Boot执行器信息扩充Cloud Foundry管理UI（例如可用于查看已部署应用程序的Web应用程序）。 例如，应用程序状态页面可以包括完整的健康信息而不是典型的“运行”或“停止”状态。

>常规用户无法直接访问/cloudfoundryapplication路径。 为了使用端点，必须与请求一起传递有效的UAA令牌。

### **5.10.1 禁用Extended Cloud Foundry Actuator支持**

&emsp;&emsp;如果要完全禁用/cloudfoundryapplication端点，可以将以下设置添加到application.properties文件中：

``` 
management.cloudfoundry.enabled=false
```

### **5.10.2 Cloud Foundry自签名证书**

&emsp;&emsp;默认情况下，/cloudfoundryapplication端点的安全验证会对各种Cloud Foundry服务进行SSL调用。 如果您的Cloud Foundry UAA或Cloud Controller服务使用自签名证书，则需要设置以下属性：

``` 
management.cloudfoundry.skip-ssl-validation=true
```

### **5.10.3 自定义上下文路径**

&emsp;&emsp;如果服务器的上下文路径已配置为/以外的任何其他内容，则Cloud Foundry端点将无法在应用程序的根目录中使用。 例如，如果server.servlet.context-path = /app，Cloud Foundry端点将在/app/cloudfoundryapplication/*中提供。

&emsp;&emsp;如果您希望Cloud Foundry端点始终在/cloudfoundryapplication/*处可用，则无论服务器的上下文路径如何，您都需要在应用程序中明确配置它。 配置将根据使用的Web服务器而有所不同。 对于Tomcat，可以添加以下配置：

``` 
@Bean
public TomcatServletWebServerFactory servletWebServerFactory() {
	return new TomcatServletWebServerFactory() {

		@Override
		protected void prepareContext(Host host,
				ServletContextInitializer[] initializers) {
			super.prepareContext(host, initializers);
			StandardContext child = new StandardContext();
			child.addLifecycleListener(new Tomcat.FixContextListener());
			child.setPath("/cloudfoundryapplication");
			ServletContainerInitializer initializer = getServletContextInitializer(
					getContextPath());
			child.addServletContainerInitializer(initializer, Collections.emptySet());
			child.setCrossContext(true);
			host.addChild(child);
		}

	};
}

private ServletContainerInitializer getServletContextInitializer(String contextPath) {
	return (c, context) -> {
		Servlet servlet = new GenericServlet() {

			@Override
			public void service(ServletRequest req, ServletResponse res)
					throws ServletException, IOException {
				ServletContext context = req.getServletContext()
						.getContext(contextPath);
				context.getRequestDispatcher("/cloudfoundryapplication").forward(req,
						res);
			}

		};
		context.addServlet("cloudfoundry", servlet).addMapping("/*");
	};
}
```

## **5.11 接下来要阅读的内容**

&emsp;&emsp;如果您想探索本章中讨论的一些概念，您可以查看执行器示例应用程序。 您还可能想了解Graphite等图形工具。

&emsp;&emsp;否则，您可以继续阅读有关“部署选项”的信息，或者继续阅读有关Spring Boot构建工具插件的一些深入信息。

# **6 部署Spring Boot应用程序**

&emsp;&emsp;Spring Boot的灵活打包选项在部署应用程序时提供了大量选择。 您可以将Spring Boot应用程序部署到各种云平台，容器映像（如Docker）或虚拟/真实计算机。

&emsp;&emsp;本节介绍一些更常见的部署方案。

## **6.1 部署到Cloud**

&emsp;&emsp;Spring Boot的可执行jar是现成的，适用于大多数流行的云PaaS（平台即服务）提供商。 这些提供商往往要求您“自带容器”。 它们管理应用程序进程（而不是具体的Java应用程序），因此它们需要一个中间层，使您的应用程序适应云的运行过程概念。

&emsp;&emsp;两个流行的云提供商Heroku和Cloud Foundry采用“buildpack”方法。 buildpack将您部署的代码包装在启动应用程序所需的任何内容中。 它可能是JDK，也是对java，嵌入式Web服务器或完整应用程序服务器的调用。 buildpack是可插拔的，但理想情况下，您应该能够尽可能少地进行自定义。 这减少了不受您控制的功能的占用空间。 它最大限度地减少了开发和生产环境之间的差异。

&emsp;&emsp;理想情况下，您的应用程序（如Spring Boot可执行jar）具有在其中运行打包所需的所有内容。

&emsp;&emsp;在本节中，我们将了解如何在“入门”部分中开发并在云中运行的简单应用程序。

### **6.1.1 Cloud Foundry**

&emsp;&emsp;如果未指定其他buildpack，Cloud Foundry将提供默认的构建包。 Cloud Foundry Java buildpack对Spring应用程序（包括Spring Boot）提供了出色的支持。 您可以部署独立的可执行jar应用程序以及传统的.war打包应用程序。

&emsp;&emsp;构建应用程序（例如，使用mvn clean package）并安装cf命令行工具后，使用cf push命令部署应用程序，将路径替换为已编译的.jar。 在推送应用程序之前，请务必使用cf命令行客户端登录。 以下行显示使用cf push命令部署应用程序：

``` 
$ cf push acloudyspringtime -p target/demo-0.0.1-SNAPSHOT.jar
```

>在前面的示例中，我们将acloudyspringtime替换为您给出的任何值cf作为应用程序的名称。

&emsp;&emsp;有关更多选项，请参阅cf push文档。 如果同一目录中存在Cloud Foundry manifest.yml文件，则会考虑该文件。

&emsp;&emsp;此时，cf开始上传您的应用程序，生成类似于以下示例的输出：

``` 
Uploading acloudyspringtime... OK
Preparing to start acloudyspringtime... OK
-----> Downloaded app package (8.9M)
-----> Java Buildpack Version: v3.12 (offline) | https://github.com/cloudfoundry/java-buildpack.git#6f25b7e
-----> Downloading Open Jdk JRE 1.8.0_121 from https://java-buildpack.cloudfoundry.org/openjdk/trusty/x86_64/openjdk-1.8.0_121.tar.gz (found in cache)
       Expanding Open Jdk JRE to .java-buildpack/open_jdk_jre (1.6s)
-----> Downloading Open JDK Like Memory Calculator 2.0.2_RELEASE from https://java-buildpack.cloudfoundry.org/memory-calculator/trusty/x86_64/memory-calculator-2.0.2_RELEASE.tar.gz (found in cache)
       Memory Settings: -Xss349K -Xmx681574K -XX:MaxMetaspaceSize=104857K -Xms681574K -XX:MetaspaceSize=104857K
-----> Downloading Container Certificate Trust Store 1.0.0_RELEASE from https://java-buildpack.cloudfoundry.org/container-certificate-trust-store/container-certificate-trust-store-1.0.0_RELEASE.jar (found in cache)
       Adding certificates to .java-buildpack/container_certificate_trust_store/truststore.jks (0.6s)
-----> Downloading Spring Auto Reconfiguration 1.10.0_RELEASE from https://java-buildpack.cloudfoundry.org/auto-reconfiguration/auto-reconfiguration-1.10.0_RELEASE.jar (found in cache)
Checking status of app 'acloudyspringtime'...
  0 of 1 instances running (1 starting)
  ...
  0 of 1 instances running (1 starting)
  ...
  0 of 1 instances running (1 starting)
  ...
  1 of 1 instances running (1 running)

App started
```

&emsp;&emsp;恭喜！ 该应用程序现已上线！

&emsp;&emsp;应用程序启动后，您可以使用cf apps命令验证已部署应用程序的状态，如以下示例所示：

``` 
$ cf apps
Getting applications in ...
OK

name                 requested state   instances   memory   disk   urls
...
acloudyspringtime    started           1/1         512M     1G     acloudyspringtime.cfapps.io
...
```

&emsp;&emsp;一旦Cloud Foundry确认您的应用程序已部署，您应该能够在给定的URI处找到该应用程序。 在前面的示例中，您可以在http://acloudyspringtime.cfapps.io/找到它。

**6.1.1.1 绑定到服务**

&emsp;&emsp;默认情况下，有关正在运行的应用程序的元数据以及服务连接信息将作为环境变量公开给应用程序（例如：$ VCAP_SERVICES）。 此体系结构决策归功于Cloud Foundry的多语言（任何语言和平台都可以作为buildpack支持）。 进程范围的环境变量与语言无关。

&emsp;&emsp;环境变量并不总是适用于最简单的API，因此Spring Boot会自动提取它们并将数据展平为可通过Spring的Environment抽象访问的属性，如以下示例所示：

``` 
@Component
class MyBean implements EnvironmentAware {

	private String instanceId;

	@Override
	public void setEnvironment(Environment environment) {
		this.instanceId = environment.getProperty("vcap.application.instance_id");
	}

	// ...

}
```

&emsp;&emsp;所有Cloud Foundry属性都以vcap为前缀。 您可以使用vcap属性来访问应用程序信息（例如应用程序的公共URL）和服务信息（例如数据库凭据）。 有关完整的详细信息，请参阅“CloudFoundryVcapEnvironmentPostProcessor”Javadoc。

>Spring Cloud Connectors项目更适合配置DataSource等任务。 Spring Boot包括自动配置支持和spring-boot-starter-cloud-connectors启动器。

### **6.1.2 Heroku**

&emsp;&emsp;Heroku是另一个流行的PaaS平台。 要自定义Heroku构建，请提供Procfile，它提供部署应用程序所需的代码。 Heroku为Java应用程序分配一个端口，然后确保路由到外部URI。

&emsp;&emsp;您必须将应用程序配置为侦听正确的端口。 以下示例显示了启动REST应用程序的Procfile：

``` 
web: java -Dserver.port=$PORT -jar target/demo-0.0.1-SNAPSHOT.jar
```

&emsp;&emsp;Spring Boot使-D参数可用作可从Spring Environment实例访问的属性。 server.port配置属性被提供给嵌入式Tomcat，Jetty或Undertow实例，然后在启动时使用该端口。 $PORT环境变量由Heroku PaaS分配给我们。

&emsp;&emsp;这应该是你需要的一切。 Heroku部署最常见的部署工作流是将代码推送到生产环境，如以下示例所示：

``` 
$ git push heroku master

Initializing repository, done.
Counting objects: 95, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (78/78), done.
Writing objects: 100% (95/95), 8.66 MiB | 606.00 KiB/s, done.
Total 95 (delta 31), reused 0 (delta 0)

-----> Java app detected
-----> Installing OpenJDK 1.8... done
-----> Installing Maven 3.3.1... done
-----> Installing settings.xml... done
-----> Executing: mvn -B -DskipTests=true clean install

       [INFO] Scanning for projects...
       Downloading: https://repo.spring.io/...
       Downloaded: https://repo.spring.io/... (818 B at 1.8 KB/sec)
		....
       Downloaded: http://s3pository.heroku.com/jvm/... (152 KB at 595.3 KB/sec)
       [INFO] Installing /tmp/build_0c35a5d2-a067-4abc-a232-14b1fb7a8229/target/...
       [INFO] Installing /tmp/build_0c35a5d2-a067-4abc-a232-14b1fb7a8229/pom.xml ...
       [INFO] ------------------------------------------------------------------------
       [INFO] BUILD SUCCESS
       [INFO] ------------------------------------------------------------------------
       [INFO] Total time: 59.358s
       [INFO] Finished at: Fri Mar 07 07:28:25 UTC 2014
       [INFO] Final Memory: 20M/493M
       [INFO] ------------------------------------------------------------------------

-----> Discovering process types
       Procfile declares types -> web

-----> Compressing... done, 70.4MB
-----> Launching... done, v6
       http://agile-sierra-1405.herokuapp.com/ deployed to Heroku

To git@heroku.com:agile-sierra-1405.git
 * [new branch]      master -> master
```

&emsp;&emsp;您的应用程序现在应该在Heroku上启动并运行。

### **6.1.3 OpenShift**

&emsp;&emsp;OpenShift是Kubernetes容器编排平台的Red Hat公共（和企业）扩展。 与Kubernetes类似，OpenShift有许多选项可用于安装基于Spring Boot的应用程序。

&emsp;&emsp;OpenShift有许多资源描述如何部署Spring Boot应用程序，包括：

- 使用S2I构建器
- 构建指南
- 在Wildfly上作为传统Web应用程序运行
- OpenShift Commons简报


### **6.1.4 Amazon Web Services (AWS)**

&emsp;&emsp;Amazon Web Services提供了多种方法来安装基于Spring Boot的应用程序，既可以作为传统的Web应用程序（战争），也可以作为带有嵌入式Web服务器的可执行jar文件。 选项包括：

- AWS Elastic Beanstalk
- AWS Code Deploy
- AWS OPS Works
- AWS Cloud Formation
- AWS Container Registry


&emsp;&emsp;每个都有不同的功能和定价模型。 在本文档中，我们仅描述了最简单的选项：AWS Elastic Beanstalk。

**6.1.4.1 AWS Elastic Beanstalk**

&emsp;&emsp;如官方Elastic Beanstalk Java指南中所述，部署Java应用程序有两个主要选项。 您可以使用“Tomcat平台”或“Java SE平台”。

**1）使用Tomcat平台**

&emsp;&emsp;此选项适用于生成war文件的Spring Boot项目。 无需特殊配置。 您只需遵循官方指南即可。

**2）使用Java SE平台**

&emsp;&emsp;此选项适用于生成jar文件并运行嵌入式Web容器的Spring Boot项目。 Elastic Beanstalk环境在端口80上运行nginx实例以代理在端口5000上运行的实际应用程序。要配置它，请将以下行添加到application.properties文件中：

``` 
server.port=5000
```

>默认情况下，Elastic Beanstalk上传源并在AWS中编译它们。 但是，最好上传二进制文件。 为此，请在.elasticbeanstalk/config.yml文件中添加类似于以下内容的行： 

>```
deploy:
	artifact: target/demo-0.0.1-SNAPSHOT.jar
>```

&emsp;
>默认情况下，Elastic Beanstalk环境是负载均衡的。 负载均衡器具有显着的成本。 要避免此成本，请将环境类型设置为“单实例”，如Amazon文档中所述。 您还可以使用CLI和以下命令创建单实例环境： 

>```
eb create -s
>```

**6.1.4.2 总结**

&emsp;&emsp;这是访问AWS的最简单方法之一，但还有更多内容需要涉及，例如如何将Elastic Beanstalk集成到任何CI / CD工具中，使用Elastic Beanstalk Maven插件而不是CLI等。 有一篇博文更详细地介绍了这些主题。

### **6.1.5 Boxfuse 和 Amazon Web Services**

&emsp;&emsp;Boxfuse的工作原理是将Spring Boot可执行jar或war转换为可在VirtualBox或AWS上无需部署的最小VM映像。 Boxfuse带有Spring Boot的深度集成，并使用Spring Boot配置文件中的信息自动配置端口和运行状况检查URL。 Boxfuse利用这些信息来处理它产生的图像以及它提供的所有资源（实例，安全组，弹性负载均衡器等）。

&emsp;&emsp;创建Boxfuse帐户后，将其连接到您的AWS账户，安装最新版本的Boxfuse Client，并确保该应用程序已由Maven或Gradle构建（例如，使用mvn clean package），您可以 使用类似于以下的命令将Spring Boot应用程序部署到AWS：

``` 
$ boxfuse run myapp-1.0.jar -env=prod
```

&emsp;&emsp;有关更多选项，请参阅boxfuse运行文档。 如果当前目录中存在boxfuse.conf文件，则会考虑该文件。

>默认情况下，Boxfuse在启动时激活名为boxfuse的Spring配置文件。 如果您的可执行jar或war包含application-boxfuse.properties文件，Boxfuse将其配置基于它包含的属性。

&emsp;&emsp;此时，boxfuse为您的应用程序创建一个映像，上传它，并在AWS上配置和启动必要的资源，从而产生类似于以下示例的输出：

``` 
Fusing Image for myapp-1.0.jar ...
Image fused in 00:06.838s (53937 K) -> axelfontaine/myapp:1.0
Creating axelfontaine/myapp ...
Pushing axelfontaine/myapp:1.0 ...
Verifying axelfontaine/myapp:1.0 ...
Creating Elastic IP ...
Mapping myapp-axelfontaine.boxfuse.io to 52.28.233.167 ...
Waiting for AWS to create an AMI for axelfontaine/myapp:1.0 in eu-central-1 (this may take up to 50 seconds) ...
AMI created in 00:23.557s -> ami-d23f38cf
Creating security group boxfuse-sg_axelfontaine/myapp:1.0 ...
Launching t2.micro instance of axelfontaine/myapp:1.0 (ami-d23f38cf) in eu-central-1 ...
Instance launched in 00:30.306s -> i-92ef9f53
Waiting for AWS to boot Instance i-92ef9f53 and Payload to start at http://52.28.235.61/ ...
Payload started in 00:29.266s -> http://52.28.235.61/
Remapping Elastic IP 52.28.233.167 to i-92ef9f53 ...
Waiting 15s for AWS to complete Elastic IP Zero Downtime transition ...
Deployment completed successfully. axelfontaine/myapp:1.0 is up and running at http://myapp-axelfontaine.boxfuse.io/
```

&emsp;&emsp;您的应用程序现在应该在AWS上启动并运行。

&emsp;&emsp;请参阅有关在EC2上部署Spring Boot应用程序的博客文章以及Boxfuse Spring Boot集成的文档，以开始使用Maven构建来运行应用程序。

### **6.1.6 Google Cloud**

&emsp;&emsp;Google Cloud有几个可用于启动Spring Boot应用程序的选项。 最容易上手的可能是App Engine，但您也可以找到在带有Container Engine的容器中运行Spring Boot的方法，或者在具有Compute Engine的虚拟机上运行Spring Boot的方法。

&emsp;&emsp;要在App Engine中运行，您可以首先在UI中创建项目，该项目为您设置唯一标识符并设置HTTP路由。 将Java应用程序添加到项目中并将其留空，然后使用Google Cloud SDK将Spring Boot应用程序从命令行或CI构建推送到该插槽。

&emsp;&emsp;App Engine Standard要求您使用WAR包装。 按照以下步骤将App Engine Standard应用程序部署到Google Cloud。

&emsp;&emsp;或者，App Engine Flex要求您创建app.yaml文件以描述您的应用所需的资源。 通常，您将此文件放在src/main/appengine中，它应该类似于以下文件：

``` 
service: default

runtime: java
env: flex

runtime_config:
  jdk: openjdk8

handlers:
- url: /.*
  script: this field is required, but ignored

manual_scaling:
  instances: 1

health_check:
  enable_health_check: False

env_variables:
  ENCRYPT_KEY: your_encryption_key_here
```

&emsp;&emsp;您可以通过将项目ID添加到构建配置来部署应用程序（例如，使用Maven插件），如以下示例所示：

``` 
<plugin>
	<groupId>com.google.cloud.tools</groupId>
	<artifactId>appengine-maven-plugin</artifactId>
	<version>1.3.0</version>
	<configuration>
		<project>myproject</project>
	</configuration>
</plugin>
```

&emsp;&emsp;然后使用mvn appengine:deploy进行部署（如果需要先进行身份验证，则构建失败）。

## **6.2 安装Spring Boot应用程序**

>完全可执行的jar通过在文件的前面嵌入额外的脚本来工作。 目前，某些工具不接受此格式，因此您可能无法始终使用此技术。 例如，jar -xf可能会无声地提取已完全可执行的jar或war。 建议您只有在打算直接执行jar或war时才能使jar或war完全可执行，而不是使用java -jar运行它或将其部署到servlet容器。

&emsp;&emsp;要使用Maven创建“完全可执行”jar，请使用以下插件配置：

``` 
<plugin>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-maven-plugin</artifactId>
	<configuration>
		<executable>true</executable>
	</configuration>
</plugin>
```

&emsp;&emsp;以下示例显示了等效的Gradle配置：

``` 
bootJar {
	launchScript()
}
```

&emsp;&emsp;然后，您可以通过键入./my-application.jar（其中my-application是您的工件的名称）来运行您的应用程序。 包含jar的目录用作应用程序的工作目录。

### **6.2.1 支持的操作系统**

&emsp;&emsp;默认脚本支持大多数Linux发行版，并在CentOS和Ubuntu上进行测试。 其他平台，如OS X和FreeBSD，需要使用自定义embeddedLaunchScript。

### **6.2.2 Unix/Linux服务**

&emsp;&emsp;通过使用init.d或systemd，可以轻松地将Spring Boot应用程序作为Unix / Linux服务启动。

**6.2.2.1 作为init.d服务安装（系统V）**

&emsp;&emsp;如果您配置了Spring Boot的Maven或Gradle插件来生成完全可执行的jar，并且您没有使用自定义embeddedLaunchScript，那么您的应用程序可以用作init.d服务。 为此，请将jar符号链接到init.d以支持标准的启动，停止，重新启动和状态命令。

&emsp;&emsp;该脚本支持以下功能：

- 以拥有jar文件的用户身份启动服务
- 使用/var/run/<appname>/<appname>.pid跟踪应用程序的PID
- 将控制台日志写入/var/log/<appname>.log


&emsp;&emsp;假设您在/var/myapp中安装了Spring Boot应用程序，要将Spring Boot应用程序安装为init.d服务，请创建符号链接，如下所示：

``` 
$ sudo ln -s /var/myapp/myapp.jar /etc/init.d/myapp
```

&emsp;&emsp;安装后，您可以按常规方式启动和停止服务。 例如，在基于Debian的系统上，您可以使用以下命令启动它：

``` 
$ service myapp start
```

>如果您的应用程序无法启动，请检查写入/var/log/<appname>.log的日志文件是否有错误。

&emsp;&emsp;您还可以使用标准操作系统工具将应用程序标记为自动启动。 例如，在Debian上，您可以使用以下命令：

``` 
$ update-rc.d myapp defaults <priority>
```

**1）保护init.d服务**

>以下是一组有关如何保护作为init.d服务运行的Spring Boot应用程序的指南。 它并不是为了强化应用程序及其运行环境而应该做的所有事情的详尽列表。

&emsp;&emsp;当以root身份执行时，就像root用于启动init.d服务的情况一样，默认可执行脚本以拥有jar文件的用户身份运行应用程序。 您永远不应该以root身份运行Spring Boot应用程序，因此应用程序的jar文件永远不应该由root拥有。 相反，创建一个特定用户来运行您的应用程序并使用chown使其成为jar文件的所有者，如以下示例所示：

``` 
$ chown bootapp:bootapp your-app.jar
```

&emsp;&emsp;在这种情况下，默认可执行脚本将该应用程序作为bootapp用户运行。

>为了减少应用程序用户帐户遭到入侵的可能性，您应该考虑阻止它使用登录shell。 例如，您可以将帐户的shell设置为/usr/sbin/nologin。

&emsp;&emsp;您还应该采取措施来防止修改应用程序的jar文件。 首先，配置其权限，使其无法编写，只能由其所有者读取或执行，如以下示例所示：

``` 
$ chmod 500 your-app.jar
```

&emsp;&emsp;其次，如果您的应用程序或运行它的帐户受到损害，您还应该采取措施限制损害。 如果攻击者确实获得了访问权限，他们可以使jar文件可写并更改其内容。 防止这种情况的一种方法是使用chattr使其不可变，如以下示例所示：

``` 
$ sudo chattr +i your-app.jar
```

&emsp;&emsp;这将阻止任何用户（包括root）修改jar。

&emsp;&emsp;如果root用于控制应用程序的服务，并且您使用.conf文件来自定义其启动，则root用户将读取并评估.conf文件。 它应该得到相应的保护。 使用chmod以便文件只能由所有者读取并使用chown使root成为所有者，如以下示例所示：

``` 
$ chmod 400 your-app.conf
$ sudo chown root:root your-app.conf
```

**6.2.2.2 作为系统服务安装**

&emsp;&emsp;systemd是System V init系统的后继产品，现在被许多现代Linux发行版使用。 虽然您可以继续将init.d脚本与systemd一起使用，但也可以使用systemd“service”脚本启动Spring Boot应用程序。

&emsp;&emsp;假设您在/var/myapp中安装了Spring Boot应用程序，要将Spring Boot应用程序安装为systemd服务，请创建名为myapp.service的脚本并将其放在/etc/systemd/system目录中。 以下脚本提供了一个示例：

``` 
[Unit]
Description=myapp
After=syslog.target

[Service]
User=myapp
ExecStart=/var/myapp/myapp.jar
SuccessExitStatus=143

[Install]
WantedBy=multi-user.target
```

>请记住更改应用程序的Description，User和ExecStart字段。

&emsp;
>ExecStart字段不声明脚本操作命令，这意味着默认情况下使用run命令。

&emsp;&emsp;请注意，与作为init.d服务运行时不同，运行应用程序的用户，PID文件和控制台日志文件由systemd本身管理，因此必须使用“service”脚本中的相应字段进行配置。 有关更多详细信息，请参阅服务单元配置手册页。

&emsp;&emsp;要将应用程序标记为在系统引导时自动启动，请使用以下命令：

``` 
$ systemctl enable myapp.service
```

&emsp;&emsp;有关更多详细信息，请参阅man systemctl。

**6.2.2.3 自定义启动脚本**

&emsp;&emsp;可以通过多种方式自定义Maven或Gradle插件编写的默认嵌入式启动脚本。 对于大多数人来说，使用默认脚本和一些自定义通常就足够了。 如果您发现无法自定义所需内容，请使用embeddedLaunchScript选项完全编写自己的文件。

**1）在编写时自定义启动脚本**

&emsp;&emsp;在将脚本写入jar文件时自定义启动脚本的元素通常是有意义的。 例如，init.d脚本可以提供“描述”。 由于您事先了解了描述（并且无需更改），因此您可以在生成jar时提供它。

&emsp;&emsp;要自定义编写的元素，请使用Spring Boot Maven插件的embeddedLaunchScriptProperties选项或Spring Boot Gradle插件的launchScript的properties属性。

&emsp;&emsp;默认脚本支持以下属性替换：

<table>
	<tr>
		<th>Name</th>
		<th>Description</th>
		<th>Gradle default</th>
		<th>Maven default</th>
	</tr>
	<tr>
		<td>mode</td>
		<td>script的模式</td>
		<td>auto</td>
		<td>auto</td>
	</tr>
	<tr>
		<td>initInfoProvides</td>
		<td>INIT INFO的Provides部分</td>
		<td>\${task.baseName}</td>
		<td>\${project.artifactId}</td>
	</tr>
	<tr>
		<td>initInfoRequiredStart</td>
		<td>INIT INFO的Required-Start部分</td>
		<td>\$remote_fs \$syslog \$network</td>
		<td>\$remote_fs \$syslog \$network</td>
	</tr>
	<tr>
		<td>initInfoRequiredStop</td>
		<td>INIT INFO的Required-Stop部分</td>
		<td>\$remote_fs \$syslog \$network</td>
		<td>\$remote_fs \$syslog \$network</td>
	</tr>
	<tr>
		<td>initInfoDefaultStart</td>
		<td>INIT INFO的Default-Start部分</td>
		<td>2 3 4 5</td>
		<td>2 3 4 5</td>
	</tr>
	<tr>
		<td>initInfoDefaultStop</td>
		<td>INIT INFO的Default-Stop部分</td>
		<td>0 1 6</td>
		<td>0 1 6</td>
	</tr>
	<tr>
		<td>initInfoShortDescription</td>
		<td>INIT INFO的Short-Description部分</td>
		<td>Single-line version of \${project.description}(falling back to \${task.baseName})</td>
		<td>\${project.name}</td>
	</tr>
	<tr>
		<td>initInfoDescription</td>
		<td>INIT INFO的Description部分</td>
		<td>\${project.description}(falling back to \${task.baseName})</td>
		<td>\${project.description}(falling back to \${project.name})</td>
	</tr>
	<tr>
		<td>initInfoChkconfig</td>
		<td>INIT INFO的chkconfig部分</td>
		<td>2345 99 01</td>
		<td>2345 99 01</td>
	</tr>
	<tr>
		<td>confFolder</td>
		<td>CONF_FOLDER的默认属性</td>
		<td>Folder containing the jar</td>
		<td>Folder containing the jar</td>
	</tr>
	<tr>
		<td>inlinedConfScript</td>
		<td>引用应在默认启动脚本中内联的文件脚本。 在加载任何外部配置文件之前，这可用于设置环境变量，例如JAVA_OPTS</td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>logFolder</td>
		<td>LOG_FOLDER的默认值。 仅对init.d服务有效</td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>logFilename</td>
		<td>LOG_FILENAME的默认值。 仅对init.d服务有效</td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>pidFolder</td>
		<td>PID_FOLDER的默认值。 仅对init.d服务有效</td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>pidFilename</td>
		<td>PID_FOLDER中PID文件名称的默认值。 仅对init.d服务有效</td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>useStartStopDaemon</td>
		<td>start-stop-daemon命令是否可用，应该用于控制进程</td>
		<td>true</td>
		<td>true</td>
	</tr>
	<tr>
		<td>stopWaitTime</td>
		<td>STOP_WAIT_TIME的默认值（以秒为单位）。 仅对init.d服务有效</td>
		<td>60</td>
		<td>60</td>
	</tr>
</table>

**2）在它运行时自定义脚本**

&emsp;&emsp;对于在编写jar后需要自定义的脚本项，可以使用环境变量或配置文件。

&emsp;&emsp;默认脚本支持以下环境属性：

<table>
	<tr>
		<th>Variable</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>MODE</td>
		<td>操作的“mode”。 默认值取决于jar的构建方式，但通常是auto（意味着它通过检查它是否是名为init.d的目录中的符号链接来尝试猜测它是否是init脚本）。 您可以显式将其设置为service，以便stop | start | status | restart命令可以在前台运行脚本时运行或运行。</td>
	</tr>
	<tr>
		<td>USE_START_STOP_DAEMON</td>
		<td>start-stop-daemon命令是否可用，应该用于控制进程。 默认为true。</td>
	</tr>
	<tr>
		<td>PID_FOLDER</td>
		<td>pid文件夹的根名称（默认情况下为/var/run）。</td>
	</tr>
	<tr>
		<td>LOG_FOLDER</td>
		<td>放置日志文件的文件夹的名称（默认情况下为/var/log）。</td>
	</tr>
	<tr>
		<td>CONF_FOLDER</td>
		<td>从中读取.conf文件的文件夹的名称（默认情况下与jar文件相同）。</td>
	</tr>
	<tr>
		<td>LOG_FILENAME</td>
		<td>LOG_FOLDER中的日志文件的名称（默认情况下为&lt;appname&rt;.log）。</td>
	</tr>
	<tr>
		<td>APP_NAME</td>
		<td>应用程序的名称。 如果jar从符号链接运行，则脚本会猜测应用程序名称。 如果它不是符号链接或您想要显式设置应用程序名称，这可能很有用。</td>
	</tr>
	<tr>
		<td>RUN_ARGS</td>
		<td>传递给程序的参数（Spring Boot应用程序）。</td>
	</tr>
	<tr>
		<td>JAVA_HOME</td>
		<td>默认情况下使用PATH发现java可执行文件的位置，但如果$ JAVA_HOME/bin/java中存在可执行文件，则可以显式设置它。</td>
	</tr>
	<tr>
		<td>JAVA_OPTS</td>
		<td>启动时传递给JVM的选项。</td>
	</tr>
	<tr>
		<td>JARFILE</td>
		<td>jar文件的显式位置，以防脚本用于启动实际上未嵌入的jar。</td>
	</tr>
	<tr>
		<td>DEBUG</td>
		<td>如果不为空，则在shell进程上设置-x标志，以便于在脚本中查看逻辑。</td>
	</tr>
	<tr>
		<td>STOP_WAIT_TIME</td>
		<td>在强制关闭之前停止应用程序时等待的时间（默认为60）。</td>
	</tr>
</table>

>PID_FOLDER，LOG_FOLDER和LOG_FILENAME变量仅对init.d服务有效。 对于systemd，使用“service”脚本进行等效的自定义。 有关更多详细信息，请参阅服务单元配置手册页。

&emsp;&emsp;除JARFILE和APP_NAME外，可以使用.conf文件配置上一节中列出的设置。 该文件应该位于jar文件的旁边，并且具有相同的名称，但后缀为.conf而不是.jar。 例如，名为/var/myapp/myapp.jar的jar使用名为/var/myapp/myapp.conf的配置文件，如以下示例所示：

``` 
JAVA_OPTS=-Xmx1024M
LOG_FOLDER=/custom/log/folder
```

>如果您不喜欢在jar文件旁边有配置文件，可以设置CONF_FOLDER环境变量来自定义配置文件的位置。

&emsp;&emsp;要了解有关正确保护此文件的信息，请参阅保护init.d服务的准则。

### **6.2.3 Microsoft Windows服务**

&emsp;&emsp;可以使用winsw将Spring Boot应用程序作为Windows服务启动。

&emsp;&emsp;单独维护的示例逐步介绍了如何为Spring Boot应用程序创建Windows服务。

## **6.3 接下来要阅读的内容**

&emsp;&emsp;查看Cloud Foundry，Heroku，OpenShift和Boxfuse网站，了解有关PaaS可提供的各种功能的更多信息。 这些只是四个最受欢迎的Java PaaS提供商。 由于Spring Boot非常适合基于云的部署，因此您也可以自由地考虑其他提供程序。

&emsp;&emsp;下一节将介绍Spring Boot CLI，或者您可以继续阅读有关构建工具插件的内容。

# **7 Spring Boot CLI**

&emsp;&emsp;Spring Boot CLI是一个命令行工具，如果您想快速开发Spring应用程序，可以使用它。 它允许您运行Groovy脚本，这意味着您拥有熟悉的类似Java的语法，而没有太多的样板代码。 您还可以引导新项目或为其编写自己的命令。

## **7.1 安装CLI**

&emsp;&emsp;可以使用SDKMAN!（SDK Manager）手动安装Spring Boot CLI（命令行界面）或者如果您是OSX用户，则使用Homebrew或MacPorts。 有关全面的安装说明，请参见“入门”一节中的第10.2节“安装Spring Boot CLI”。

## **7.2 使用CLI**

&emsp;&emsp;安装CLI后，可以通过键入spring并在命令行按Enter键来运行它。 如果在没有任何参数的情况下运行spring，将显示一个简单的帮助屏幕，如下所示：

``` 
$ spring
usage: spring [--help] [--version]
       <command> [<args>]

Available commands are:

  run [options] <files> [--] [args]
    Run a spring groovy script

  ... more command help is shown here
```

&emsp;&emsp;您可以键入spring help以获取有关任何支持的命令的更多详细信息，如以下示例所示：

``` 
$ spring help run
spring run - Run a spring groovy script

usage: spring run [options] <files> [--] [args]

Option                     Description
------                     -----------
--autoconfigure [Boolean]  Add autoconfigure compiler
                             transformations (default: true)
--classpath, -cp           Additional classpath entries
-e, --edit                 Open the file with the default system
                             editor
--no-guess-dependencies    Do not attempt to guess dependencies
--no-guess-imports         Do not attempt to guess imports
-q, --quiet                Quiet logging
-v, --verbose              Verbose logging of dependency
                             resolution
--watch                    Watch the specified file for changes
```

&emsp;&emsp;version命令提供了一种快速方法来检查您正在使用的Spring Boot版本，如下所示：

``` 
$ spring version
Spring CLI v2.1.2.RELEASE
```

### **7.2.1 使用CLI运行应用程序**

&emsp;&emsp;您可以使用run命令编译和运行Groovy源代码。 Spring Boot CLI是完全独立的，因此您不需要任何外部Groovy安装。

&emsp;&emsp;以下示例显示了使用Groovy编写的“hello world”Web应用程序：

``` 
@RestController
class WebApplication {

	@RequestMapping("/")
	String home() {
		"Hello World!"
	}

}
```

&emsp;&emsp;要编译并运行该应用程序，请键入以下命令：

``` 
$ spring run hello.groovy
```

&emsp;&emsp;要将命令行参数传递给应用程序，请使用 -- 将命令与“spring”命令参数分开，如以下示例所示：

``` 
$ spring run hello.groovy -- --server.port=9000
```

&emsp;&emsp;要设置JVM命令行参数，可以使用JAVA_OPTS环境变量，如以下示例所示：

``` 
$ JAVA_OPTS=-Xmx1024m spring run hello.groovy
```

>在Microsoft Windows上设置JAVA_OPTS时，请确保引用整个指令，例如设置“JAVA_OPTS = -Xms256m -Xmx2048m”。 这样做可确保将值正确传递给流程。

**7.2.1.1 推导“grab”依赖关系**

&emsp;&emsp;标准Groovy包含一个@Grab注释，它允许您声明对第三方库的依赖性。 这个有用的技术让Groovy以与Maven或Gradle相同的方式下载jar，但不需要你使用构建工具。

&emsp;&emsp;Spring Boot进一步扩展了这种技术，并尝试根据您的代码推断出“抓取”哪些库。 例如，由于先前显示的WebApplication代码使用@RestController注释，因此Spring Boot会抓取“Tomcat”和“Spring MVC”。

&emsp;&emsp;以下项目用作“grap提示”：

<table>
	<tr>
		<th>Items</th>
		<th>Grabs</th>
	</tr>
	<tr>
		<td>JdbcTemplate, NamedParameterJdbcTemplate, DataSource</td>
		<td>JDBC Application.</td>
	</tr>
	<tr>
		<td>@EnableJms</td>
		<td>JMS Application.</td>
	</tr>
	<tr>
		<td>@EnableCaching</td>
		<td>Caching abstraction.</td>
	</tr>
	<tr>
		<td>@Test</td>
		<td>JUnit.</td>
	</tr>
	<tr>
		<td>@EnableRabbit</td>
		<td>RabbitMQ.</td>
	</tr>
	<tr>
		<td>extends Specification</td>
		<td>Spock test.</td>
	</tr>
	<tr>
		<td>@EnableBatchProcessing</td>
		<td>Spring Batch.</td>
	</tr>
	<tr>
		<td>@MessageEndpoint @EnableIntegration</td>
		<td>Spring Integration.</td>
	</tr>
	<tr>
		<td>@Controller @RestController @EnableWebMvc</td>
		<td>Spring MVC + Embedded Tomcat.</td>
	</tr>
	<tr>
		<td>@EnableWebSecurity</td>
		<td>Spring Security.</td>
	</tr>
	<tr>
		<td>@EnableTransactionManagement</td>
		<td>Spring Transaction Management.</td>
	</tr>
</table>

>请参阅Spring Boot CLI源代码中的CompilerAutoConfiguration的子类，以准确了解自定义的应用方式。

**7.2.1.2 推导“grab”坐标**

&emsp;&emsp;Spring Boot通过允许您指定没有组或版本的依赖项来扩展Groovy的标准@Grab支持（例如，@Gran('freemarker')）。 这样做可以参考Spring Boot的默认依赖关系元数据来推断工件的组和版本。

>默认元数据与您使用的CLI版本相关联。 只有当您移动到新版本的CLI时，它才会发生变化，让您可以控制依赖项版本何时发生变化。 可以在附录中找到显示默认元数据中包含的依赖关系及其版本的表。

**7.2.1.3 默认导入语句**

&emsp;&emsp;为了帮助减小Groovy代码的大小，自动包含几个import语句。 请注意前面的示例如何引用@ Component，@ RestController和@RequestMapping，而无需使用完全限定名称或import语句。

>许多Spring注释在不使用import语句的情况下工作。 尝试运行应用程序以在添加导入之前查看失败的内容。

**7.2.1.4 自动Main方法**

&emsp;&emsp;与等效的Java应用程序不同，您不需要在Groovy脚本中包含public static void main（String [] args）方法。 将自动创建SpringApplication，并将编译后的代码作为源代码。

**7.2.1.5 自定义依赖关系管理**

&emsp;&emsp;默认情况下，CLI在解析@Grab依赖项时使用spring-boot-dependencies中声明的依赖关系管理。 可以使用@DependencyManagementBom批注配置覆盖缺省依赖关系管理的其他依赖关系管理。 注释的值应指定一个或多个Maven BOM的坐标（groupId:artifactId:version）。

例如，请考虑以下声明：

``` 
@DependencyManagementBom("com.example.custom-bom:1.0.0")
```

&emsp;&emsp;前面的声明在com/example/custom-versions/1.0.0/下的Maven存储库中选择了custom-bom-1.0.0.pom。

&emsp;&emsp;指定多个BOM时，它们将按您声明的顺序应用，如以下示例所示：

``` 
@DependencyManagementBom(["com.example.custom-bom:1.0.0",
		"com.example.another-bom:1.0.0"])
```

&emsp;&emsp;前面的示例表明另一个bom中的依赖关系管理会覆盖custom-bom中的依赖关系管理。

&emsp;&emsp;您可以在任何可以使用@Grab的地方使用@DependencyManagementBom。 但是，为了确保依赖关系管理的一致排序，您可以在应用程序中最多使用一次@DependencyManagementBom。 Spring IO平台是一个有用的依赖关系管理源（它是Spring Boot的依赖关系管理的超集），您可以在其中包含以下行：

``` 
@DependencyManagementBom('io.spring.platform:platform-bom:1.1.2.RELEASE')
```

### **7.2.2 多资源文件的应用程序**

&emsp;&emsp;您可以对所有接受文件输入的命令使用“shell globbing”。 这样做可以让您使用单个目录中的多个文件，如以下示例所示：

``` 
$ spring run *.groovy
```

### **7.2.3 打包您的应用程序**

&emsp;&emsp;您可以使用jar命令将应用程序打包到一个自包含的可执行jar文件中，如以下示例所示：

``` 
$ spring jar my-app.jar *.groovy
```

&emsp;&emsp;生成的jar包含通过编译应用程序和所有应用程序的依赖项生成的类，以便可以使用java -jar运行它。 jar文件还包含应用程序类路径中的条目。 您可以使用--include和--exclude添加和删除jar的显式路径。 两者都以逗号分隔，并且都以“+”和“ - ”的形式接受前缀，以表示它们应该从默认值中删除。 默认包括如下：

``` 
public/**, resources/**, static/**, templates/**, META-INF/**, *
```

&emsp;&emsp;默认排除如下：

``` 
.*, repository/**, build/**, target/**, **/*.jar, **/*.groovy
```

&emsp;&emsp;在命令行上键入spring help jar以获取更多信息。

### **7.2.4 初始化一个新项目**

&emsp;&emsp;init命令允许您在不离开shell的情况下使用start.spring.io创建新项目，如以下示例所示：

``` 
$ spring init --dependencies=web,data-jpa my-project
Using service at https://start.spring.io
Project extracted to '/Users/developer/example/my-project'
```

&emsp;&emsp;上面的示例使用基于Maven的项目创建一个my-project目录，该项目使用spring-boot-starter-web和spring-boot-starter-data-jpa。 您可以使用--list标志列出服务的功能，如以下示例所示：

``` 
$ spring init --list
=======================================
Capabilities of https://start.spring.io
=======================================

Available dependencies:
-----------------------
actuator - Actuator: Production ready features to help you monitor and manage your application
...
web - Web: Support for full-stack web development, including Tomcat and spring-webmvc
websocket - Websocket: Support for WebSocket development
ws - WS: Support for Spring Web Services

Available project types:
------------------------
gradle-build -  Gradle Config [format:build, build:gradle]
gradle-project -  Gradle Project [format:project, build:gradle]
maven-build -  Maven POM [format:build, build:maven]
maven-project -  Maven Project [format:project, build:maven] (default)

...
```

&emsp;&emsp;init命令支持许多选项。 有关详细信息，请参阅帮助输出。 例如，以下命令创建一个使用Java 8和war包装的Gradle项目：

``` 
$ spring init --build=gradle --java-version=1.8 --dependencies=websocket --packaging=war sample-app.zip
Using service at https://start.spring.io
Content saved to 'sample-app.zip'
```

### **7.2.5 使用嵌入式Shell**

&emsp;&emsp;Spring Boot包含BASH和zsh shell的命令行完成脚本。 如果不使用这些shell中的任何一个（可能是Windows用户），则可以使用shell命令启动集成shell，如以下示例所示：

``` 
$ spring shell
Spring Boot (v2.1.2.RELEASE)
Hit TAB to complete. Type \'help' and hit RETURN for help, and \'exit' to quit.
```

&emsp;&emsp;从嵌入式shell内部，您可以直接运行其他命令：

``` 
$ version
Spring CLI v2.1.2.RELEASE
```

&emsp;&emsp;嵌入式shell支持ANSI颜色输出以及选项卡完成。 如果需要运行本机命令，可以使用！ 字首。 要退出嵌入式shell，请按ctrl-c。

### **7.2.6 将扩展添加到CLI**

&emsp;&emsp;您可以使用install命令向CLI添加扩展。 该命令采用格式组中的一组或多组工件坐标group:artifact:version，如以下示例所示：

``` 
$ spring install com.example:spring-boot-cli-extension:1.0.0.RELEASE
```

&emsp;&emsp;除了安装由您提供的坐标标识的工件外，还会安装所有工件的依赖项。

&emsp;&emsp;要卸载依赖项，请使用uninstall命令。 与install命令一样，它采用group:artifact:version格式的一组或多组工件坐标，如以下示例所示：

``` 
$ spring uninstall com.example:spring-boot-cli-extension:1.0.0.RELEASE
```

&emsp;&emsp;它会卸载由您提供的坐标及其依赖项标识的工件。

&emsp;&emsp;要卸载所有其他依赖项，可以使用--all选项，如以下示例所示：

``` 
$ spring uninstall --all
```

## **7.3 使用Groovy Bean DSL开发应用程序**

&emsp;&emsp;Spring Framework 4.0本身支持beans{}“DSL”（从Grails借用），您可以使用相同的格式在bean的Groovy应用程序脚本中嵌入bean定义。 这有时是包含中间件声明等外部功能的好方法，如以下示例所示：

``` 
@Configuration
class Application implements CommandLineRunner {

	@Autowired
	SharedService service

	@Override
	void run(String... args) {
		println service.message
	}

}

import my.company.SharedService

beans {
	service(SharedService) {
		message = "Hello World"
	}
}
```

&emsp;&emsp;您可以将类声明与beans{}混合在同一个文件中，只要它们保持在顶层，或者，如果您愿意，可以将Bean DSL放在单独的文件中。

## **7.4 使用settings.xml配置CLI**

&emsp;&emsp;Spring Boot CLI使用Aether，Maven的依赖性解析引擎来解决依赖关系。 CLI使用~/.m2/settings.xml中的Maven配置来配置Aether。 CLI支持以下配置设置：

- Offline
- Mirrors
- Servers
- Proxies
- Profiles Activation Repositories
- Active profiles

&emsp;&emsp;有关详细信息，请参阅Maven的设置文档。

## **7.5 接下来要阅读的内容**

&emsp;&emsp;GitHub存储库中提供了一些示例groovy脚本，您可以使用它们来尝试Spring Boot CLI。 整个源代码中还有广泛的Javadoc。

&emsp;&emsp;如果您发现自己达到了CLI工具的限制，那么您可能希望将应用程序转换为完整的Gradle或Maven构建的“Groovy项目”。 下一节将介绍Spring Boot的“构建工具插件”，您可以将其与Gradle或Maven一起使用。

# **8 构建工具插件**

&emsp;&emsp;Spring Boot为Maven和Gradle提供构建工具插件。 这些插件提供了各种功能，包括可执行jar的包装。 本节提供了有关这两个插件的更多详细信息，以及在需要扩展不受支持的构建系统时的一些帮助。

## **8.1 Spring Boot Maven插件**

&emsp;&emsp;Spring Boot Maven插件在Maven中提供Spring Boot支持，允许您打包可执行jar或war档案并“就地”运行应用程序。 要使用它，您必须使用Maven 3.2（或更高版本）。

>有关完整的插件文档，请参阅Spring Boot Maven插件站点。

### **8.1.1 添加插件**

&emsp;&emsp;要使用Spring Boot Maven插件，请在pom.xml的plugins部分中包含相应的XML，如以下示例所示：

``` 
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<!-- ... -->
	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<version>2.1.3.RELEASE</version>
				<executions>
					<execution>
						<goals>
							<goal>repackage</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
		</plugins>
	</build>
</project>
```

&emsp;&emsp;上述配置重新打包在Maven生命周期的打包阶段构建的jar或war。 以下示例显示了重新打包的jar以及目标目录中的原始jar：

``` 
$ mvn package
$ ls target/*.jar
target/myproject-1.0.0.jar target/myproject-1.0.0.jar.original
```

&emsp;&emsp;如果不包含<execution />配置，如前面的示例所示，您可以单独运行插件（但仅在使用包目标时），如以下示例所示：

``` 
$ mvn package spring-boot:repackage
$ ls target/*.jar
target/myproject-1.0.0.jar target/myproject-1.0.0.jar.original
```

&emsp;&emsp;如果使用milestone或snapshot版本，则还需要添加相应的pluginRepository元素，如下面的清单所示：

``` 
<pluginRepositories>
	<pluginRepository>
		<id>spring-snapshots</id>
		<url>https://repo.spring.io/snapshot</url>
	</pluginRepository>
	<pluginRepository>
		<id>spring-milestones</id>
		<url>https://repo.spring.io/milestone</url>
	</pluginRepository>
</pluginRepositories>
```

### **8.1.2 打包可执行jar和war包**

&emsp;&emsp;一旦spring-boot-maven-plugin包含在你的pom.xml中，它就会自动尝试使用spring-boot:repackage目标重写档案以使它们可执行。 您应该使用通常的打包元素将项目配置为构建jar或war（视情况而定），如以下示例所示：

``` 
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<!-- ... -->
	<packaging>jar</packaging>
	<!-- ... -->
</project>
```

&emsp;&emsp;在程序包阶段，Spring Boot会增强现有存档。 可以通过使用配置选项或通过以常规方式向清单添加Main-Class属性来指定要启动的主类。 如果未指定主类，则插件将搜索具有public static void main(String[] args)方法的类。

&emsp;&emsp;要构建和运行项目工件，可以键入以下内容：

``` 
$ mvn package
$ java -jar target/mymodule-0.0.1-SNAPSHOT.jar
```

&emsp;&emsp;要构建可执行且可部署到外部容器的war文件，需要将嵌入式容器依赖项标记为“provided”，如以下示例所示：

``` 
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<!-- ... -->
	<packaging>war</packaging>
	<!-- ... -->
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-tomcat</artifactId>
			<scope>provided</scope>
		</dependency>
		<!-- ... -->
	</dependencies>
</project>
```

>有关如何创建可部署的war文件的更多详细信息，请参阅“第9.17.1节”，“创建可部署的war文件”部分。

&emsp;&emsp;插件信息页面中提供了高级配置选项和示例。

## **8.2 Spring Boot Gradle插件**

&emsp;&emsp;Spring Boot Gradle Plugin在Gradle中提供Spring Boot支持，允许您打包可执行jar或war存档，运行Spring Boot应用程序，并使用spring-boot-dependencies提供的依赖关系管理。 它需要Gradle 4.4或更高版本。 请参阅插件的文档以了解更多信息：

- Reference (HTML 和 PDF)
- API


## **8.3 Spring Boot AntLib模块**

&emsp;&emsp;Spring Boot AntLib模块为Apache Ant提供基本的Spring Boot支持。 您可以使用该模块创建可执行jar。 要使用该模块，您需要在build.xml中声明一个额外的spring-boot命名空间，如以下示例所示：

``` 
<project xmlns:ivy="antlib:org.apache.ivy.ant"
	xmlns:spring-boot="antlib:org.springframework.boot.ant"
	name="myapp" default="build">
	...
</project>
```

&emsp;&emsp;您需要记住使用-lib选项启动Ant，如以下示例所示：

``` 
$ ant -lib <folder containing spring-boot-antlib-2.1.3.RELEASE.jar>
```

>“使用Spring Boot”部分包含一个使用带有spring-boot-antlib的Apache Ant的更完整示例。

### **8.3.1 Spring Boot Ant Tasks**

&emsp;&emsp;一旦声明了spring-boot-antlib命名空间，就可以使用以下附加任务：

- spring-boot:exejar
- spring-boot:findmainclass


**8.3.1.1 spring-boot:exejar**

&emsp;&emsp;您可以使用exejar任务来创建Spring Boot可执行jar。 任务支持以下属性：

<table>
	<tr>
		<th>Attribute</th>
		<th>Description</th>
		<th>Required</th>
	</tr>
	<tr>
		<td>destfile</td>
		<td>要创建的目标jar文件</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>classes</td>
		<td>Java类文件的根目录</td>
		<td>Yes</td>
	</tr>
	<tr>
		<td>start-class</td>
		<td>要运行的主要应用程序类</td>
		<td>No (默认值是找到的第一个声明main方法的类)</td>
	</tr>
</table>

&emsp;&emsp;以下嵌套元素可与任务一起使用：

<table>
	<tr>
		<th>Element</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>resources</td>
		<td>一个或多个资源集合，描述应添加到创建的jar文件内容中的一组资源。</td>
	</tr>
	<tr>
		<td>lib</td>
		<td>应该添加到构成应用程序的运行时依赖性类路径的jar库集的一个或多个资源集合。</td>
	</tr>
</table>

**8.3.1.2 示例**

&emsp;&emsp;本节显示Ant任务的两个示例。

``` 
<spring-boot:exejar destfile="target/my-application.jar"
		classes="target/classes" start-class="com.example.MyApplication">
	<resources>
		<fileset dir="src/main/resources" />
	</resources>
	<lib>
		<fileset dir="lib" />
	</lib>
</spring-boot:exejar>
```

``` 
<exejar destfile="target/my-application.jar" classes="target/classes">
	<lib>
		<fileset dir="lib" />
	</lib>
</exejar>
```

### **8.3.2 spring-boot:findmainclass**

&emsp;&emsp;exejar在内部使用findmainclass任务来定位声明main的类。 如有必要，您还可以直接在构建中使用此任务。 支持以下属性：

<table>
	<tr>
		<th>Attribute</th>
		<th>Description</th>
		<th>Required</th>
	</tr>
	<tr>
		<td>classesroot</td>
		<td>Java类文件的根目录</td>
		<td>Yes (除非指定了mainclass)</td>
	</tr>
	<tr>
		<td>mainclass</td>
		<td>可用于短路主类搜索</td>
		<td>No</td>
	</tr>
	<tr>
		<td>property</td>
		<td>应该使用结果设置的Ant属性</td>
		<td>No (如果未指定，将记录结果)</td>
	</tr>
</table>

**8.3.2.1 示例**

&emsp;&emsp;本节包含三个使用findmainclass的示例。

``` 
<findmainclass classesroot="target/classes" />
```

``` 
<findmainclass classesroot="target/classes" property="main-class" />
```

``` 
<findmainclass mainclass="com.example.MainClass" property="main-class" />
```

## **8.4 支持其他构建系统**

&emsp;&emsp;如果您想使用Maven，Gradle或Ant以外的构建工具，您可能需要开发自己的插件。 可执行jar需要遵循特定的格式，并且某些条目需要以未压缩的形式编写（有关详细信息，请参阅附录中的“可执行jar格式”部分）。

&emsp;&emsp;Spring Boot Maven和Gradle插件都使用spring-boot-loader-tools来实际生成jar。 如果需要，您可以直接使用此库。

### **8.4.1 重新打包Archives**

&emsp;&emsp;要重新打包现有存档以使其成为自包含的可执行存档，请使用org.springframework.boot.loader.tools.Repackager。 Repackager类采用一个构造函数参数，该参数引用现有的jar或war存档。 使用两个可用的repackage()方法之一来替换原始文件或写入新目标。 在重新打包程序运行之前，也可以配置各种设置。

### **8.4.2 嵌套Libraries**

&emsp;&emsp;重新打包存档时，可以使用org.springframework.boot.loader.tools.Libraries接口包含对依赖项文件的引用。 我们在这里没有提供任何具体的库实现，因为它们通常是特定于构建系统的。

&emsp;&emsp;如果您的存档已包含库，则可以使用Libraries.NONE。

### **8.4.3 找到Main类**

&emsp;&emsp;如果不使用Repackager.setMainClass()指定主类，则repackager使用ASM读取类文件并尝试使用public static void main(String[] args)方法查找合适的类。 如果找到多个候选项，则抛出异常。

### **8.4.4 重新打包实施示例**

&emsp;&emsp;以下示例显示了典型的重新打包实现：

``` 
Repackager repackager = new Repackager(sourceJarFile);
repackager.setBackupSource(false);
repackager.repackage(new Libraries() {
			@Override
			public void doWithLibraries(LibraryCallback callback) throws IOException {
				// Build system specific implementation, callback for each dependency
				// callback.library(new Library(nestedFile, LibraryScope.COMPILE));
			}
		});
```

## **8.5 接下来要阅读的内容**

&emsp;&emsp;如果您对构建工具插件的工作方式感兴趣，可以查看GitHub上的spring-boot-tools模块。 附录中介绍了可执行jar格式的更多技术细节。

&emsp;&emsp;如果您有与构建相关的特定问题，可以查看“操作方法”指南。

# **9 ‘How-to’ 指南**

&emsp;&emsp;本节提供了使用Spring Boot时经常出现的一些常见“我该怎么做......”的问题的答案。 它的报道并不详尽，但确实涵盖了很多。

&emsp;&emsp;如果您遇到我们未在此处讨论的特定问题，您可能需要查看stackoverflow.com以查看是否有人已提供答案。 这也是提出新问题的好地方（请使用spring-boot标签）。

&emsp;&emsp;我们也非常乐意扩展这一部分。 如果您想添加“操作方法”，请向我们发送拉取请求。

# **9.1 Spring Boot应用**

&emsp;&emsp;本节包括与Spring Boot应用程序直接相关的主题。

### **9.1.1 创建自己的失败解析器**

&emsp;&emsp;FailureAnalyzer是一种在启动时拦截异常并将其转换为人类可读消息的好方法，包含在FailureAnalysis中。 Spring Boot为应用程序上下文相关异常，JSR-303验证等提供了这样的分析器。 您也可以创建自己的。

&emsp;&emsp;AbstractFailureAnalyzer是FailureAnalyzer的一个方便扩展，它检查要处理的异常中是否存在指定的异常类型。 您可以从中进行扩展，以便您的实现只有在实际存在时才有机会处理异常。 如果由于某种原因，您无法处理异常，则返回null以使另一个实现有机会处理异常。

&emsp;&emsp;FailureAnalyzer实现必须在META-INF/spring.factories中注册。 以下示例注册ProjectConstraintViolationFailureAnalyzer：

``` 
org.springframework.boot.diagnostics.FailureAnalyzer=\
com.example.ProjectConstraintViolationFailureAnalyzer
```

>如果您需要访问BeanFactory或Environment，则FailureAnalyzer可以分别简单地实现BeanFactoryAware或EnvironmentAware。

### **9.1.2 自动配置疑难解答**

&emsp;&emsp;Spring Boot自动配置尽力“做正确的事”，但有时事情会失败，而且很难说清楚原因。

### **9.1.3 在开始之前自定义Environment或ApplicationContext**

&emsp;&emsp;任何Spring Boot ApplicationContext都有一个非常有用的ConditionEvaluationReport。 如果启用DEBUG日志记录输出，则可以看到它。 如果使用spring-boot-actuator（参见Actuator章节），还有一个条件端点以JSON格式呈现报表。 使用该端点调试应用程序，并查看Spring Boot在运行时添加了哪些功能（以及哪些尚未添加）。

&emsp;&emsp;通过查看源代码和Javadoc可以回答更多问题。 阅读代码时，请记住以下经验法则：

- 查找名为*AutoConfiguration的类并阅读其来源。 特别注意@Conditional*注释，找出它们启用的功能和时间。 将--debug添加到命令行或系统属性-Ddebug，以在控制台上记录应用程序中所做的所有自动配置决策。 在正在运行的Actuator应用程序中，查看条件端点（/actuator/conditions或JMX等效物）以获取相同的信息。
- 查找@ConfigurationProperties（例如ServerProperties）的类，并从那里读取可用的外部配置选项。 @ConfigurationProperties批注具有name属性，该属性充当外部属性的前缀。 因此，ServerProperties具有prefix ="server"，其配置属性为server.port，server.address等。 在正在运行的Actuator应用程序中，查看configprops端点。
- 查看Binder上bind方法的使用，以轻松的方式将配置值明确地提取出Environment。 它通常与前缀一起使用。
- 查找直接绑定到Environment的@Value注释。
- 查找@ConditionalOnExpression注释，以响应SpEL表达式打开和关闭功能，通常使用从环境中解析的占位符进行评估。


### **9.1.4 构建ApplicationContext层次结构（添加父或根上下文）**

&emsp;&emsp;SpringApplication具有ApplicationListeners和ApplicationContextInitializers，用于将自定义应用于上下文或环境。 Spring Boot加载了许多此类自定义项，以便在META-INF/spring.factories内部使用。 注册其他自定义项的方法不止一种：

- 按程序编程，通过在运行之前调用SpringApplication上的addListeners和addInitializers方法。
- 声明性地，根据应用程序，通过设置context.initializer.classes或context.listener.classes属性。
- 声明性地，对于所有应用程序，通过添加META-INF/spring.factories并打包应用程序全部用作库的jar文件。


&emsp;&emsp;SpringApplication向侦听器发送一些特殊的ApplicationEvent（有些甚至在创建上下文之前），然后为ApplicationContext发布的事件注册侦听器。 有关完整列表，请参见“Spring Boot功能”部分中的“第4.1.5节”“应用程序事件和监听器”。

&emsp;&emsp;在使用EnvironmentPostProcessor刷新应用程序上下文之前，还可以自定义环境。 每个实现都应该在META-INF/spring.factories中注册，如以下示例所示：

``` 
org.springframework.boot.env.EnvironmentPostProcessor=com.example.YourEnvironmentPostProcessor
```

&emsp;&emsp;该实现可以加载任意文件并将它们添加到环境中。 例如，以下示例从类路径加载YAML配置文件：

``` 
public class EnvironmentPostProcessorExample implements EnvironmentPostProcessor {

	private final YamlPropertySourceLoader loader = new YamlPropertySourceLoader();

	@Override
	public void postProcessEnvironment(ConfigurableEnvironment environment,
			SpringApplication application) {
		Resource path = new ClassPathResource("com/example/myapp/config.yml");
		PropertySource<?> propertySource = loadYaml(path);
		environment.getPropertySources().addLast(propertySource);
	}

	private PropertySource<?> loadYaml(Resource path) {
		if (!path.exists()) {
			throw new IllegalArgumentException("Resource " + path + " does not exist");
		}
		try {
			return this.loader.load("custom-resource", path).get(0);
		}
		catch (IOException ex) {
			throw new IllegalStateException(
					"Failed to load yaml configuration from " + path, ex);
		}
	}

}
```

>环境已经准备好了Spring Boot默认加载的所有常用属性源。 因此，可以从环境中获取文件的位置。 前面的示例在列表的末尾添加了custom-resource属性source，以便在任何通常的其他位置中定义的键优先。 自定义实现可以定义另一个顺序。

&emsp;
>虽然在@SpringBootApplication上使用@PropertySource似乎是在环境中加载自定义资源的一种方便而简单的方法，但我们不建议这样做，因为Spring Boot会在刷新ApplicationContext之前准备环境。 使用@PropertySource定义的任何键加载太晚都不会对自动配置产生任何影响。

### **9.1.5 创建非Web应用程序**

&emsp;&emsp;并非所有Spring应用程序都必须是Web应用程序（或Web服务）。 如果要在main方法中执行某些代码，还要引导Spring应用程序来设置要使用的基础结构，则可以使用Spring Boot的SpringApplication功能。 SpringApplication更改其ApplicationContext类，具体取决于它是否认为它需要Web应用程序。 您可以做的第一件事就是将与服务器相关的依赖项（例如servlet API）从类路径中删除。 如果您不能这样做（例如，您从相同的代码库运行两个应用程序），那么您可以在SpringApplication实例上显式调用setWebApplicationType(WebApplicationType.NONE)或设置applicationContextClass属性（通过Java API或外部属性）。 您希望作为业务逻辑运行的应用程序代码可以作为CommandLineRunner实现，并作为@Bean定义放入上下文中。

## **9.2 属性和配置**

&emsp;&emsp;您可以使用ApplicationBuilder类来创建父/子ApplicationContext层次结构。 有关详细信息，请参阅“Spring Boot功能”部分中的“第4.1.4节”，“Fluent Builder API”。

### **9.2.1 在构建时自动展开属性**

&emsp;&emsp;您可以使用现有的构建配置自动扩展它们，而不是硬编码在项目的构建配置中也指定的某些属性。 这在Maven和Gradle都是可行的。

**9.2.1.1 使用Maven自动扩展属性**

&emsp;&emsp;您可以使用资源过滤从Maven项目自动扩展属性。 如果使用spring-boot-starter-parent，则可以使用@ .. @占位符引用Maven的“项目属性”，如以下示例所示：

``` 
app.encoding=@project.build.sourceEncoding@
app.java.version=@java.version@
```

>只有生产配置以这种方式过滤（换句话说，不对src/test/resources应用过滤）。

&emsp;
>如果启用addResources标志，则spring-boot：run目标可以将src/main/resources直接添加到类路径中（用于热重新加载）。 这样做可以绕过资源过滤和此功能。 相反，您可以使用exec：java目标或自定义插件的配置。 有关详细信息，请参阅插件使用情况页面。

&emsp;&emsp;如果不使用starter父级，则需要在pom.xml的<build />元素中包含以下元素：

``` 
<resources>
	<resource>
		<directory>src/main/resources</directory>
		<filtering>true</filtering>
	</resource>
</resources>
```

&emsp;&emsp;您还需要在<plugins />中包含以下元素：

``` 
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-resources-plugin</artifactId>
	<version>2.7</version>
	<configuration>
		<delimiters>
			<delimiter>@</delimiter>
		</delimiters>
		<useDefaultDelimiters>false</useDefaultDelimiters>
	</configuration>
</plugin>
```

>如果在配置中使用标准的Spring占位符（例如${placeholder}），则useDefaultDelimiters属性很重要。 如果该属性未设置为false，则可以通过构建扩展这些属性。

**9.2.1.2 使用Gradle自动扩展属性**

&emsp;&emsp;您可以通过配置Java插件的processResources任务来自动扩展Gradle项目中的属性，如以下示例所示：

``` 
processResources {
	expand(project.properties)
}
```

&emsp;&emsp;然后，您可以使用占位符来引用Gradle项目的属性，如以下示例所示：

``` 
app.name=${name}
app.description=${description}
```

>Gradle的expand方法使用Groovy的SimpleTemplateEngine，它可以转换`${..}`标记。 `${..}`样式与Spring自己的属性占位符机制冲突。 要将Spring属性占位符与自动扩展一起使用，请按如下方式转义Spring属性占位符：`\${..}`。

### **9.2.2 外部化SpringApplication的配置**

&emsp;&emsp;SpringApplication具有bean属性（主要是setter），因此您可以在创建应用程序时使用其Java API来修改其行为。 或者，您可以通过在spring.main.*中设置属性来外部化配置。 例如，在application.properties中，您可能具有以下设置：

``` 
spring.main.web-application-type=none
spring.main.banner-mode=off
```

&emsp;&emsp;然后在启动时不打印Spring Boot横幅，并且应用程序未启动嵌入式Web服务器。

&emsp;&emsp;外部配置中定义的属性将覆盖使用Java API指定的值，但用于创建ApplicationContext的源的明显例外。 考虑以下应用程序：

``` 
new SpringApplicationBuilder()
	.bannerMode(Banner.Mode.OFF)
	.sources(demo.MyApp.class)
	.run(args);
```

&emsp;&emsp;现在考虑以下配置：

``` 
spring.main.sources=com.acme.Config,com.acme.ExtraConfig
spring.main.banner-mode=console
```

&emsp;&emsp;实际应用程序现在显示横幅（由配置覆盖）并使用ApplicationContext的三个源（按以下顺序）：demo.MyApp，com.acme.Config和com.acme.ExtraConfig。

### **9.2.3 更改应用程序的外部属性的位置**

&emsp;&emsp;默认情况下，来自不同源的属性将按照定义的顺序添加到Spring Environment中（有关确切的顺序，请参阅“Spring Boot features”部分中的“第4.2章，外部化配置”）。

&emsp;&emsp;增加和修改此排序的一种好方法是将@PropertySource注释添加到应用程序源。 传递给SpringApplication静态便捷方法的类和使用setSources()添加的类将被检查以查看它们是否具有@PropertySources。 如果这样做，那么这些属性会尽早添加到Environment中，以便在ApplicationContext生命周期的所有阶段中使用。 以这种方式添加的属性的优先级低于使用默认位置（例如application.properties），系统属性，环境变量或命令行添加的属性。

&emsp;&emsp;您还可以提供以下系统属性（或环境变量）来更改行为：

- spring.config.name（SPRING_CONFIG_NAME）：默认为application作为文件名的根。
- spring.config.location（SPRING_CONFIG_LOCATION）：要加载的文件（例如类路径资源或URL）。 为此文档设置了一个单独的Environment属性源，它可以被系统属性，环境变量或命令行覆盖。


&emsp;&emsp;无论您在环境中设置什么，Spring Boot始终如上所述加载application.properties。 默认情况下，如果使用YAML，则扩展名为“.yml”的文件也会添加到列表中。

&emsp;&emsp;Spring Boot记录在DEBUG级别加载的配置文件以及在TRACE级别找不到的候选项。

&emsp;&emsp;有关更多详细信息，请参阅ConfigFileApplicationListener。

### **9.2.4 使用“短”命令行参数**

&emsp;&emsp;有些人喜欢使用（例如）--port = 9000而不是--server.port = 9000来在命令行上设置配置属性。 您可以通过在application.properties中使用占位符来启用此行为，如以下示例所示：

``` 
server.port=${port:8080}
```

>如果从spring-boot-starter-parent POM继承，则maven-resources-plugins的默认过滤器令牌已从`${*}`更改为@（即@maven.token@而不是$ {maven.token}）以防止与Spring样式的占位符冲突。 如果您已直接为application.properties启用了Maven筛选，则可能还需要更改默认筛选器标记以使用其他分隔符。

&emsp;
>在这种特定情况下，端口绑定可在Paoku环境（如Heroku或Cloud Foundry）中运行。 在这两个平台中，PORT环境变量自动设置，Spring可以绑定到环境属性的大写同义词。

### **9.2.5 使用YAML作为外部属性**

&emsp;&emsp;YAML是JSON的超集，因此，它是以分层格式存储外部属性的便捷语法，如以下示例所示：

``` 
spring:
	application:
		name: cruncher
	datasource:
		driverClassName: com.mysql.jdbc.Driver
		url: jdbc:mysql://localhost/test
server:
	port: 9000
```

&emsp;&emsp;创建一个名为application.yml的文件，并将其放在类路径的根目录中。 然后将snakeyaml添加到依赖项中（Maven坐标org.yaml:snakeyaml，如果使用spring-boot-starter则已包含在内）。 将YAML文件解析为Java Map&lt;String，Object&rt;（类似于JSON对象），并且Spring Boot将Map展平，使其深度为一级并具有句点分隔的键，因为许多人习惯在Java中使用Properties文件 。

&emsp;&emsp;上面的示例YAML对应于以下application.properties文件：

``` 
spring.application.name=cruncher
spring.datasource.driverClassName=com.mysql.jdbc.Driver
spring.datasource.url=jdbc:mysql://localhost/test
server.port=9000
```

&emsp;&emsp;有关YAML的更多信息，请参见“Spring Boot features”部分中的“第4.2.7节”，“使用YAML而不是属性”。

### **9.2.6 设置活动的配置文件**

&emsp;&emsp;Spring Environment有一个API，但你通常会设置一个System属性（spring.profiles.active）或一个OS环境变量（SPRING_PROFILES_ACTIVE）。 此外，您可以使用-D参数启动应用程序（请记住将其放在主类或jar存档之前），如下所示：

``` 
$ java -jar -Dspring.profiles.active=production demo-0.0.1-SNAPSHOT.jar
```

&emsp;&emsp;在Spring Boot中，您还可以在application.properties中设置活动配置文件，如以下示例所示：

``` 
spring.profiles.active=production
```

&emsp;&emsp;以这种方式设置的值将由System属性或环境变量设置替换，但不会由SpringApplicationBuilder.profiles()方法替换。 因此，后一个Java API可用于扩充配置文件而不更改默认值。

&emsp;&emsp;有关详细信息，请参阅“Spring Boot功能”部分中的“第4.3章，配置文件”。

### **9.2.7 根据环境更改配置**

&emsp;&emsp;YAML文件实际上是由---行分隔的文档序列，每个文档分别解析为展平的Map。

&emsp;&emsp;如果YAML文档包含spring.profiles键，则配置文件值（以逗号分隔的配置文件列表）将输入Spring Environment.acceptsProfiles（）方法。 如果这些配置文件中的任何一个处于活动状态，则该文档将包含在最终合并中（否则，它不包含在内），如以下示例所示：

``` 
server:
	port: 9000
---

spring:
	profiles: development
server:
	port: 9001

---

spring:
	profiles: production
server:
	port: 0
```

&emsp;&emsp;在前面的示例中，默认端口为9000。但是，如果名为“development”的Spring配置文件处于活动状态，则端口为9001.如果“production”处于活动状态，则端口为0。

>YAML文档按其遇到的顺序合并。 以后的值会覆盖以前的值。

&emsp;&emsp;要对属性文件执行相同的操作，可以使用application-${profile}.properties指定特定于配置文件的值。

### **9.2.8 发现外部属性的内置选项**

&emsp;&emsp;Spring Boot在运行时将外部属性从application.properties（或.yml文件和其他位置）绑定到应用程序中。 没有（并且在技术上不可能）单个位置中所有受支持属性的详尽列表，因为贡献可以来自类路径上的其他jar文件。

&emsp;&emsp;具有Actuator功能的正在运行的应用程序具有configprops端点，该端点显示通过@ConfigurationProperties可用的所有绑定和可绑定属性。

&emsp;&emsp;附录包含一个application.properties示例，其中包含Spring Boot支持的最常见属性的列表。 最终列表来自于搜索@ConfigurationProperties和@Value注释的源代码以及偶尔使用Binder。 有关加载属性的确切顺序的更多信息，请参见“第4.2章，外部化配置”。

## **9.3 嵌入式Web服务器**

&emsp;&emsp;每个Spring Boot Web应用程序都包含一个嵌入式Web服务器。 此功能会导致许多操作方法问题，包括如何更改嵌入式服务器以及如何配置嵌入式服务器。 本节回答了这些问题。

### **9.3.1 使用其他Web服务器**

&emsp;&emsp;许多Spring Boot启动器都包含默认的嵌入式容器。

- 对于servlet堆栈应用程序，spring-boot-starter-web包括tomcat，包括spring-boot-starter-tomcat，但你可以使用spring-boot-starter-jetty或spring-boot-starter-undertow。
- 对于反应堆栈应用，spring-boot-starter-webflux包括反应器网络，包括spring-boot-starter-reactor-netty，但你可以使用spring-boot-starter-tomcat，spring-boot-starter-jetty或spring -boot-starter-undertow。


&emsp;&emsp;切换到其他HTTP服务器时，除了包含所需的依赖项外，还需要排除默认依赖项。 Spring Boot为HTTP服务器提供单独的启动程序，以帮助使此过程尽可能简单。

&emsp;&emsp;以下Maven示例显示如何排除Tomcat并为Spring MVC包含Jetty：

``` 
<properties>
	<servlet-api.version>3.1.0</servlet-api.version>
</properties>
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
	<exclusions>
		<!-- Exclude the Tomcat dependency -->
		<exclusion>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-tomcat</artifactId>
		</exclusion>
	</exclusions>
</dependency>
<!-- Use Jetty instead -->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-jetty</artifactId>
</dependency>
```

>Servlet API的版本已被覆盖，因为与Tomcat 9和Undertow 2.0不同，Jetty 9.4不支持Servlet 4.0。

&emsp;&emsp;以下Gradle示例显示如何排除Netty并包含Spring WebFlux的Undertow：

``` 
configurations {
	// exclude Reactor Netty
	compile.exclude module: 'spring-boot-starter-reactor-netty'
}

dependencies {
	compile 'org.springframework.boot:spring-boot-starter-webflux'
	// Use Undertow instead
	compile 'org.springframework.boot:spring-boot-starter-undertow'
	// ...
}
```

>spring-boot-starter-reactor-netty需要使用WebClient类，因此即使需要包含不同的HTTP服务器，也可能需要依赖Netty。

### **9.3.2 禁用Web服务器**

&emsp;&emsp;如果您的类路径包含启动Web服务器所需的位，Spring Boot将自动启动它。 要禁用此行为，请在application.properties中配置WebApplicationType，如以下示例所示：

``` 
spring.main.web-application-type=none
```

### **9.3.3 更改HTTP端口**

&emsp;&emsp;在独立应用程序中，主HTTP端口默认为8080，但可以使用server.port设置（例如，在application.properties中或作为System属性）。 由于轻松绑定了Environment值，您还可以使用SERVER_PORT（例如，作为OS环境变量）。

&emsp;&emsp;要完全关闭HTTP端点但仍创建WebApplicationContext，请使用server.port = -1。 （这样做有时对测试很有用。）

&emsp;&emsp;有关更多详细信息，请参阅“Spring Boot功能”部分中的“第4.6.4.4节”，“自定义嵌入式Servlet容器”或ServerProperties源代码。

### **9.3.4 使用随机未分配的HTTP端口**

&emsp;&emsp;要扫描空闲端口（使用OS本机来防止冲突），请使用server.port = 0。

### **9.3.5 在运行时发现HTTP端口**

&emsp;&emsp;您可以从日志输出访问服务器运行的端口，也可以通过其WebServer访问ServletWebServerApplicationContext。 获得它并确保它已被初始化的最好方法是添加一个类型为ApplicationListener <ServletWebServerInitializedEvent>的@Bean，并在发布时将容器拉出事件。

&emsp;&emsp;使用@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)的测试也可以使用@LocalServerPort批注将实际端口注入字段，如以下示例所示：

``` 
@RunWith(SpringJUnit4ClassRunner.class)
@SpringBootTest(webEnvironment=WebEnvironment.RANDOM_PORT)
public class MyWebIntegrationTests {

	@Autowired
	ServletWebServerApplicationContext server;

	@LocalServerPort
	int port;

	// ...

}
```

>@LocalServerPort是@Value（“$ {local.server.port}”）的元注释。 不要尝试在常规应用程序中注入端口。 正如我们刚刚看到的那样，只有在容器初始化之后才设置该值。 与测试相反，应用程序代码回调会尽早处理（在值实际可用之前）。

### **9.3.6 启用HTTP响应压缩**

&emsp;&emsp;Jetty，Tomcat和Undertow支持HTTP响应压缩。 它可以在application.properties中启用，如下所示：

``` 
server.compression.enabled=true
```

&emsp;&emsp;默认情况下，只有在内容类型为以下内容之一时才会压缩响应：

- text/html
- text/xml
- text/plain
- text/css
- text/javascript
- application/javascript
- application/json
- application/xml


&emsp;&emsp;您可以通过设置server.compression.mime-types属性来配置此行为。

### **9.3.7 配置SSL**

&emsp;&emsp;可以通过设置各种server.ssl.*属性以声明方式配置SSL，通常在application.properties或application.yml中。 以下示例显示了在application.properties中设置SSL属性：

``` 
server.port=8443
server.ssl.key-store=classpath:keystore.jks
server.ssl.key-store-password=secret
server.ssl.key-password=another-secret
```

&emsp;&emsp;有关所有受支持属性的详细信息，请参阅Ssl。

&emsp;&emsp;使用上述示例之类的配置意味着应用程序不再支持端口8080上的普通HTTP连接器.Spring Boot不支持通过application.properties配置HTTP连接器和HTTPS连接器。 如果要同时使用两者，则需要以编程方式配置其中一个。 我们建议使用application.properties来配置HTTPS，因为HTTP连接器更容易以编程方式配置。 有关示例，请参阅spring-boot-sample-tomcat-multi-connectors示例项目。

### **9.3.8 配置HTTP/2**

&emsp;&emsp;您可以使用server.http2.enabled配置属性在Spring Boot应用程序中启用HTTP/2支持。 此支持取决于所选的Web服务器和应用程序环境，因为JDK8不支持该协议。

>Spring Boot不支持h2c，即HTTP/2协议的明文版本。 因此，您必须先配置SSL。

**9.3.8.1 Undertow的HTTP/2**

&emsp;&emsp;从Undertow 1.4.0+开始，支持HTTP/2，对JDK8没有任何额外要求。

**9.3.8.2 Jetty的HTTP/2**

&emsp;&emsp;从Jetty 9.4.8开始，Conscrypt库也支持HTTP / 2。 要启用该支持，您的应用程序需要有两个额外的依赖项：org.eclipse.jetty:jetty-alpn-conscrypt-server和org.eclipse.jetty.http2:http2-server。

**9.3.8.3 Tomcat的HTTP/2**

&emsp;&emsp;Spring Boot默认使用Tomcat 9.0.x，它在使用JDK 9或更高版本时支持HTTP/2的开箱即用。 或者，如果在主机操作系统上安装了libtcnative库及其依赖项，则可以在JDK 8上使用HTTP/2。

&emsp;&emsp;必须使库文件夹（如果尚未可用）到JVM库路径。 您可以使用JVM参数执行此操作，例如-Djava.library.path = /usr/local/opt/tomcat-native/lib。 有关更多信息请查看Tomcat官方文档。

&emsp;&emsp;在没有该本机支持的情况下在JDK 8上启动Tomcat 9.0.x会记录以下错误：

``` 
ERROR 8787 --- [           main] o.a.coyote.http11.Http11NioProtocol      : The upgrade handler [org.apache.coyote.http2.Http2Protocol] for [h2] only supports upgrade via ALPN but has been configured for the ["https-jsse-nio-8443"] connector that does not support ALPN.
```

&emsp;&emsp;此错误不是致命错误，应用程序仍以HTTP/1.1 SSL支持启动。

**9.3.8.4 Reactor Netty的HTTP/2**

&emsp;&emsp;spring-boot-webflux-starter默认使用Reactor Netty作为服务器。 可以使用JDK 9或更高版本的JDK支持为Reactor Netty配置HTTP/2。 对于JDK 8环境或最佳运行时性能，此服务器还支持具有本机库的HTTP/2。 要启用它，您的应用程序需要具有其他依赖项。

&emsp;&emsp;Spring Boot管理io.netty的版本：netty-tcnative-boringssl-static“uber jar”，包含适用于所有平台的本机库。 开发人员可以选择使用classifier仅导入所需的依赖项（请参阅Netty官方文档）。

### **9.3.9 配置Web服务器**

&emsp;&emsp;通常，您应首先考虑使用众多可用配置键中的一个，并通过在application.properties（或application.yml或环境等）中添加新条目来自定义Web服务器，请参阅“第9.2.8 发现外部属性的内置选项”）。 server.* namespace在这里非常有用，它包括server.tomcat.*，server.jett.*等名称空间，用于特定于服务器的功能。 请参阅附录A，常见应用程序属性列表。

&emsp;&emsp;前面的部分介绍了许多常见用例，例如压缩，SSL或HTTP / 2。 但是，如果您的用例不存在配置键，则应该查看WebServerFactoryCustomizer。 您可以声明这样的组件并获得与您选择的服务器工厂相关的访问权限：您应该为所选服务器（Tomcat，Jetty，Reactor Netty，Undertow）和所选Web堆栈（Servlet或Reactive）选择变量。

&emsp;&emsp;以下示例适用于具有spring-boot-starter-web（Servlet堆栈）的Tomcat：

``` 
@Component
public class MyTomcatWebServerCustomizer
		implements WebServerFactoryCustomizer<TomcatServletWebServerFactory> {

	@Override
	public void customize(TomcatServletWebServerFactory factory) {
		// customize the factory here
	}
}
```

&emsp;&emsp;另外Spring Boot提供：

<table>
	<tr>
		<th>Server</th>
		<th>Servlet stack</th>
		<th>Reactive stack</th>
	</tr>
	<tr>
		<td>Tomcat</td>
		<td>TomcatServletWebServerFactory</td>
		<td>TomcatReactiveWebServerFactory</td>
	</tr>
	<tr>
		<td>Jetty</td>
		<td>JettyServletWebServerFactory</td>
		<td>JettyReactiveWebServerFactory</td>
	</tr>
	<tr>
		<td>Undertow</td>
		<td>UndertowServletWebServerFactory</td>
		<td>UndertowReactiveWebServerFactory</td>
	</tr>
	<tr>
		<td>Reactor</td>
		<td>N/A</td>
		<td>NettyReactiveWebServerFactory</td>
	</tr>
</table>

&emsp;&emsp;一旦您有权访问WebServerFactory，您通常可以向其添加定制器以配置特定部件，如连接器，服务器资源或服务器本身 - 所有这些都使用特定于服务器的API。

&emsp;&emsp;作为最后的手段，您还可以声明自己的WebServerFactory组件，它将覆盖Spring Boot提供的组件。 在这种情况下，您不能再依赖服务器命名空间中的配置属性。

### **9.3.10 向应用程序添加Servlet，Filter或Listener**

&emsp;&emsp;在servlet堆栈应用程序中，即使用spring-boot-starter-web，有两种方法可以将Servlet API，Filter，ServletContextListener和Servlet API支持的其他侦听器添加到您的应用程序中：

- 使用Spring Bean添加Servlet，Filter或Listener
- 使用类路径扫描添加Servlet，Filter或Listener


**9.3.10.1 使用Spring Bean添加Servlet，Filter或Listener**

&emsp;&emsp;要使用Spring bean添加Servlet，Filter或Servlet * Listener，必须为其提供@Bean定义。 当您想要注入配置或依赖项时，这样做非常有用。 但是，您必须非常小心，它们不会导致太多其他bean的初始化，因为它们必须在应用程序生命周期的早期安装在容器中。 （例如，让它们依赖于您的DataSource或JPA配置并不是一个好主意。）您可以通过在首次使用而不是初始化时懒惰地初始化bean来解决此类限制。

&emsp;&emsp;对于Filters和Servlet，您还可以通过添加FilterRegistrationBean或ServletRegistrationBean来代替底层组件或添加底层组件来添加映射和init参数。

>如果在过滤器注册中未指定dispatcherType，则使用REQUEST。 这与Servlet规范的默认调度程序类型一致。

&emsp;&emsp;像任何其他Spring bean一样，您可以定义Servlet过滤器bean的顺序; 请务必查看“注册Servlets, Filters, 和 Listeners 作为 Spring Beans“部分。

**1）禁用Servlet或Filter的注册**

&emsp;&emsp;如前所述，任何Servlet或Filter bean都会自动注册到servlet容器。 要禁用特定Filter或Servlet bean的注册，请为其创建注册Bean并将其标记为已禁用，如以下示例所示：

``` 
@Bean
public FilterRegistrationBean registration(MyFilter filter) {
	FilterRegistrationBean registration = new FilterRegistrationBean(filter);
	registration.setEnabled(false);
	return registration;
}
```

**9.3.10.2 使用类路径扫描添加Servlet，Filter或Listener**

&emsp;&emsp;通过使用@ServletComponentScan注释@Configuration类并指定包含要注册的组件的包，可以使用嵌入式servlet容器自动注册@WebServlet，@WebFilter和@WebListener注释类。 默认情况下，@ServletComponentScan会从带注释的类的包中进行扫描。

### **9.3.11 配置访问日志记录**

&emsp;&emsp;可以通过各自的命名空间为Tomcat，Undertow和Jetty配置访问日志。

例如，以下设置使用自定义模式在Tomcat上记录访问权限。

``` 
server.tomcat.basedir=my-tomcat
server.tomcat.accesslog.enabled=true
server.tomcat.accesslog.pattern=%t %a "%r" %s (%D ms)
```

>日志的默认位置是相对于Tomcat基目录的日志目录。 默认情况下，logs目录是临时目录，因此您可能希望修复Tomcat的基目录或使用日志的绝对路径。 在前面的示例中，日志在my-tomcat/logs中相对于应用程序的工作目录可用。

&emsp;&emsp;可以以类似的方式配置Undertow的访问日志记录，如以下示例所示：

``` 
server.undertow.accesslog.enabled=true
server.undertow.accesslog.pattern=%t %a "%r" %s (%D ms)
```

&emsp;&emsp;日志存储在相对于应用程序工作目录的日志目录中。 您可以通过设置server.undertow.accesslog.directory属性来自定义此位置。

&emsp;&emsp;最后，Jetty的访问日志记录也可以配置如下：

``` 
server.jetty.accesslog.enabled=true
server.jetty.accesslog.filename=/var/log/jetty-access.log
```

&emsp;&emsp;默认情况下，日志会重定向到System.err。 有关更多详细信息，请参阅Jetty文档。

### **9.3.12 在前端代理服务器后面运行**

&emsp;&emsp;您的应用程序可能需要发送302重定向或使用绝对链接将内容呈现回自身。 在代理后面运行时，调用者需要指向代理的链接，而不是托管应用程序的计算机的物理地址。 通常，这种情况是通过与代理的合同来处理的，代理会添加标题以告诉后端如何构建自己的链接。

&emsp;&emsp;如果代理添加了传统的X-Forwarded-For和X-Forwarded-Proto标头（大多数代理服务器都这样做），那么绝对链接应该正确呈现，只要在application.properties中将server.use-forward-headers设置为true即可。

>如果您的应用程序在Cloud Foundry或Heroku中运行，则server.use-forward-headers属性默认为true。 在所有其他实例中，它默认为false。

**9.3.12.1 自定义Tomcat的代理配置**

&emsp;&emsp;如果使用Tomcat，还可以配置用于携带“forwarded”信息的标头名称，如以下示例所示：

``` 
server.tomcat.remote-ip-header=x-your-remote-ip-header
server.tomcat.protocol-header=x-your-protocol-header
```

&emsp;&emsp;Tomcat还配置了一个默认的正则表达式，该表达式匹配要信任的内部代理。 默认情况下，10/8,192.168/16,169.254/16和127/8中的IP地址是可信的。 您可以通过向application.properties添加条目来自定义值的配置，如以下示例所示：

``` 
server.tomcat.internal-proxies=192\\.168\\.\\d{1,3}\\.\\d{1,3}
```

>仅当使用properties文件进行配置时，才需要双反斜杠。 如果使用YAML，则单个反斜杠就足够了，并且与前面示例中显示的值相等的值为192\.168\.\d{1,3}\.\d{1,3}。

&emsp;
>您可以通过将internal-proxies设置为空来信任所有代理（但在生产中不这样做）。

&emsp;&emsp;您可以通过关闭自动关闭（执行此操作，设置server.use-forward-headers = false）并在TomcatServletWebServerFactory bean中添加新的阀门实例来完全控制Tomcat的RemoteIpValve的配置。

### **9.3.13 使用Tomcat启用多个连接**

&emsp;&emsp;您可以将org.apache.catalina.connector.Connector添加到TomcatServletWebServerFactory，它可以允许多个连接器，包括HTTP和HTTPS连接器，如以下示例所示：

``` 
@Bean
public ServletWebServerFactory servletContainer() {
	TomcatServletWebServerFactory tomcat = new TomcatServletWebServerFactory();
	tomcat.addAdditionalTomcatConnectors(createSslConnector());
	return tomcat;
}

private Connector createSslConnector() {
	Connector connector = new Connector("org.apache.coyote.http11.Http11NioProtocol");
	Http11NioProtocol protocol = (Http11NioProtocol) connector.getProtocolHandler();
	try {
		File keystore = new ClassPathResource("keystore").getFile();
		File truststore = new ClassPathResource("keystore").getFile();
		connector.setScheme("https");
		connector.setSecure(true);
		connector.setPort(8443);
		protocol.setSSLEnabled(true);
		protocol.setKeystoreFile(keystore.getAbsolutePath());
		protocol.setKeystorePass("changeit");
		protocol.setTruststoreFile(truststore.getAbsolutePath());
		protocol.setTruststorePass("changeit");
		protocol.setKeyAlias("apitester");
		return connector;
	}
	catch (IOException ex) {
		throw new IllegalStateException("can't access keystore: [" + "keystore"
				+ "] or truststore: [" + "keystore" + "]", ex);
	}
}
```

### **9.3.14 使用Tomcat的LegacyCookieProcessor**

&emsp;&emsp;默认情况下，Spring Boot使用的嵌入式Tomcat不支持Cookie格式的“Version 0”，因此您可能会看到以下错误：

``` 
java.lang.IllegalArgumentException: An invalid character [32] was present in the Cookie value
```

&emsp;&emsp;如果可能的话，您应该考虑将代码更新为仅存储符合以后Cookie规范的值。 但是，如果您无法更改cookie的编写方式，则可以将Tomcat配置为使用LegacyCookieProcessor。 要切换到LegacyCookieProcessor，请使用添加TomcatContextCustomizer的WebServerFactoryCustomizer bean，如以下示例所示：

``` 
@Bean
public WebServerFactoryCustomizer<TomcatServletWebServerFactory> cookieProcessorCustomizer() {
	return (factory) -> factory.addContextCustomizers(
			(context) -> context.setCookieProcessor(new LegacyCookieProcessor()));
}
```

### **9.3.15 使用Undertow启用多个Listener**

&emsp;&emsp;将UndertowBuilderCustomizer添加到UndertowServletWebServerFactory并向Builder添加一个侦听器，如以下示例所示：

``` 
@Bean
public UndertowServletWebServerFactory servletWebServerFactory() {
	UndertowServletWebServerFactory factory = new UndertowServletWebServerFactory();
	factory.addBuilderCustomizers(new UndertowBuilderCustomizer() {

		@Override
		public void customize(Builder builder) {
			builder.addHttpListener(8080, "0.0.0.0");
		}

	});
	return factory;
}
```

### **9.3.16 使用@ServerEndpoint创建WebSocket端点**

&emsp;&emsp;如果要在使用嵌入式容器的Spring Boot应用程序中使用@ServerEndpoint，则必须声明单个ServerEndpointExporter @Bean，如以下示例所示：

``` 
@Bean
public ServerEndpointExporter serverEndpointExporter() {
	return new ServerEndpointExporter();
}
```

&emsp;&emsp;前面示例中显示的bean使用基础WebSocket容器注册任何带有@ServerEndpoint注释的bean。 当部署到独立的servlet容器时，此角色由servlet容器初始化程序执行，而不需要ServerEndpointExporter bean。

## **9.4 Spring MVC**

&emsp;&emsp;Spring Boot有许多包含Spring MVC的启动器。 请注意，一些启动器包含对Spring MVC的依赖，而不是直接包含它。 本节回答有关Spring MVC和Spring Boot的常见问题。

### **9.4.1 编写JSON REST服务**

&emsp;&emsp;只要Jackson2在类路径中，Spring Boot应用程序中的任何Spring @RestController都应默认呈现JSON响应，如以下示例所示：

``` 
@RestController
public class MyController {

	@RequestMapping("/thing")
	public MyThing thing() {
			return new MyThing();
	}

}
```

&emsp;&emsp;只要MyThing可以被Jackson2序列化（对于普通的POJO或Groovy对象都是如此），那么localhost:8080/thing默认提供它的JSON表示。 请注意，在浏览器中，您有时可能会看到XML响应，因为浏览器倾向于发送更喜欢XML的接受标头。

### **9.4.2 编写XML REST服务**

&emsp;&emsp;如果在类路径上有Jackson XML扩展（jackson-dataformat-xml），则可以使用它来呈现XML响应。 我们用于JSON的前一个示例可以使用。 要使用Jackson XML渲染器，请将以下依赖项添加到项目中：

``` 
<dependency>
	<groupId>com.fasterxml.jackson.dataformat</groupId>
	<artifactId>jackson-dataformat-xml</artifactId>
</dependency>
```

&emsp;&emsp;如果Jackson的XML扩展不可用，则使用JAXB（默认情况下在JDK中提供），并且需要将MyThing注释为@XmlRootElement，如以下示例所示：

``` 
@XmlRootElement
public class MyThing {
	private String name;
	// .. getters and setters
}
```

&emsp;&emsp;要使服务器呈现XML而不是JSON，您可能必须发送Accept:text/xml标头（或使用浏览器）。

### **9.4.3 自定义Jackson ObjectMapper**

&emsp;&emsp;Spring MVC（客户端和服务器端）使用HttpMessageConverters在HTTP交换中协商内容转换。 如果Jackson在类路径上，您已经获得了Jackson2ObjectMapperBuilder提供的默认转换器，其中一个实例是为您自动配置的。

&emsp;&emsp;ObjectMapper（或Jackson XML转换器的XmlMapper）实例（默认创建）具有以下自定义属性：

- MapperFeature.DEFAULT_VIEW_INCLUSION已禁用
- DeserializationFeature.FAIL_ON_UNKNOWN_PROPERTIES已禁用
- SerializationFeature.WRITE_DATES_AS_TIMESTAMPS已禁用


&emsp;&emsp;Spring Boot还具有一些功能，可以更轻松地自定义此行为。

&emsp;&emsp;您可以使用环境配置ObjectMapper和XmlMapper实例。 Jackson提供了一套广泛的简单开/关功能，可用于配置其处理的各个方面。 这些功能在六个enum（在Jackson中）中描述，它们映射到环境中的属性：

<table>
	<tr>
		<th>Enum</th>
		<th>Property</th>
		<th>Values</th>
	</tr>
	<tr>
		<td>com.fasterxml.jackson.databind.DeserializationFeature</td>
		<td>spring.jackson.deserialization.</td>
		<td>true, false</td>
	</tr>
	<tr>
		<td>com.fasterxml.jackson.core.JsonGenerator.Feature</td>
		<td>spring.jackson.generator.&lt;feature_name></td>
		<td>true, false</td>
	</tr>
	<tr>
		<td>com.fasterxml.jackson.databind.MapperFeature</td>
		<td>spring.jackson.mapper.&lt;feature_name></td>
		<td>true, false</td>
	</tr>
	<tr>
		<td>com.fasterxml.jackson.core.JsonParser.Feature</td>
		<td>spring.jackson.parser.&lt;feature_name></td>
		<td>true, false</td>
	</tr>
	<tr>
		<td>com.fasterxml.jackson.databind.SerializationFeature</td>
		<td>spring.jackson.serialization.&lt;feature_name></td>
		<td>true, false</td>
	</tr>
	<tr>
		<td>com.fasterxml.jackson.annotation.JsonInclude.Include</td>
		<td>spring.jackson.default-property-inclusion</td>
		<td>always, non_null, non_absent, non_default, non_empty</td>
	</tr>
</table>

例如，要启用格式化打印，请设置spring.jackson.serialization.indent_output = true。 请注意，由于使用了宽松绑定，indent_output的情况不必与相应的枚举常量（即INDENT_OUTPUT）的情况相匹配。

&emsp;&emsp;此基于环境的配置应用于自动配置的Jackson2ObjectMapperBuilder bean，并应用于使用构建器创建的任何映射器，包括自动配置的ObjectMapper bean。

&emsp;&emsp;上下文的Jackson2ObjectMapperBuilder可以由一个或多个Jackson2ObjectMapperBuilderCustomizer bean定制。 可以排序这样的定制器bean（Boot自己的定制器的顺序为0），允许在Boot定制之前和之后应用其他定制。

&emsp;&emsp;任何类型为com.fasterxml.jackson.databind.Module的bean都会自动注册到自动配置的Jackson2ObjectMapperBuilder，并应用于它创建的任何ObjectMapper实例。 这为您在应用程序中添加新功能时提供了一种提供自定义模块的全局机制。

&emsp;&emsp;如果要完全替换默认的ObjectMapper，请定义该类型的@Bean并将其标记为@Primary，或者，如果您更喜欢基于构建器的方法，请定义Jackson2ObjectMapperBuilder @Bean。 请注意，在任何一种情况下，这样做都会禁用ObjectMapper的所有自动配置。

&emsp;&emsp;如果您提供任何类型为MappingJackson2HttpMessageConverter的@Beans，它们将替换MVC配置中的默认值。 此外，还提供了类型为HttpMessageConverters的便捷bean（如果使用默认的MVC配置，则始终可用）。 它有一些有用的方法来访问默认和用户增强的消息转换器。

&emsp;&emsp;有关更多详细信息，请参见“9.4.4节”，“自定义@ResponseBody渲染”部分和WebMvcAutoConfiguration源代码。

### **9.4.4 自定义@ResponseBody渲染**

&emsp;&emsp;Spring使用HttpMessageConverters呈现@ResponseBody（或来自@RestController的响应）。 您可以通过在Spring Boot上下文中添加适当类型的bean来提供其他转换器。 如果您添加的bean是默认包含的类型（例如，用于JSON转换的MappingJackson2HttpMessageConverter），它将替换默认值。 提供了类型为HttpMessageConverters的便捷bean，如果您使用默认的MVC配置，它始终可用。 它有一些有用的方法来访问默认和用户增强的消息转换器（例如，如果要将它们手动注入自定义RestTemplate，它可能很有用）。

&emsp;&emsp;与正常的MVC用法一样，您提供的任何WebMvcConfigurer bean也可以通过覆盖configureMessageConverters方法来提供转换器。 但是，与普通的MVC不同，您只能提供所需的其他转换器（因为Spring Boot使用相同的机制来提供其默认值）。 最后，如果您通过提供自己的@EnableWebMvc配置选择退出Spring Boot默认MVC配置，则可以完全控制并通过使用WebMvcConfigurationSupport中的getMessageConverters手动完成所有操作。

&emsp;&emsp;有关更多详细信息，请参阅WebMvcAutoConfiguration源代码。

### **9.4.5 处理多部分文件上传**

&emsp;&emsp;Spring Boot包含Servlet 3 javax.servlet.http.Part API以支持上传文件。 默认情况下，Spring Boot配置Spring MVC，每个文件的最大大小为1MB，单个请求中的文件数据最大为10MB。 您可以覆盖这些值，中间数据的存储位置（例如，到/tmp目录），以及使用MultipartProperties类中公开的属性将数据刷新到磁盘的阈值。 例如，如果要指定文件不受限制，请将spring.servlet.multipart.max-file-size属性设置为-1。

&emsp;&emsp;当您希望在Spring MVC控制器处理程序方法中将多部分编码的文件数据作为MultipartFile类型的@RequestParam注释参数接收时，多部分支持非常有用。

&emsp;&emsp;有关更多详细信息，请参阅MultipartAutoConfiguration源。

>建议使用容器的内置支持进行分段上传，而不是引入其他依赖项，例如Apache Commons File Upload。

### **9.4.6 关闭Spring MVC DispatcherServlet**

&emsp;&emsp;默认情况下，所有内容都是从应用程序的根目录（/）提供的。 如果您希望映射到其他路径，可以按如下方式配置：

``` 
spring.mvc.servlet.path=/acme
```

&emsp;&emsp;如果你有额外的servlet，你可以为每个servlet声明一个类型为Servlet或ServletRegistrationBean的@Bean，Spring Boot会将它们透明地注册到容器中。 因为servlet是以这种方式注册的，所以可以将它们映射到DispatcherServlet的子上下文而不调用它。

&emsp;&emsp;自己配置DispatcherServlet是不寻常的，但如果你真的需要这样做，还必须提供类型为DispatcherServletPath的@Bean，以提供自定义DispatcherServlet的路径。

### **9.4.7 关闭默认MVC配置**

&emsp;&emsp;完全控制MVC配置的最简单方法是使用@EnableWebMvc注释提供您自己的@Configuration。 这样做会将所有MVC配置留在您的手中。

### **9.4.8 自定义ViewResolvers**

&emsp;&emsp;ViewResolver是Spring MVC的核心组件，将@Controller中的视图名称转换为实际的View实现。 请注意，ViewResolvers主要用于UI应用程序，而不是REST样式的服务（View不用于呈现@ResponseBody）。 ViewResolver有很多可供选择的实现，而Spring本身并不认为你应该使用哪些。 另一方面，Spring Boot会为您安装一个或两个，具体取决于它在类路径和应用程序上下文中找到的内容。 DispatcherServlet使用它在应用程序上下文中找到的所有解析器，依次尝试每个解析器，直到得到结果，因此，如果添加自己的解析器，则必须知道顺序以及添加解析器的位置。

&emsp;&emsp;WebMvcAutoConfiguration将以下ViewResolvers添加到您的上下文中：

- 一个名为“defaultViewResolver”的InternalResourceViewResolver。 这个定位可以使用DefaultServlet呈现的物理资源（包括静态资源和JSP页面，如果您使用它们）。 它将前缀和后缀应用于视图名称，然后在servlet上下文中查找具有该路径的物理资源（默认值为空，但可通过spring.mvc.view.prefix和spring.mvc.view.suffix进行外部配置）。 您可以通过提供相同类型的bean来覆盖它。
- 名为“beanNameViewResolver”的BeanNameViewResolver。 这是视图解析器链的一个有用成员，并获取与正在解析的视图同名的任何bean。 没有必要覆盖或替换它。
- 仅当存在View类型的Bean时，才会添加名为“viewResolver”的ContentNegotiatingViewResolver。 这是一个“主”解析器，委托给所有其他解析器，并尝试找到客户端发送的“Accept”HTTP标头的匹配项。 有一个关于ContentNegotiatingViewResolver的有用博客，您可能希望学习以了解更多信息，您也可以查看源代码以获取详细信息。 您可以通过定义名为“viewResolver”的bean来关闭自动配置的ContentNegotiatingViewResolver。
- 如果您使用Thymeleaf，您还有一个名为'thymeleafViewResolver'的ThymeleafViewResolver。 它通过使用前缀和后缀包围视图名称来查找资源。 前缀是spring.thymeleaf.prefix，后缀是spring.thymeleaf.suffix。 前缀和后缀的值分别默认为“classpath:/templates/”和“.html”。 您可以通过提供相同名称的bean来覆盖ThymeleafViewResolver。
- 如果您使用FreeMarker，您还有一个名为“freeMarkerViewResolver”的FreeMarkerViewResolver。 它通过用前缀和后缀包围视图名称来查找加载器路径中的资源（外部化为spring.freemarker.templateLoaderPath并具有默认值'classpath:/templates/'）。 前缀外部化为spring.freemarker.prefix，后缀外部化为spring.freemarker.suffix。 前缀和后缀的默认值分别为空和“.ftl”。 您可以通过提供相同名称的bean来覆盖FreeMarkerViewResolver。
- 如果您使用Groovy模板（实际上，如果groovy-templates在您的类路径中），您还有一个名为'groovyMarkupViewResolver'的GroovyMarkupViewResolver。 它通过用前缀和后缀包围视图名称来查找加载器路径中的资源（外部化为spring.groovy.template.prefix和spring.groovy.template.suffix）。 前缀和后缀分别具有“classpath:/templates/”和“.tpl”的默认值。 您可以通过提供相同名称的bean来覆盖GroovyMarkupViewResolver。


&emsp;&emsp;有关更多详细信息，请参阅以下类的源码：

- WebMvcAutoConfiguration
- ThymeleafAutoConfiguration
- FreeMarkerAutoConfiguration
- GroovyTemplateAutoConfiguration


## **9.5 使用Spring Security进行测试**

&emsp;&emsp;Spring Security支持以特定用户身份运行测试。 例如，下面代码段中的测试将与具有ADMIN角色的经过身份验证的用户一起运行。

``` 
@Test
@WithMockUser(roles="ADMIN")
public void requestProtectedUrlWithUser() throws Exception {
	mvc
		.perform(get("/"))
		...
}
```

&emsp;&emsp;Spring Security提供了与Spring MVC Test的全面集成，这也可以在使用@WebMvcTest切片和MockMvc测试控制器时使用。

&emsp;&emsp;有关Spring Security测试支持的其他详细信息，请参阅Spring Security的参考文档）。

## **9.6 Jersey**

### **9.6.1 使用Spring Security保护Jersey端点**

&emsp;&emsp;Spring Security可用于保护基于Jersey的Web应用程序，其方式与用于保护基于Spring MVC的Web应用程序的方式非常相似。 但是，如果要在Jersey中使用Spring Security的方法级安全性，则必须将Jersey配置为使用setStatus(int)而不是sendError(int)。 这可以防止Jersey在Spring Security有机会向客户端报告身份验证或授权失败之前提交响应。

&emsp;&emsp;必须在应用程序的ResourceConfig bean上将jersey.config.server.response.setStatusOverSendError属性设置为true，如以下示例所示：

``` 
@Component
public class JerseyConfig extends ResourceConfig {

	public JerseyConfig() {
		register(Endpoint.class);
		setProperties(Collections.singletonMap(
				"jersey.config.server.response.setStatusOverSendError", true));
	}

}
```

## **9.7 HTTP客户端**

&emsp;&emsp;Spring Boot提供了许多与HTTP客户端配合使用的启动器。 本节回答与使用它们相关的问题。

### **9.7.1 配置RestTemplate以使用代理**

&emsp;&emsp;如第4.13.1节“自定义RestTemplate”中所述，您可以将RestTemplateCustomizer与RestTemplateBuilder一起使用来构建自定义的RestTemplate。 这是创建配置为使用代理的RestTemplate的推荐方法。

&emsp;&emsp;代理配置的确切详细信息取决于正在使用的基础客户端请求工厂。 以下示例使用HttpClient配置HttpComponentsClientRequestFactory，该HttpClient使用除192.168.0.5之外的所有主机的代理：

``` 
static class ProxyCustomizer implements RestTemplateCustomizer {

	@Override
	public void customize(RestTemplate restTemplate) {
		HttpHost proxy = new HttpHost("proxy.example.com");
		HttpClient httpClient = HttpClientBuilder.create()
				.setRoutePlanner(new DefaultProxyRoutePlanner(proxy) {

					@Override
					public HttpHost determineProxy(HttpHost target,
							HttpRequest request, HttpContext context)
							throws HttpException {
						if (target.getHostName().equals("192.168.0.5")) {
							return null;
						}
						return super.determineProxy(target, request, context);
					}

				}).build();
		restTemplate.setRequestFactory(
				new HttpComponentsClientHttpRequestFactory(httpClient));
	}

}
```

## **9.8 日志**

&emsp;&emsp;除了Commons Logging API之外，Spring Boot没有强制的日志记录依赖性，Commons Logging API通常由Spring Framework的spring-jcl模块提供。 要使用Logback，您需要在类路径中包含它和spring-jcl。 最简单的方法是通过启动器，它们都依赖于spring-boot-starter-logging。 对于Web应用程序，您只需要spring-boot-starter-web，因为它依赖于日志记录启动器。 如果您使用Maven，以下依赖项会为您添加日志记录：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

&emsp;&emsp;Spring Boot有一个LoggingSystem抽象，它试图根据类路径的内容配置日志记录。 如果Logback可用，则它是第一选择。

&emsp;&emsp;如果您需要对日志记录进行的唯一更改是设置各种记录器的级别，则可以使用“logging.level”前缀在application.properties中执行此操作，如以下示例所示：

``` 
logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate=ERROR
```

&emsp;&emsp;您还可以使用“logging.file”设置要写入日志的文件的位置（除控制台外）。

&emsp;&emsp;要配置日志记录系统的更细粒度设置，您需要使用相关LoggingSystem支持的本机配置格式。 默认情况下，Spring Boot从系统的默认位置（例如classpath:Logback的logback.xml）中选择本机配置，但您可以使用“logging.config”属性设置配置文件的位置。

### **9.8.1 配置Logback来记录日志**

&emsp;&emsp;如果将logback.xml放在类路径的根目录中，则从那里（或从logback-spring.xml中获取）以利用Boot提供的模板功能。 Spring Boot提供了一个默认的基本配置，如果要设置级别，可以包括该配置，如以下示例所示：

``` 
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
	<include resource="org/springframework/boot/logging/logback/base.xml"/>
	<logger name="org.springframework.web" level="DEBUG"/>
</configuration>
```

&emsp;&emsp;如果你看一下spring-boot jar中的base.xml，你会发现它使用了LoggingSystem为你创建的一些有用的System属性：

- \${PID}：当前进程ID。
- \${LOG_FILE}：是否在Boot的外部配置中设置了logging.file。
- \${LOG_PATH}：是否在Boot的外部配置中设置了logging.path（表示日志文件所在的目录）。
- \${LOG_EXCEPTION_CONVERSION_WORD}：是否在Boot的外部配置中设置了logging.exception-conversion-word。

&emsp;&emsp;Spring Boot还通过使用自定义Logback转换器在控制台上（但不在日志文件中）提供了一些漂亮的ANSI颜色终端输出。 有关详细信息，请参阅默认的base.xml配置。

&emsp;&emsp;如果Groovy在类路径上，您应该能够使用logback.groovy配置Logback。 如果存在，则优先考虑此设置。

**9.8.1.1 配置仅文件输出的Logback**

&emsp;&emsp;如果要禁用控制台日志记录并仅将输出写入文件，则需要使用自定义logback-spring.xml导入file-appender.xml但不导入console-appender.xml，如以下示例所示：

``` 
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
	<include resource="org/springframework/boot/logging/logback/defaults.xml" />
	<property name="LOG_FILE" value="${LOG_FILE:-${LOG_PATH:-${LOG_TEMP:-${java.io.tmpdir:-/tmp}}/}spring.log}"/>
	<include resource="org/springframework/boot/logging/logback/file-appender.xml" />
	<root level="INFO">
		<appender-ref ref="FILE" />
	</root>
</configuration>
```

&emsp;&emsp;您还需要将logging.file添加到application.properties，如以下示例所示：

``` 
logging.file=myapplication.log
```

### **9.8.2 配置Log4j来记录日志**

&emsp;&emsp;Spring Boot支持Log4j 2进行日志记录配置（如果它在类路径上）。 如果使用启动器来组装依赖项，则必须排除Logback，然后再包含log4j 2。 如果你不使用启动器，除了Log4j 2之外，还需要提供（至少）spring-jcl。

&emsp;&emsp;最简单的路径可能是通过启动器，即使它需要一些与排除项。 以下示例显示如何在Maven中设置启动器：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter</artifactId>
	<exclusions>
		<exclusion>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-logging</artifactId>
		</exclusion>
	</exclusions>
</dependency>
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-log4j2</artifactId>
</dependency>
```

&emsp;&emsp;以下示例显示了在Gradle中设置启动器的一种方法：

``` 
dependencies {
	compile 'org.springframework.boot:spring-boot-starter-web'
	compile 'org.springframework.boot:spring-boot-starter-log4j2'
}

configurations {
	all {
		exclude group: 'org.springframework.boot', module: 'spring-boot-starter-logging'
	}
}
```

>Log4j启动程序将常见日志记录要求的依赖关系聚集在一起（例如让Tomcat使用java.util.logging但使用Log4j 2配置输出）。 有关详细信息，请参阅Actuator Log4j 2示例并查看其实际操作。

&emsp;
>要确保使用java.util.logging执行的调试日志记录路由到Log4j 2，请通过将java.util.logging.manager系统属性设置为org.apache.logging.log4j.jul.LogManager来配置其JDK日志记录适配器。

**9.8.2.1 使用YAML或JSON配置Log4j 2**

&emsp;&emsp;除了默认的XML配置格式外，Log4j 2还支持YAML和JSON配置文件。 要将Log4j 2配置为使用备用配置文件格式，请将相应的依赖项添加到类路径，并将配置文件命名为与所选文件格式匹配，如以下示例所示：

<table>
	<tr>
		<th>Format</th>
		<th>Dependencies</th>
		<th>File names</th>
	</tr>
	<tr>
		<td>YAML</td>
		<td>com.fasterxml.jackson.core:jackson-databind com.fasterxml.jackson.dataformat:jackson-dataformat-yaml</td>
		<td>log4j2.yaml log4j2.yml</td>
	</tr>
	<tr>
		<td>JSON</td>
		<td>com.fasterxml.jackson.core:jackson-databind</td>
		<td>log4j2.json log4j2.jsn</td>
	</tr>
</table>

## **9.9 数据访问**

&emsp;&emsp;Spring Boot包含许多用于处理数据源的启动器。 本节回答与此相关的问题。

### **9.9.1 配置自定义数据源**

&emsp;&emsp;要配置自己的DataSource，请在配置中定义该类型的@Bean。 Spring Boot在任何需要的地方重用您的DataSource，包括数据库初始化。 如果需要外部化某些设置，可以将DataSource绑定到环境中（请参阅“第4.2.8.1节”“第三方配置”）。

&emsp;&emsp;以下示例显示如何在bean中定义数据源：

``` 
@Bean
@ConfigurationProperties(prefix="app.datasource")
public DataSource dataSource() {
	return new FancyDataSource();
}
```

&emsp;&emsp;以下示例显示如何通过设置属性来定义数据源：

``` 
app.datasource.url=jdbc:h2:mem:mydb
app.datasource.username=sa
app.datasource.pool-size=30
```

&emsp;&emsp;假设您的FancyDataSource具有URL的常规JavaBean属性，用户名和池大小，这些设置在DataSource可供其他组件使用之前自动绑定。 常规数据库初始化也会发生（因此spring.datasource.*的相关子集仍可以与您的自定义配置一起使用）。

&emsp;&emsp;Spring Boot还提供了一个名为DataSourceBuilder的实用程序构建器类，可用于创建其中一个标准数据源（如果它位于类路径中）。 构建器可以根据类路径上的可用内容检测要使用的那个。 它还会根据JDBC URL自动检测驱动程序。

&emsp;&emsp;以下示例说明如何使用DataSourceBuilder创建数据源：

``` 
@Bean
@ConfigurationProperties("app.datasource")
public DataSource dataSource() {
	return DataSourceBuilder.create().build();
}
```

&emsp;&emsp;要使用该DataSource运行应用程序，您只需要连接信息。 还可以提供特定于池的设置。 检查将在运行时使用的实现以获取更多详细信息。

&emsp;&emsp;以下示例说明如何通过设置属性来定义JDBC数据源：

``` 
app.datasource.url=jdbc:mysql://localhost/test
app.datasource.username=dbuser
app.datasource.password=dbpass
app.datasource.pool-size=30
```

&emsp;&emsp;然而，有一个问题。 由于未公开连接池的实际类型，因此在自定义DataSource的元数据中不会生成任何键，并且IDE中没有可用的结论（因为DataSource接口不公开任何属性）。 此外，如果你碰巧在类路径上有Hikari，这个基本设置不起作用，因为Hikari没有url属性（但是有一个jdbcUrl属性）。 在这种情况下，您必须按如下方式重写配置：

``` 
app.datasource.jdbc-url=jdbc:mysql://localhost/test
app.datasource.username=dbuser
app.datasource.password=dbpass
app.datasource.maximum-pool-size=30
```

&emsp;&emsp;您可以通过强制连接池使用并返回专用实现而不是DataSource来解决此问题。 您无法在运行时更改实现，但选项列表将是显式的。

&emsp;&emsp;以下示例显示如何使用DataSourceBuilder创建HikariDataSource：

``` 
@Bean
@ConfigurationProperties("app.datasource")
public HikariDataSource dataSource() {
	return DataSourceBuilder.create().type(HikariDataSource.class).build();
}
```

&emsp;&emsp;您甚至可以通过利用DataSourceProperties为您做的事情来进一步发展 - 也就是说，如果没有提供URL，则通过提供具有合理用户名和密码的默认嵌入式数据库。 您可以从任何DataSourceProperties对象的状态轻松初始化DataSourceBuilder，因此您也可以注入Spring Boot自动创建的DataSource。 但是，这会将您的配置拆分为两个名称空间：spring.datasource上的url，username，password，type和driver，以及自定义名称空间（app.datasource）上的其余名称空间。 为避免这种情况，您可以在自定义命名空间上重新定义自定义DataSourceProperties，如以下示例所示：

``` 
@Bean
@Primary
@ConfigurationProperties("app.datasource")
public DataSourceProperties dataSourceProperties() {
	return new DataSourceProperties();
}

@Bean
@ConfigurationProperties("app.datasource.configuration")
public HikariDataSource dataSource(DataSourceProperties properties) {
	return properties.initializeDataSourceBuilder().type(HikariDataSource.class)
			.build();
}
```

&emsp;&emsp;默认情况下，此设置使您与Spring Boot为您执行的操作保持同步，除了选择专用连接池（在代码中）并且其设置在app.datasource.configuration子命名空间中公开。 因为DataSourceProperties正在为您处理url/jdbcUrl转换，所以您可以按如下方式对其进行配置：

``` 
app.datasource.url=jdbc:mysql://localhost/test
app.datasource.username=dbuser
app.datasource.password=dbpass
app.datasource.configuration.maximum-pool-size=30
```

>Spring Boot会将Hikari特定的设置暴露给spring.datasource.hikari。 此示例使用更通用的配置子命名空间，因为该示例不支持多个数据源实现。

&emsp;
>由于您的自定义配置选择使用Hikari，因此app.datasource.type无效。 在实践中，构建器初始化为您可能在那里设置的任何值，然后通过调用.type()来覆盖。

&emsp;&emsp;有关更多详细信息，请参见“Spring Boot features”部分中的“4.9.1 配置数据源”和DataSourceAutoConfiguration类。

### **9.9.2 配置两个数据源**

&emsp;&emsp;如果需要配置多个数据源，可以应用上一节中描述的相同技巧。 但是，您必须将其中一个DataSource实例标记为@Primary，因为随后的各种自动配置希望能够按类型获取。

&emsp;&emsp;如果您创建自己的DataSource，则自动配置会退回。 在以下示例中，我们提供与主数据源上提供的自动配置完全相同的功能集：

``` 
@Bean
@Primary
@ConfigurationProperties("app.datasource.first")
public DataSourceProperties firstDataSourceProperties() {
	return new DataSourceProperties();
}

@Bean
@Primary
@ConfigurationProperties("app.datasource.first.configuration")
public HikariDataSource firstDataSource() {
	return firstDataSourceProperties().initializeDataSourceBuilder()
			.type(HikariDataSource.class).build();
}

@Bean
@ConfigurationProperties("app.datasource.second")
public BasicDataSource secondDataSource() {
	return DataSourceBuilder.create().type(BasicDataSource.class).build();
}
```

>必须将firstDataSourceProperties标记为@Primary，以便数据库初始化程序功能使用您的副本（如果使用初始化程序）。

&emsp;&emsp;这两个数据源也绑定了高级自定义。 例如，您可以按如下方式配置它们：

``` 
app.datasource.first.url=jdbc:mysql://localhost/first
app.datasource.first.username=dbuser
app.datasource.first.password=dbpass
app.datasource.first.configuration.maximum-pool-size=30

app.datasource.second.url=jdbc:mysql://localhost/second
app.datasource.second.username=dbuser
app.datasource.second.password=dbpass
app.datasource.second.max-total=30
```

&emsp;&emsp;您也可以将相同的方式应用于辅助DataSource，如以下示例所示：

``` 
@Bean
@Primary
@ConfigurationProperties("app.datasource.first")
public DataSourceProperties firstDataSourceProperties() {
	return new DataSourceProperties();
}

@Bean
@Primary
@ConfigurationProperties("app.datasource.first.configuration")
public HikariDataSource firstDataSource() {
	return firstDataSourceProperties().initializeDataSourceBuilder()
			.type(HikariDataSource.class).build();
}

@Bean
@ConfigurationProperties("app.datasource.second")
public DataSourceProperties secondDataSourceProperties() {
	return new DataSourceProperties();
}

@Bean
@ConfigurationProperties("app.datasource.second.configuration")
public BasicDataSource secondDataSource() {
	return secondDataSourceProperties().initializeDataSourceBuilder()
			.type(BasicDataSource.class).build();
}
```

&emsp;&emsp;上面的示例使用与Spring Boot在自动配置中使用的逻辑相同的逻辑在自定义命名空间上配置两个数据源。 请注意，每个配置子命名空间都基于所选实现提供高级设置。

### **9.9.3 使用Spring Data Repositories**

&emsp;&emsp;Spring Data可以创建各种风格的@Repository接口的实现。 Spring Boot会为您处理所有这些，只要这些@Repositories包含在@EnableAutoConfiguration类的同一个包（或子包）中。

&emsp;&emsp;对于许多应用程序，您只需要在类路径上放置正确的Spring Data依赖项（对于JPA有一个spring-boot-starter-data-jpa，对于Mongodb有一个spring-boot-starter-data-mongodb）并创建一些 存储库接口来处理您的@Entity对象。 例子在JPA样本和Mongodb样本中。

&emsp;&emsp;Spring Boot会根据找到的@EnableAutoConfiguration尝试猜测@Repository定义的位置。 要获得更多控制，请使用@EnableJpaRepositories注释（来自Spring Data JPA）。

&emsp;&emsp;有关Spring Data的更多信息，请参阅Spring Data项目页面。

### **9.9.4 从Spring配置中分离@Entity定义**

&emsp;&emsp;Spring Boot会根据找到的@EnableAutoConfiguration尝试猜测@Entity定义的位置。 要获得更多控制，可以使用@EntityScan批注，如以下示例所示：

``` 
@Configuration
@EnableAutoConfiguration
@EntityScan(basePackageClasses=City.class)
public class Application {

	//...

}
```

### **9.9.5 配置JPA属性**

&emsp;&emsp;Spring Data JPA已经提供了一些独立于供应商的配置选项（例如用于SQL日志记录的选项），Spring Boot公开了这些选项以及一些Hibernate作为外部配置属性的选项。 根据上下文自动检测其中一些，因此您不必设置它们。

&emsp;&emsp;spring.jpa.hibernate.ddl-auto是一种特殊情况，因为根据运行时条件，它具有不同的默认值。 如果使用嵌入式数据库且没有架构管理器（例如Liquibase或Flyway）正在处理DataSource，则默认为create-drop。 在所有其他情况下，默认为none。

&emsp;&emsp;还可以根据当前的DataSource自动检测要使用的方言，但是如果要显式并且在启动时绕过该检查，则可以自己设置spring.jpa.database。

>指定数据库会导致配置明确定义的Hibernate方言。 有几个数据库有多个Dialect，这可能不适合您的需求。 在这种情况下，您可以将spring.jpa.database设置为default，让Hibernate通过设置spring.jpa.database-platform属性来解决问题。

&emsp;&emsp;以下示例中显示了最常用的设置选项：

``` 
spring.jpa.hibernate.naming.physical-strategy=com.example.MyPhysicalNamingStrategy
spring.jpa.show-sql=true
```

&emsp;&emsp;此外，当创建本地EntityManagerFactory时，spring.jpa.properties.*中的所有属性都作为普通的JPA属性（带有前缀剥离）传递。

>如果需要对Hibernate属性应用高级自定义，请考虑注册将在创建EntityManagerFactory之前调用的HibernatePropertiesCustomizer bean。 这优先于自动配置应用的任何内容。

### **9.9.6 配置Hibernate命名策略**

&emsp;&emsp;Hibernate使用两种不同的命名策略将名称从对象模型映射到相应的数据库名称。 可以通过分别设置spring.jpa.hibernate.naming.physical-strategy和spring.jpa.hibernate.naming.implicit-strategy属性来配置物理策略实现和隐式策略实现的完全限定类名。 或者，如果应用程序上下文中有ImplicitNamingStrategy或PhysicalNamingStrategy bean，Hibernate将自动配置为使用它们。

&emsp;&emsp;默认情况下，Spring Boot使用SpringPhysicalNamingStrategy配置物理命名策略。 这个实现提供了与Hibernate 4相同的表结构：所有点都被下划线替换，而驼峰外壳也被下划线替换。 默认情况下，所有表名都以小写形式生成，但如果您的架构需要，则可以覆盖该标志。

例如，TelephoneNumber实体被映射到telephone_number表。

&emsp;&emsp;如果您更喜欢使用Hibernate 5的默认设置，请设置以下属性：

``` 
spring.jpa.hibernate.naming.physical-strategy=org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
```

&emsp;&emsp;或者，您可以配置以下bean：

``` 
@Bean
public PhysicalNamingStrategy physicalNamingStrategy() {
	return new PhysicalNamingStrategyStandardImpl();
}
```

&emsp;&emsp;有关更多详细信息，请参阅HibernateJpaAutoConfiguration和JpaBaseConfiguration。

### **9.9.7 配置Hibernate二级缓存**

&emsp;&emsp;可以为一系列缓存提供程序配置Hibernate二级缓存。 不是将Hibernate配置为再次查找缓存提供程序，最好尽可能提供上下文中可用的那个。

&emsp;&emsp;如果你正在使用JCache，这很容易。 首先，确保org.hibernate：hibernate-jcache在类路径上可用。 然后，添加一个HibernatePropertiesCustomizer bean，如以下示例所示：

``` 
@Configuration
public class HibernateSecondLevelCacheExample {

	@Bean
	public HibernatePropertiesCustomizer hibernateSecondLevelCacheCustomizer(
			JCacheCacheManager cacheManager) {
		return (properties) -> properties.put(ConfigSettings.CACHE_MANAGER,
				cacheManager.getCacheManager());

	}

}
```

&emsp;&emsp;此自定义程序将配置Hibernate以使用与应用程序使用的CacheManager相同的CacheManager。 也可以使用单独的CacheManager实例。 有关详细信息，请参阅Hibernate用户指南。

### **9.9.8 在Hibernate组件中使用依赖注入**

&emsp;&emsp;默认情况下，Spring Boot注册使用BeanFactory的BeanContainer实现，以便转换器和实体侦听器可以使用常规依赖注入。

&emsp;&emsp;您可以通过注册删除或更改hibernate.resource.beans.container属性的HibernatePropertiesCustomizer来禁用或调整此行为。

### **9.9.9 使用自定义EntityManagerFactory**

&emsp;&emsp;要完全控制EntityManagerFactory的配置，需要添加名为“entityManagerFactory”的@Bean。 Spring Boot自动配置在存在该类型的bean时关闭其实体管理器。

### **9.9.10 使用两个EntityManagers**

&emsp;&emsp;即使默认的EntityManagerFactory工作正常，您也需要定义一个新的。 否则，该类型的第二个bean的存在将关闭默认值。 为了方便起见，您可以使用Spring Boot提供的方便的EntityManagerBuilder。 或者，您可以直接从Spring ORM中获取LocalContainerEntityManagerFactoryBean，如以下示例所示：

``` 
// add two data sources configured as above

@Bean
public LocalContainerEntityManagerFactoryBean customerEntityManagerFactory(
		EntityManagerFactoryBuilder builder) {
	return builder
			.dataSource(customerDataSource())
			.packages(Customer.class)
			.persistenceUnit("customers")
			.build();
}

@Bean
public LocalContainerEntityManagerFactoryBean orderEntityManagerFactory(
		EntityManagerFactoryBuilder builder) {
	return builder
			.dataSource(orderDataSource())
			.packages(Order.class)
			.persistenceUnit("orders")
			.build();
}
```

&emsp;&emsp;上面的配置几乎可以单独使用。 要完成这幅图，您还需要为两个EntityManagers配置TransactionManagers。 如果你将其中一个标记为@Primary，它可以被Spring Boot中的默认JpaTransactionManager选中。 另一个必须明确地注入新实例。 或者，您可以使用跨越两者的JTA事务管理器。

&emsp;&emsp;如果使用Spring Data，则需要相应地配置@EnableJpaRepositories，如以下示例所示：

``` 
@Configuration
@EnableJpaRepositories(basePackageClasses = Customer.class,
		entityManagerFactoryRef = "customerEntityManagerFactory")
public class CustomerConfiguration {
	...
}

@Configuration
@EnableJpaRepositories(basePackageClasses = Order.class,
		entityManagerFactoryRef = "orderEntityManagerFactory")
public class OrderConfiguration {
	...
}
```

### **9.9.11 使用传统的persistence.xml文件**

&emsp;&emsp;默认情况下，Spring Boot不会搜索或使用META-INF/persistence.xml。 如果您更喜欢使用传统的persistence.xml，则需要定义自己的类型为LocalEntityManagerFactoryBean的@Bean（ID为'entityManagerFactory'）并在其中设置持久性单元名称。

&emsp;&emsp;有关默认设置，请参阅JpaBaseConfiguration。

### **9.9.12 使用Spring Data JPA和Mongo Repositories**

&emsp;&emsp;Spring Data JPA和Spring Data Mongo都可以自动为您创建Repository实现。 如果它们都存在于类路径中，则可能需要执行一些额外的配置来告诉Spring Boot要创建哪些存储库。 最明确的方法是使用标准的Spring Data @EnableJpaRepositories和@EnableMongoRepositories注释，并提供Repository接口的位置。

&emsp;&emsp;还有标志（spring.data.*.repositories.enabled和spring.data.*.repositories.type），您可以使用这些标志在外部配置中打开和关闭自动配置的存储库。 这样做很有用，例如，如果您想关闭Mongo存储库并仍然使用自动配置的MongoTemplate。

&emsp;&emsp;其他自动配置的Spring Data存储库类型（Elasticsearch，Solr等）也存在相同的障碍和相同的功能。 要使用它们，请相应地更改注释和标志的名称。

### **9.9.13 自定义Spring Data的Web支持**

&emsp;&emsp;Spring Data提供Web支持，简化了Web应用程序中Spring Data存储库的使用。 Spring Boot在spring.data.web命名空间中提供属性以自定义其配置。 请注意，如果您使用的是Spring Data REST，则必须使用spring.data.rest命名空间中的属性

### **9.9.14 将Spring Data Repositories暴露为REST端点**

&emsp;&emsp;如果为应用程序启用了Spring MVC，Spring Data REST可以为您公开Repository实现作为REST端点。

&emsp;&emsp;Spring Boot公开了一组自定义RepositoryRestConfiguration的有用属性（来自spring.data.rest命名空间）。 如果需要提供其他自定义，则应使用RepositoryRestConfigurer bean。

>如果未在自定义RepositoryRestConfigurer上指定任何顺序，则它将在内部使用一个Spring Boot之后运行。 如果需要指定顺序，请确保order高于0。

### **9.9.15 配置JPA使用的组件**

&emsp;&emsp;如果要配置JPA使用的组件，则需要确保在JPA之前初始化组件。 组件自动配置后，Spring Boot会为您完成此操作。 例如，当自动配置Flyway时，Hibernate配置为依赖于Flyway，以便在Hibernate尝试使用它之前，Flyway有机会初始化数据库。

&emsp;&emsp;如果您自己配置组件，则可以使用EntityManagerFactoryDependsOnPostProcessor子类作为设置必要依赖项的便捷方法。 例如，如果将Hibernate Search与Elasticsearch一起用作其索引管理器，则必须将任何EntityManagerFactory bean配置为依赖elasticsearchClient bean，如以下示例所示：

``` 
/**
 * {@link EntityManagerFactoryDependsOnPostProcessor} that ensures that
 * {@link EntityManagerFactory} beans depend on the {@code elasticsearchClient} bean.
 */
@Configuration
static class ElasticsearchJpaDependencyConfiguration
		extends EntityManagerFactoryDependsOnPostProcessor {

	ElasticsearchJpaDependencyConfiguration() {
		super("elasticsearchClient");
	}

}
```

### **9.9.16 使用两个数据源配置jOOQ**

&emsp;&emsp;如果您需要将jOOQ用于多个数据源，则应为每个数据源创建自己的DSLContext。 有关更多详细信息，请参阅JooqAutoConfiguration。

>特别是，可以重用JooqExceptionTranslator和SpringTransactionProvider来提供与单个DataSource的自动配置相似的功能。

## **9.10 数据库初始化**

&emsp;&emsp;可以使用不同的方式初始化SQL数据库，具体取决于堆栈的内容。 当然，如果数据库是一个单独的过程，您也可以手动完成。 建议使用单一机制生成模式。

### **9.10.1 使用JPA初始化数据库**

&emsp;&emsp;JPA具有DDL生成功能，可以将这些功能设置为在数据库启动时运行。 这是通过两个外部属性控制的：

- spring.jpa.generate-ddl（boolean）打开和关闭该功能，与供应商无关。
- spring.jpa.hibernate.ddl-auto（enum）是一个Hibernate功能，它以更细粒度的方式控制行为。 本指南后面将详细介绍此功能。


### **9.10.2 使用Hibernate初始化数据库**

&emsp;&emsp;您可以显式设置spring.jpa.hibernate.ddl-auto，标准Hibernate属性值为none，validate，update，create和create-drop。 Spring Boot会根据是否认为您的数据库是嵌入式的，为您选择一个默认值。 如果未检测到架构管理器，则默认为create-drop，在所有其他情况下，默认为none。 通过查看连接类型来检测嵌入式数据库。 hsqldb，h2和derby是嵌入的，而其他则不是。 从内存切换到“真实”数据库时要小心，不要假设新平台中存在表和数据。 您必须显式设置ddl-auto或使用其他机制之一来初始化数据库。

>您可以通过启用org.hibernate.SQL记录器来输出架构创建。 如果启用调试模式，则会自动完成此操作。

&emsp;&emsp;此外，如果Hibernate从头开始创建架构（即，如果ddl-auto属性设置为create或create-drop），则在启动时会在启动时执行类路径根目录中名为import.sql的文件。 这对于演示和测试（如果您很小心的话）都很有用，但是您可能不希望在生产中的类路径上出现这种情况。 它是一个Hibernate功能（与Spring无关）。

### **9.10.3 初始化数据库**

>Spring Boot自动创建嵌入式DataSource的模式。 可以使用spring.datasource.initialization-mode属性自定义此行为。 例如，如果要始终初始化DataSource，而不管其类型如何： spring.datasource.initialization-mode=always

&emsp;&emsp;默认情况下，Spring Boot启用Spring JDBC初始化程序的快速故障功能。 这意味着，如果脚本导致异常，则应用程序无法启动。 您可以通过设置spring.datasource.continue-on-error来调整该行为。

>在基于JPA的应用程序中，您可以选择让Hibernate创建schema或使用schema.sql，但您不能同时执行这两个操作。 如果使用schema.sql，请确保disablespring.jpa.hibernate.ddl-auto。

### **9.10.4 初始化Spring批处理数据库**

``` 
spring.batch.initialize-schema=always
```

&emsp;&emsp;您还可以通过设置spring.batch.initialize-schema = never来显式关闭初始化。

### **9.10.5 使用更高级别的数据库迁移工具**

&emsp;&emsp;Spring Boot支持两种更高级别的迁移工具：Flyway和Liquibase。

**9.10.5.1 在启动时执行Flyway数据库迁移**

&emsp;&emsp;要在启动时自动运行Flyway数据库迁移，请将org.flywaydb:flyway-core添加到类路径中。

&emsp;&emsp;迁移是V<VERSION>__<NAME>.sql形式的脚本（<VERSION>下划线分隔版本，例如'1'或'2_1'）。 默认情况下，它们位于名为classpath:db/migration的文件夹中，但您可以通过设置spring.flyway.locations来修改该位置。 这是一个以逗号分隔的列表，其中包含一个或多个classpath:或filesystem:locations。 例如，以下配置将在默认类路径位置和/opt/migration目录中搜索脚本：

``` 
spring.flyway.locations=classpath:db/migration,filesystem:/opt/migration
```

&emsp;&emsp;您还可以添加特殊的{vendor}占位符以使用特定于供应商的脚本。 假设如下：

``` 
spring.flyway.locations=classpath:db/migration/{vendor}
```

&emsp;&emsp;前面的配置不是使用db/migration，而是根据数据库的类型设置要使用的文件夹（例如MySQL的db/migration/mysql）。 DatabaseDriver中提供了受支持的数据库列表。

&emsp;&emsp;FlywayProperties提供了大部分Flyway的设置和一小组附加属性，可用于禁用迁移或关闭位置检查。 如果需要更多控制配置，请考虑注册FlywayConfigurationCustomizer bean。

&emsp;&emsp;Spring Boot调用Flyway.migrate()来执行数据库迁移。 如果您想要更多控制，请提供实现FlywayMigrationStrategy的@Bean。

&emsp;&emsp;Flyway支持SQL和Java回调。 要使用基于SQL的回调，请将回调脚本放在classpath:db/migration文件夹中。 要使用基于Java的回调，请创建一个或多个实现Callback的bean。 任何此类bean都会自动在Flyway注册。 可以使用@Order或通过实现Ordered来订购它们。 也可以检测实现已弃用的FlywayCallback接口的Bean，但它们不能与Callback bean一起使用。

&emsp;&emsp;默认情况下，Flyway会在您的上下文中自动装配（@Primary）DataSource并将其用于迁移。 如果您想使用其他DataSource，可以创建一个并将其@Bean标记为@FlywayDataSource。 如果您这样做并想要两个数据源，请记住创建另一个数据源并将其标记为@Primary。 或者，您可以通过在外部属性中设置spring.flyway.[url，user，password]来使用Flyway的本机DataSource。 设置spring.flyway.url或spring.flyway.user足以使Flyway使用自己的DataSource。 如果尚未设置三个属性中的任何一个，则将使用其等效的spring.datasource属性的值。

&emsp;&emsp;有一个Flyway示例，您可以看到如何设置。

&emsp;&emsp;您还可以使用Flyway为特定方案提供数据。 例如，您可以在src/test/resources中放置特定于测试的迁移，并且只有在应用程序启动进行测试时才会运行它们。 此外，您可以使用特定于配置文件的配置来自定义spring.flyway.locations，以便某些迁移仅在特定配置文件处于活动状态时运行。 例如，在application-dev.properties中，您可以指定以下设置：

``` 
spring.flyway.locations=classpath:/db/migration,classpath:/dev/db/migration
```

&emsp;&emsp;使用该设置，dev/db/migration中的迁移仅在dev配置文件处于活动状态时运行。

**9.10.5.2 在启动时执行Liquibase数据库迁移**

&emsp;&emsp;要在启动时自动运行Liquibase数据库迁移，请将org.liquibase:liquibase-core添加到类路径中。

&emsp;&emsp;默认情况下，从db/changelog/db.changelog-master.yaml读取主更改日志，但您可以通过设置spring.liquibase.change-log来更改位置。 除了YAML，Liquibase还支持JSON，XML和SQL更改日志格式。

&emsp;&emsp;默认情况下，Liquibase会在您的上下文中自动装配（@Primary）DataSource并将其用于迁移。 如果需要使用其他DataSource，可以创建一个并将其@Bean标记为@LiquibaseDataSource。 如果您这样做并且想要两个数据源，请记住创建另一个数据源并将其标记为@Primary。 或者，您可以通过在外部属性中设置spring.liquibase.[url，user，password]来使用Liquibase的本机DataSource。 设置spring.liquibase.url或spring.liquibase.user足以使Liquibase使用自己的DataSource。 如果尚未设置三个属性中的任何一个，则将使用其等效的spring.datasource属性的值。

&emsp;&emsp;有关可用设置（如上下文，默认架构等）的详细信息，请参阅LiquibaseProperties。

&emsp;&emsp;有一个Liquibase示例，以便您可以看到如何设置。

## **9.11 消息**

&emsp;&emsp;Spring Boot提供了许多包含消息传递的启动器。 本节回答使用Spring Boot消息传递产生的问题。

### **9.11.1 禁用事务处理的JMS会话**

&emsp;&emsp;如果您的JMS代理不支持事务会话，则必须完全禁用事务支持。 如果您创建自己的JmsListenerContainerFactory，则无需执行任何操作，因为默认情况下无法进行事务处理。 如果要使用DefaultJmsListenerContainerFactoryConfigurer重用Spring Boot的默认值，可以禁用事务处理会话，如下所示：

``` 
@Bean
public DefaultJmsListenerContainerFactory jmsListenerContainerFactory(
		ConnectionFactory connectionFactory,
		DefaultJmsListenerContainerFactoryConfigurer configurer) {
	DefaultJmsListenerContainerFactory listenerFactory =
			new DefaultJmsListenerContainerFactory();
	configurer.configure(listenerFactory, connectionFactory);
	listenerFactory.setTransactionManager(null);
	listenerFactory.setSessionTransacted(false);
	return listenerFactory;
}
```

&emsp;&emsp;上面的示例将覆盖默认工厂，并且应该应用于应用程序定义的任何其他工厂（如果有）。

## **9.12 Batch Applications**

&emsp;&emsp;本节回答使用Spring Boot的Spring Batch产生的问题。

>默认情况下，批处理应用程序需要DataSource来存储作业详细信息。 如果要偏离它，则需要实现BatchConfigurer。 有关更多详细信息，请参阅@EnableBatchProcessing的Javadoc。

&emsp;&emsp;有关Spring Batch的更多信息，请参阅Spring Batch项目页面。

### **9.12.1 在启动时执行Spring Batch作业**

&emsp;&emsp;通过在上下文中的某处添加@EnableBatchProcessing（来自Spring Batch）来启用Spring Batch自动配置。

&emsp;&emsp;默认情况下，它在启动时在应用程序上下文中执行所有作业（有关详细信息，请参阅JobLauncherCommandLineRunner）。 您可以通过指定spring.batch.job.names（以逗号分隔的作业名称模式列表）缩小到特定的作业或作业。

>与在环境中设置属性的命令行选项参数（即以 - 开头，例如--my-property = value）不同，必须在命令行上指定作业参数而不使用破折号（例如jobParam = value）。

&emsp;&emsp;如果应用程序上下文包含JobRegistry，则spring.batch.job.names中的作业将在注册表中查找，而不是从上下文中自动装配。 这是一个具有更复杂系统的常见模式，其中多个作业在子上下文中定义并集中注册。

&emsp;&emsp;有关更多详细信息，请参阅BatchAutoConfiguration和@EnableBatchProcessing。

## **9.13 执行器**

&emsp;&emsp;Spring Boot包括Spring Boot Actuator。 本节回答了其使用中经常出现的问题。

### **9.13.1 更改执行器端点的HTTP端口或地址**

&emsp;&emsp;在独立应用程序中，Actuator HTTP端口默认与主HTTP端口相同。 要使应用程序侦听其他端口，请设置外部属性：management.server.port。 要侦听完全不同的网络地址（例如，当您有用于管理的内部网络和用于用户应用程序的外部网络时），您还可以将management.server.address设置为服务器能够绑定到的有效IP地址。

&emsp;&emsp;有关更多详细信息，请参阅“生产就绪功能”部分中的ManagementServerProperties源代码和“5.3.2 自定义管理服务器端口”。

### **9.13.2 自定义'whitelabel'错误页面**

&emsp;&emsp;如果您遇到服务器错误，Spring Boot将安装您在浏览器客户端中看到的“whitelabel”错误页面（使用JSON和其他媒体类型的计算机客户端应该看到具有正确错误代码的合理响应）。

>设置server.error.whitelabel.enabled = false以关闭默认错误页面。 这样做会恢复您正在使用的servlet容器的默认值。 请注意，Spring Boot仍会尝试解析错误视图，因此您应该添加自己的错误页面，而不是完全禁用它。

&emsp;&emsp;使用您自己的错误页面覆盖错误页面取决于您使用的模板技术。 例如，如果您使用Thymeleaf，则可以添加error.html模板。 如果您使用FreeMarker，则可以添加error.ftl模板。 通常，您需要一个以错误名称解析的View或一个处理/错误路径的@Controller。 除非您替换了一些默认配置，否则您应该在ApplicationContext中找到BeanNameViewResolver，因此@Bean命名错误将是一种简单的方法。 有关更多选项，请参见ErrorMvcAutoConfiguration。

&emsp;&emsp;有关如何在servlet容器中注册处理程序的详细信息，另请参阅“错误处理”一节。

### **9.13.3 审查关键字**

&emsp;&emsp;env和configprops端点返回的信息可能有些敏感，因此默认情况下将匹配某个模式的密钥进行清理（即它们的值由******替换）。

&emsp;&emsp;Spring Boot对这些密钥使用合理的默认值：例如，任何以“password”，“secret”，“key”或“token”结尾的密钥都将被清理。 也可以使用正则表达式，例如* credentials.*来清理任何将单词凭证作为密钥的一部分的密钥。

&emsp;&emsp;可以使用management.endpoint.env.keys-to-sanitize和management.endpoint.configprops.keys-to-sanitize分别自定义要使用的模式。

## **9.14 安全**

&emsp;&emsp;本节讨论使用SpringBoot时的安全性问题，包括在SpringBoot中使用Spring Security时出现的问题。

### **9.14.1 关闭Spring Boot安全配置**

&emsp;&emsp;如果在应用程序中使用WebSecurityConfigurerAdapter定义@Configuration，则会关闭Spring Boot中的默认Webapp安全设置。

### **9.14.2 更改UserDetailsService和添加用户帐户**

&emsp;&emsp;如果您提供类型为AuthenticationManager，AuthenticationProvider或UserDetailsService的@Bean，则不会创建InMemoryUserDetailsManager的默认@Bean，因此您可以使用Spring Security的完整功能集（例如各种身份验证选项）。

&emsp;&emsp;添加用户帐户的最简单方法是提供自己的UserDetailsService bean。

### **9.14.3 当运行在代理服务器下时启用HTTPS**

&emsp;&emsp;确保所有主要端点仅通过HTTPS可用是任何应用程序的重要工作。 如果您使用Tomcat作为servlet容器，那么Spring Boot会在检测到某些环境设置时自动添加Tomcat自己的RemoteIpValve，并且您应该能够依赖HttpServletRequest来报告它是否安全（甚至是代理服务器的下游） 处理真正的SSL终止）。 标准行为取决于某些请求标头（x-forwarded-for和x-forwarded-proto）的存在与否，其名称是常规的，因此它应该适用于大多数前端代理。 您可以通过向application.properties添加一些条目来打开阀门，如以下示例所示：

``` 
server.tomcat.remote-ip-header=x-forwarded-for
server.tomcat.protocol-header=x-forwarded-proto
```

&emsp;&emsp;（其中任何一个属性的存在都会打开阀门。或者，您可以通过添加TomcatServletWebServerFactory bean来添加RemoteIpValve。）

&emsp;&emsp;要将Spring Security配置为要求所有（或某些）请求的安全通道，请考虑添加自己的WebSecurityConfigurerAdapter，以添加以下HttpSecurity配置：

``` 
@Configuration
public class SslWebSecurityConfigurerAdapter extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		// Customize the application security
		http.requiresChannel().anyRequest().requiresSecure();
	}

}
```

## **9.15 热部署**

&emsp;&emsp;Spring Boot支持热部署。 本节回答有关其工作原理的问题。

### **9.15.1 重新加载静态内容**

&emsp;&emsp;热部署有几种选择。推荐的方法是使用spring-boot-devtools，因为它提供了额外的开发时特性，例如支持快速应用程序重新启动和LiveReload以及合理的开发时配置(例如模板缓存)。DevTools通过监视更改的类路径来工作。这意味着必须“构建”静态资源更改才能使更改生效。默认情况下，在Eclipse中保存更改时会自动发生这种情况。在IntelliJIDEA中，makeProject命令触发必要的构建。由于默认的重新启动排除，对静态资源的更改不会触发应用程序的重新启动。然而，他们确实触发了一个LiveReload。

&emsp;&emsp;或者，在IDE中运行（尤其是在调试时）是一种很好的开发方式（所有现代IDE都允许重新加载静态资源，并且通常还允许热插拔Java类更改）。

&emsp;&emsp;最后，可以配置Maven和Gradle插件（请参阅addResources属性）以支持从命令行运行，并直接从源重新加载静态文件。 如果您使用更高级别的工具编写该代码，则可以将其与外部css/js编译器进程一起使用。

### **9.15.2 重新加载模板而不重新启动容器**

&emsp;&emsp;Spring Boot支持的大多数模板技术都包含一个禁用缓存的配置选项（本文档后面会介绍）。 如果使用spring-boot-devtools模块，则会在开发时自动为您配置这些属性。

**9.15.2.1 Thymeleaf模板**

&emsp;&emsp;如果您使用Thymeleaf，请将spring.thymeleaf.cache设置为false。 有关其他Thymeleaf自定义选项，请参阅ThymeleafAutoConfiguration。

**9.15.2.2 FreeMarker模板**

&emsp;&emsp;如果您使用FreeMarker，请将spring.freemarker.cache设置为false。 有关其他FreeMarker自定义选项，请参阅FreeMarkerAutoConfiguration。

**9.15.2.3 Groovy模板**

&emsp;&emsp;如果使用Groovy模板，请将spring.groovy.template.cache设置为false。 有关其他Groovy自定义选项，请参阅GroovyTemplateAutoConfiguration。

### **9.15.3 快速重启应用**

&emsp;&emsp;spring-boot-devtools模块支持自动应用程序重启。 虽然没有像JRebel这样的技术那么快，但它通常比“冷启动”快得多。 在调查本文档后面讨论的一些更复杂的重载选项之前，您应该尝试一下。

&emsp;&emsp;有关更多详细信息，请参见第“3.8 开发者工具”部分。

### **9.15.4 重新加载Java类而不重新启动容器**

&emsp;&emsp;许多现代IDE（Eclipse，IDEA和其他）支持字节码的热交换。 因此，如果您进行的更改不会影响类或方法签名，则应该干净地重新加载，不会产生任何副作用。

## **9.16 构建**

&emsp;&emsp;Spring Boot包含Maven和Gradle的构建插件。 本节回答有关这些插件的常见问题。

### **9.16.1 生成构建信息**

&emsp;&emsp;Maven插件和Gradle插件都允许生成包含项目坐标，名称和版本的构建信息。 插件还可以配置为通过配置添加其他属性。 当存在这样的文件时，Spring Boot会自动配置BuildProperties bean。

&emsp;&emsp;要使用Maven生成构建信息，请为build-info目标添加执行，如以下示例所示：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
			<version>2.1.3.RELEASE</version>
			<executions>
				<execution>
					<goals>
						<goal>build-info</goal>
					</goals>
				</execution>
			</executions>
		</plugin>
	</plugins>
</build>
```

>有关更多详细信息，请参阅Spring Boot Maven插件文档。

&emsp;&emsp;以下示例对Gradle执行相同操作：

``` 
springBoot {
	buildInfo()
}
```

>有关更多详细信息，请参阅Spring Boot Gradle Plugin文档。

### **9.16.2 生成Git信息**

&emsp;&emsp;Maven和Gradle都允许生成一个git.properties文件，其中包含有关构建项目时git源代码存储库状态的信息。

&emsp;&emsp;对于Maven用户，spring-boot-starter-parent POM包含一个预先配置的插件，用于生成git.properties文件。 要使用它，请将以下声明添加到POM：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>pl.project13.maven</groupId>
			<artifactId>git-commit-id-plugin</artifactId>
		</plugin>
	</plugins>
</build>
```

&emsp;&emsp;Gradle用户可以使用gradle-git-properties插件获得相同的结果，如以下示例所示：

``` 
plugins {
	id "com.gorylenko.gradle-git-properties" version "1.5.1"
}
```

>git.properties中的提交时间应符合以下格式：yyyy-MM-dd'T'HH:mm:ssZ。 这是上面列出的两个插件的默认格式。 使用此格式可以将时间解析为日期及其格式，在序列化为JSON时，由Jackson的日期序列化配置设置控制。

### **9.16.3 自定义依赖版本**

&emsp;&emsp;如果您使用直接或间接从spring-boot-dependencies（例如，spring-boot-starter-parent）继承的Maven构建，但是您想要覆盖特定的第三方依赖项，则可以添加适当的<properties>元素。 浏览spring-boot-dependencies POM以获取完整的属性列表。 例如，要选择不同的slf4j版本，您需要添加以下属性：

``` 
<properties>
	<slf4j.version>1.7.5<slf4j.version>
</properties>
```

>这样做只有在Maven项目从spring-boot-dependencies（直接或间接）继承时才有效。 如果在自己的dependencyManagement部分中使用<scope> import </ scope>添加了spring-boot-dependencies，则必须自己重新定义工件而不是覆盖该属性。

&emsp;
>每个Spring Boot版本都是针对这组特定的第三方依赖项进行设计和测试的。 覆盖版本可能会导致兼容性问题。

&emsp;&emsp;要在Gradle中覆盖依赖项版本，请参阅Gradle插件文档的此部分。

### **9.16.4 使用Maven创建可执行的JAR**

&emsp;&emsp;spring-boot-maven-plugin可用于创建可执行的“完整”JAR。 如果你使用spring-boot-starter-parent POM，你可以声明插件，你的jar重新打包如下：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>
```

&emsp;&emsp;如果您不使用父POM，您仍然可以使用该插件。 但是，您还必须添加<executions>部分，如下所示：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
			<version>2.1.3.RELEASE</version>
			<executions>
				<execution>
					<goals>
						<goal>repackage</goal>
					</goals>
				</execution>
			</executions>
		</plugin>
	</plugins>
</build>
```

&emsp;&emsp;有关完整的使用详细信息，请参阅插件文档。

### **9.16.5 使用Spring Boot应用程序作为依赖项**

&emsp;&emsp;与war文件一样，Spring Boot应用程序不能用作依赖项。 如果您的应用程序包含要与其他项目共享的类，建议的方法是将该代码移动到单独的模块中。 然后，您的应用程序和其他项目可以依赖单独的模块。

&emsp;&emsp;如果您不能按照上面的建议重新安排代码，则必须配置Spring Boot的Maven和Gradle插件，以生成适合用作依赖项的单独工件。 可执行存档不能用作依赖项，因为可执行jar格式打包BOOT-INF/classes中的应用程序类。 这意味着当可执行jar用作依赖项时，无法找到它们。

&emsp;&emsp;要生成两个工件，一个可以用作依赖项，另一个可执行，必须指定一个分类器。 此分类器应用于可执行归档的名称，保留默认归档以用作依赖项。

&emsp;&emsp;要在Maven中配置exec的分类器，可以使用以下配置：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
			<configuration>
				<classifier>exec</classifier>
			</configuration>
		</plugin>
	</plugins>
</build>
```

### **9.16.6 可执行jar运行时提取特定库**

&emsp;&emsp;可执行jar中的大多数嵌套库不需要解压缩才能运行。 但是，某些库可能存在问题。 例如，JRuby包含自己的嵌套jar支持，它假定jruby-complete.jar总是直接作为文件直接使用。

&emsp;&emsp;要处理任何有问题的库，您可以标记在可执行jar首次运行时应该自动解压缩特定的嵌套jar。 这些嵌套的jar文件写在java.io.tmpdir系统属性标识的临时目录下。

>应注意确保配置操作系统，以便在应用程序仍在运行时不会删除已解压缩到临时目录的jar。

例如，要指示应使用Maven插件标记JRuby以进行解包，您将添加以下配置：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
			<configuration>
				<requiresUnpack>
					<dependency>
						<groupId>org.jruby</groupId>
						<artifactId>jruby-complete</artifactId>
					</dependency>
				</requiresUnpack>
			</configuration>
		</plugin>
	</plugins>
</build>
```

### **9.16.7 使用排除项创建不可执行的JAR**

&emsp;&emsp;通常，如果您将可执行文件和非可执行jar作为两个单独的构建产品，则可执行版本具有库jar中不需要的其他配置文件。 例如，application.yml配置文件可能从非可执行JAR中排除。

&emsp;&emsp;在Maven中，可执行jar必须是主要工件，您可以为库添加一个分类jar，如下所示：

``` 
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
		<plugin>
			<artifactId>maven-jar-plugin</artifactId>
			<executions>
				<execution>
					<id>lib</id>
					<phase>package</phase>
					<goals>
						<goal>jar</goal>
					</goals>
					<configuration>
						<classifier>lib</classifier>
						<excludes>
							<exclude>application.yml</exclude>
						</excludes>
					</configuration>
				</execution>
			</executions>
		</plugin>
	</plugins>
</build>
```

### **9.16.8 从Maven开始远程调试Spring Boot应用程序**

&emsp;&emsp;要将远程调试器附加到使用Maven启动的Spring Boot应用程序，您可以使用maven插件的jvmArguments属性。

&emsp;&emsp;有关详细信息，请参阅此示例。

### **9.16.9 不使用spring-boot-antlib从Ant构建可执行文件存档**

&emsp;&emsp;要使用Ant构建，您需要获取依赖项，编译，然后创建jar或war存档。 要使其可执行，您可以使用spring-boot-antlib模块，也可以按照以下说明操作：

1. 如果要构建jar，请将应用程序的类和资源打包到嵌套的BOOT-INF/classes目录中。 如果要构建war，请像往常一样将应用程序的类打包在嵌套的WEB-INF/classes目录中。
2. 在嵌套的BOOT-INF/lib目录中为jar或WEB-INF/lib添加运行时依赖项以进行war。 切记不要压缩存档中的条目。
3. 将提供的（嵌入式容器）依赖项添加到嵌套的BOOT-INF/lib目录中，用于jar或为战争提供的WEB-INF/lib。 切记不要压缩存档中的条目。
4. 在归档的根目录中添加spring-boot-loader类（以便Main-Class可用）。
5. 使用适当的启动程序（例如jar文件的JarLauncher）作为清单中的Main-Class属性，并指定其作为清单条目所需的其他属性 - 主要通过设置Start-Class属性。


&emsp;&emsp;以下示例显示如何使用Ant构建可执行存档：

``` 
<target name="build" depends="compile">
	<jar destfile="target/${ant.project.name}-${spring-boot.version}.jar" compress="false">
		<mappedresources>
			<fileset dir="target/classes" />
			<globmapper from="*" to="BOOT-INF/classes/*"/>
		</mappedresources>
		<mappedresources>
			<fileset dir="src/main/resources" erroronmissingdir="false"/>
			<globmapper from="*" to="BOOT-INF/classes/*"/>
		</mappedresources>
		<mappedresources>
			<fileset dir="${lib.dir}/runtime" />
			<globmapper from="*" to="BOOT-INF/lib/*"/>
		</mappedresources>
		<zipfileset src="${lib.dir}/loader/spring-boot-loader-jar-${spring-boot.version}.jar" />
		<manifest>
			<attribute name="Main-Class" value="org.springframework.boot.loader.JarLauncher" />
			<attribute name="Start-Class" value="${start-class}" />
		</manifest>
	</jar>
</target>
```

&emsp;&emsp;Ant Sample有一个build.xml文件，其中包含一个手动任务，如果使用以下命令运行它，该文件应该可以正常运行：

``` 
$ ant -lib <folder containing ivy-2.2.jar> clean manual
```

&emsp;&emsp;然后，您可以使用以下命令运行该应用程序：

``` 
$ java -jar target/*.jar
```

## **9.17 传统部署**

&emsp;&emsp;Spring Boot支持传统部署以及更现代的部署形式。 本节回答有关传统部署的常见问题。

### **9.17.1 创建可部署的War文件**

>由于Spring WebFlux并不严格依赖于Servlet API，并且默认情况下会在嵌入式Reactor Netty服务器上部署应用程序，因此WebFlux应用程序不支持War部署。

&emsp;&emsp;生成可部署war文件的第一步是提供SpringBootServletInitializer子类并覆盖其configure方法。 这样做可以利用Spring Framework的Servlet 3.0支持，并允许您在servlet容器启动时配置应用程序。 通常，您应该更新应用程序的主类以扩展SpringBootServletInitializer，如以下示例所示：

``` 
@SpringBootApplication
public class Application extends SpringBootServletInitializer {

	@Override
	protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
		return application.sources(Application.class);
	}

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

}
```

&emsp;&emsp;下一步是更新构建配置，以便项目生成war文件而不是jar文件。 如果您使用Maven和spring-boot-starter-parent（为您配置Maven的war插件），您需要做的就是修改pom.xml以将包装更改为war，如下所示：

``` 
<packaging>war</packaging>
```

&emsp;&emsp;如果使用Gradle，则需要修改build.gradle以将war插件应用于项目，如下所示：

``` 
apply plugin: 'war'
```

&emsp;&emsp;该过程的最后一步是确保嵌入式servlet容器不会干扰部署war文件的servlet容器。 为此，您需要将嵌入式servlet容器依赖项标记为已提供。

&emsp;&emsp;如果您使用Maven，以下示例将servlet容器（在本例中为Tomcat）标记为提供：

``` 
<dependencies>
	<!-- … -->
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-tomcat</artifactId>
		<scope>provided</scope>
	</dependency>
	<!-- … -->
</dependencies>
```

&emsp;&emsp;如果使用Gradle，则以下示例将servlet容器（在本例中为Tomcat）标记为提供：

``` 
dependencies {
	// …
	providedRuntime 'org.springframework.boot:spring-boot-starter-tomcat'
	// …
}
```

>providedRuntime比Gradle的compileOnly配置更受欢迎。 除了其他限制之外，compileOnly依赖项不在测试类路径上，因此任何基于Web的集成测试都会失败。

&emsp;&emsp;如果使用Spring Boot构建工具，则标记所提供的嵌入式servlet容器依赖项将生成一个可执行war文件，其中提供的依赖项打包在lib提供的目录中。 这意味着，除了可部署到servlet容器之外，还可以在命令行上使用java -jar运行应用程序。

>查看Spring Boot的示例应用程序，了解基于Maven的先前配置示例。

### **9.17.2 将现有应用程序转换为Spring Boot**

&emsp;&emsp;对于非Web应用程序，应该很容易将现有的Spring应用程序转换为Spring Boot应用程序。 为此，请丢弃创建ApplicationContext的代码，并将其替换为对SpringApplication或SpringApplicationBuilder的调用。 Spring MVC Web应用程序通常可以首先创建可部署的war应用程序，然后再将其迁移到可执行的war或jar。 请参阅将jar转换为war的入门指南。

&emsp;&emsp;要通过扩展SpringBootServletInitializer（例如，在名为Application的类中）并添加Spring Boot @SpringBootApplication批注来创建可部署的war，请使用类似于以下示例中所示的代码：

``` 
@SpringBootApplication
public class Application extends SpringBootServletInitializer {

	@Override
	protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
		// Customize the application or call application.sources(...) to add sources
		// Since our example is itself a @Configuration class (via @SpringBootApplication)
		// we actually don't need to override this method.
		return application;
	}

}
```

&emsp;&emsp;请记住，无论你在源代码中添加什么，都只是一个Spring ApplicationContext。 通常，任何已经有效的东西都应该在这里工作。 可能有一些bean可以在以后删除，让Spring Boot为它们提供自己的默认值，但应该可以在需要之前获得一些工作。

&emsp;&emsp;静态资源可以移动到类路径根目录中的/public（或/static或/resources或/META-INF/resources）。 这同样适用于messages.properties（Spring Boot会自动在类路径的根中检测到）。

&emsp;&emsp;Spring DispatcherServlet和Spring Security的Vanilla使用不需要进一步更改。 如果应用程序中有其他功能（例如，使用其他servlet或过滤器），则可能需要通过从web.xml替换这些元素，将一些配置添加到Application上下文，如下所示：

- 类型为Servlet或ServletRegistrationBean的@Bean将该bean安装在容器中，就好像它是web.xml中的<servlet />和<servlet-mapping />一样。
- 类型为Filter或FilterRegistrationBean的@Bean的行为类似（作为<filter />和<filter-mapping />）。
- 可以通过Application中的@ImportResource添加XML文件中的ApplicationContext。 或者，已经大量使用注释配置的简单情况可以在几行中重新创建为@Bean定义。


&emsp;&emsp;一旦war文件正常工作，您可以通过向Application添加main方法使其可执行，如以下示例所示：

``` 
public static void main(String[] args) {
	SpringApplication.run(Application.class, args);
}
```

如果您打算将应用程序作为war或可执行应用程序启动，则需要在一个方法中共享构建器的自定义，该方法既可用于SpringBootServletInitializer回调，也可用于类似于以下类的main方法中：

>```
@SpringBootApplication
public class Application extends SpringBootServletInitializer {
>
	@Override
	protected SpringApplicationBuilder configure(SpringApplicationBuilder builder) {
		return configureApplication(builder);
	}
>
	public static void main(String[] args) {
		configureApplication(new SpringApplicationBuilder()).run(args);
	}
>
	private static SpringApplicationBuilder configureApplication(SpringApplicationBuilder builder) {
		return builder.sources(Application.class).bannerMode(Banner.Mode.OFF);
	}
>
}
>```

&emsp;&emsp;应用程序可以分为多个类别：

- 没有web.xml的Servlet 3.0+应用程序。
- 带有web.xml的应用程序。
- 具有上下文层次结构的应用
- 没有上下文层次结构的应用


&emsp;&emsp;所有这些都应该适合转变，但每种都可能需要稍微不同的技术。

&emsp;&emsp;如果Servlet 3.0+应用程序已经使用了Spring Servlet 3.0+初始化程序支持类，那么它们可能很容易翻译。 通常，现有WebApplicationInitializer中的所有代码都可以移动到SpringBootServletInitializer中。 如果现有应用程序具有多个ApplicationContext（例如，如果它使用AbstractDispatcherServletInitializer），那么您可以将所有上下文源组合到单个SpringApplication中。 您可能遇到的主要复杂情况是，如果组合不起作用，您需要维护上下文层次结构。 有关示例，请参阅构建层次结构的条目。 通常需要拆分包含特定于Web的功能的现有父上下文，以便所有ServletContextAware组件都位于子上下文中。

&emsp;&emsp;尚未安装Spring应用程序的应用程序可以转换为Spring Boot应用程序，前面提到的指南可能有所帮助。 但是，您可能会遇到问题。 在这种情况下，我们建议使用spring-boot标记在Stack Overflow上提问。

### **9.17.3 将WAR部署到WebLogic**

&emsp;&emsp;要将Spring Boot应用程序部署到WebLogic，必须确保servlet初始化程序直接实现WebApplicationInitializer（即使从已实现它的基类扩展）。

&emsp;&emsp;WebLogic的典型初始化程序应类似于以下示例：

``` 
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.boot.web.servlet.support.SpringBootServletInitializer;
import org.springframework.web.WebApplicationInitializer;

@SpringBootApplication
public class MyApplication extends SpringBootServletInitializer implements WebApplicationInitializer {

}
```

&emsp;&emsp;如果使用Logback，则还需要告知WebLogic更喜欢打包版本而不是服务器预安装的版本。 您可以通过添加包含以下内容的WEB-INF/weblogic.xml文件来完成此操作：

``` 
<?xml version="1.0" encoding="UTF-8"?>
<wls:weblogic-web-app
	xmlns:wls="http://xmlns.oracle.com/weblogic/weblogic-web-app"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
		http://java.sun.com/xml/ns/javaee/ejb-jar_3_0.xsd
		http://xmlns.oracle.com/weblogic/weblogic-web-app
		http://xmlns.oracle.com/weblogic/weblogic-web-app/1.4/weblogic-web-app.xsd">
	<wls:container-descriptor>
		<wls:prefer-application-packages>
			<wls:package-name>org.slf4j</wls:package-name>
		</wls:prefer-application-packages>
	</wls:container-descriptor>
</wls:weblogic-web-app>
```

### **9.17.4 用Jedis而不是Lettuce**

&emsp;&emsp;默认情况下，Spring Boot启动程序（spring-boot-starter-data-redis）使用Lettuce。 您需要排除该依赖项并改为包含Jedis。 Spring Boot管理这些依赖项，以帮助使这个过程尽可能简单。

&emsp;&emsp;以下示例显示了如何在Maven中执行此操作：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-redis</artifactId>
	<exclusions>
		<exclusion>
			<groupId>io.lettuce</groupId>
			<artifactId>lettuce-core</artifactId>
		</exclusion>
	</exclusions>
</dependency>
<dependency>
	<groupId>redis.clients</groupId>
	<artifactId>jedis</artifactId>
</dependency>
```

&emsp;&emsp;以下示例显示了如何在Gradle中执行此操作：

``` 
configurations {
	compile.exclude module: "lettuce"
}

dependencies {
	compile("redis.clients:jedis")
	// ...
}
```

# **10 附录**

## **10.1 常见的应用属性**

&emsp;&emsp;可以在application.properties文件中，application.yml文件中或命令行开关中指定各种属性。 本附录提供了常见Spring Boot属性的列表以及对使用它们的基础类的引用。

>Spring Boot提供了各种具有高级值格式的转换机制，请务必查看属性转换部分。

&emsp;
>属性可以来自类路径上的其他jar文件，因此您不应将此视为详尽的列表。 此外，您可以定义自己的属性。

&emsp;
>此示例文件仅供参考。 不要将整个内容复制并粘贴到您的应用程序中。 相反，只选择您需要的属性。

&emsp;&emsp;详情请查看附件
[springboot配置属性.xlsx](leanote://file/getAttach?fileId=5c96587cf7c35f023f000000)

## **10.2 配置元数据**

&emsp;&emsp;Spring Boot jar包含元数据文件，提供所有支持的配置属性的详细信息。 这些文件旨在让IDE开发人员在使用application.properties或application.yml文件时提供上下文帮助和“代码完成”。

### **10.2.1 格式化元数据**

&emsp;&emsp;通过处理使用@ConfigurationProperties注释的所有项目，在编译时自动生成大部分元数据文件。 但是，可以针对极端情况或更高级的用例手动编写部分元数据。

&emsp;&emsp;配置元数据文件位于META-INF/spring-configuration-metadata.json下的jar中。它们使用简单的JSON格式，其中的项目分类为“groups”或“properties”，其他值提示分类在“hints”下，如 以下示例：

``` 
{"groups": [
	{
		"name": "server",
		"type": "org.springframework.boot.autoconfigure.web.ServerProperties",
		"sourceType": "org.springframework.boot.autoconfigure.web.ServerProperties"
	},
	{
		"name": "spring.jpa.hibernate",
		"type": "org.springframework.boot.autoconfigure.orm.jpa.JpaProperties$Hibernate",
		"sourceType": "org.springframework.boot.autoconfigure.orm.jpa.JpaProperties",
		"sourceMethod": "getHibernate()"
	}
	...
],"properties": [
	{
		"name": "server.port",
		"type": "java.lang.Integer",
		"sourceType": "org.springframework.boot.autoconfigure.web.ServerProperties"
	},
	{
		"name": "server.address",
		"type": "java.net.InetAddress",
		"sourceType": "org.springframework.boot.autoconfigure.web.ServerProperties"
	},
	{
		  "name": "spring.jpa.hibernate.ddl-auto",
		  "type": "java.lang.String",
		  "description": "DDL mode. This is actually a shortcut for the \"hibernate.hbm2ddl.auto\" property.",
		  "sourceType": "org.springframework.boot.autoconfigure.orm.jpa.JpaProperties$Hibernate"
	}
	...
],"hints": [
	{
		"name": "spring.jpa.hibernate.ddl-auto",
		"values": [
			{
				"value": "none",
				"description": "Disable DDL handling."
			},
			{
				"value": "validate",
				"description": "Validate the schema, make no changes to the database."
			},
			{
				"value": "update",
				"description": "Update the schema if necessary."
			},
			{
				"value": "create",
				"description": "Create the schema and destroy previous data."
			},
			{
				"value": "create-drop",
				"description": "Create and then destroy the schema at the end of the session."
			}
		]
	}
]}
```

&emsp;&emsp;每个“properties”是用户使用给定值指定的配置项。 例如，server.port和server.address可能在application.properties中指定，如下所示：

``` 
server.port=9090
server.address=127.0.0.1
```

&emsp;&emsp;“groups”是更高级别的项目，它们本身不指定值，而是为属性提供上下文分组。 例如，server.port和server.address属性是服务器组的一部分。

>并不要求每个“property”都有“group”。 某些属性可能本身就存在。

&emsp;&emsp;最后，“hints”是用于帮助用户配置给定属性的附加信息。 例如，当开发人员配置spring.jpa.hibernate.ddl-auto属性时，工具可以使用提示为none，validate，update，create和create-drop值提供一些自动完成帮助。

**10.2.1.1 Group属性**

&emsp;&emsp;groups数组中包含的JSON对象可以包含下表中显示的属性：

<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>name</td>
		<td>String</td>
		<td>组的全名。 此属性是必需的。</td>
	</tr>
	<tr>
		<td>type</td>
		<td>String</td>
		<td>组的数据类型的类名称。 例如，如果该组基于使用@ConfigurationProperties注释的类，则该属性将包含该类的完全限定名称。 如果它基于@Bean方法，那么它将是该方法的返回类型。 如果类型未知，则可以省略该属性。</td>
	</tr>
	<tr>
		<td>description</td>
		<td>String</td>
		<td>可以向用户显示的组的简短描述。 如果没有描述，则可以省略。 建议描述为简短段落，第一行提供简明摘要。 描述中的最后一行应以句点（。）结尾。</td>
	</tr>
	<tr>
		<td>sourceType</td>
		<td>String</td>
		<td>贡献此组的源的类名称。 例如，如果该组基于使用@ConfigurationProperties注释的@Bean方法，则此属性将包含包含该方法的@Configuration类的完全限定名称。 如果源类型未知，则可以省略该属性。</td>
	</tr>
	<tr>
		<td>sourceMethod</td>
		<td>String</td>
		<td>贡献该组的方法的全名（包括括号和参数类型）（例如，@ConigurationProperties注释的@Bean方法的名称）。 如果源方法未知，则可以省略。</td>
	</tr>
</table>

**10.2.1.2 Property属性**

&emsp;&emsp;properties数组中包含的JSON对象可以包含下表中描述的属性：

<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>name</td>
		<td>String</td>
		<td>该属性的全名。 名称采用小写的句点分隔形式（例如，server.address）。 此属性是必需的。</td>
	</tr>
	<tr>
		<td>type</td>
		<td>String</td>
		<td>属性的数据类型的完整签名（例如，java.lang.String），但也是完整的泛型类型（例如java.util.Map&lt;java.util.String，acme.MyEnum>）。 您可以使用此属性来指导用户可以输入的值的类型。 为了保持一致性，通过使用其包装器对应项来指定基元的类型（例如，boolean变为java.lang.Boolean）。 请注意，此类可能是一个复杂类型，在绑定值时会从String转换。 如果类型未知，则可以省略。</td>
	</tr>
	<tr>
		<td>description</td>
		<td>String</td>
		<td>可以向用户显示的组的简短描述。 如果没有可用的描述，则可以省略。 建议描述为简短段落，第一行提供简明摘要。 描述中的最后一行应以句点（。）结尾。</td>
	</tr>
	<tr>
		<td>sourceType</td>
		<td>String</td>
		<td>贡献此属性的源的类名称。 例如，如果属性来自使用@ConfigurationProperties注释的类，则此属性将包含该类的完全限定名称。 如果源类型未知，则可以省略。</td>
	</tr>
	<tr>
		<td>defaultValue</td>
		<td>Object</td>
		<td>默认值，如果未指定属性，则使用该值。 如果属性的类型是数组，则它可以是值数组。 如果默认值未知，则可以省略。</td>
	</tr>
	<tr>
		<td>deprecation</td>
		<td>Deprecation</td>
		<td>指定是否弃用该属性。 如果该字段未被弃用或者该信息未知，则可以省略该字段。 下表提供了有关deprecation属性的更多详细信息。</td>
	</tr>
</table>

&emsp;&emsp;每个属性元素的deprecation属性中包含的JSON对象可以包含以下属性：

<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>level</td>
		<td>String</td>
		<td>弃用级别，可以是警告（默认）或错误。 当属性具有警告弃用级别时，它仍应绑定在环境中。 但是，如果它具有错误弃用级别，则不再管理该属性，也不会绑定该属性。</td>
	</tr>
	<tr>
		<td>reason</td>
		<td>String</td>
		<td>该属性被弃用的原因的简短描述。 如果没有可用的原因，可以省略。 建议描述为简短段落，第一行提供简明摘要。 描述中的最后一行应以句点（。）结尾。</td>
	</tr>
	<tr>
		<td>replacement</td>
		<td>String</td>
		<td>替换此不推荐使用的属性的属性的全名。 如果此属性没有替换，则可以省略。</td>
	</tr>
</table>

<table>
	<tr>
		<td></td>
	</tr>
	<tr>
		<td>在Spring Boot 1.3之前，可以使用单个弃用的布尔属性来代替deprecation元素。 这仍然以不推荐的方式支持，不应再使用。 如果没有可用的原因和替换，则应设置空的弃用对象。</td>
	</tr>
</table>

&emsp;&emsp;通过将@DeprecatedConfigurationProperty批注添加到getter，公开不推荐使用的属性，也可以在代码中以声明方式指定弃用。 例如，假设app.acme.target属性令人困惑，并重命名为app.acme.name。 以下示例显示了如何处理这种情况：

``` 
@ConfigurationProperties("app.acme")
public class AcmeProperties {

	private String name;

	public String getName() { ... }

	public void setName(String name) { ... }

	@DeprecatedConfigurationProperty(replacement = "app.acme.name")
	@Deprecated
	public String getTarget() {
		return getName();
	}

	@Deprecated
	public void setTarget(String target) {
		setName(target);
	}
}
```

>没有办法设定一个级别。 始终假定警告，因为代码仍在处理属性。

&emsp;&emsp;上面的代码确保deprecated属性仍然有效（委托给幕后的name属性）。 一旦可以从公共API中删除getTarget和setTarget方法，元数据中的自动弃用提示也会消失。 如果要保留提示，添加具有错误弃用级别的手动元数据可确保用户仍然了解该属性。 当提供替换时，这样做特别有用。

**10.2.1.3 Hint属性**

&emsp;&emsp;提示数组中包含的JSON对象可以包含下表中显示的属性：

<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>name</td>
		<td>String</td>
		<td>此提示引用的属性的全名。 名称采用小写的句点分隔形式（例如spring.mvc.servlet.path）。 如果属性引用了映射（例如system.contexts），则提示要么应用于映射的键（system.context.keys），要么应用于映射的值（system.context.values）。 此属性是必需的。</td>
	</tr>
	<tr>
		<td>values</td>
		<td>ValueHint[]</td>
		<td>ValueHint对象定义的有效值列表（在下表中描述）。 每个条目定义值并且可以具有描述。</td>
	</tr>
	<tr>
		<td>providers</td>
		<td>ValueProvider[]</td>
		<td>由ValueProvider对象定义的提供程序列表（在本文档后面部分中描述）。 每个条目定义提供者的名称及其参数（如果有）。</td>
	</tr>
</table>

&emsp;&emsp;每个提示元素的values属性中包含的JSON对象可以包含下表中描述的属性：

<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>value</td>
		<td>Object</td>
		<td>提示引用的元素的有效值。 如果属性的类型是数组，它也可以是值数组。 此属性是必需的。</td>
	</tr>
	<tr>
		<td>description</td>
		<td>String</td>
		<td>可以向用户显示的值的简短描述。 如果没有可用的描述，则可以省略。 建议描述为简短段落，第一行提供简明摘要。 描述中的最后一行应以句点（。）结尾。</td>
	</tr>
</table>

&emsp;&emsp;每个提示元素的providers属性中包含的JSON对象可以包含下表中描述的属性：

<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>name</td>
		<td>String</td>
		<td>用于为提示引用的元素提供其他内容帮助的提供程序的名称。</td>
	</tr>
	<tr>
		<td>parameters</td>
		<td>JSON object</td>
		<td>提供程序支持的任何其他参数（有关更多详细信息，请查看提供程序的文档）。</td>
	</tr>
</table>

**10.2.1.4 重复的元数据项**

&emsp;&emsp;具有相同“属性”和“组”名称的对象可以在元数据文件中多次出现。 例如，您可以将两个单独的类绑定到同一个前缀，每个类都有可能重叠的属性名称。 虽然多次出现在元数据中的相同名称不应该是常见的，但元数据的使用者应该注意确保他们支持它。

### **10.2.2 提供手动提示**

&emsp;&emsp;要改善用户体验并进一步帮助用户配置给定属性，您可以提供以下附加元数据：

- 描述属性的潜在值列表。
- 关联提供者，将明确定义的语义附加到属性，以便工具可以根据项目的上下文发现潜在值列表。


**10.2.2.1 Value提示**

&emsp;&emsp;每个提示的name属性引用属性的名称。 在前面显示的初始示例中，我们为spring.jpa.hibernate.ddl-auto属性提供了五个值：none，validate，update，create和create-drop。 每个值也可以有描述。

&emsp;&emsp;如果您的属性是Map类型，则可以为键和值提供提示（但不提供Map本身的提示）。 特殊的.keys和.values后缀必须分别引用键和值。

&emsp;&emsp;假设sample.contexts将String值映射为整数，如以下示例所示：

``` 
@ConfigurationProperties("sample")
public class SampleProperties {

	private Map<String,Integer> contexts;
	// getters and setters
}
```

&emsp;&emsp;值（在本例中）是sample1和sample2。 为了为密钥提供额外的内容帮助，您可以将以下JSON添加到模块的手动元数据中：

``` 
{"hints": [
	{
		"name": "sample.contexts.keys",
		"values": [
			{
				"value": "sample1"
			},
			{
				"value": "sample2"
			}
		]
	}
]}
```

>我们建议您使用Enum代替这两个值。 如果您的IDE支持它，这是迄今为止最有效的自动完成方法。

**10.2.2.2 Value的提供者**

&emsp;&emsp;提供程序是将语义附加到属性的强大方法。 在本节中，我们定义了可用于您自己的提示的官方提供程序。 但是，您最喜欢的IDE可能会实现其中一些或不实现。 此外，它最终可以提供自己的。

>由于这是一项新功能，因此IDE供应商必须了解其工作原理。 采用时间自然会有所不同。

&emsp;&emsp;下表总结了支持的提供程序列表：

<table>
	<tr>
		<th>Name</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>any</td>
		<td>允许提供任何附加值。</td>
	</tr>
	<tr>
		<td>class-reference</td>
		<td>自动完成项目中可用的类。 通常由target参数指定的基类约束。</td>
	</tr>
	<tr>
		<td>handle-as</td>
		<td>处理属性，就好像它是由强制目标参数定义的类型定义的一样。</td>
	</tr>
	<tr>
		<td>logger-name</td>
		<td>自动完成有效的记录器名称和记录器组。 通常，当前项目中可用的包名和类名可以自动完成，也可以自定义组。</td>
	</tr>
	<tr>
		<td>spring-bean-reference</td>
		<td>自动完成当前项目中的可用bean名称。 通常由targetparameter指定的基类约束。</td>
	</tr>
	<tr>
		<td>spring-profile-name</td>
		<td>自动完成项目中可用的Spring配置文件名称。</td>
	</tr>
</table>

>对于给定的属性，只有一个提供程序可以处于活动状态，但如果它们都可以以某种方式管理属性，则可以指定多个提供程序。 确保首先放置最强大的提供程序，因为IDE必须使用它可以处理的JSON部分中的第一个。 如果不支持给定属性的提供者，则也不提供特殊内容帮助。

**1）any**

&emsp;&emsp;特殊的任何提供者值都允许提供任何其他值。 如果支持，则应应用基于属性类型的常规值验证。

&emsp;&emsp;如果您有值列表并且任何额外值仍应被视为有效，则通常使用此提供程序。

&emsp;&emsp;以下示例为system.state提供on和off作为自动完成值：

``` 
{"hints": [
	{
		"name": "system.state",
		"values": [
			{
				"value": "on"
			},
			{
				"value": "off"
			}
		],
		"providers": [
			{
				"name": "any"
			}
		]
	}
]}
```

&emsp;&emsp;请注意，在前面的示例中，还允许任何其他值。

**2）class-reference**

&emsp;&emsp;类引用提供程序自动完成项目中可用的类。 此提供程序支持以下参数：

<table>
	<tr>
		<th>Parameter</th>
		<th>Type</th>
		<th>Default value</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>target</td>
		<td>String(Class)</td>
		<td>none</td>
		<td>应分配给所选值的类的完全限定名称。 通常用于过滤非候选类。 请注意，通过公开具有适当上限的类，可以通过类型本身提供此信息。</td>
	</tr>
	<tr>
		<td>concrete</td>
		<td>boolean</td>
		<td>true</td>
		<td>指定是否仅将具体类视为有效候选。</td>
	</tr>
</table>

&emsp;&emsp;以下元数据片段对应于标准server.servlet.jsp.class-name属性，该属性定义要使用的JspServlet类名：

``` 
{"hints": [
	{
		"name": "server.servlet.jsp.class-name",
		"providers": [
			{
				"name": "class-reference",
				"parameters": {
					"target": "javax.servlet.http.HttpServlet"
				}
			}
		]
	}
]}
```

**3）handle-as**

&emsp;&emsp;handle-as提供程序允许您将属性的类型替换为更高级别的类型。 当属性具有java.lang.String类型时，通常会发生这种情况，因为您不希望配置类依赖于可能不在类路径上的类。 此提供程序支持以下参数：

<table>
	<tr>
		<th>Parameter</th>
		<th>Type</th>
		<th>Default value</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>target</td>
		<td>String (Class)</td>
		<td>none</td>
		<td>要为该属性考虑的类型的完全限定名称。 此参数是必需的。</td>
	</tr>
</table>

&emsp;&emsp;可以使用以下类型：

- 任何java.lang.Enum：列出属性的可能值。 （我们建议使用Enum类型定义属性，因为IDE不需要进一步提示来自动完成值。）
- java.nio.charset.Charset：支持自动完成charset / encoding值（例如UTF-8）
- java.util.Locale：自动完成语言环境（例如en_US）
- org.springframework.util.MimeType：支持自动完成内容类型值（例如text / plain）
- org.springframework.core.io.Resource：支持Spring的资源抽象的自动完成，以引用文件系统或类路径上的文件。（例如classpath:/sample.properties）

>如果可以提供多个值，请使用Collection或Array类型向IDE讲授它。

&emsp;&emsp;以下元数据片段对应于标准spring.liquibase.change-log属性，该属性定义要使用的更改日志的路径。 它实际上在内部用作org.springframework.core.io.Resource但不能这样公开，因为我们需要保留原始的String值以将其传递给Liquibase API。

``` 
{"hints": [
	{
		"name": "spring.liquibase.change-log",
		"providers": [
			{
				"name": "handle-as",
				"parameters": {
					"target": "org.springframework.core.io.Resource"
				}
			}
		]
	}
]}
```

**4）logger-name**

&emsp;&emsp;logger-name提供程序自动完成有效的记录器名称和记录器组。 通常，可以自动完成当前项目中可用的包名和类名。 如果启用了组（默认），并且在配置中标识了自定义记录器组，则应提供自动完成组。 特定框架可能还有额外的魔术记录器名称，也可以支持。

&emsp;&emsp;此提供程序支持以下参数：

<table>
	<tr>
		<th>Parameter</th>
		<th>Type</th>
		<th>Default value</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>group</td>
		<td>boolean</td>
		<td>true</td>
		<td>指定是否应考虑已知组。</td>
	</tr>
</table>

&emsp;&emsp;由于记录器名称可以是任意名称，因此此提供程序应允许任何值，但可以突出显示项目类路径中不可用的有效包名和类名。

&emsp;&emsp;以下元数据片段对应于标准的logging.level属性。 键是记录器名称，值对应于标准日志级别或任何自定义级别。 由于Spring Boot定义了几个开箱即用的记录器组，因此为这些组件添加了专用值提示。

``` 
{"hints": [
	{
		"name": "logging.level.keys",
		"values": [
			{
				"value": "root",
				"description": "Root logger used to assign the default logging level."
			},
			{
				"value": "sql",
				"description": "SQL logging group including Hibernate SQL logger."
			},
			{
				"value": "web",
				"description": "Web logging group including codecs."
			}
		],
		"providers": [
			{
				"name": "logger-name"
			}
		]
	},
	{
		"name": "logging.level.values",
		"values": [
			{
				"value": "trace"
			},
			{
				"value": "debug"
			},
			{
				"value": "info"
			},
			{
				"value": "warn"
			},
			{
				"value": "error"
			},
			{
				"value": "fatal"
			},
			{
				"value": "off"
			}

		],
		"providers": [
			{
				"name": "any"
			}
		]
	}
]}
```

**5）spring-bean-reference**

&emsp;&emsp;spring-bean-reference提供程序自动完成在当前项目的配置中定义的bean。 此提供程序支持以下参数：

<table>
	<tr>
		<th>Parameter</th>
		<th>Type</th>
		<th>Default value</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>target</td>
		<td>String(Class)</td>
		<td>none</td>
		<td>应分配给候选者的bean类的完全限定名称。 通常用于过滤掉非候选bean。</td>
	</tr>
</table>

&emsp;&emsp;以下元数据片段对应于标准spring.jmx.server属性，该属性定义要使用的MBeanServer bean的名称：

``` 
{"hints": [
	{
		"name": "spring.jmx.server",
		"providers": [
			{
				"name": "spring-bean-reference",
				"parameters": {
					"target": "javax.management.MBeanServer"
				}
			}
		]
	}
]}
```

>绑定程序不知道元数据。 如果提供该提示，则仍需要使用ApplicationContext将bean名称转换为实际的Bean引用。

**6）spring-profile-name**

&emsp;&emsp;spring-profile-name提供程序自动完成在当前项目的配置中定义的Spring配置文件。

&emsp;&emsp;以下元数据片段对应于标准spring.profiles.active属性，该属性定义要启用的Spring配置文件的名称：

``` 
{"hints": [
	{
		"name": "spring.profiles.active",
		"providers": [
			{
				"name": "spring-profile-name"
			}
		]
	}
]}
```

### **10.2.3 使用注解处理器生成自己的元数据**

&emsp;&emsp;您可以使用spring-boot-configuration-processor jar从使用@ConfigurationProperties注释的项目轻松生成自己的配置元数据文件。 jar包含一个Java注释处理器，在您编译项目时调用该处理器。 要使用处理器，请包含对spring-boot-configuration-processor的依赖性。

&emsp;&emsp;使用Maven时，依赖项应声明为可选，如以下示例所示：

``` 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-configuration-processor</artifactId>
	<optional>true</optional>
</dependency>
```

&emsp;&emsp;使用Gradle 4.5及更早版本时，应在compileOnly配置中声明依赖项，如以下示例所示：

``` 
dependencies {
	compileOnly "org.springframework.boot:spring-boot-configuration-processor"
}
```

&emsp;&emsp;使用Gradle 4.6及更高版本时，应在annotationProcessor配置中声明依赖项，如以下示例所示：

``` 
dependencies {
	annotationProcessor "org.springframework.boot:spring-boot-configuration-processor"
}
```

&emsp;&emsp;如果您使用的是additional-spring-configuration-metadata.json文件，则应该将compileJava任务配置为依赖于processResources任务，如以下示例所示：

``` 
compileJava.dependsOn(processResources)
```

&emsp;&emsp;此依赖关系确保在编译期间注释处理器运行时可以使用其他元数据。

&emsp;&emsp;处理器选择使用@ConfigurationProperties注释的类和方法。 配置类中的字段值的Javadoc用于填充description属性。

>您应该只使用带有@ConfigurationProperties字段Javadoc的简单文本，因为它们在添加到JSON之前不会被处理。

&emsp;&emsp;通过存在标准的getter和setter来发现属性，这些getter和setter具有对集合类型的特殊处理（即使只有getter存在也会检测到）。 注释处理器还支持使用@ Data，@ Getter和@Setter lombok注释。

>如果在项目中使用AspectJ，则需要确保注释处理器仅运行一次。 有几种方法可以做到这一点。 使用Maven，您可以显式配置maven-apt-plugin，并仅在那里将依赖项添加到注释处理器。 您还可以让AspectJ插件在maven-compiler-plugin配置中运行所有处理并禁用注释处理，如下所示：

>```
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-compiler-plugin</artifactId>
	<configuration>
		<proc>none</proc>
	</configuration>
</plugin>
>```

**10.2.3.1 嵌套属性**

注释处理器自动将内部类视为嵌套属性。 考虑以下类：

``` 
@ConfigurationProperties(prefix="server")
public class ServerProperties {

	private String name;

	private Host host;

	// ... getter and setters

	public static class Host {

		private String ip;

		private int port;

		// ... getter and setters

	}

}
```

&emsp;&emsp;上面的示例为server.name，server.host.ip和server.host.port属性生成元数据信息。 您可以在字段上使用@NestedConfigurationProperty批注来指示应将常规（非内部）类视为嵌套。

>这对集合和映射没有影响，因为这些类型是自动标识的，并且为每个类型生成单个元数据属性。

**10.2.3.2 添加其他元数据**

&emsp;&emsp;Spring Boot的配置文件处理非常灵活，通常情况下可能存在未绑定到@ConfigurationProperties bean的属性。 您可能还需要调整现有密钥的某些属性。 为了支持此类情况并允许您提供自定义“提示”，注释处理器会自动将META-INF/additional-spring-configuration-metadata.json中的项合并到主元数据文件中。

&emsp;&emsp;如果引用自动检测到的属性，则会覆盖描述，默认值和弃用信息（如果已指定）。 如果未在当前模块中标识手动属性声明，则将其添加为新属性。

&emsp;&emsp;additional-spring-configuration-metadata.json文件的格式与常规的spring-configuration-metadata.json完全相同。 附加属性文件是可选的。 如果您没有任何其他属性，请不要添加该文件。

## **10.3 自动配置类**

&emsp;&emsp;以下是Spring Boot提供的所有自动配置类的列表，其中包含文档和源代码的链接。 请记住还要查看应用程序中的条件报告，以获取有关打开哪些功能的更多详细信息。 （为此，请使用--debug或-Ddebug启动应用程序，或者在Actuator应用程序中使用条件端点）。

### **10.3.1 来自“spring-boot-autoconfigure”模块**

&emsp;&emsp;以下自动配置类来自spring-boot-autoconfigure模块：

<table>
	<tr>
		<th>Configuration Class</th>
		<th>Links</th>
	</tr>
	<tr>
		<td>ActiveMQAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>AopAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ArtemisAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>BatchAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CacheAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraReactiveDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraReactiveRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ClientHttpConnectorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CloudServiceConnectorsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CodecsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ConfigurationPropertiesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseReactiveDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseReactiveRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DataSourceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DataSourceTransactionManagerAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DispatcherServletAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticsearchAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticsearchDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticsearchRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>EmbeddedLdapAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>EmbeddedMongoAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>EmbeddedWebServerFactoryCustomizerAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ErrorMvcAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ErrorWebFluxAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>FlywayAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>FreeMarkerAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>GroovyTemplateAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>GsonAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>H2ConsoleAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HazelcastAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HazelcastJpaDependencyAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HibernateJpaAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HttpEncodingAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HttpHandlerAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HttpMessageConvertersAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HypermediaAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>InfluxDbAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>IntegrationAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JacksonAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JdbcRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JdbcTemplateAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JerseyAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JestAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JmsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JmxAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JndiConnectionFactoryAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JndiDataSourceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JooqAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JpaRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JsonbAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JtaAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>KafkaAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LdapAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LdapRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LiquibaseAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MailSenderAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MailSenderValidatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MessageSourceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoReactiveAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoReactiveDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoReactiveRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MultipartAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MustacheAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>Neo4jDataAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>Neo4jRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>OAuth2ClientAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>OAuth2ResourceServerAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>PersistenceExceptionTranslationAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ProjectInfoAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>PropertyPlaceholderAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>QuartzAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RabbitAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveOAuth2ClientAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveOAuth2ResourceServerAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveSecurityAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveUserDetailsServiceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveWebServerFactoryAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactorCoreAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RedisAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RedisReactiveAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RedisRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RepositoryRestMvcAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RestClientAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RestTemplateAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SecurityAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SecurityFilterAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SecurityRequestMatcherProviderAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SendGridAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ServletWebServerFactoryAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SessionAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SolrAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SolrRepositoriesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SpringApplicationAdminJmxAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SpringDataWebAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>TaskExecutionAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>TaskSchedulingAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ThymeleafAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>TransactionAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>UserDetailsServiceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ValidationAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebClientAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebFluxAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebMvcAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebServiceTemplateAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebServicesAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebSocketMessagingAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebSocketReactiveAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebSocketServletAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>XADataSourceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
</table>

### **10.3.2 来自“spring-boot-actuator-autoconfigure”模块**

&emsp;&emsp;以下自动配置类来自spring-boot-actuator-autoconfigure模块：

<table>
	<tr>
		<th>Configuration Class</th>
		<th>Links</th>
	</tr>
	<tr>
		<td>AppOpticsMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>AtlasMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>AuditAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>AuditEventsEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>BeansEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CacheMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CachesEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CassandraReactiveHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CloudFoundryActuatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CompositeMeterRegistryAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ConditionsReportEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ConfigurationPropertiesReportEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>CouchbaseReactiveHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DataSourceHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DataSourcePoolMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DatadogMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DiskSpaceHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>DynatraceMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticSearchClientHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticSearchJestHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ElasticSearchRestHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>EndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>EnvironmentEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>FlywayEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>GangliaMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>GraphiteMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HealthEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HeapDumpWebEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HibernateMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HttpClientMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HttpTraceAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HttpTraceEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>HumioMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>InfluxDbHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>InfluxMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>InfoContributorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>InfoEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>IntegrationGraphEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JerseyServerMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JettyMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JmsHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JmxEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JmxMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JolokiaEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>JvmMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>KafkaMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>KairosMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LdapHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LiquibaseEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>Log4J2MetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LogFileWebEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LogbackMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>LoggersEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MailHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ManagementContextAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ManagementWebSecurityAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MappingsEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MetricsEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>MongoReactiveHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>Neo4jHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>NewRelicMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>PrometheusMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RabbitHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RabbitMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveCloudFoundryActuatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveManagementContextAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ReactiveManagementWebSecurityAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RedisHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>RedisReactiveHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ScheduledTasksEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ServletManagementContextAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SessionsEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ShutdownEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SignalFxMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SimpleMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SolrHealthIndicatorAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>StatsdMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>SystemMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>ThreadDumpEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>TomcatMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WavefrontMetricsExportAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebEndpointAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebFluxMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
	<tr>
		<td>WebMvcMetricsAutoConfiguration</td>
		<td>javadoc</td>
	</tr>
</table>

## **10.4 测试自动配置注解**

&emsp;&emsp;下表列出了各种@...Test注释，可用于测试应用程序的片段以及默认情况下导入的自动配置：

<table>
	<tr>
		<th>Test slice</th>
		<th>Imported auto-configuration</th>
	</tr>
	<tr>
		<td>@DataJdbcTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.data.jdbc.JdbcRepositoriesAutoConfiguration org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceTransactionManagerAutoConfiguration org.springframework.boot.autoconfigure.jdbc.JdbcTemplateAutoConfiguration org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration org.springframework.boot.autoconfigure.transaction.TransactionAutoConfiguration org.springframework.boot.test.autoconfigure.jdbc.TestDatabaseAutoConfiguration</td>
	</tr>
	<tr>
		<td>@DataJpaTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceTransactionManagerAutoConfiguration org.springframework.boot.autoconfigure.jdbc.JdbcTemplateAutoConfiguration org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaAutoConfiguration org.springframework.boot.autoconfigure.transaction.TransactionAutoConfiguration org.springframework.boot.test.autoconfigure.jdbc.TestDatabaseAutoConfiguration org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManagerAutoConfiguration</td>
	</tr>
	<tr>
		<td>@DataLdapTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.data.ldap.LdapRepositoriesAutoConfiguration org.springframework.boot.autoconfigure.ldap.LdapAutoConfiguration org.springframework.boot.autoconfigure.ldap.embedded.EmbeddedLdapAutoConfiguration</td>
	</tr>
	<tr>
		<td>@DataMongoTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.data.mongo.MongoDataAutoConfiguration org.springframework.boot.autoconfigure.data.mongo.MongoReactiveDataAutoConfiguration org.springframework.boot.autoconfigure.data.mongo.MongoReactiveRepositoriesAutoConfiguration org.springframework.boot.autoconfigure.data.mongo.MongoRepositoriesAutoConfiguration org.springframework.boot.autoconfigure.mongo.MongoAutoConfiguration org.springframework.boot.autoconfigure.mongo.MongoReactiveAutoConfiguration org.springframework.boot.autoconfigure.mongo.embedded.EmbeddedMongoAutoConfiguration</td>
	</tr>
	<tr>
		<td>@DataNeo4jTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.data.neo4j.Neo4jDataAutoConfiguration org.springframework.boot.autoconfigure.data.neo4j.Neo4jRepositoriesAutoConfiguration org.springframework.boot.autoconfigure.transaction.TransactionAutoConfiguration</td>
	</tr>
	<tr>
		<td>@DataRedisTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.data.redis.RedisAutoConfiguration org.springframework.boot.autoconfigure.data.redis.RedisRepositoriesAutoConfiguration</td>
	</tr>
	<tr>
		<td>@JdbcTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceTransactionManagerAutoConfiguration org.springframework.boot.autoconfigure.jdbc.JdbcTemplateAutoConfiguration org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration org.springframework.boot.autoconfigure.transaction.TransactionAutoConfiguration org.springframework.boot.test.autoconfigure.jdbc.TestDatabaseAutoConfiguration</td>
	</tr>
	<tr>
		<td>@JooqTest</td>
		<td>org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration org.springframework.boot.autoconfigure.jdbc.DataSourceTransactionManagerAutoConfiguration org.springframework.boot.autoconfigure.jooq.JooqAutoConfiguration org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration org.springframework.boot.autoconfigure.transaction.TransactionAutoConfiguration</td>
	</tr>
	<tr>
		<td>@JsonTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.gson.GsonAutoConfiguration org.springframework.boot.autoconfigure.jackson.JacksonAutoConfiguration org.springframework.boot.autoconfigure.jsonb.JsonbAutoConfiguration org.springframework.boot.test.autoconfigure.json.JsonTestersAutoConfiguration</td>
	</tr>
	<tr>
		<td>@RestClientTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.gson.GsonAutoConfiguration org.springframework.boot.autoconfigure.http.HttpMessageConvertersAutoConfiguration org.springframework.boot.autoconfigure.http.codec.CodecsAutoConfiguration org.springframework.boot.autoconfigure.jackson.JacksonAutoConfiguration org.springframework.boot.autoconfigure.jsonb.JsonbAutoConfiguration org.springframework.boot.autoconfigure.web.client.RestTemplateAutoConfiguration org.springframework.boot.autoconfigure.web.reactive.function.client.WebClientAutoConfiguration org.springframework.boot.test.autoconfigure.web.client.MockRestServiceServerAutoConfiguration org.springframework.boot.test.autoconfigure.web.client.WebClientRestTemplateAutoConfiguration</td>
	</tr>
	<tr>
		<td>@WebFluxTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.context.MessageSourceAutoConfiguration org.springframework.boot.autoconfigure.gson.GsonAutoConfiguration org.springframework.boot.autoconfigure.http.codec.CodecsAutoConfiguration org.springframework.boot.autoconfigure.jackson.JacksonAutoConfiguration org.springframework.boot.autoconfigure.jsonb.JsonbAutoConfiguration org.springframework.boot.autoconfigure.security.reactive.ReactiveSecurityAutoConfiguration org.springframework.boot.autoconfigure.security.reactive.ReactiveUserDetailsServiceAutoConfiguration org.springframework.boot.autoconfigure.validation.ValidationAutoConfiguration org.springframework.boot.autoconfigure.web.reactive.WebFluxAutoConfiguration org.springframework.boot.test.autoconfigure.web.reactive.WebTestClientAutoConfiguration</td>
	</tr>
	<tr>
		<td>@WebMvcTest</td>
		<td>org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration org.springframework.boot.autoconfigure.context.MessageSourceAutoConfiguration org.springframework.boot.autoconfigure.data.web.SpringDataWebAutoConfiguration org.springframework.boot.autoconfigure.freemarker.FreeMarkerAutoConfiguration org.springframework.boot.autoconfigure.groovy.template.GroovyTemplateAutoConfiguration org.springframework.boot.autoconfigure.gson.GsonAutoConfiguration org.springframework.boot.autoconfigure.hateoas.HypermediaAutoConfiguration org.springframework.boot.autoconfigure.http.HttpMessageConvertersAutoConfiguration org.springframework.boot.autoconfigure.jackson.JacksonAutoConfiguration org.springframework.boot.autoconfigure.jsonb.JsonbAutoConfiguration org.springframework.boot.autoconfigure.mustache.MustacheAutoConfiguration org.springframework.boot.autoconfigure.task.TaskExecutionAutoConfiguration org.springframework.boot.autoconfigure.thymeleaf.ThymeleafAutoConfiguration org.springframework.boot.autoconfigure.validation.ValidationAutoConfiguration org.springframework.boot.autoconfigure.web.servlet.WebMvcAutoConfiguration org.springframework.boot.autoconfigure.web.servlet.error.ErrorMvcAutoConfiguration org.springframework.boot.test.autoconfigure.web.servlet.MockMvcAutoConfiguration org.springframework.boot.test.autoconfigure.web.servlet.MockMvcSecurityAutoConfiguration org.springframework.boot.test.autoconfigure.web.servlet.MockMvcWebClientAutoConfiguration org.springframework.boot.test.autoconfigure.web.servlet.MockMvcWebDriverAutoConfiguration</td>
	</tr>
</table>

## **10.5 可执行的Jar格式**

&emsp;&emsp;spring-boot-loader模块允许Spring Boot支持可执行jar和war文件。 如果您使用Maven插件或Gradle插件，则会自动生成可执行jar，您通常不需要知道它们如何工作的详细信息。

&emsp;&emsp;如果您需要从不同的构建系统创建可执行jar，或者如果您只是对底层技术感到好奇，本节提供了一些背景知识。

### **10.5.1 嵌套的JAR**

&emsp;&emsp;Java没有提供任何标准方法来加载嵌套的jar文件（即jar文件本身包含在jar中）。 如果您需要分发可以从命令行运行而不解压缩的自包含应用程序，则可能会出现问题。

&emsp;&emsp;为了解决这个问题，许多开发人员使用“shaded” jar。 一个shaded的jar将所有jar包里的所有class别打包成一个“超级jar”。 shaded jar的问题在于很难看出哪些库实际上在您的应用程序中。 如果在多个jar中使用相同的文件名（但具有不同的内容），也可能会有问题。 Spring Boot采用不同的方法，让您直接嵌套jar。

### **10.5.1.1 可执行Jar文件结构**

&emsp;&emsp;Spring Boot Loader兼容的jar文件应按以下方式构建：

``` 
example.jar
 |
 +-META-INF
 |  +-MANIFEST.MF
 +-org
 |  +-springframework
 |     +-boot
 |        +-loader
 |           +-<spring boot loader classes>
 +-BOOT-INF
    +-classes
    |  +-mycompany
    |     +-project
    |        +-YourClasses.class
    +-lib
       +-dependency1.jar
       +-dependency2.jar
```

&emsp;&emsp;应用程序类应放在嵌套的BOOT-INF/classes目录中。 依赖项应放在嵌套的BOOT-INF/lib目录中。

### **10.5.1.2 可执行War文件结构**

&emsp;&emsp;应用程序类应放在嵌套的BOOT-INF/classes目录中。依赖项应放在嵌套的BOOT-INF/lib目录中。

``` 
example.war
 |
 +-META-INF
 |  +-MANIFEST.MF
 +-org
 |  +-springframework
 |     +-boot
 |        +-loader
 |           +-<spring boot loader classes>
 +-WEB-INF
    +-classes
    |  +-com
    |     +-mycompany
    |        +-project
    |           +-YourClasses.class
    +-lib
    |  +-dependency1.jar
    |  +-dependency2.jar
    +-lib-provided
       +-servlet-api.jar
       +-dependency3.jar
```

&emsp;&emsp;依赖项应放在嵌套的WEB-INF/lib目录中。 运行嵌入式时所需的任何依赖项，但在部署到传统Web容器时不需要，应放在WEB-INF/lib-provided中。

### **10.5.2 Spring Boot的“JarFile”类**

&emsp;&emsp;用于支持加载嵌套jar的核心类是org.springframework.boot.loader.jar.JarFile。 它允许您从标准jar文件或嵌套子jar数据中加载jar内容。 首次加载时，每个JarEntry的位置都映射到外部jar的物理文件偏移量，如以下示例所示：

``` 
myapp.jar
+-------------------+-------------------------+
| /BOOT-INF/classes | /BOOT-INF/lib/mylib.jar |
|+-----------------+||+-----------+----------+|
||     A.class      |||  B.class  |  C.class ||
|+-----------------+||+-----------+----------+|
+-------------------+-------------------------+
 ^                    ^           ^
 0063                 3452        3980
```

&emsp;&emsp;前面的例子显示了如何在位于0063的myapp.jar中的/BOOT-INF/classes中找到A.class。嵌套jar中的B.class实际上可以在位置3452的myapp.jar中找到，而C.class是 在第3980位。

&emsp;&emsp;有了这些信息，我们可以通过寻找外部jar的适当部分来加载特定的嵌套条目。 我们不需要解压缩归档文件，也不需要将所有条目数据读入内存。

**10.5.2.1 与标准Java“JarFile”的兼容性**

&emsp;&emsp;Spring Boot Loader力求与现有代码和库保持兼容。 org.springframework.boot.loader.jar.JarFile从java.util.jar.JarFile扩展而来，应该作为替代品。 getURL()方法返回一个URL，该URL打开与java.net.JarURLConnection兼容的连接，并可与Java的URLClassLoader一起使用。

### **10.5.3 启动可执行的Jars**

&emsp;&emsp;org.springframework.boot.loader.Launcher类是一个特殊的引导类，用作可执行jar的主入口点。 它是jar文件中的实际Main-Class，它用于设置适当的URLClassLoader并最终调用main()方法。

&emsp;&emsp;有三个启动器子类（JarLauncher，WarLauncher和PropertiesLauncher）。 它们的目的是从嵌套的jar文件或目录中的war文件加载资源（.class文件等）。（而不是在类路径上显式的那些）。 在JarLauncher和WarLauncher的情况下，嵌套路径是固定的。 JarLauncher在BOOT-INF/lib/中查找，WarLauncher在WEB-INF/lib/和WEB-INF/lib-provided/中查找。 如果您需要更多，可以在这些位置添加额外的jar。默认情况下，PropertiesLauncher在应用程序归档中的BOOT-INF/lib/中查找，但您可以通过在loader.properties中设置一个名为LOADER_PATH或loader.path的环境变量来添加其他位置（这是一个以逗号分隔的目录列表，归档 或档案馆内的目录）。

**10.5.3.1 启动器清单**

&emsp;&emsp;您需要将适当的Launcher指定为META-INF/MANIFEST.MF的Main-Class属性。 应在Start-Class属性中指定要启动的实际类（即包含main方法的类）。

&emsp;&emsp;以下示例显示了可执行jar文件的典型MANIFEST.MF：

``` 
Main-Class: org.springframework.boot.loader.JarLauncher
Start-Class: com.mycompany.project.MyApplication
```

&emsp;&emsp;对于war文件，它将如下：

``` 
Main-Class: org.springframework.boot.loader.WarLauncher
Start-Class: com.mycompany.project.MyApplication
```

>您无需在清单文件中指定Class-Path条目。 类路径是从嵌套的jar中推导出来的。

**10.5.3.2 Exploded Archives**

&emsp;&emsp;某些PaaS实现可能会选择在运行之前解压缩档案。 例如，Cloud Foundry以这种方式运营。 您可以通过启动相应的启动程序来运行解压缩的存档，如下所示：

``` 
$ unzip -q myapp.jar
$ java org.springframework.boot.loader.JarLauncher
```

### **10.5.4 PropertiesLauncher功能**

&emsp;&emsp;PropertiesLauncher具有一些可以使用外部属性（系统属性，环境变量，清单条目或loader.properties）启用的特殊功能。 下表描述了这些属性：

<table>
	<tr>
		<th>Key</th>
		<th>Purpose</th>
	</tr>
	<tr>
		<td>loader.path</td>
		<td>以逗号分隔的Classpath，例如lib，${HOME}/app/lib。 较早的条目优先，就像javac命令行上的常规-classpath一样。</td>
	</tr>
	<tr>
		<td>loader.home</td>
		<td>用于解析loader.path中的相对路径。 例如，给定loader.path = lib，然后\$ {loader.home}/ lib是一个类路径位置（以及该目录中的所有jar文件）。 此属性还用于查找loader.properties文件，如以下示例/opt/app中默认为\${user.dir}。</td>
	</tr>
	<tr>
		<td>loader.args</td>
		<td>main方法的默认参数（空格分隔）。</td>
	</tr>
	<tr>
		<td>loader.main</td>
		<td>要启动的主类的名称（例如，com.app.Application）。</td>
	</tr>
	<tr>
		<td>loader.config.name</td>
		<td>属性文件的名称（例如，启动程序）默认为加载程序。</td>
	</tr>
	<tr>
		<td>loader.config.location</td>
		<td>属性文件的路径（例如，classpath：loader.properties）。 它默认为loader.properties。</td>
	</tr>
	<tr>
		<td>loader.system</td>
		<td>布尔标志，指示应将所有属性添加到系统属性中默认为false。</td>
	</tr>
</table>

&emsp;&emsp;当指定为环境变量或清单条目时，应使用以下名称：

<table>
	<tr>
		<th>Key</th>
		<th>Manifest entry</th>
		<th>Environment variable</th>
	</tr>
	<tr>
		<td>loader.path</td>
		<td>Loader-Path</td>
		<td>LOADER_PATH</td>
	</tr>
	<tr>
		<td>loader.home</td>
		<td>Loader-Home</td>
		<td>LOADER_HOME</td>
	</tr>
	<tr>
		<td>loader.args</td>
		<td>Loader-Args</td>
		<td>LOADER_ARGS</td>
	</tr>
	<tr>
		<td>loader.main</td>
		<td>Start-Class</td>
		<td>LOADER_MAIN</td>
	</tr>
	<tr>
		<td>loader.config.location</td>
		<td>Loader-Config-Location</td>
		<td>LOADER_CONFIG_LOCATION</td>
	</tr>
	<tr>
		<td>loader.system</td>
		<td>Loader-System</td>
		<td>LOADER_SYSTEM</td>
	</tr>
</table>

>构建完整jar时，构建插件会自动将Main-Class属性移动到Start-Class。 如果使用它，请使用Main-Class属性指定要启动的类的名称，并省略Start-Class。

&emsp;&emsp;以下规则适用于使用PropertiesLauncher：

- 在loader.home中搜索loader.properties，然后在类路径的根目录中搜索，然后在类路径中搜索：/BOOT-INF/classes。 使用具有该名称的文件的第一个位置。
- 仅当未指定loader.config.location时，loader.home是附加属性文件的目录位置（覆盖缺省值）。
- loader.path可以包含目录（以递归方式扫描jar和zip文件），存档路径，存档中扫描jar文件的目录（例如，dependencies.jar!/lib）或通配符模式（用于默认的JVM行为）。 存档路径可以相对于loader.home或文件系统中的任何位置使用jar:file:prefix。
- loader.path（如果为空）默认为BOOT-INF/lib（表示本地目录或嵌套的目录，如果从存档运行）。 因此，当没有提供其他配置时，PropertiesLauncher的行为与JarLauncher相同。
- loader.path不能用于配置loader.properties的位置（用于搜索后者的类路径是启动PropertiesLauncher时的JVM类路径）。
- 占位符替换是在使用前从系统和环境变量以及属性文件本身在所有值上完成的
- 属性的搜索顺序（在多个位置查看的位置）是环境变量，系统属性，loader.properties，展开的归档清单和归档清单。

### **10.5.5 可执行的Jar限制**

&emsp;&emsp;使用Spring Boot Loader打包应用程序时，需要考虑以下限制：

- Zip条目压缩：必须使用ZipEntry.STORED方法保存嵌套jar的ZipEntry。 这是必需的，以便我们可以直接寻找嵌套jar中的单个内容。 嵌套的jar文件本身的内容仍然可以被压缩，外部jar中的任何其他条目也是如此。
- System classLoader：启动的应用程序在加载类时应使用Thread.getContextClassLoader()（默认情况下，大多数库和框架都这样做）。 尝试使用ClassLoader.getSystemClassLoader()加载嵌套的jar类失败。 java.util.Logging总是使用系统类加载器。 因此，您应该考虑使用不同的日志记录实现。

### **10.5.6 替代单一jar的方案**

&emsp;&emsp;如果前面的限制意味着您不能使用Spring Boot Loader，请考虑以下备选方案：

- Maven Shade Plugin
- JarClassLoader
- OneJar
- Gradle Shadow Plugin

## **10.6 依赖版本**

&emsp;&emsp;下表提供了Spring Boot在其CLI（命令行界面），Maven依赖关系管理和Gradle插件中提供的所有依赖关系版本的详细信息。 在未声明版本的情况下声明对其中一个工件的依赖关系时，将使用表中列出的版本。
[springboot依赖.xlsx](leanote://file/getAttach?fileId=5c965ae5f7c35f023f000001)
