<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Install App Server ](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div><div class="page-next">

[Install Website SSL - NEXT](/Setup/fr0306_Setup-Website-SSL-Ubuntu.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

## 2.5 Setup Instructions for Data server using MySQL on a Vultr Ubuntu VM #### [Purpose and Background](../Setup/purposes/pfr0305_Setup-Data-Server-Ubuntu.md)


----
### 1. Restart your Vultr VM and Login
----
1. Login the your Vultr FormR1 console and click the Restart button

![Restart VM](./images/fr0300-01_restart-vm.png "Restart VM")

2. From your Vultr FormR1 console
 
3. Copy the root password
 
4. Click View Console button
 
![Restart VM](./images/fr0300-01_restart-vm1.png "Restart VM")

5. Login as root using the Send Clipboard button

![Restart VM](./images/fr0300-01_restart-vm2.png "Restart VM")

----
### 2. Install MySQL from the Vultr FormR1 console
----
1. Install MySQL
```
apt-get install mysql-server
```

![Install MySQL](./images/fr0305-01_Ubuntu-install-mysql.png "Install MySQL")

2. Check installation
```
mysql --version
```

![Check MySQL](./images/fr0305-02_Ubuntu-check-mysql.png "Check MySQL")

----
### 3. Secure MySQL
----
1. Lock down MySQL - Running this script will ask you

```
mysql_secure_installation

      - Add VALIDATE PASSWORD PLUGIN: Yes
      - Enter a "password validation policy level": 2
      - Enter a password for the user, root, to login to MySQL: FormR!1234
      - Remove anonymous users? Yes
      - Disallow root login remotely? No (Yes on a production server)
      - Remove test database and access to it? No 
      - Reload privilege tables now? Yes
```

![Secure MySQL](./images/fr0305-03_Ubuntu-secure-mysql.png "Secure MySQL")

![Secure MySQL part 2](./images/fr0305-03_Ubuntu-secure-mysql2.png "Secure MySQL part 2")

2. Allow remote access to MySQL 

```
nano /etc/mysql/mysql.conf.d/mysqld.cnf

Change line:         bind-address = 127.0.0.1
to:                  bind-address = 0.0.0.0
```

![Mysql-setup-nano-bind-address](./images/fr0305-04_Ubuntu-nano-bind-address-mysql.png "Mysql-setup-nano-bind-address")

3. Save the file

4. Restart mysql and comfirm its running

```
systemctl restart mysql.service
netstat -tulnp | grep mysql
```

![Mysql-setup-allow-remote-access](./images/fr0305-05_Ubuntu-allow-remote-access-mysql.png "Mysql-setup-allow-remote-access")

5. Open firewall rule for port 3306
```
ufw allow 3306/tcp

ufw status   
```

![Mysql-setup-open-firewall-port-3360](./images/fr0305-06_Ubuntu-open-firewall-port-3360-mysql.png "Mysql-setup-open-firewall-port-3360")

6. Create and Grant Privileges to user account: nimdas with host %
(Note: root@localhost has all rights and nimdas@% will have all rights) 

7. From the Vultr console prompt enter:

```
mysql -p
```

8. Enter : the root password -> FormR!1234

```
password: FormR!1234

#### !! Remember to write your passwords in a safe place !!
```

9. Enter the following:

```
mysql> CREATE USER 'nimdas'@'%' IDENTIFIED WITH mysql_native_password BY 'FormR!1234';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'nimdas'@'%';
mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;
```
![Mysql-setup-create-admin](./images/fr0305-07_Ubuntu-create-admin-mysql.png "Mysql-setup-create-admin")

10. Exit mysql
```
mysql> \quit
```

![Mysql-quit-to-console](./images/fr0305-08_Ubuntu-quit-to-console-mysql.png "Mysql-quit-to-console")

11. Stop, Start and check status of MySQL
```
systemctl stop mysql
systemctl start mysql
systemctl status mysql.service
```

![Mysql-setup-check-status](./images/fr0305-09_Ubuntu-check-status-mysql.png "Mysql-setup-check-status")

----
### 4. Login as nimdas remotely from your local PC with MySQL Shell. --Don't save the password-- 
----
1. From Windows command prompt enter the following: (Use your Vultur server IP address)

![Mysql-setup-vultr-ip](./images/fr0305-09_Ubuntu-vultr-ip.png "Mysql-setup-vultr-ip")

```
mysqlsh /connect nimdas@xxx.xxx.xxx.xxx:3306
```
2. Check Version. From the mysql command prompt enter the following:

```
\sql SELECT VERSION();
```

![Mysql-setup-login-admin-mysqlsh-local](./images/fr0305-10_Ubuntu-login-admin-mysqlsh-local.png "Mysql-setup-login-admin-mysqlsh-local")
 
3. Exit mysqlsh. From the mysql command prompt enter the following:

```
\quit
```

----
### Congratulations! You have installed a Database server on your Ubuntu server.
----

<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Install App Server ](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div><div class="page-next">

[Install Website SSL - NEXT](/Setup/fr0306_Setup-Website-SSL-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->
