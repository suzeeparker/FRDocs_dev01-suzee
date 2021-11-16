<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Harden Ubuntu     ](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div class="page-next">

[Install App Server - NEXT](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->

## Setup Instructions for the web server, NGINX, on Ubuntu

 ### 0. Restart your Vultr VM and Login

 - Login the your Vultr FormR1 console and click the Restart button

![Restart VM](./images/fr0300-01_restart-vm.png "Restart VM")

 - From your Vultr FormR1 console
 - Copy the root password
 - Click View Console button
 
![Restart VM](./images/fr0300-01_restart-vm1.png "Restart VM")

Login as root using the Send Clipboard button

![Restart VM](./images/fr0300-01_restart-vm2.png "Restart VM")


### 1. Install nginx
- Install
```
apt-get install nginx
```

![Install NGINX](./images/fr0303-01_Ubuntu-install-nginx.png "Install NGINX")

- Check
```
nginx -t
```

![Check NGINX](./images/fr0303-02_Ubuntu-check-nginx.png "Check NGINX")

- Enable nginx to auto start
```
systemctl enable nginx
```

![Enable NGINX](./images/fr0303-03_Ubuntu-enable-nginx.png "Enable NGINX")

- Allow http & https through firewall
```
ufw allow 'Nginx Full'
```

![Allow NGINX Ports](./images/fr0303-04_Ubuntu-allow-nginx-ports.png "Allow NGINX Ports")

- Test the default web site by IP. 

- Get the server IP from Vultr

![Get IP Address](./images/fr0303-05_Ubuntu-get-ip-address.png "Get IP Address")

- Browse to your server's IP address.

```
http://xxx.xxx.xxx.xxx
```

![Test Web Site](./images/fr0303-05_Ubuntu-test-web-site.png "Test Web Site")

### 2. Install Certbot

Certbot is used to create SSL certificates using LetsEncrypt.

```
apt-get install python-certbot-nginx
```

![Install Certbot](./images/fr0303-06_Ubuntu-install-certbot.png "Install Certbot")


### 3. Create webs directory

- Create a directory to hold your applications.
```
mkdir /webs
```

- Check that /webs directory was created
```
cd /
ls -ld /webs
```

![Create Webs Directory](./images/fr0303-07_Ubuntu-create-webs-directory.png "Create Webs Directory")

### 4. Create Snapshot of server in Vultr
```
Use label: FormR-Installed-Web-Server
```

![Take Snapshot](./images/fr0303-08_Ubuntu-take-snapshot.png "Take Snapshot")

<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Harden Ubuntu     ](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div class="page-next">

[Install App Server - NEXT](/Setup/fr0304_Setup-App-Server-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->

