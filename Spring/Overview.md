# Spring Project Overview

At first, look at the basic structure of the project:

![](pictures/Structure.png)

### Maven

The `mvnw`, `mvnw.cmd`, `pom.xml` files indicate that this project is a
**maven** project.

Maven is a tool that can manage the imported packages, i.e. dependencies of
the project. Mostly used for Java projects. All the dependencies are metioned in
the `pom.xml` file.

Like npm of Node.js, we can easily import packages through maven with command
line:

```
maven install ***
```

## Entrance

![](pictures/main.png)

The 'entrance' for java projects is the `main` method. For this, it's in
'DemoApplication.java'.

## Framework

![](pictures/overall.png)

![](pictures/framework.png)

### RESTful API

Locate resource by URL(Universal Resource Locator), then operate with the
resource. The types of operation are described by HTTP verbs: GET, POST, PUT, DELETE.

**Resource**: Data(picture, text, song, etc..)
**Representational**: How to represent the data.(JSON, XML, JPEG etc..)
**State Transfer**: Realized by HTTP verbs.

RESTful API uniformize the interface of CRUD(create, read, update, delete) operations
to make them be corresponding to HTTP methods: GET, POST, PUT, DELETE.

Important feature: **Stateless**: All the resource can be located by URL, and
this location has nothing to do with other resources.

RESTful API connects frontend with the services. In Spring it is also the controller.
Here is an example of controller in Spring.

![](pictures/controller.png)

We can see service layer is made to handle different service logics. In the past,
it also interacts with the backend database. However, this violets the system
design rule: **Single Responsibility**.

Thus we need another layer: DAO. DAO layer is made to interact with the backend
database. In Spring it is the **repository**.

### Spring Key Techs

![](pictures/keytechs.png)

**SpringBoot**: Initializer to quickly initialize and set up the project environment.

**SpringMVC** and **SpringCore**: Main packages used in the project. e.g. @GetMapping is
in SpringMVC, @Component, @Service is in SpringCore.

#### Spring Bean

Everytime we create a new object, it will be managed by the **Spring IoC Container**,
and it is called **beans**. A number of beans will be managed by **BeanFactory**, which
manage all these beans' life cycle.

If we manually use Java Garbage Collection, it is not good for memory use optimization.

#### IOC(Inverse of Control)

It's a key concept of Spring. At first we manually control the life cycle of objects, but
now we make **Bean** to manage their life cycle. This is the philosophy of IOC.

In the example, when initializing a new `CourseService` object, we use:

```java
@Autowired // IOC
    CourseService courseService; // Singleton
```

Instead of

```java
CourseService courseService = new CourseService();
```

This is a simple instance of IOC in Spring.

#### Dependency Injection

Also in the example, in the `CourseController` class, we need some dependencies of
another class `CourseService`. That means **Dependency Injection**.

#### Lombok

A convienient way to manage a class, here is an example:

![](pictures/lombok.png)

### Modal & DTO

Madals are the class which is **identical** to the database. That means, all the
fields should be the same as the attributes in the database.

DTO can be regarded as some lite version of madals. That means DTOs can remove
some attributes from the madals. Like a dto with studentId removed for security reasons.
