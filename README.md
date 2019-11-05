# MIcroService-study-samples
spring cloud 与 Docker 练习</br>
1、构建一个用户服务提供者和一个电影服务消费者<br>
2、为微服务集成spring boot Actuator,可以对我们的应用进行监控,（添加依赖-编写application.yml-测试actuator提供的端点）<br>
3、编写服务发现服务eureka-server（引入 Netflix eureka server 依赖-启动类上添加@EnableEurekaServer-编写application.yml理解port、hostname、registerWithEureka、fetchRegistry、serviceUrl.defaultZone）<br>
4、注册微服务至 Eureka Server（增加eureka依赖-启动类添加@EnableDiscoveryClient-编写application.yml新增 Eureka Client 相关配置eureka.client.serviceUrl.defaultZone、eureka.instance.prefer-ip-address）<br>
5、Ribbon客户端负载均衡（Maven 引入依赖-只需在 RestTemplate 上添加@LoadBalanced 注解，即可让 RestTemplate整合Ribbon - Ribbon 会自动将目标服务名替换为该服务的IP和端口。）<br>
6、Feign声明式REST调用（添加依赖openfeign-启动类上添加@EnableFeignClients-编写 Feign Client @FeignClient(name = "microservice-provider-user")）<br>
7、Hystrix容错处理（引入依赖-在启动类上添加@EnableCircuitBreaker注解-在mapping上添加@HystrixCommand(fallbackMethod = "findByIdFallback")-编写fallbackMethod）<br>
8、Zuul网关（添加依赖-在启动类上面添加注解@EnableZuulProxy-编写application.yml）<br>
9、Spring Cloud Config配置管理（创建Git仓库在仓库根目录存放一些配置文件-引入ConfigServer依赖-启动主类上添加注解@EnableConfigServer-编写application.yml-指定cloud.config.server.git.uri)（引入Config Client的依赖-在resources添加配置文件bootstrap.yml-演示类）<br>
10、Sleuth与Zipkin结合图形化展示追踪（引入Sleuth依赖-可以修改application.yml查看更多Sleuth相关的日志-将Sleuth采集到的数据发送给Zipkin服务端Zipkin 分析之后展示在界面上-添加依赖-编写application.yml-下载zipkin-server-2.12.9-exec.jar 运行java -jar 访问http://localhost:9411）<br>
11、Docker的常用命令docker search - docker pull -docker images-docker run-docker ps<br>
12、微服务运行在Docker上（Dockerfile及常用命令-引入打包Docker镜像的maven插件-项目根目录创建Dockerfile文件-服务打包成Jar包运行Docker构建镜像-run镜像-访问测试地址）<br>
13、Docker Compose编排微服务 （在项目根目录添加docker-compose.yml文件-maven 构建项目和 Docker 镜像-docker-compose up运行）<br>
14、Compose编排多个微服务（构建多个微服务镜像-编写docker-compose.yml文件通过depends_on和links的方式将三个服务关联-使用docker-compose up或者docker-compose stop启动或者关闭服务）<br>
15、Docker-Compose部署一个双节点的Eureka集群（修改application.yml来添加配置，让不同 Eureka 节点都互相知道对方-构建 Eureka 镜像-编写docker-compose.yml）<br>
