# 01 Spring Boot 的简单配置和使用

## Spring Boot 简介

使用 Spring Boot 可以让我们快速创建一个基于 Spring 的项目，而让这个 Spring 项目跑起来我们只需要很少的配置就可以了。

## 创建 Spring Boot 项目

以IntelliJ IDEA为例，创建时选择 Spring Initializr，如下图：

![][1]

填写项目信息，如下图：

![][2]

勾选Web ，如下图：

![][3]

填写工程名字，点击 finish，如下图：

![][4]

项目创建成功之后，在项目的根目录下会有一个 artifactId+Application 命名规则的入口类，如下图：

![][5]

`SpringBoot0223Application`是我们整个项目的入口类，这个类有一个`@SpringBootApplication`注解，是整个`Spring Boot`的核心注解，它的目的就是开启`Spring Boot`的自动配置。我们在这个类上再添加一个`@RestController`注解，使之变为一个`Controller`，然后提供一个地址转换方法，代码如下：

```java
package com.nnngu.spring_boot_0223;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@SpringBootApplication
public class SpringBoot0223Application {

    public static void main(String[] args) {
        SpringApplication.run(SpringBoot0223Application.class, args);
    }

    @RequestMapping(value = "/", produces = "text/plain;charset=UTF-8")
    String index() {
        return "第一次使用 Spring Boot!";
    }
}

```

然后点击启动按钮运行，如下图：

![][6]

启动之后，在浏览器中访问 http://localhost:8080/ ，如下： 

![][7]











---

本文永久更新地址：[https://github.com/nnngu/LearningNotes/blob/master/Spring%20Boot/01%20Spring%20Boot%20%E7%9A%84%E7%AE%80%E5%8D%95%E9%85%8D%E7%BD%AE%E5%92%8C%E4%BD%BF%E7%94%A8.md](https://github.com/nnngu/LearningNotes/blob/master/Spring%20Boot/01%20Spring%20Boot%20%E7%9A%84%E7%AE%80%E5%8D%95%E9%85%8D%E7%BD%AE%E5%92%8C%E4%BD%BF%E7%94%A8.md)


  [1]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519348032608.jpg
  [2]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519348267498.jpg
  [3]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519348494431.jpg
  [4]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519348636641.jpg
  [5]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519348884713.jpg
  [6]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519350023181.jpg
  [7]: https://www.github.com/nnngu/FigureBed/raw/master/2018/2/23/1519350172148.jpg