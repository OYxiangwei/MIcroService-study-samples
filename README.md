# MIcroService-study-samples
spring cloud 与 Docker 练习
1、构建一个用户服务提供者和一个电影服务消费者
2、为微服务集成spring boot Actuator,可以对我们的应用进行监控,（添加依赖-编写application.yml-测试actuator提供的端点）
3、编写服务发现服务eureka-server（引入 Netflix eureka server 依赖-启动类上添加@EnableEurekaServer-编写application.yml理解port、hostname、registerWithEureka、fetchRegistry、serviceUrl.defaultZone）
4、注册微服务至 Eureka Server（增加eureka依赖-启动类添加@EnableDiscoveryClient-编写application.yml新增 Eureka Client 相关配置eureka.client.serviceUrl.defaultZone、eureka.instance.prefer-ip-address）
5、Ribbon客户端负载均衡（Maven 引入依赖-只需在 RestTemplate 上添加@LoadBalanced 注解，即可让 RestTemplate整合Ribbon - Ribbon 会自动将目标服务名替换为该服务的IP和端口。）
6、Feign声明式REST调用（添加依赖openfeign-启动类上添加@EnableFeignClients-编写 Feign Client @FeignClient(name = "microservice-provider-user")）
7、Hystrix容错处理（引入依赖-在启动类上添加@EnableCircuitBreaker注解-在mapping上添加@HystrixCommand(fallbackMethod = "findByIdFallback")-编写fallbackMethod）
8、Zuul网关（添加依赖-在启动类上面添加注解@EnableZuulProxy-编写application.yml）
9、Spring Cloud Config配置管理（创建 Git 仓库在仓库根目录存放一些配置文件）
