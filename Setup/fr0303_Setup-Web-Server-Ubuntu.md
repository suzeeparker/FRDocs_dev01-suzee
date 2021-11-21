<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Harden Ubuntu     ](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div class="page-next">

[Install App Server - NEXT](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

## Setup Instructions for the web server, NGINX, on Ubuntu

 ### 1. Restart your Vultr VM and Login

 1. Login the your Vultr FormR1 console and click the Restart button

![Restart VM](./images/fr0300-01_restart-vm.png "Restart VM")

 2. From your Vultr FormR1 console
 
 3. Copy the root password
 
 4. Click View Console button
 
![Restart VM](./images/fr0300-01_restart-vm1.png "Restart VM")

5. Login as root using the Send Clipboard button

![Restart VM](./images/fr0300-01_restart-vm2.png "Restart VM")

### 2. Install nginx

1. Install

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

### 3. Install Certbot

1. Certbot is used to create SSL certificates using LetsEncrypt. Install:

```
apt-get install python-certbot-nginx
```

![Install Certbot](./images/fr0303-06_Ubuntu-install-certbot.png "Install Certbot")

### 4. Create webs directory

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

### 5. Create Snapshot of server in Vultr

1. Use label: FormR-Installed-Web-Server

![Take Snapshot](./images/fr0303-08_Ubuntu-take-snapshot.png "Take Snapshot")

----
### Congratulations! You have installed a Web server on your Ubuntu server.
----

<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Harden Ubuntu     ](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div class="page-next">

[Install App Server - NEXT](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->

