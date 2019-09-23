# Spring Boot

## 1 配置 maven

1.1 自己下载的 maven，目录为 D:/Maven/apache-maven-3.5.3

修改 `conf\setting.xml` 文件的 `profiles` 标签，添加如下代码：

```xml
<profile>
    <id>jdk-1.8</id>
    <activation>
        <activeByDefault>true</activeByDefault>
        <jdk>1.8</jdk>
    </activation>
    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
        <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
    </properties>
</profile>
```

1.2 设置 IDEA 使用自己配置的 maven（三个地方）

菜单找到 setting - Build,Excution,Deployment - Build Tools - Maven

+ Maven home directory，设置为 D:/Maven/apache-maven-3.5.3
+ User setting file，勾选上 Override，设置为 D:\Maven\apache-maven-3.5.3\conf\settings.xml
+ Local repository，勾选上 Override，设置为 D:\Maven\apache-maven-3.5.3\repository

## 2 Hello World （maven）

2.1 创建一个 maven 项目

2.2 导入 Spring boot 相关的依赖

```xml
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.1.6.RELEASE</version>
</parent>

<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
</dependencies>
```

2.3 创建一个主程序类 com.ylka.HelloWorldMainApplication, 注解1 `@SpringBootApplication`

```java
/*
* SpringBootApplication 标注一个主程序类，说明这是一个Spring Boot应用
*/
@SpringBootApplication
public class HelloWorldMainApplication {
    public static void main(String[] args) {
        SpringApplication.run(HelloWorldMainApplication.class, args);
    }
}
```

2.4 创建 Controller.HelloController，
注解2 `@Controller`，
注解3 `@RequestMapping`，
注解4 `@ResponseBody`

```java
@Controller
public class HelloController {

    @ResponseBody   // body 返回
    @RequestMapping("/hello") // 接收 hello 请求，就是路由
    public String Hello(){
        return "Hello World!";
    }
}
```

## 3 部署

导入 maven 插件，修改 pom.xml

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

把应用程序打包成一个可执行的 jar 包，使用 java -jar 的命令执行。
