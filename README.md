# SpringBootAssignment-PatientRecords
  This is spring boot project for demonstrating REST Api. This provides functionality for CRUD operation on patient records and also support Authentication by using JWT.
  
# Libraries are being used by this project.
   1) spring-boot-starter-web.
        This is the basic library for spring boot project.It is used for building the web application, including RESTful applications using Spring MVC. It uses Tomcat as the               default embedded container.
  
   2) spring-boot-starter-data-jpa.
        For using JPA(Java Persistance Api) we have to include this library.Jpa is a specification for managing relational data in Java applications.It allows us to access and           persist data between Java object/ class and relational database.The implementations of JPA are many tools like Hibernate,Eclipse link and ibatis etc.But this library             includes hibernate as default Jpa vendor.
        
   3) spring-boot-starter-security.
        As the name suggest,it is used to enable security features in spring boot application. This enables all the requests except(/, /home) are required to authenticate first.
        We can configure it as per our requirement.
        
   4) spring-boot-starter-validation.
        this is used for Bean Validation works by defining constraints to the fields of a class by annotating them with certain annotations. Then, you pass an object of that class         into a Validator which checks whether the constraints are satisfied or not and provides the appropirate message. 
        
   5) mysql-connector-java.
        this library is used to connect java application to MySQL server and provides many usefull classes to interact with databases and tables, And performing operation on               tables and databases.
    
   6) jjwt.
        Used for enable JSON Web Tokens(Jwt) functionality for security purpose.
        
   7) springfox-swagger2.
        Swagger2 is an open source project used to generate the REST API documents for RESTful web services.If you want to know more than visit https://swagger.io/.
        "springfox-swagger-ui" this library provides a user interface to access our RESTful web services via the web browser.
        
# Features have been added in this project.

    1) Maven build tool.
        Maven is a powerful project management tool that is based on POM (project object model). It is used for projects build, dependency and documentation. It simplifies the           build process like ANT , Gradle etc.
        
    2) Swagger2
        Swagger is a set of rules (in other words, a specification) for a format describing REST APIs. It can be used to share documentation among product managers, testers and         developers, but can also be used by various tools to automate API-related processes.
    
    3) JSON Web Token.
        It is used For Authenticate every request. I have configred this by java class and harcode User credential as username is "blackpool" and password is "1234".
        If you want to perform CRUD operations in this project. Make first POST request of json object with body contains username="blackpool" and password="1234" then you will         get response with jwt=json_web_token.Copy this "Bearer json_web_token" in the  value of header of requests for performing CRUD operation with key as "Authorization"
        example:-  Key="Authorization" and  value="Bearer                   eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c".
        
        NOTE- keep only one space between Bearer and json_web_token.
        
# How to deploy spring boot application.

  STEP-1 we create sring boot application we get options to choose "Packaging = Jar" or "Packaging = War" then choose second option i.e "Packaging = "War",Because jar file is            used to run application without being deployed on any server and it use embedded tomact server.JAR file is not suitable to be deployed on Web Servers.
  
  STEP-2 In our main class which is annotated with @SpringBootApplication extend  the SpringBootServletInitializer class. Spring Boot Servlet Initializer class file allows                you to configure the application when it is launched by using Servlet Container. 
  
  STEP-3 we need to mention the main class that should start in the build file. For this purpose, we can use the following pieces of code in pom.xml file
         <start-class>com.tutorialspoint.demo.DemoApplication</start-class>
  
  STEP-4 we are going to create a war file use the command mvn clean install for packaging your application. Then, the WAR file will be created and you can find it in the                target directory.
  
  STEP-5 Deploy the WAR file under the webapps directory in tomcat and run tomcat server.
