<!-- ------------------------------------------------------------------------- -->

<div class="page-back disabled">

</div><div class="page-next">

[Workstation - NEXT](/Setup/fr0101_Setup-Developer-Workstation.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

----
### FormR - The Renaissance Developer 
----

- Shouldn't every computer professional understand the total picture? Whether your expertise is infrastructure, database, presentation or project management, you can't go wrong with more knowledge about the other disciplines. 
- The goal of this FormR tutorial is to give you a step by step guide to building a complete environment for a secure server on the cloud serving web pages that access and manipulate data via the Internet.
----

#### You can do this tutorial:
----

1. If you have access to a Windows 10 or higher workstation.
2. If you have zero knowledge about computing.
3. If you have substantial knowledge about it.
4. If you want to spend under $30.
5. If you want to boast:  "I have completed all the steps to build my own live and secure web database server on the Internet" 

----
Your URL would be: formr-yourinitials-00.com

<br/>

![Your FormR Website](/images/fr0001-01_FormR.png "Your FormR Website")

and it's very secure

<br/>

![Your FormR Secure](/images/fr0001-01_FormR1.png "Your FormR Secure")

----
### Background for FormR
----

- FormR is based on development strategy called FormX that was used by the authors for more than 20 years in 30 applications for the US federal government. The now retired URL was FIDO.gov -- Federal Interagency Databases Online. Each application required the team to manage the infrastructure, database server, web server and web pages. The Microsoft product suite included everything from Visual Interdev through .Net MVC, Windows Server and SQL server. The team was and always has been focused on Rapid Application Development (RAD). 

- [Visit the FIDO.gov applications here](http://web.archive.org/web/20130825012943/http://www.fido.gov)

----
### How is this FormR tutorial funded
----
- We are funded by donations from you. If you find this tutorial valuable, then please donate $5, $10 or $20 via Zelle at your bank. Send to 8020data@gmail.com. Thank you! This helps us keep FormR updated.

- [Zelle Information](https://zellepay.com)
----
### The FormR Tools and Technologies
----
- FormR uses the tools and techniques popular in 2021. The list contains:
<br/>

1. Ubuntu Server on the cloud.
2. Windows 10 development workstation.
3. VSCode development environment.
4. MySQL database. ---------------------------------- (M)
5. ExpressJS web server. ---------------------------- (E)
6. React-Admin framework. ----------------------- (R)
7. NodeKS programming technology. -------- (N)
8. Sequelize database access technology.
9. Bitvise ssh client for cloud server access
10. MySQL Workbench for database access
<br/><br/>
- In keeping with "current-speak" we say that FormR uses a MERN stack. 

----
### The FormR Flow
----
#### Build a Developer Workstation
----
1. You will first create a development workstation.
2. You will test that all of your tools are working properly.
3. You will clone the FormR github repository to your local workstation.
4. You will test FormR locally.
----
#### Build a secure Cloud Server
----
1. You will create an Ubuntu server on the cloud. (Estimated cost $5/mo.)
2. You will harden your Ubuntu server to make it secure.
3. You will install and test web, application and database servers.
4. You will obtain a unique domain/URL (Estimated cost $20/yr.)
5. You will intall and test an SSL certificate and access your website from the Internet.
----
### The FormR Application Development Strategy
----

![FormR Stack Diagram](/images/fr0001-01_FormR-Stack-Diagram.png "FormR Stack Diagram")

1. A NodeJS ExpressJS server will be used to receive API calls that use Sequelize to perform database tasks using the database server.  

2. A React-Admin client is used to provide authentication of  users and standard create, retrieve, update and delete (CRUD) functions for any database table. 

3. JWT and Axios are used for authentication. 

4. AdminLTE is used for the user interface (UI).

5. Formik and YUP for data forms.
<br/>

- Client-side

![FormR Front End Diagram](/images/fr0001-01_FormR-Front-End-Diagram.png "FormR Front End Diagram")

- Server-side

![FormR Back End Diagram](/images/fr0001-01_FormR-Back-End-Diagram.png "FormR Back End Diagram")


#### The FormR coding philosophy leans more towards DAMP ("Descriptive and Meaningful Phases") and DRY ("Don't Repeat Yourself") more than  WET ("Write Every Time").

#### We have chosen the most popular Javascript ES6 for this project. This allows the same programming language to be used in modern browsers, Node servers, scripting tools and Windows and Unix based operating systems.
----
### The FormR Migration Strategy
----

- All coding will be done locally using VSCode
- Changes will be pushed to your own github repository.
- Changes to your code on your web server will access the github repository.

----
### Some Final Points
----

- The example database is the sample MySql World database.

- This documentation is writtem in Markdown and uses Docsify.

- Credit is given to all whose tutorials, videos and blogs have provided inspiration, information and insight into these topics. 

- We especially thank BezKoder, Ben Awad, Jared Palmer, Jason Watmore, 
GraspingTech, LifeWire, SQL-Hub, W3Schools,

<!-- ------------------------------------------------------------------------- -->

<div class="page-back disabled">


</div><div class="page-next">

[Workstation - NEXT](/Setup/fr0101_Setup-Developer-Workstation.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

