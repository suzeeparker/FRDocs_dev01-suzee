
<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Install Database Server](/Setup/fr0305_Setup-Data-Server-Ubuntu.md)
</div><div class="page-next disabled">

NEXT
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

## Setup Instructions for creating a simple website with SSL

### 1. Use Bitvise securely. Open Bitvise on your local workstation and login as nimda to the Ubuntu server

  1. Open Bitvise Client app 

 ![BitVise Open](./images/fr0306-01_Ubuntu-Bitvise-Open.png "BitVise Open")

  2. Click New Profile
 
![BitVise New Profile](./images/fr0306-01_Ubuntu-Bitvise-New-Profile.png "BitVise New Profile")

  3. Enter new profile name: 

```
FormR1-Vultr-nimda
```

![BitVise New Profile Name](./images/fr0306-01_Ubuntu-Bitvise-New-Profile-Name.png "BitVise New Profile Name")


  4. Enter:

```
  Host IP address: Your Vultr Ubuntu server IP 
```

 ![BitVise IP](./images/fr0306-01_Ubuntu-Bitvise-IP.png "BitVise IP")

  5. then enter:

```
  Port: 22
  Username: nimda
  Initial Method: password
  Password: FormR!1234
```

```
#### !! Remember to write your passwords in a safe place !!
```
![BitVise Initial Login](./images/fr0306-02_Ubuntu-Bitvise-Initial-Login.png "BitVise Initial Login")
  
  6. Click log In (You will see Warning message and then be logged in via password)

![BitVise Click Login](./images/fr0306-03_Ubuntu-Bitvise-Click-Login.png "BitVise Click Login")

![BitVise Click Login2](./images/fr0306-03_Ubuntu-Bitvise-Click-Login2.png "BitVise Click Login2")


  7. Click Save profile icon and save as FormR1-Vultr-nimda

![BitVise Save Profile](./images/fr0306-04_Ubuntu-Bitvise-Save-Profile.png "BitVise Save Profile")

![BitVise Save Profile2](./images/fr0306-04_Ubuntu-Bitvise-Save-Profile2.png "BitVise Save Profile2")

### 2. Configure Login via Public Key (SSH keys are more secure than passwords)

  1. Open Bitvise profile, Formr-Vultr-nimda, click Log in, then click New SFTP window icon

![BitVise New SFTP window](./images/fr0306-05_Ubuntu-Bitvise-New-SFTP-window.png "BitVise New SFTP window")

![BitVise New SFTP window2](./images/fr0306-05_Ubuntu-Bitvise-New-SFTP-window2.png "BitVise New SFTP window2")

    2. Right click in remote files pane (right)

    - create folder: /root/.ssh

![BitVise Create SSH Folder](./images/fr0306-05_Ubuntu-Bitvise-Create-SSH-Folder.png "BitVise Create SSH Folder")

![BitVise Create SSH Folder2](./images/fr0306-05_Ubuntu-Bitvise-Create-SSH-Folder2.png "BitVise Create SSH Folder2")

    - navigate to folder /root/.ssh and create file: authorized_keys

![BitVise Create File authorized_keys](./images/fr0306-05_Ubuntu-Bitvise-Create-File-authorized_keys.png "BitVise Create File authorized_keys")

![BitVise Create File authorized_keys2](./images/fr0306-05_Ubuntu-Bitvise-Create-File-authorized_keys2.png "BitVise Create File authorized_keys2") 

    3. In local files panes (left)
    - Navigate to C:/users/Local_Admin/.ssh and edit the public key (.pub) file for FormR_Vultr_nimda

    - Right click and select Edit

    (Note you may need to expand the name column to see the .pub extension)

![BitVise Copy public key](./images/fr0306-05_Ubuntu-Bitvise-Copy-public-key.png "BitVise Copy public key") 

    - Copy the one line of text. e.g.
    ssh-rsa AAAAB3NzaC1yc2...brucetroutman_v210511

![BitVise Copy public key2](./images/fr0306-05_Ubuntu-Bitvise-Copy-public-key2.png "BitVise Copy public key2")  


    4. In the Remote Files pane (right)
      - Edit the file /root/.ssh/authorized_keys

![BitVise Edit authorized_keys](./images/fr0306-05_Ubuntu-Bitvise-Edit-authorized_keys.png "BitVise Edit authorized_keys") 

      - Paste the public key text and Save

![BitVise Paste public key](./images/fr0306-05_Ubuntu-Bitvise-Paste-public-key.png "BitVise Paste public key")


      - close SFTP window

    5. From the Profile window
    - Logout 
    - Change Authentication, Initial method from 'password' to 'public key' and 
    - Click the Client Key Manager link in the middle of the form, then 
    - Click Import

![BitVise Client Key Manager](./images/fr0306-05_Ubuntu-Bitvise-Client-Key-Manager.png "BitVise Client Key Manager")

![BitVise Client Key Manager2](./images/fr0306-05_Ubuntu-Bitvise-Client-Key-Manager2.png "BitVise Client Key Manager2")

    - Navigate to Local-Admin/.ssh folder
    - Select 'All files' in the Bitvise Keypair drop down then 
    - Select the Private key file that matched the previously used Public key then 
    - Click Open
    - Click Import in the Import Client Key window

![BitVise Select Private Key](./images/fr0306-05_Ubuntu-Bitvise-Select-Private-Key.png "BitVise Select Private Key")

    - Click Import in the Import Client Key window

![BitVise Select Private Key2](./images/fr0306-05_Ubuntu-Bitvise-Select-Private-Key2.png "BitVise Select Private Key2")

    - Click to close Client Key Manager

![BitVise Select Private Key3](./images/fr0306-05_Ubuntu-Bitvise-Select-Private-Key3.png "BitVise Select Private Key3")

    - Select the just imported key (Profile 1) from the Client key drop down and 
    - Click Login (You will be logged in via public key)

![BitVise Select Client Key](./images/fr0306-05_Ubuntu-Bitvise-Select-Client-Key.png "BitVise Select Client Key")

#### IMPORTANT -- Click Save Profile !!!

![BitVise Save Profile](./images/fr0306-05_Ubuntu-Bitvise-Save-Profile.png "BitVise Save Profile")

### 3. Using Bitvice New Terminal console delete nginx default files 

  1. Open New Terminal console

![BitVise New Terminal](./images/fr0306-06_Ubuntu-Bitvise-new-terminal.png "BitVise New Terminal")

```
unlink /etc/nginx/sites-available/default

unlink /etc/nginx/sites-enabled/default
```

![BitVise Unlink nginx default](./images/fr0306-06_Ubuntu-Bitvise-Unlink-nginx-default.png "BitVise Unlink nginx default")

### 4. Clone simpleApp using git 
```
cd /webs
git clone https://github.com/8020data/simpleApp.git simpleApp
```
  1. Confim clone
```
cd simpleApp
ls -l
```
  2. Open port 5000 through the firewall
```
ufw allow 5000
```

![BitVise Clone simpleApp](./images/fr0306-07_Ubuntu-Bitvise-Clone-simpleApp.png "BitVise Clone simpleApp")

  3. Start app.js on the server
```
node app.js
```

![BitVise Run simpleApp](./images/fr0306-07_Ubuntu-Bitvise-Run-simpleApp.png "BitVise Run simpleApp")

  4. Use your local browser to test your server
  5. Get your IP address from the Bitvise console

![BitVise Browse simpleApp0](./images/fr0306-07_Ubuntu-Bitvise-Browse-simpleApp0.png "BitVise Browse simpleApp0")

```
<your server ip address here>:5000
```

![BitVise Browse simpleApp](./images/fr0306-07_Ubuntu-Bitvise-Browse-simpleApp.png "BitVise Browse simpleApp")

### 5. Setup pm2 to run website automatically

  1. Go to the Bitvise Terminal console
  2. Navigate to 

```
cd /webs/simpleApp
```

  3. Start app.js

```
pm2 start app.js 
```

![BitVise PM2 start](./images/fr0306-08_Ubuntu-Bitvise-PM2-start.png "BitVise PM2 start")

  4. Allow pm2 to start on boot up

```
pm2 startup systemd
```

![BitVise PM2 startup](./images/fr0306-08_Ubuntu-Bitvise-PM2-startup.png "BitVise PM2 startup")

  5. Save pm2 configuration, then Reboot

```
pm2 save --force

reboot
```

![BitVise PM2 save](./images/fr0306-08_Ubuntu-Bitvise-PM2-save.png "BitVise PM2 save")

  6. Test from local browser, 

```
<your server ip address here>:5000
```

![BitVise Browse simpleApp](./images/fr0306-07_Ubuntu-Bitvise-Browse-simpleApp.png "BitVise Browse simpleApp")

### 6. Setup nginx proxy 

  1. Copy simpleApp.conf file

```
cp /webs/simpleApp/etc/nginx/sites-available/simpleApp.conf /etc/nginx/sites-available/simpleApp.conf
```

  2. Create symbolic link to /etc/nginx/sites-enabled

```
ln -s /etc/nginx/sites-available/simpleApp.conf /etc/nginx/sites-enabled/simpleApp.conf
```

![BitVise nginx conf file](./images/fr0306-08_Ubuntu-Bitvise-nginx-conf-file.png "BitVise nginx conf file")

  3. Test and Reload nginx
```
nginx -t
```

```
systemctl reload nginx
```

![BitVise nginx reload](./images/fr0306-08_Ubuntu-Bitvise-nginx-reload.png "BitVise nginx reload")

### 7. Create a domain for public access to your server (Skip to step 11, if you don't wan't to purchase a domain.) 

#### Note: To install a Letsencrypt SSL certificate you will need a Domain Name. Our example creates a domain at GoDaddy.com.

####    There are many domain providers. You can expect to pay about $19/yr. Often there are sales promotions. Also all of them offer many extra services.

#### ***In our example we decline all extra services.*** 
#### (Note that the GoDaddy web site changes frequently, so the screen shots below may not match. The steps are repeatable. Contact GoDaddy support for more assistance.)
 
  1. Create a new Domain Name e.g. formr-cbt-00.com at GoDaddy.com. (cbt = my initials. Use yours or something else that is unique)

  2. Browse to

```
godaddy.com 
```

  3. Enter domain name

```
formr-<your initiatls>-00.com

e.g. formr-cbt-00.com
```

![Create Domain](./images/fr0306-09_Ubuntu-create-domain.png "Create Domain")

![Create Domain1](./images/fr0306-09_Ubuntu-create-domain1.png "Create Domain1")

  4. Follow the instructions to use or create your account and place your order

![Create Domain2](./images/fr0306-09_Ubuntu-create-domain2.png "Create Domain2")

![Create Domain3](./images/fr0306-09_Ubuntu-create-domain3.png "Create Domain3") 

![Create Domain3](./images/fr0306-09_Ubuntu-create-domain4.png "Create Domain3") 


### 8. Update your DNS record to point YourURL to your server IP address.

  1. Login to your GoDaddy.com account
  2. Click Your Account
  3. Click My Products
  4. Click YourURL e.g. formr-cbt-00.com

![BitVise Point DNS](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS.png "BitVise Point DNS")

  5. Click DNS dropdown
  6. Select Manage Zones

![BitVise Point DNS1](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS1.png "BitVise Point DNS1")

  7. Enter Your domain e.g. formr-cbt-00.com
  8. Click it

![BitVise Point DNS2](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS2.png "BitVise Point DNS2")

  9. Click the Edit icon for the A record

![BitVise Point DNS3](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS3.png "BitVise Point DNS3")

  10. Change the Points to = Parked to - the IP address of your Vultr server

  11. Get your IP address from the Bitvise console

![BitVise Browse simpleApp0](./images/fr0306-07_Ubuntu-Bitvise-Browse-simpleApp0.png "BitVise Browse simpleApp0")

  12. Change Parked

![BitVise Point DNS4](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS4.png "BitVise Point DNS4")
 
To Your server IP address and Save

![BitVise Point DNS5](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS5.png "BitVise Point DNS5")

![BitVise Point DNS6](./images/fr0306-09_Ubuntu-Bitvise-Point-DNS6.png "BitVise Point DN65")

  13. Wait 10-15 minutes then 
  14. Browse to your web site via http

```
http://formr-<yourinitials>-00com

e.g http://formr-cbt-00.com
```
@@@@@@ 01 pic 00
![BitVise Browse your website](./images/fr0306-10_Ubuntu-Bitvise-Browse-your-website.png "BitVise Browse your website")

### 9. Modify simpleApp.conf to use your new URL

  1. Open Bitvise 
  2. Load Profile: FormR1-Vultr-nimda.tlp
  3. Login
  4. From your Bitvise SFTP window navigate to 

```
/etc/nginx/sites-available/simpleApp.conf

```
  5. Click Edit 

![BitVise simpleApp1](./images/fr0306-10_Ubuntu-Bitvise-simpleApp1.png "BitVise simpleApp1")

  6. Change  yourURL  to  formr-yourInitials-00.com

![BitVise simpleApp2](./images/fr0306-10_Ubuntu-Bitvise-simpleApp2.png "BitVise simpleApp2")
 
![BitVise simpleApp3](./images/fr0306-10_Ubuntu-Bitvise-simpleApp3.png "BitVise simpleApp3")

  7. Save this file then Close the SFTP window

### 10. Add SSL certificate using Letsencrypt

  1. From your Bitvice New Terminal Console enter (You might use notpad to build yoururl)

```
certbot --nginx -d <yoururl>  

yoururl =  formr-<yourinitials>-00.com e.g. formr-cbt-00.com
```
  2. Enter A to Accept

![BitVise Add SSL](./images/fr0306-11_Ubuntu-Bitvise-add-ssl.png "BitVise Add SSL")

  3. Enter 2 to Redirect

![BitVise Add SSL2](./images/fr0306-11_Ubuntu-Bitvise-add-ssl2.png "BitVise Add SSL2")

  4. Test your SSL certificate by browsing to:

```
ssllabs.com/ssltest/analyze.html?d=<yoururl>

e.g. ssllabs.com/ssltest/analyze.html?d=formr-cbt.01.com
```

![BitVise Add SSL3](./images/fr0306-11_Ubuntu-Bitvise-add-ssl3.png "BitVise Add SSL3")

  5. Browse to your web via https

```
https://yoururl

e.g. https://formr-cbt-00.com

```

![BitVise Browse with https](./images/fr0306-12_Ubuntu-Bitvise-Browse-with-https.png "BitVise Browse with https")

### 11. Close Port 5000

  1. From the Bitvise Terminal Console enter:

```
   ufw status numbered 

   ufw delete 8

   ufw delete 4
```

![BitVise Close Port 5000](./images/fr0306-13_Ubuntu-Bitvise-Close-Port-5000.png "BitVise Close Port 5000")

<h3> Congratulations your Ubuntu server is secure and ready for action. </h3> 

<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Install Database Server](/Setup/fr0305_Setup-Data-Server-Ubuntu.md)
</div><div class="page-next disabled">

NEXT
</div>

<!-- ------------------------------------------------------------------------- -->
