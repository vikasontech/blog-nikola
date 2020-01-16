.. title: Add swaggwer to the kotlin spring 
.. slug: add-swaggwer-to-the-kotlin-spring-boot-project
.. date: 2020-01-16 16:22:54 UTC+07:00
.. tags: swagger, kotlin, spring-boot
.. category: technical
.. link: 
.. description: Add swagger to the kotline spring boot project
.. type: text



**Introduction**

In this short article we shall see how to configure swagger with spring webflux project. We create a project on spring initializer and then shall configure swagger.


**Dependencies**


Create a project on the spring boot initializer page with dpendency as 'webflux' and language as 'java'
In order to work swagger with kotlin you need to add the following repositories in you pom.xml file.
{{%gist a5dd22e084c90f46189bd5fdff5b03c6  %}}
  
Since the swagger dipendency is avalialb in another repository you need to add that repository as well in you 'pom.xml' file as below-
{{%gist b53e428ae9ddfe5faeefe9882d36c89a %}}


**Setup swagger with kotlin**


Create a class called 'SwaggerCofig' this class is reponsible to configure Docket for our application as below 
{{%gist 7fa314501ad66bc46ad2a00c04d356ec %}}

at line no# 9 we set the path of the rest controllers, swagger will scan this package to pick the endpoints.


**Add Resource configuration**


Configure the resource cofniguration for swagger ui as below 
{{% gist 20b01be5adab3b901f1d9972e23e5b24 %}}

**Create a sample response object**

Create a simple `LoanDetailFacade` that will contains the details about the loan.
{{% gist 538fe51780ebe36103dd5f395b5b561d %}}


**Create rest controller**


It's same as we do in spring web create some endpoints as below 
{{% gist 9583ef4551ee379bc8f7a8f1e1fc2cb4 %}}

**Test Application**


To run the application use below commn
mvn spring-boot:run 

go to the url http://localhost:8080/swagger-ui.html

the swagger page should show like this
todo: add screen dump


**Repository**


the full source code is available here 
???



