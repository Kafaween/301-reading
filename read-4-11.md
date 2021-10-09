# Spring App Basics

To build application with **Spring MVS** we need:

* IDE

* jdk 1.8 or later

* Gradle 4+



## Create a Web Controller

* `@Controller` : it is an annotation used for marks a class as Controller and for handling the HTTP requests.

* `GetMapping` : it is an annotation used to map the class with the specified URL name. It ensures the specific HTTP GET requests are maped to specific method.

* `@RequestParam` : it is an annotation  used to read the form data and bind it automatically to the parameter present in the provided method.

## Run the Application

* `@SpringBootApplication` : it is convenience annotation that use to auto-configuration, component scan and be able to define extra configuration on application class.

* `@EnableAutoConfiguration` : Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.

* `@Configuration` : allow to register extra beans in the context or import additional configuration classes

## Build an executable JAR

We can run the application from command line with Gradle. We can also build a single executable JAR file that contains all the necessary dependencies, classes, and resources and run that. The advantages of building an executable jar aare makes it easy to ship, version, and deploy the service as an application throughout the development lifecycle, across different environments.

# Spring MVC and Thymeleaf

**Thymeleaf** is a Java library . It is template engine for processing and creating HTML, XML, JavaScript, CSS, and text.

1. **Spring model attributes**

Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes. The equivalent term in Thymeleaf language is context variables.

2. **Request parameters**

Easily accessed in Thymeleaf views. Request parameters are passed from the client to server.

3. **Session attributes**

Session attributes can be accessed by using the `session.` prefix or Or by using `#session`.

4. **ServletContext attributes**

To access ServletContext attributes in Thymeleaf you can use the `#servletContext.` prefix.

5. **Spring beans**

## Thymeleaf

- Thymeleaf is a popular server-side template engine for Java applications. You can easily integrate it into a Spring Boot project to develop web applications.

 - In a standard Spring MVC application, the controller classes are the ones that collect data from different sources like databases or RESTful APIs, and then select a view to render and return the HTML back to the user. They create a model map with data that is later converted into a Thymeleaf context object.

##### Spring Model Attributes
Spring model attributes are useful for transferring data from Spring controllers to Thymeleaf views. In Thymeleaf terminology, they are called context variables.

- There are several ways to add model attributes to a view in Spring MVC. The simplest way is to use the Model's addAttribute()

**Accessing the attributes depends upon where they were added. If the attributes were added to the ModelAndView object, they must be accessed throught "${modelAndView.model.xxxx}" where xxxx is the attribute name. If the attributes were added to Model object, they are accessible using just the attribute name itself "${attributeName}".**
