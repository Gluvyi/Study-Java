<!-- vscode-markdown-toc -->
	* 1. [1、什么是 Spring Boot？](#SpringBoot)
	* 2. [2、Spring Boot 有哪些优点？](#SpringBoot-1)
	* 3. [3、Spring 和 SpringBoot 有什么不同？](#SpringSpringBoot)
	* 4. [4、如何重新加载 Spring Boot 上的更改，而无需重新启动服务器？](#SpringBoot-1)
	* 5. [5、Spring Boot 中的监视器是什么？](#SpringBoot-1)
	* 6. [6、如何在 Spring Boot 中禁用 Actuator 端点安全性？](#SpringBootActuator)
	* 7. [7、如何在自定义端口上运行 Spring Boot 应用程序？](#SpringBoot-1)
	* 8. [8、怎么使用 Maven 来构建一个 SpringBoot 程序？](#MavenSpringBoot)
	* 9. [9、如何实现 Spring Boot 应用程序的安全性？](#SpringBoot-1)
	* 10. [10、如何集成 Spring Boot 和 ActiveMQ？](#SpringBootActiveMQ)
	* 11. [11、如何使用 Spring Boot 实现分页和排序？](#SpringBoot-1)
	* 12. [12、如何使用 Spring Boot 实现异常处理？](#SpringBoot-1)
	* 13. [13、我们如何监视所有 Spring Boot 微服务？](#SpringBoot-1)
	* 14. [14、什么是 Swagger？你用 Spring Boot 实现了它吗？](#SwaggerSpringBoot)
	* 15. [15、SpringBoot starter 作用在什么地方？](#SpringBootstarter)
	* 16. [16、怎么禁用某些自动配置特性？](#)
	* 17. [17、怎么注册一个定制的自动化配置？](#-1)
	* 18. [18、当 bean 存在的时候怎么置后执行自动配置？](#bean)
	* 19. [19、怎么将 SpringBoot web 应用程序部署为 JAR 或 WAR 文件？](#SpringBootwebJARWAR)
	* 20. [20、怎么使用 SpringBoot 去执行命令行程序？](#SpringBoot-1)
	* 21. [21、有什么外部配置的可能来源？](#-1)
	* 22. [22、SpringBoot 支持松绑定代表什么？](#SpringBoot-1)
	* 23. [23、SpringBoot DevTools 的用途是什么？](#SpringBootDevTools)
	* 24. [24、怎么编写一个集成测试？](#-1)
	* 25. [25、SpringBoot的 Actuator 是做什么的？](#SpringBootActuator-1)
	* 26. [26、什么是 AOP？](#AOP)
	* 27. [27、什么是 Apache Kafka？](#ApacheKafka)
	* 28. [28、什么是 CSRF 攻击？](#CSRF)
	* 29. [29、什么是 WebSockets？](#WebSockets)
	* 30. [30、您使用了哪些 starter maven 依赖项？](#startermaven)
	* 31. [31、什么是 Spring Batch？](#SpringBatch)
	* 32. [32、什么是 FreeMarker 模板？](#FreeMarker)
	* 33. [33、什么是 Spring Profiles？](#SpringProfiles)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->
###  1. <a name='SpringBoot'></a>1、什么是 Spring Boot？
多年来，随着新功能的增加，spring 变得越来越复杂。访问spring官网页面，我们就会看到可以在我们的应用程序中使用的所有 Spring 项目的不同功能。如果必须启动一个新的 Spring 项目，我们必须添加构建路径或添加 Maven 依赖关系，配置应用程序服务器，添加 spring 配置。因此，开始一个新的 spring 项目需要很多努力，因为我们现在必须从头开始做所有事情。

Spring Boot 是解决这个问题的方法。Spring Boot 已经建立在现有 spring 框架之上。使用 spring 启动，我们避免了之前我们必须做的所有样板代码和配置。因此，Spring Boot 可以帮助我们以最少的工作量，更加健壮地使用现有的 Spring功能。

###  2. <a name='SpringBoot-1'></a>2、Spring Boot 有哪些优点？
Spring Boot 的优点有：

1、减少开发，测试时间和努力。

2、使用 JavaConfig 有助于避免使用 XML。

3、避免大量的 Maven 导入和各种版本冲突。

4、提供意见发展方法。

5、通过提供默认值快速开始开发。

6、没有单独的 Web 服务器需要。这意味着你不再需要启动 Tomcat，Glassfish或其他任何东西。

7、需要更少的配置 因为没有 web.xml 文件。只需添加用@ Configuration 注释的类，然后添加用@Bean 注释的方法，Spring 将自动加载对象并像以前一样对其进行管理。您甚至可以将@Autowired 添加到 bean 方法中，以使 Spring 自动装入需要的依赖关系中。

8、基于环境的配置 使用这些属性，您可以将您正在使用的环境传递到应用程序：-Dspring.profiles.active = {enviornment}。在加载主应用程序属性文件后，Spring 将在（application{environment} .properties）中加载后续的应用程序属性文件。

###  3. <a name='SpringSpringBoot'></a>3、Spring 和 SpringBoot 有什么不同？
Spring 框架提供多种特性使得 web 应用开发变得更简便，包括依赖注入、数据绑定、切面编程、数据存取等等。

随着时间推移，Spring 生态变得越来越复杂了，并且应用程序所必须的配置文件也令人觉得可怕。这就是 Spirng Boot 派上用场的地方了 – 它使得 Spring 的配置变得更轻而易举。

实际上，Spring 是 unopinionated（予以配置项多，倾向性弱） 的，Spring Boot 在平台和库的做法中更 opinionated ，使得我们更容易上手。

这里有两条 SpringBoot 带来的好处：

根据 classpath 中的 artifacts 的自动化配置应用程序
提供非功能性特性例如安全和健康检查给到生产环境中的应用程序
###  4. <a name='SpringBoot-1'></a>4、如何重新加载 Spring Boot 上的更改，而无需重新启动服务器？
这可以使用 DEV 工具来实现。通过这种依赖关系，您可以节省任何更改，嵌入式tomcat 将重新启动。Spring Boot 有一个开发工具（DevTools）模块，它有助于提高开发人员的生产力。Java 开发人员面临的一个主要挑战是将文件更改自动部署到服务器并自动重启服务器。开发人员可以重新加载 Spring Boot 上的更改，而无需重新启动服务器。这将消除每次手动部署更改的需要。Spring Boot 在发布它的第一个版本时没有这个功能。这是开发人员最需要的功能。DevTools 模块完全满足开发人员的需求。该模块将在生产环境中被禁用。它还提供 H2 数据库控制台以更好地测试应用程序。

<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-devtools</artifactId>
<optional>true</optional>

###  5. <a name='SpringBoot-1'></a>5、Spring Boot 中的监视器是什么？
Spring boot actuator 是 spring 启动框架中的重要功能之一。Spring boot 监视器可帮助您访问生产环境中正在运行的应用程序的当前状态。有几个指标必须在生产环境中进行检查和监控。即使一些外部应用程序可能正在使用这些服务来向相关人员触发警报消息。监视器模块公开了一组可直接作为 HTTP URL 访问的REST 端点来检查状态。

###  6. <a name='SpringBootActuator'></a>6、如何在 Spring Boot 中禁用 Actuator 端点安全性？
默认情况下，所有敏感的 HTTP 端点都是安全的，只有具有 ACTUATOR 角色的用户才能访问它们。安全性是使用标准的 HttpServletRequest.isUserInRole 方法实施的。 我们可以使用来禁用安全性。只有在执行机构端点在防火墙后访问时，才建议禁用安全性。

###  7. <a name='SpringBoot-1'></a>7、如何在自定义端口上运行 Spring Boot 应用程序？
为了在自定义端口上运行 Spring Boot 应用程序，您可以在application.properties 中指定端口。server.port = 8090

###  8. <a name='MavenSpringBoot'></a>8、怎么使用 Maven 来构建一个 SpringBoot 程序？
就像引入其他库一样，我们可以在 Maven 工程中加入 SpringBoot 依赖。然而，最好是从 spring-boot-starter-parent 项目中继承以及声明依赖到 Spring Boot starters。这样做可以使我们的项目可以重用 SpringBoot 的默认配置。

继承 spring-boot-starter-parent 项目依赖很简单 – 我们只需要在 pom.xml 中定义一个 parent 节点：

1 <parent>
2     <groupId>org.springframework.boot</groupId>
3     <artifactId>spring-boot-starter-parent</artifactId>
4     <version>2.1.1.RELEASE</version>
5 </parent>

我们可以在 Maven central 中找到 spring-boot-starter-parent 的最新版本。

使用 starter 父项目依赖很方便，但并非总是可行。例如，如果我们公司都要求项目继承标准 POM，我们就不能依赖 SpringBoot starter 了。

这种情况，我们可以通过对 POM 元素的依赖管理来处理：
 1 <dependencyManagement>
 2     <dependencies>
 3         <dependency>
 4             <groupId>org.springframework.boot</groupId>
 5             <artifactId>spring-boot-dependencies</artifactId>
 6             <version>2.1.1.RELEASE</version>
 7             <type>pom</type>
 8             <scope>import</scope>
 9         </dependency>
10     </dependencies>
11 </dependencyManagement>
最后，我们可以添加 SpringBoot starter 中一些依赖，然后我们就可以开始了。

###  9. <a name='SpringBoot-1'></a>9、如何实现 Spring Boot 应用程序的安全性？
为了实现 Spring Boot 的安全性，我们使用 spring-boot-starter-security 依赖项，并且必须添加安全配置。它只需要很少的代码。配置类将必须扩展WebSecurityConfigurerAdapter 并覆盖其方法。

###  10. <a name='SpringBootActiveMQ'></a>10、如何集成 Spring Boot 和 ActiveMQ？
对于集成 Spring Boot 和 ActiveMQ，我们使用依赖关系。 它只需要很少的配置，并且不需要样板代码。 

###  11. <a name='SpringBoot-1'></a>11、如何使用 Spring Boot 实现分页和排序？
使用 Spring Boot 实现分页非常简单。使用 Spring Data-JPA 可以实现将可分页的传递给存储库方法。

###  12. <a name='SpringBoot-1'></a>12、如何使用 Spring Boot 实现异常处理？
Spring 提供了一种使用 ControllerAdvice 处理异常的非常有用的方法。 我们通过实现一个 ControlerAdvice 类，来处理控制器类抛出的所有异常。

###  13. <a name='SpringBoot-1'></a>13、我们如何监视所有 Spring Boot 微服务？
Spring Boot 提供监视器端点以监控各个微服务的度量。这些端点对于获取有关应用程序的信息（如它们是否已启动）以及它们的组件（如数据库等）是否正常运行很有帮助。但是，使用监视器的一个主要缺点或困难是，我们必须单独打开应用程序的知识点以了解其状态或健康状况。想象一下涉及 50 个应用程序的微服务，管理员将不得不击中所有 50 个应用程序的执行终端。为了帮助我们处理这种情况，我们将使用位于的开源项目。 它建立在 Spring Boot Actuator 之上，它提供了一个 Web UI，使我们能够可视化多个应用程序的度量。

###  14. <a name='SwaggerSpringBoot'></a>14、什么是 Swagger？你用 Spring Boot 实现了它吗？
Swagger 广泛用于可视化 API，使用 Swagger UI 为前端开发人员提供在线沙箱。Swagger 是用于生成 RESTful Web 服务的可视化表示的工具，规范和完整框架实现。它使文档能够以与服务器相同的速度更新。当通过 Swagger 正确定义时，消费者可以使用最少量的实现逻辑来理解远程服务并与其进行交互。因此，Swagger消除了调用服务时的猜测。

###  15. <a name='SpringBootstarter'></a>15、SpringBoot starter 作用在什么地方？
依赖管理是所有项目中至关重要的一部分。当一个项目变得相当复杂，管理依赖会成为一个噩梦，因为当中涉及太多 artifacts 了。

这时候 SpringBoot starter 就派上用处了。每一个 stater 都在扮演着提供我们所需的 Spring 特性的一站式商店角色。其他所需的依赖以一致的方式注入并且被管理。

所有的 starter 都归于 org.springframework.boot 组中，并且它们都以由 spring-boot-starter- 开头取名。这种命名方式使得我们更容易找到 starter 依赖，特别是当我们使用那些支持通过名字查找依赖的 IDE 当中。

在写这篇文章的时候，已经有超过50个 starter了，其中最常用的是：

spring-boot-starter：核心 starter，包括自动化配置支持，日志以及 YAML
spring-boot-starter-aop：Spring AOP 和 AspectJ 相关的切面编程 starter
spring-boot-starter-data-jpa：使用 Hibernate Spring Data JPA 的 starter
spring-boot-starter-jdbc：使用 HikariCP 连接池 JDBC 的 starter
spring-boot-starter-security：使用 Spring Security 的 starter
spring-boot-starter-test：SpringBoot 测试相关的 starter
spring-boot-starter-web：构建 restful、springMVC 的 web应用程序的 starter
###  16. <a name=''></a>16、怎么禁用某些自动配置特性？
如果我们想禁用某些自动配置特性，可以使用 @EnableAutoConfiguration 注解的 exclude 属性来指明。例如，下面的代码段是使 DataSourceAutoConfiguration 无效：

1 // other annotations
2 @EnableAutoConfiguration(exclude = DataSourceAutoConfiguration.class)
3 public class MyConfiguration { }

如果我们使用 @SpringBootApplication 注解 — 那个将 @EnableAutoConfiguration 作为元注解的项，来启用自动化配置，我们能够使用相同名字的属性来禁用自动化配置：

1 // other annotations
2 @SpringBootApplication(exclude = DataSourceAutoConfiguration.class)
3 public class MyConfiguration { }

我们也能够使用 spring.autoconfigure.exclude 环境属性来禁用自动化配置。application.properties 中的这项配置能够像以前那样做同样的事情：

spring.autoconfigure.exclude=org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration

###  17. <a name='-1'></a>17、怎么注册一个定制的自动化配置？
为了注册一个自动化配置类，我们必须在 META-INF/spring.factories 文件中的 EnableAutoConfiguration 键下列出它的全限定名：

org.springframework.boot.autoconfigure.EnableAutoConfiguration=com.baeldung.autoconfigure.CustomAutoConfiguration

如果我们使用 Maven 构建项目，这个文件需要放置在在 package 阶段被写入完成的 resources/META-INF 目录中。

###  18. <a name='bean'></a>18、当 bean 存在的时候怎么置后执行自动配置？
为了当 bean 已存在的时候通知自动配置类置后执行，我们可以使用 @ConditionalOnMissingBean 注解。这个注解中最值得注意的属性是：

value：被检查的 beans 的类型
name：被检查的 beans 的名字
当将 @Bean 修饰到方法时，目标类型默认为方法的返回类型：



1 @Configuration
2 public class CustomConfiguration {
3     @Bean
4     @ConditionalOnMissingBean
5     public CustomService service() { ... }
6 }


###  19. <a name='SpringBootwebJARWAR'></a>19、怎么将 SpringBoot web 应用程序部署为 JAR 或 WAR 文件？
通常，我们将 web 应用程序打包成 WAR 文件，然后将它部署到另外的服务器上。这样做使得我们能够在相同的服务器上处理多个项目。当 CPU 和内存有限的情况下，这是一种最好的方法来节省资源。

然而，事情发生了转变。现在的计算机硬件相比起来已经很便宜了，并且现在的注意力大多转移到服务器配置上。部署中对服务器配置的一个细小的失误都会导致无可预料的灾难发生。

Spring 通过提供插件来解决这个问题，也就是 spring-boot-maven-plugin 来打包 web 应用程序到一个额外的 JAR 文件当中。为了引入这个插件，只需要在 pom.xml 中添加一个 plugin 属性：

1 <plugin>
2     <groupId>org.springframework.boot</groupId>
3     <artifactId>spring-boot-maven-plugin</artifactId>
4 </plugin>

有了这个插件，我们会在执行 package 步骤后得到一个 JAR 包。这个 JAR 包包含所需的所有依赖以及一个嵌入的服务器。因此，我们不再需要担心去配置一个额外的服务器了。

我们能够通过运行一个普通的 JAR 包来启动应用程序。

注意一点，为了打包成 JAR 文件，pom.xml 中的 packgaing 属性必须定义为 jar：

<packaging>jar</packaging>

如果我们不定义这个元素，它的默认值也为 jar。

如果我们想构建一个 WAR 文件，将 packaging 元素修改为 war：

<packaging>war</packaging>

并且将容器依赖从打包文件中移除：

1 <dependency>
2     <groupId>org.springframework.boot</groupId>
3     <artifactId>spring-boot-starter-tomcat</artifactId>
4     <scope>provided</scope>
5 </dependency>

执行 Maven 的 package 步骤之后，我们得到一个可部署的 WAR 文件。

###  20. <a name='SpringBoot-1'></a>20、怎么使用 SpringBoot 去执行命令行程序？
像其他 Java 程序一样，一个 SpringBoot 命令行程序必须要有一个 main 方法。这个方法作为一个入口点，通过调用 SpringApplication#run 方法来驱动程序执行：

1 @SpringBootApplication
2 public class MyApplication {
3     public static void main(String[] args) {
4         SpringApplication.run(MyApplication.class);
5         // other statements
6     }
7 }

SpringApplication 类会启动一个 Spirng 容器以及自动化配置 beans。

要注意的是我们必须把一个配置类传递到 run 方法中作为首要配置资源。按照惯例，这个参数一般是入口类本身。

在调用 run 方法之后，我们可以像平常的程序一样执行其他语句。

###  21. <a name='-1'></a>21、有什么外部配置的可能来源？
SpringBoot 对外部配置提供了支持，允许我们在不同环境中运行相同的应用。我们可以使用 properties 文件、YAML 文件、环境变量、系统参数和命令行选项参数来声明配置属性。

然后我们可以通过 @Value 这个通过 @ConfigurationProperties 绑定的对象的注解或者实现 Enviroment 来访问这些属性。

以下是最常用的外部配置来源：

命令行属性：命令行选项参数是以双连字符（例如，=）开头的程序参数，例如 –server.port=8080。SpringBoot将所有参数转换为属性并且添加到环境属性当中。
应用属性：应用属性是指那些从 application.properties 文件或者其 YAML 副本中获得的属性。默认情况下，SpringBoot会从当前目录、classpath 根目录或者它们自身的 config 子目录下搜索该文件。
特定 profile 配置：特殊概要配置是从 application-{profile}.properties 文件或者自身的 YAML 副本。{profile} 占位符引用一个在用的 profile。这些文件与非特定配置文件位于相同的位置，并且优先于它们。
###  22. <a name='SpringBoot-1'></a>22、SpringBoot 支持松绑定代表什么？
SpringBoot中的松绑定适用于配置属性的类型安全绑定。使用松绑定，环境属性的键不需要与属性名完全匹配。这样就可以用驼峰式、短横线式、蛇形式或者下划线分割来命名。

例如，在一个有 @ConfigurationProperties 声明的 bean 类中带有一个名为 myProp 的属性，它可以绑定到以下任何一个参数中，myProp、 my-prop、my_prop 或者 MY_PROP。

###  23. <a name='SpringBootDevTools'></a>23、SpringBoot DevTools 的用途是什么？
SpringBoot 开发者工具，或者说 DevTools，是一系列可以让开发过程变得简便的工具。为了引入这些工具，我们只需要在 POM.xml 中添加如下依赖：

1 <dependency>
2     <groupId>org.springframework.boot</groupId>
3     <artifactId>spring-boot-devtools</artifactId>
4 </dependency>

spring-boot-devtools 模块在生产环境中是默认禁用的，archives 的 repackage 在这个模块中默认也被排除。因此，它不会给我们的生产环境带来任何开销。

通常来说，DevTools 应用属性适合于开发环境。这些属性禁用模板缓存，启用 web 组的调试日志记录等等。最后，我们可以在不设置任何属性的情况下进行合理的开发环境配置。

每当 classpath 上的文件发生更改时，使用 DevTools 的应用程序都会重新启动。这在开发中非常有用，因为它可以为修改提供快速的反馈。

默认情况下，像视图模板这样的静态资源修改后是不会被重启的。相反，资源的更改会触发浏览器刷新。注意，只有在浏览器中安装了 LiveReload 扩展并以与 DevTools 所包含的嵌入式 LiveReload 服务器交互时，才会发生。

###  24. <a name='-1'></a>24、怎么编写一个集成测试？
当我们使用 Spring 应用去跑一个集成测试时，我们需要一个 ApplicationContext。

为了使我们开发更简单，SpringBoot 为测试提供一个注解 – @SpringBootTest。这个注释由其 classes 属性指示的配置类创建一个 ApplicationContext。

如果没有配置 classes 属性，SpringBoot 将会搜索主配置类。搜索会从包含测试类的包开始直到找到一个使用 @SpringBootApplication 或者 @SpringBootConfiguration 的类为止。

注意如果使用 JUnit4，我们必须使用 @RunWith(SpringRunner.class) 来修饰这个测试类。

###  25. <a name='SpringBootActuator-1'></a>25、SpringBoot的 Actuator 是做什么的？
本质上，Actuator 通过启用 production-ready 功能使得 SpringBoot 应用程序变得更有生命力。这些功能允许我们对生产环境中的应用程序进行监视和管理。

集成 SpringBoot Actuator 到项目中非常简单。我们需要做的只是将 spring-boot-starter-actuator starter 引入到 POM.xml 文件当中：

1 <dependency>
2     <groupId>org.springframework.boot</groupId>
3     <artifactId>spring-boot-starter-actuator</artifactId>
4 </dependency>

SpringBoot Actuaor 可以使用 HTTP 或者 JMX endpoints来浏览操作信息。大多数应用程序都是用 HTTP，作为 endpoint 的标识以及使用 /actuator 前缀作为 URL路径。

这里有一些常用的内置 endpoints Actuator：

auditevents：查看 audit 事件信息
env：查看 环境变量
health：查看应用程序健康信息
httptrace：展示 HTTP 路径信息
info：展示 arbitrary 应用信息
metrics：展示 metrics 信息
loggers：显示并修改应用程序中日志器的配置
mappings：展示所有 @RequestMapping 路径信息
scheduledtasks：展示应用程序中的定时任务信息
threaddump：执行 Thread Dump
###  26. <a name='AOP'></a>26、什么是 AOP？
在软件开发过程中，跨越应用程序多个点的功能称为交叉问题。这些交叉问题与应用程序的主要业务逻辑不同。因此，将这些横切关注与业务逻辑分开是面向方面编程（AOP）的地方。

###  27. <a name='ApacheKafka'></a>27、什么是 Apache Kafka？
Apache Kafka 是一个分布式发布 - 订阅消息系统。它是一个可扩展的，容错的发布 - 订阅消息系统，它使我们能够构建分布式应用程序。这是一个 Apache 顶级项目。Kafka 适合离线和在线消息消费。

###  28. <a name='CSRF'></a>28、什么是 CSRF 攻击？
CSRF 代表跨站请求伪造。这是一种攻击，迫使最终用户在当前通过身份验证的Web 应用程序上执行不需要的操作。CSRF 攻击专门针对状态改变请求，而不是数据窃取，因为攻击者无法查看对伪造请求的响应。

###  29. <a name='WebSockets'></a>29、什么是 WebSockets？
WebSocket 是一种计算机通信协议，通过单个 TCP 连接提供全双工通信信道。

1、WebSocket 是双向的 -使用 WebSocket 客户端或服务器可以发起消息发送。

2、WebSocket 是全双工的 -客户端和服务器通信是相互独立的。

3、单个 TCP 连接 -初始连接使用 HTTP，然后将此连接升级到基于套接字的连接。然后这个单一连接用于所有未来的通信

4、Light -与 http 相比，WebSocket 消息数据交换要轻得多。

###  30. <a name='startermaven'></a>30、您使用了哪些 starter maven 依赖项？
使用了下面的一些依赖项

spring-boot-starter-activemq

spring-boot-starter-security

这有助于增加更少的依赖关系，并减少版本的冲突。

###  31. <a name='SpringBatch'></a>31、什么是 Spring Batch？
Spring Boot Batch 提供可重用的函数，这些函数在处理大量记录时非常重要，包括日志/跟踪，事务管理，作业处理统计信息，作业重新启动，跳过和资源管理。它还提供了更先进的技术服务和功能，通过优化和分区技术，可以实现极高批量和高性能批处理作业。简单以及复杂的大批量批处理作业可以高度可扩展的方式利用框架处理重要大量的信息。

###  32. <a name='FreeMarker'></a>32、什么是 FreeMarker 模板？
FreeMarker 是一个基于 Java 的模板引擎，最初专注于使用 MVC 软件架构进行动态网页生成。使用 Freemarker 的主要优点是表示层和业务层的完全分离。程序员可以处理应用程序代码，而设计人员可以处理 html 页面设计。最后使用freemarker 可以将这些结合起来，给出最终的输出页面。

###  33. <a name='SpringProfiles'></a>33、什么是 Spring Profiles？
Spring Profiles 允许用户根据配置文件（dev，test，prod 等）来注册 bean。因此，当应用程序在开发中运行时，只有某些 bean 可以加载，而在 PRODUCTION中，某些其他 bean 可以加载。假设我们的要求是 Swagger 文档仅适用于 QA 环境，并且禁用所有其他文档。这可以使用配置文件来完成。Spring Boot 使得使用配置文件非常简单。
