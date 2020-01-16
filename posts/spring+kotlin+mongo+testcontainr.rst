.. title: spring+kotlin+mongo+testcontainr
.. slug: spring+kotlin+mongo+testcontainr
.. date: 2020-01-17 00:42:49 UTC+07:00
.. tags: testcontainer,spring,kotlin,mongo
.. category: 
.. link: 
.. description: 
.. type: text


**Introduction**


In this project we shall see how to use `testcontainer <https://www.testcontainers.org/>`_ to test the repository created in `mongodb <https://www.mongodb.com/>`_

**Create sample project**


Go to the `spring initializer <http://start.spring.io/>`_ and create poject with language as kotlin and dependencies required are `webflux` & `reactive mongo db`


Here we shall create an Loan details application, where we will save and query loan detail.


for that we need to create a document class to save in mongo.
??? gist for the document class


Create an `repository` to access data from the DB.
??? gist for the repository class


Create an `service` class to access the loan details.
??? gist for the repository class


**Dependency for testcontainer**


We need following depencies to add testconainer in the appliation
{{% gist https://gist.github.com/9870bb368b01f5a7ae07148efd2276f8 %}}
That's all we need to start with testconatainer.


**Container Configuration**


1. Create an container class that extends Generic ccontainer to be used as mongo container
{{% gist https://gist.github.com/f4bc3ac99aa38cdfe130ff572c55f478 %}}


2. Create configuration for the mongo container as below 
{{% gist https://gist.github.com/6c1ace895b9b7e1cdf18c3370192336f %}}


TODO: add some description about the configuraion



**Create first test case**


Let's create our first test case as below 
{{% gist https://gist.github.com/a9bd4b673a792f94ca426d1ad988d981 %}}


TODO: add some description about the configuraion


**Repository**


TODO: create repository and link here


