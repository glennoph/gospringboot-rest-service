go springboot restful web service project

See https://spring.io/guides/gs/rest-service/

create hello world rest service with spring

# Restful Web Service projec

## Restful web service definition
> Representational state transfer (REST) is a software architectural style that defines a set of constraints to be used for creating Web services. ... In a RESTful Web service, requests made to a resource's URI will elicit a response with a payload formatted in HTML, XML, JSON, or some other format. (from wikipedia)

## Project goal
* accept http get requests:
`http://localhost:8080/greeting`
* respond with json greeting 
`{"id":1,"content":"Hello, World!"}`

## tools
* emacs
* openjdk 1.8
* maven and/or gradle
* import to intellij

## source files
* source dir - `src/main/java/hello`
* build.gradle - gradle build script 
* pom.xml - maven build script
* Greeting.java - pojo for id and greeting 
* GreetingController.java - resource controller 
  - handles http GET requests to `/greeting`
  - request parm: name has default World
  - returns Greeting object
  - Spring @RestController annotation - makes class controller and returns object
* Application.java - spring boot application class
  - configured by spring 
  
  
## build with gradle
* `gradle -version` # check version
* `gradle clean build` # build application
* `gradle bootRun` # run application
   * or `java -jar build/libs/*.jar` to execute
   * check that localhost:8080 is available

## build with maven
* `mvn validate` ## validate pom
* `mvn -version` ## get maven version
* `mvn clean package`   ## clean & package
* `mvn spring-boot:run` ## run application with spring boot 



## test with :
```
curl localhost:8080/greeting ## returns {"id":1,"content":"Hello, World!"}
curl localhost:8080/greeting?name=someone ## returns {"id":3,"content":"Hello, someone!"}
``` 

