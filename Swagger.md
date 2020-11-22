# Swagger学习

官网：[API Documentation & Design Tools for Teams | Swagger](https://swagger.io/)

在项目使用Swagger需要Springbox

* Swagger2
* UI

## SpringBoot集成Swagger

1. 新建一个Spring Initializer-> Web项目

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

5. 编写一个Hello World

   1. src/main/java/com/[projectName]/swagger/controller/HelloController

   2. ``` Java
      @RestContoller
      public class HelloController {
          @RequestMapping("/hello")
          public String hello(){
              return "hello";
          }
      }
      ```

   3. 

6. 配置Swagger -> src/main/java/com/[projectName]/swagger/config/SwaggerConfig.java

   ``` java
   @Configuration
   @EnableSwagger2		//开启Swaagger2
   public class SwggerConfig {
       //配置了Swagger的Docket的bean实例
       @Bean
       public Docket docket(){
           return new Docket(DocumentationType.SWAGGER_2)
               .apiInfo(apiInfo());
       }
       //配置Swagger信息=apiInfo
       private ApiInfo apiInfo{
           //作者信息
           Contact contact = new Contact(name:"Vance Bai", url:"https://你的URL",email:"valence.bai@qq.com");
           return new ApiInfo(
               title:"你自己的SwaggerAPI文档",
               description:"",
               version:"v1.0",
               termsofServiceUrl:"https://你的URL",
               contact,
               license:"Apache 2.0",
               licenseUrl:"http://www.apache.org/licenses/LICENSE-2.0",
               new ArrayList()
           );
       }
   }
   ```

7. 测试运行：http://localhost:8080/swagger-ui.html

8. 