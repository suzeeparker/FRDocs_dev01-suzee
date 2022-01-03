<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Harden Ubuntu     ](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div class="page-next">

[Install App Server - NEXT](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

## 2.3 Install Web Server (<20 mins)
#### [Purpose and Background](../Setup/purposes/pfr0303_Setup-Web-Server-Ubuntu.md)

#### Introduction


#### Important note about names, capitalization and pictures
- In this tutorial please be careful to use the Exact Spelling and Capitalization. You will be using Windows, Unix and GitBash command prompts. Improper captialization will cause commands to fail. Some examples are: Local_Admin, myProject, repos, remotes and .ssh.
- This documentation was produced during 2021. You will experience differences in some of the pictures due to the changes made over time by the developers of the softwares and web sites that are used.

----
 ### 1. Restart your Vultr VM and Login  (<5 mins)
----
 1. Login the your Vultr-FormR0 console and click the Restart button

![Restart VM](./images/fr0300-01_restart-vm.png "Restart VM")

 2. From your Vultr-FormR0 console
 
 3. Copy the root password
 
 4. Click View Console button
 
![Restart VM](./images/fr0300-01_restart-vm1.png "Restart VM")

5. Login as root using the Send Clipboard button

![Restart VM](./images/fr0300-01_restart-vm2.png "Restart VM")

----
### 2. Install nginx (<5 mins)

1. Install
----
```
apt-get install nginx
```

![Install NGINX](./images/fr0303-01_Ubuntu-install-nginx.png "Install NGINX")

2. Check
```
nginx -t
```

![Check NGINX](./images/fr0303-02_Ubuntu-check-nginx.png "Check NGINX")

3. Enable nginx to auto start

```
systemctl enable nginx
```

![Enable NGINX](./images/fr0303-03_Ubuntu-enable-nginx.png "Enable NGINX")

4. Allow http & https through firewall
```
ufw allow 'Nginx Full'
```

![Allow NGINX Ports](./images/fr0303-04_Ubuntu-allow-nginx-ports.png "Allow NGINX Ports")

5. Test the default web site by IP. 

6. Get the server IP from Vultr

![Get IP Address](./images/fr0303-05_Ubuntu-get-ip-address.png "Get IP Address")

7. Browse to your server's IP address.

```
http://xxx.xxx.xxx.xxx
```

![Test Web Site](./images/fr0303-05_Ubuntu-test-web-site.png "Test Web Site")

----
### 3. Install Certbot  (<5 mins)
----
1. Install  (Certbot is used to create SSL certificates using LetsEncrypt.)

```
apt-get install python-certbot-nginx
```

![Install Certbot](./images/fr0303-06_Ubuntu-install-certbot.png "Install Certbot")

----
### 4. Create webs directory (<5 mins)
----
1. Create a directory to hold your applications.

```
mkdir /webs
```

2. Check that /webs directory was created

```
cd /
ls -ld /webs
```

![Create Webs Directory](./images/fr0303-07_Ubuntu-create-webs-directory.png "Create Webs Directory")

----
#### Congratulations! You have installed a Web server on your Ubuntu server.
----

<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Harden Ubuntu     ](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div class="page-next">

[Install App Server - NEXT](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->

