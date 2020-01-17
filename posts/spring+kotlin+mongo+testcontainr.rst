.. title: spring+kotlin+mongo+testcontainr
.. slug: spring+kotlin+mongo+testcontainr
.. date: 2020-01-17 00:42:49 UTC+07:00
.. tags: testcontainer,spring,kotlin,mongo
.. category: 
.. link: 
.. description: 
.. type: text


**Introduction**


In this project we shall see how to use `testcontainer <https://www.testcontainers.org/>`_ to test the repository created in `mongodb <https://www.mongodb.com/>`_. As per their document Testcontainers is a Java library that supports JUnit tests, providing lightweight, throwaway instances of common databases, Selenium web browsers, or anything else that can run in a Docker container.

**Create sample project**


Go to the `spring initializer <http://start.spring.io/>`_ and create poject with language as kotlin and dependencies required are `webflux` & `reactive mongo db`


Here we shall create an Loan details application, where we will save loan detail.

**Create basic struction of the application**
 
Create a `document` class to save in mongo
{{% gist 538fe51780ebe36103dd5f395b5b561d %}}


Create an `repository` to access data from the DB.
{{% gist https://gist.github.com/434440bacb6ae4c8b65d81024274e08f %}}


Create an `service` class to access the loan details.
{{% gist https://gist.github.com/e0970e10dfc16f24195a8f932537a0dc %}}


**Dependency for testcontainer**


We need following depencies to add testconainer in the appliation
{{% gist https://gist.github.com/9870bb368b01f5a7ae07148efd2276f8 %}}
That's all we need to start with testconatainer.


**Container Configuration**


1. Create an container class that extends Generic ccontainer to be used as mongo container
{{% gist https://gist.github.com/f4bc3ac99aa38cdfe130ff572c55f478 %}}


2. Create configuration for initialize mongo container as below 
{{% gist https://gist.github.com/6c1ace895b9b7e1cdf18c3370192336f %}}


The code is very simple and self explenetry. On ``line#3`` we specify the image that we want to use for testing. I am here using ``mongo:4.2.0-rc2-bionic`` you can use same vertion as you are using onproduction. on ``line#5-6`` create mongo container and starting it. on ``line#9-11`` specify the test property values for the mongo database.


**Create first test case**


Let's create our first test case as below 
{{% gist https://gist.github.com/a9bd4b673a792f94ca426d1ad988d981 %}}

Here we test the data can be saved in the mongo db.To use mongo container we spcify the initializer class using the annotation ``@ContextConfiguratin`` at ``line#3``.


**Repository**


TODO: create repository and link here


