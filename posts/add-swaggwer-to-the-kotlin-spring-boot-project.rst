.. title: Add swaggwer to the kotlin spring boot project
.. slug: add-swaggwer-to-the-kotlin-spring-boot-project
.. date: 2020-01-16 16:22:54 UTC+07:00
.. tags: swagger, kotlin, spring-boot
.. category: technical
.. link: 
.. description: Add swagger to the kotline spring boot project
.. type: text


This is a typical paragraph.  An indented literal block follows.

::

    for a in [5,4,3,2,1]:   # this is program code, shown as-is
        print a
    print "it's..."
    # a literal block continues until the indentation ends

This text has returned to the indentation of the first paragraph,
is outside of the literal block, and is therefore treated as an
ordinary paragraph.


``Introduction`` 

**Dependencies**


Create a project on the spring boot initializer page with dpendency as 'webflux' and language as 'java'
In order to work swagger with kotlin you need to add the following repositories in you pom.xml file.
{{%gist a5dd22e084c90f46189bd5fdff5b03c6  %}}
  
Since the swagger dipendency is avalialb in another repository you need to add that repository as well in you 'pom.xml' file as below-
{{%gist b53e428ae9ddfe5faeefe9882d36c89a %}}


``Setup swagger with kotlin``


Create a class called 'SwaggerCofig' this class is reponsible to configure Docket for our application as below 
{{%gist 7fa314501ad66bc46ad2a00c04d356ec %}}

at line no# 9 we set the path of the rest controllers, swagger will scan this package to pick the endpoints.



``Add Resource configuration``
Configure the resource cofniguration for swagger ui as below 
{{% gist 20b01be5adab3b901f1d9972e23e5b24 %}}

Create rest controller
It's same as we do in spring web create some endpoints as below 
{{% gist 9583ef4551ee379bc8f7a8f1e1fc2cb4 %}}

Test Application
to run the application use below commn
mvn spring-boot:run 

go to the url `http://localhost:8080/swagger-ui.html`

the swagger page should show like this
todo: add screen dump


Repository
the full source code is available here 



