##### SpringBoot启动流程

###### 核心分为2个步骤：

1. 创建SpringApplication对象；
2. 调用SpringApplication run方法实现启动，同时返回当前容器的上下文。

###### 详细流程：

1. 创建SpringApplication对象 SpringBoot容器初始化操作；
2. 获取当前应用启动类型； 原理：判断当前classpath是否有加载我们的servlet 类，返回servlet web启动方式。
3. setInitializers 读取SpringBoot包下面的META-INF/spring.factories 获取到对应ApplicationContextInitializer 装配到集合中。
4. serListeners 读取SpringBoot包下面的META-INF/spring.factories 获取到对应ApplicationListener 装配到集合中。
5. mainApplicationClass 获取当前运行的主函数。
6. 调用SpringApplication run方法实现启动
7. StopWatch stopWatch = new StopWatch（）；记录SpringBoot项目启动时间。
8. getRunListeners(args); 读取我们的META-INF/spring.factories 获取到对应的 SpringApplicationRunListeners 类型存入到集合中。
9. listeners.starting(); 循环调用监听starting方法
10. ConfigurableEnvironment environment = prepareEnvironment（listeners, applicationArguments）; 读取配置文件到SpringBoot容器中
11. Banner printedBanner = printBanner(environment); 打印SpringBoot Banner；
12. 创建SpringBoot 上下文 AnnotationConfigServletWebServerApplicationContext对象；
13. refreshContext(context);刷新我们上下文。
14. 开始创建tomcat 容器。
15. 开始加载SoringMVC
16. afterRefresh 定义一个空的模板给其他子类实现重写
17. listeners.started(context); 使用广播和回调机制通知监听器 SpringBoot 容器已启动成功；
18. 最后返回当前上下文

webApplicationType（启动类型）分为三种类型：

1. 响应式启动（spring5新特性）；
2. None 不会嵌入Web容器启动；
3. Servlet 基于Web容器启动