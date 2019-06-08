---
layout: default
title: Create Application
nav_order: 1
comments: true
parent: Spring Boot
---

## Create Spring Boot Application [->](https://docs.spring.io/spring-boot/docs/current/reference/html/getting-started-first-application.html){: .label .label-purple }

1. Create your Application
    * Use [Spring Initializr](https://start.spring.io/) to quickly create your application. In the page, you're allow to set the basic configuration.
    ![Spring Initializr Page](../../../assets/images/spring-initializr.png)

2. Add Controller
    * Add a HomeController and a RequestMapping method

    ```java
    @RestController
    @EnableAutoConfiguration
    public class HomeController {

    @GetMapping("/")
    String home() {
        return "Hello World!";
    }
    ```

3. Running the Sample
    * After running the follwing command, open the browser and go to 'localhost:8080', 'Hello World!' is printed in the page.

    ```sh
    mvn spring-boot:run
    ```

4. Creating an Executable Jar
    * Run the command line to get Executable jar in /target folder

    ```sh
    mvn package
    ```

    * To peek inside, `jar tvf` can be used

    ```sh
    jar tvf target/sample-0.0.1-SNAPSHOT.jar
    ```

5. Running the Jar
    * To run the jar application, use `java -jar` command

    ```bash
    java -jar target/sample-0.0.1-SNAPSHOT.jar 
    ```
    
