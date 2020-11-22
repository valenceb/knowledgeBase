# Swagger学习

官网：[API Documentation & Design Tools for Teams | Swagger](https://swagger.io/)

在项目使用Swagger需要Springbox

* Swagger2
* UI

## SpringBoot集成Swagger

1. 新建一个SpringBoot = Web项目

2. [Maven Repository: Springfox swaggger (mvnrepository.com)](https://mvnrepository.com/search?q=Springfox+swaggger)

3. 导入相关依赖

   ```
   <!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger2 -->
   <dependency>
       <groupId>io.springfox</groupId>
       <artifactId>springfox-swagger2</artifactId>
       <version>3.0.0</version>
   </dependency>
   <!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger-ui -->
   <dependency>
       <groupId>io.springfox</groupId>
       <artifactId>springfox-swagger-ui</artifactId>
       <version>3.0.0</version>
   </dependency>
   ```

4. 放到Pom.xml的Dependencies节点

5. 配置Swagger -> Config

   ``` java
   @Configuration
   @EnableSwagger2		//开启Swaagger2
   public class SwggerConfig {
    
   }
   ```
   
6. 测试运行：http://localhost:8080/swagger-ui.html

7. 