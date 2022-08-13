# JUNIT

```
What is Unit Testing ?

1.unit testing involves the testing of each unit or an individual component of the software application.
**unit** means unit maybe an individual **function** method, **procedure**, **module**, and **object**.
```

considering we are developing a Spring boot application and typically we create a three architecture in the spring boot application right, for example, controller layer, service layer and and repository layer. and repository layer will talk with the database and we write a lot of classes within these layers and we write a lot of methods within it classes.

As a developer, we have a write unit test to test the methods, classes just to make sure that whatever the code we have written is working as expected. Unit testing is done during the development of the application by the developers. Well, whenever we write a code while application development, we have to write a unit test to make sure that whatever the logic or the piece of code that we have written is working as expected.

### How to write a unit test in for our java Application ?

In Java, we have a de facto standard framework that is **Junit framework**, which we can use to write a unit test for a Java application. Well, most of the times one component will depend on other components.So while implementing units we should **mock** the dependencies with the desired behavior, using **mocking frameworks l**ike **Mockito**. Well, consider the example

This is a three-layer architecture in a Spring boot application, and we have an **Employee controller,Employee service** and **Employee repository.** Employee controller. It depends on employee service .Employee service depends on an employee a repository.

So whenever we write the unit test for employee controller then we have to mock the employee service object because the employee controller depends on the employee service right. Hence, in order to unit test only the employee controller component, we have to mock the employee service component, an employee controller. All right, in order to mock the dependencies like employee service in employee controller, we have to use a mocking frameworks.i.e, **Mockito framework.**

## Integration Testing

Well, as names suggest integration tests focus on integrating different layers of the application.

That means no mocking is involved.

For example,  three-layer architecture - **controller layer, service layer,** and **repository layer** and repository layer will talk with the database. And this is for employee management feature.

we have our employer controller, employee service, and employee repository. And basically **integration testing means we are going to test the integration of these different layers.**

We're not going to test a single or individual component.We're going to test the integration of these layers. this complete flow from the employee controller to the database.

And we're not going to mock any object while integration testing.

We have to deal with the database. And whenever we test employee controller, it should talk with a database through these layers - employee services and employee repository.

we're not going to mock employee service or employee a repository we are directly going to store the data into the database and we're going to directly retrieve data from the database.

So integration testing means basically will test the integration of different layers.

Consider one more example **User management** feature well while implementing user management feature, we create a user controller, user service, user repository right?

And in order to do the integration testing for this feature, we do that testing for all these layers.

We don't test only the single component like user controller. We test the integration of all these components.

So just remember, integration testing means testing the integration of different layers.

And in the case of integration testing, you don't have to use a mocking mechanism.we don't have to use the Mockito framework or any other mocking frameworks.

But in the case of unit testing, we have to use a Mockito all mocking framework to mock the dependent dependencies.

### Important best practices that we can follow while doing unit testing in Java

- It is a good idea to keep the test classes separate from the main source code, so they are developed, executed and maintained separately from the production code. that means main ka joh folder hai usme test ka kuch mat likho ….basically src —→ main folder hai same level ka test folder banao ur phir usme java folder banao .

![Screenshot 2022-08-13 at 9.06.47 PM.png](JUNIT%2011e0ecd5ef544f679dcf603db12dae19/Screenshot_2022-08-13_at_9.06.47_PM.png)

- we should have to create a similar package structure in the src/test directory for test classes this will improve the reliability and maintainability of the test code. For example.consider this as a spring boot application project structure and typically, we create different packages like the controller, model, repository, and service. so these are the packages we typically create in our spring boot application, and we keep the respective classes under these packages.In order to test these respective classes, we should have to create a similar package structure under src/test folder. look at here the example,in order to test a controller package related classes, we create a similar package here and we create test classes within this package.We created this classes.Similarly, if you want to test service package related classes, then you can create a similar package test folder like this and you can keep all your test classes within a service package.And also for a repository, you can create a similar package within a test per year, and you can keep all the test classes that you create to test the repository related classes.Well, having a package naming convention is pretty simple what you need to do is you need to create a similar packaging structure, for instance, within java we have our base package net.javaguides.springboot, within that controller right and in order to test these controller package related classes, you can create a similar package under test folder like this controller and then you can create a test class, for example, employee controllers test.All right, similarly, repository and service. whatever packaging naming convention that you follow here, that should be applicable to here as well in case of testing the respective classes.All right, great.Well, the next best practice is Unit test case naming.

![Screenshot 2022-08-13 at 9.15.58 PM.png](JUNIT%2011e0ecd5ef544f679dcf603db12dae19/Screenshot_2022-08-13_at_9.15.58_PM.png)

- Unit test case naming conventions. Well, this best practice is very very important.Whenever you create a unit test case, make sure that you will give a meaningful and descriptive name to your unit test.

the test names should be insightful, and users should understand the behavior and expectation of the test by just a glancing name itself.

So make sure that whenever you write a unit test, you should give them a meaningful and descriptive name to your unit test so that anybody can able to understand like what is the behavior and expectation of the test case by just looking into the name of the unit test case.  For example, if you follow the given/when/then BDD style naming convention for your unit test, then it should be readable and descriptive.

![Screenshot 2022-08-13 at 9.21.18 PM.png](JUNIT%2011e0ecd5ef544f679dcf603db12dae19/Screenshot_2022-08-13_at_9.21.18_PM.png)

So basically, we divide a unit test into three parts. First part is given second part is when and then.

- Next best practice is appropriate Assertions.Well, this is also very important best practice.So whenever we write a unit test, make sure that we use the appropriate assertions to test the actual with expected behavior.

 Always use the proper assertions to verify the expected versus actual results.We should use            various methods available in the Assert class of the JUnit framework or similar frameworks like AssertJ.AssertJ framework basically provides a assertThat API and this API is really, really useful and it has a capability to chain the method calls.

For example, here we are calling an assertThat method on top of it again, we are calling isNotNull method.So here basically, we are verifying like the expected versus actual results.

.

![Screenshot 2022-08-13 at 9.32.19 PM.png](JUNIT%2011e0ecd5ef544f679dcf603db12dae19/Screenshot_2022-08-13_at_9.32.19_PM.png)

- The next best practice is mock external services.Well, we just focus on, you know, writing the unit test to test a specific and smaller piece of code.but there is a chance that the code is dependent on some external services for some logic.For example, consider we are testing, we are unit testing employee controller it depends on external services like employee service and email service.So in this case, we have to mock the employee service and email service in the employee controller.So make sure that whenever you unit test any classes then you should mock the external services.And in order to mock the external services, we can use, frameworks like Mockito, EasyMock or JMockit for mocking external services.
- next Best practice is specific unit tests.

**Specific Unit Tests**

 Instead of adding multiple assertions to the same unit test,we create separate test cases. Of course,it's sometimes tempting to verify multiple scenarios in the it's a good idea to keep them separate. Then,in the case of test failures easier to determine which specific scenario failed and, likewise,simpler code. Therefore,always write a unit test to test a single specific scenario.

[About Spring Boot Starter Test dependency](JUNIT%2011e0ecd5ef544f679dcf603db12dae19/About%20Spring%20Boot%20Starter%20Test%20dependency%20af536b2ff1f9496eb89ab4867b5ddd05.md)