# #Spring系学习笔记



## ##SpringFrameWork

##### 	特点：

​		<u>方便解耦，简化开发。方便继承各种优秀框架。降低java ee API的使用难度。方便程序的测试。支持AOP面向切面编程。声明式事务的支持。</u>

​		<u>可以满足一切企业级应用开发的需求。</u>

------

##### 	Spring FrameWork结构：

​		<u>Test：</u>测试模块，支持TestNG和Junit测试框架，以及一些基于Spring的测试功能。

​		<u>Core Container：</u>Spring核心容器模块，是其他模块的基础。包含：

​			Beans：Spring框架的基础支持部分，包含IOC（控制反转）以及DI（依赖注入）。

​			Core：Spring框架的核心底层部分，封装了Spring的底层实现，包括资源访问、类型转换和一些常用工具类。

​			Context：上下文支持部分。建立在Core和Beans的基础上，集成 Beans 模块功能并添加资源绑定、数据验证、国际化、Java EE 支持、容器生命周期、事件传播等。ApplicationContext 接口是上下文部分的焦点。

​			SpEL：表达式支持部分。

​		<u>AOP、Aspects、Instrumentation与Messaging：</u>建立在在Core Container 之上的模块。包含：

​				AOP：面向切面编程支持部分。

​				Aspect：提供与Aspect的集成的支持，Aspect是一个强大且成熟的AOP框架。

​				Instrumentation：类工具和类加载器实现的支持部分，可以在特定的应用中使用。

​				messaging：Spring 4.0 以后新增了对于消息（Spring-messaging）的支持部分，提供了对消息传递体系结构和协议的支持。

​		<u>Data Access/Intergration：</u>数据访问与集成模块。包含：

​				JDBC：提供了一个JDBC的样例模板，简化了JDBC的使用难度，同时附加了Spring事务管理的优势。

​				ORM：提供了对于“对象-关系”映射框架无缝集成的API，包括 JPA、JDO、Hibernate 和 MyBatis 等。可以使用Spring事务管理。

​				OXM：提供了对于Object/XML映射的抽象层实现，如 JAXB、Castor、XMLBeans、JiBX 和 XStream。用来将 Java 对象映射成 XML 数据，或者将XML 数据映射成 Java 对象。

​				JMS：指 Java 消息服务，提供一套 “消息生产者、消息消费者”模板用于更加简单的使用 JMS，JMS 用于用于在两个应用程序之间，或分布式系统中发送消息，进行异步通信。

​				Transaction：对于编程和声明式事务管理的支持部分。

​		<u>Web：</u>Web层模块。包含：

​				Web：对于基本的 Web 开发集成和支持的部分，例如多文件上传功能、使用的 Servlet 监听器的 IOC 容器初始化以及 Web 应用上下文。

​				Servlet：提供了一个 Spring MVC Web 框架实现。Spring MVC 框架提供了基于注解的请求资源注入、更简单的数据绑定、数据验证等及一套非常易用的 JSP 标签，完全无缝与 Spring 其他技术协作。

​				WebSocket ：提供了简单的接口，用户只要实现响应的接口就可以快速的搭建 WebSocket Server，从而实现双向通讯。

​				Portlet ：提供了在 Portlet 环境中使用 MVC 实现，类似 Web-Servlet 模块的功能。

------

##### 	开发环境及Spring FrameWork框架目录结构：

​		<u>Spring FrameWork。https://repo.spring.io/ui/native/release/org/springframework/spring/</u>

​			主要目录结构：

​				docs文件夹:Spring 的 API 文档和开发规范。

​				libs文件夹：开发需要的 jar 包和源码包。

​				schema文件夹：开发所需要的 schema 文件，在这些文件中定义了 Spring 相关配置文件的约束。

​		<u>JDK环境及JDK环境变量配置。</u>

​		<u>IDE配置。</u>

​		<u>Common Logging 是使用 Spring 的必要组件，用来处理日志信息。https://commons.apache.org/proper/commons-logging/download_logging.cgi</u>

​		<u>Spring FrameWork中的libs文件夹中的spring-core-x.x.xx.jar、spring-beans-x.x.xx.jar、spring-context-x.x.xx.jar、spring-expression-x.x.xx.jar以及Common Logging中的 commons-logging-x.x.jar五个jar包是Spring应用运行所需的依赖。需要复制到项目的lib目录，并发布到类路径中。</u>

------

##### 	创建Spring程序：

##### 				



​		

​		

​	

​		

​		

------

------



## ##SpringMVC

!!

------



------

------



## ##SpringBoot

!!

------



------

------



## ##SpringCloud

!!

------



------

------

