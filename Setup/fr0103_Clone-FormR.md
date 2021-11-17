
<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Simple Node Apps](/Setup/fr0102_Simple-Node-Apps.md)
</div><div class="page-next">

[Setup Vultr Ubuntu - NEXT](/Setup/fr0301_Setup-Vultr-Ubuntu.md)
</div><div style="margin-top:35px">&nbsp;</div> 

<!-- ------------------------------------------------------------------------- -->

## 1.3 Clone FormR

#### Change strategy

Master is currently on Robin's git repo and local repo as:  test1-master

Update strategy:

```
Robin changes on his local and pushes to his git repo.

Robin merges with his local 8020 test-master

Robin pushes to git 8020 test-master

Bruce/Ken git pulls from 8020 test-master to their local test-master
```

### 1. Cloning FormR repository

- Create in local repos

- Open Windows Command prompt


```
mkdir C:\repos\FormR

cd C:\repos\FormR
```
 
![FormR-Clone-01](images/fr0103-FormR-Clone-01.png "FormR-Clone-01")
 
```
git clone https://github.com/8020data/FormR_test-master.git test-master

cd test-master

dir
```

![FormR-Clone-02](images/fr0103-FormR-Clone-02.png "FormR-Clone-02")

- Open with VSCode

```
code formr_test-master.code-workspace
```
 
![FormR-Clone-03](images/fr0103-FormR-Clone-03.png "FormR-Clone-03")

### 2. Install Node modules

- Right click on the server folder and
- Click Open in Integrated Terminal, then 

![FormR-Clone-04](images/fr0103-FormR-Clone-04.png "FormR-Clone-04")

```
npm install
```

![FormR-Clone-05](images/fr0103-FormR-Clone-05.png "FormR-Clone-05")


![FormR-Clone-06](images/fr0103-FormR-Clone-06.png "FormR-Clone-06")

- Right click on the client folder and
- Click Open in Integrated Terminal, then 

![FormR-Clone-07](images/fr0103-FormR-Clone-07.png "FormR-Clone-07")

```
npm install 
```

![FormR-Clone-08](images/fr0103-FormR-Clone-08.png "FormR-Clone-08")

![FormR-Clone-09](images/fr0103-FormR-Clone-09.png "FormR-Clone-09")


### 3. Install RAuth and World databases in MySQL (Note that the World database has been modified so that all tables contain ID primary key fields)

- Open MySQL Workbench by clicking its icon in your task bar or by searching for Workbench in the Windows search, then

- Click the Local Instance under MySQL Connections

![FormR-Clone-10](images/fr0103-FormR-Clone-10.png "FormR-Clone-10")

- Run Script file

    - Click on Schemas to show your current databases

    - Click on the Open a script file in this editor


![FormR-Clone-11](images/fr0103-FormR-Clone-11.png "FormR-Clone-11")

- Navigate to and Open: 

```
 C:\repos\FormR\test-master\_3\SQLs\FormR_RAuth-DB-Create.
 sql

 then repeat these steps for:

 C:\repos\FormR\test-master\_3\SQLs\FormR_World-DB-Create.sql
 
```

![FormR-Clone-12](images/fr0103-FormR-Clone-12.png "FormR-Clone-12") 

![FormR-Clone-13](images/fr0103-FormR-Clone-13.png "FormR-Clone-13")

- Click the Execute icon

![FormR-Clone-14](images/fr0103-FormR-Clone-14.png "FormR-Clone-14")

- Click the refesh icon above the schema list

![FormR-Clone-15](images/fr0103-FormR-Clone-15.png "FormR-Clone-15")

![FormR-Clone-16](images/fr0103-FormR-Clone-16.png "FormR-Clone-16")

- IMPORTANT - Repeat these same steps for the World DB file

```
 C:\repos\FormR\test-master\_3\SQLs\FormR_World-DB-Create.sql
```

### 4. Make sure that your MySQL password for root  is set to:  FormR!1234

- Open MySQL Workbench by clicking its icon in your task bar or by searching for Workbench in the Windows search, then

- Click the Local Instance under MySQL Connections

![FormR-Clone-10](images/fr0103-FormR-Clone-10.png "FormR-Clone-10")

- Click the File tab, then click 'New Query Tab'

![FormR-Clone-17](images/fr0103-FormR-Clone-17.png "FormR-Clone-17") 

- Enter the following into the Query window, then

- Click the Execute icon

```
ALTER USER 'root'@'localhost' IDENTIFIED BY 'FormR!1234';
```

![FormR-Clone-18](images/fr0103-FormR-Clone-18.png "FormR-Clone-18")

![FormR-Clone-19](images/fr0103-FormR-Clone-19.png "FormR-Clone-19")

- Close workbench and reopen it, then

- Right click on the Local Instance, then

- Click Edit Connection, then

![FormR-Clone-20](images/fr0103-FormR-Clone-20.png "FormR-Clone-20")

- Click Store in Vault, then

- Enter the new password: FormR!1234 and click OK

![FormR-Clone-20a](images/fr0103-FormR-Clone-20a.png "FormR-Clone-20a")

- Click Test Connection then

- Click Close and then close Workbench

![FormR-Clone-20b](images/fr0103-FormR-Clone-20b.png "FormR-Clone-20b")

 ### 5. Run Client and Server applications

- Right click on the server/1s-world folder and
- Click Open in Integrated Terminal, then 

![FormR-Clone-21](images/fr0103-FormR-Clone-21.png "FormR-Clone-21") 

```
npm start
```

![FormR-Clone22](images/fr0103-FormR-Clone-22.png "FormR-Clone-22")

![FormR-Clone22a](images/fr0103-FormR-Clone-22a.png "FormR-Clone-22a")

- Right click on the client/1c-world folder and
- Click Open in Integrated Terminal, then 

(Note: The client application can take up to 15 minutes to start for the first time)

![FormR-Clone-23](images/fr0103-FormR-Clone-23.png "FormR-Clone-23")

```
npm start
```

![FormR-Clone-24](images/fr0103-FormR-Clone-24.png "FormR-Clone-24")

![FormR-Clone-24a](images/fr0103-FormR-Clone-24a.png "FormR-Clone-24a")

![FormR-Clone-24b](images/fr0103-FormR-Clone-24b.png "FormR-Clone-24b")

### 6. Test the applications

- Test the server, browse to

```
    localhost:50251
    localhost:50251/api/world/cities/test
    localhost:50251/api/world/cities/model
    localhost:50251/api/world/cities/
    localhost:50251/api/world/cities/1

    localhost:50251/api/world/countries/test
    localhost:50251/api/world/countries/model
    localhost:50251/api/world/countries/
    localhost:50251/api/world/countries/1
```

- Test the client, browse to

```
    localhost:50201
```

issues

1. test create, read, update and delete


<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Simple Node Apps](/Setup/fr0102_Simple-Node-Apps.md)
</div><div class="page-next">

[Setup Vultr Ubuntu - NEXT](/Setup/fr0301_Setup-Vultr-Ubuntu.md)
</div>

