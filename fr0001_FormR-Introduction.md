<!-- ------------------------------------------------------------------------- -->

<div class="page-back disabled">

</div><div class="page-next">

[Setup Development Workstation - NEXT](/Setup/fr0101_Setup-Developer-Workstation.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->


## FormR Introduction

----
### Renaissance Developer 
----

- Shouldn't every computer developer understand the total picture? Whether your expertise is infrastucture, database or presentation, you can't go wrong with more knowlege about the other disciplines. 
- The goal of this FormR tutorial is to give you a step by step guide to building a complete environment with a secure server on the cloud that serves web pages that allow access to and manipulation of  data via the Internet.
----

### You can do this tutorial, if:
----

1. You have access to a Windows 10 or higher workstation.
2. You have zero knowlege about computing or you have substantial knowlege about it.
3. You want to spend under $30.
4. You want to say, "I have completed all the steps to create my own working secure database web server on the Internet" --- My URL is: formr-yourinitials-00.com

----
### Background for FormR
----

- FormR is based on development strategy called FormX that was used by the authors for more than 20 years in 25 applications for the US federal government. Each application required the team to manage the infrastructure, database server and web server. The Microsoft product suite included everything from Visual Interdev through .Net MVC. The team focus has always been on Rapid Application Develpment (RAD). 

----
### The FormR Tools and Technologies
----
#### FormR uses the popular tools and techniques as of 2021. The list contains:
<br/>

1. Ubuntu Server on the cloud.
2. Windows 10 development workstation.
3. VSCode development environment.
4. MySQL database. (M)
5. ExpressJS web server. (E)
6. React-Admin framework. (R)
7. NodeKS programming technology. (N)
8. Sequelize database access technology. (S)
&nbsp;  
- In keeping with "current-speak" we say that FormR uses a MERNS stack. 

----
### The FormR Flow
----
#### Developer Workstation
----
1. You will first create a development workstation.
2. You will test that all of your tools are working prperly.
3. You will clone the FormR github repository to your local workstation.
4. You will test FormR locally.
----
#### Cloud Server
----
1. You will create an Ubuntu server on the cloud. (Estimated cost $5/mo.)
2. You will harden your Ubuntu server to make it secure.
3. You will install and test web, application and database servers.
4. You will obtain a unique domain/URL (Estimated cost $20/yr.)
5. You will intall an SSL certificate and access you website from the Internet.
----
### The FormR Application Development Strategy
----
1. A NodeJS ExpressJS server will be used to receive API calls that use Sequelize to perform database tasks using the database server.  

2. A React-Admin client is used to provide authentication of  users and standard create, retrieve, update and delete (CRUD) functions for any database table. 

3. JWT and Axios are used for authentication. 

4. AdminLTE is used for the user interface (UI).

5. Formik and YUP for data forms.
<br/>

- The FormR coding philosophy leans more towards DAMP ("Descriptive and Meaningful Phases") and DRY ("Don't Repeat Yourself") more than  WET ("Write Every Time").
----
### The FormR Migration Strategy
----

- All coding will be done locally using VSCode
- Changes will be pushed to your own github repository.
- Changes to your code on your web server can be made by Bitvise or @@@@@@ robin

----
### Some Final Points
----

- The example database is the sample MySql World database.

- This documentation is writtem in Markdown and uses Docsify.

- Credit is given to many whose tutorials, videos and blogs have provided inspiration, information and insight into these topics. 

- We especially thank BezKoder, Ben Awad, Jared Palmer, Jason Watmore, 
GraspingTech, LifeWire, SQL-Hub, W3Schools,

<!-- ------------------------------------------------------------------------- -->

<div class="page-back disabled">


</div><div class="page-next">

[Setup Development Workstation - NEXT](/Setup/fr0101_Setup-Developer-Workstation.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

