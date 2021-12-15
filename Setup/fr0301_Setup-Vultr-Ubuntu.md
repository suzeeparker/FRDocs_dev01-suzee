<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Clone FormR  ](/Setup/fr0103_Clone-FormR.md)
</div><div class="page-next">

[Harden Ubuntu - NEXT](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div><div style="margin-top:35px">&nbsp;</div>

<!-- ------------------------------------------------------------------------- -->

## 2.1 Instructions for creating an Ubuntu server on Vultr [<img src="../assets/mdi-question-mark-circle-blue.svg" style="width:25px; block:inline;">](../Setup/purposes/pfr0301_Setup-Vultr-Ubuntu.md)


- In order to test our FormR apps on the Internet
 we will create an Ubuntu server on the cloud provider, Vultr.com. Vultr costs only $5 per month. 

----
### 1. Create New Ubuntu Instance
----
1. Signin or create an account on vultr.com

2. Deploy New Server 

![Vultr Deploy New Server](./images/fr0301-01_Vultr-Deploy-New-Server.png "Deploy New Server")

3. Choose Server: Cloud Compute

![Vultr Cloud Compute](./images/fr0301-02_Vultr-Cloud-Compute.png "Cloud Compute")

4. Server Location

![Vultr Server Location](./images/fr0301-03_Vultr-Server-Location.png "Server Location")

5. Server Type: Ubuntu 18.04 x64 (We use this version for the FormR tutorial)

![Vultr Server Type](./images/fr0301-04_Vultr-Server-Type.png "Server Type")

6. Server Size: 25GB SSD

![Vultr Server Size](./images/fr0301-05_Vultr-Server-Size.png "Server Size")

7. Add SSH Key
    - Select your Vultr public key in C:\users\Local_Admin\\.ssh

![Vultr-Select-Key](./images/fr0301-06_Vultr-Select-Key.png "Vultr-Select-Key")

    - Open the file in Notepad and copy the key 

![Vultr-Copy-Key](./images/fr0301-06_Vultr-Copy-Key.png "Vultr-Copy-Key")

    - Paste the key value into the Vultr SSH Key box and give the key a name.

![Vultr-add-SSH-key-pasted](./images/fr0301-06_Vultr-add-SSH-key-pasted.png "Vultr-add-SSH-key-pasted")

8. Server Host Name and Label: Vultr-FormR00 for both

![Vultr-Host-Label](./images/fr0301-07_Vultr-Host-Label.png "Vultr-Host-Label")


9. Click Deploy Now

![Vultr Deploy Now](./images/fr0301-07_Vultr-Deploy-Now.png "Deploy Now")

- Installing

![Vultr Installing](./images/fr0301-08_Vultr-Installing.png "Installing")

----
### 2. Open Vultr VM Console to Log in
----
1. Click on Products, then the Server Name i.e. Vultr-FormR00

![Vultr Open Console](./images/fr0301-09_Vultr-Open-Console.png "Open Console")

2. Click the copy password icon

![Vultr Copy Password](./images/fr0301-10_Vultr-Copy-Password.png "Copy Password")


```
#### !! Remember to write your passwords in a safe place !!
```

3. Click the View Console icon

![Vultr View Console](./images/fr0301-11_Vultr-View-Console.png "View Console")

4. Click in the console window and then enter login: root and press enter

5. Click the Send clipboard button and press enter.

![Vultr Login](./images/fr0301-12_Vultr-Login.png "Login")


6. You will see the Welcome screen for Ubuntu and the command prompt:

    root@Vultr-FormR00:~#

![Vultr Welcome](./images/fr0301-13_Vultr-Welcome.png "Welcome")

----
### Congratulations! You have created your Ubuntu server on Vultr.
----


<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Clone FormR  ](/Setup/fr0103_Clone-FormR.md)
</div><div class="page-next">

[Harden Ubuntu - NEXT](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div>



