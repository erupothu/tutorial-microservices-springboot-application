# tutorial-microservices-springboot-application

## Basic Setup
#### spring-boot-starter-parent
#### spring-boot-starter-web
#### spring-boot-maven-plugin

## properties file
```
server.port=8081
spring.application.name=employee-service
spring.profiles.active=dev
```
## Crud operations
#### spring-boot-starter-data-jpa
#### com.h2database
#### postgresql
#### mysql-connector-java
```
application-dev.properties (h2)
application-qa.properties (mysql)
application-prod.properties (postgres)
```
## increase application memory
#### java app from command line
```
java -Xmx512m -Dspring.profiles.active=dev -jar app.jar
```
#### From maven
```
mvn spring-boot:run -Drun.jvmArguments="-Xmx512m" -Drun.profiles=dev
```
```xml
<plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
    <configuration>
        <jvmArguments>-Xmx512m</jvmArguments>
    </configuration>
</plugin>
```
#### From ENV variable:
```
export JAVA_OPTS="-Xmx1024m -Xms256m"
```
#### Test
``` java
public void printMemory() {
int mb = 1024 * 1024;
Runtime runtime = Runtime.getRuntime();
System.out.println("Used Memory:" + (runtime.totalMemory() - runtime.freeMemory()) / mb);
System.out.println("Free Memory:" + runtime.freeMemory() / mb);
System.out.println("Total Memory:" + runtime.totalMemory() / mb);
System.out.println("Max Memory:" + runtime.maxMemory() / mb);
}
```

## Auditing
## Exception Handling
## Log
## AOP
## Interceptors
## CORS
## DevTools
## Security
## Email Config
## cache
## Scheduling
## Session
## Actuator
## Unit Testing
## Deployment
