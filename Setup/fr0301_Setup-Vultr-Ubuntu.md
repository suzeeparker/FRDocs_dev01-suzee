<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Clone FormR  ](/Setup/fr0103_Clone-FormR.md)
</div><div class="page-next">

[Harden Ubuntu - NEXT](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->

## Instructions for creating an Ubuntu server on Vultr

- In order to test our FormR apps on the Internet
 we will create an Ubuntu server on the cloud provider, Vultr.com. Vultr costs only $5 per month. 

### 1. Create New Ubuntu Instance
- Signin or create an account on vultr.com

- Deploy New Server 

![Vultr Deploy New Server](./images/fr0301-01_Vultr-Deploy-New-Server.png "Deploy New Server")

- Choose Server: Cloud Compute

![Vultr Cloud Compute](./images/fr0301-02_Vultr-Cloud-Compute.png "Cloud Compute")

- Server Location

![Vultr Server Location](./images/fr0301-03_Vultr-Server-Location.png "Server Location")

- Server Type: Ubuntu 18.04 x64 (We use this version for the FormR tutorial)

![Vultr Server Type](./images/fr0301-04_Vultr-Server-Type.png "Server Type")

- Server Size: 25GB SSD

![Vultr Server Size](./images/fr0301-05_Vultr-Server-Size.png "Server Size")

- Add SSH Key
    - Select your Vultr public key in C:\users\Local_Admin\\.ssh

![Vultr-Select-Key](./images/fr0301-06_Vultr-Select-Key.png "Vultr-Select-Key")

    - Open the file in Notepad and copy the key 

![Vultr-Copy-Key](./images/fr0301-06_Vultr-Copy-Key.png "Vultr-Copy-Key")

    - Paste the key value into the Vultr SSH Key box and give the key a name.

![Vultr-add-SSH-key-pasted](./images/fr0301-06_Vultr-add-SSH-key-pasted.png "Vultr-add-SSH-key-pasted")

- Server Host Name and Label: FormRx-Vultr for both

![Vultr-Host-Label](./images/fr0301-07_Vultr-Host-Label.png "Vultr-Host-Label")


- Click Deploy Now

![Vultr Deploy Now](./images/fr0301-07_Vultr-Deploy-Now.png "Deploy Now")

- Installing

![Vultr Installing](./images/fr0301-08_Vultr-Installing.png "Installing")

### 2. Open Vultr VM Console to Log in

- Click on Products, then the Server Name i.e. FormRx-Vultr

![Vultr Open Console](./images/fr0301-09_Vultr-Open-Console.png "Open Console")

- Click the copy password icon

![Vultr Copy Password](./images/fr0301-10_Vultr-Copy-Password.png "Copy Password")


```
#### !! Remember to write your passwords in a safe place !!
```

- Click the View Console icon

![Vultr View Console](./images/fr0301-11_Vultr-View-Console.png "View Console")

- Click in the console window and then enter login: root and press enter

- Click the Send clipboard button and press enter.

![Vultr Login](./images/fr0301-12_Vultr-Login.png "Login")


- You will see the Welcome screen for Ubuntu and the command prompt:

    root@FormRx-Vultr:~#

![Vultr Welcome](./images/fr0301-13_Vultr-Welcome.png "Welcome")

<!-- ------------------------------------------------------------------------- -->

<div class="page-back">

[BACK - Clone FormR  ](/Setup/fr0103_Clone-FormR.md)
</div><div class="page-next">

[Harden Ubuntu - NEXT](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
</div>

<!-- ------------------------------------------------------------------------- -->

<!--  
### [BACK - Clone FormR ](/Setup/fr0103_Clone-FormR.md)
### [NEXT - HardenUbuntu](/Setup/fr0302_Setup-Hardening-Ubuntu.md)
 
<a class="page-back" href="Setup/fr0103_Clone-FormR.md">BACK - Clone FormR</a>
<a class="page-next" href="Setup/fr0302_Setup-Hardening-Ubuntu.md">Harden Ubuntu - NEXT</a>
 
<div class="page-back">### [BACK - Clone FormR ](/Setup/fr0103_Clone-FormR.md)</div>
<div class="page-next">### [NEXT - HardenUbuntu](/Setup/fr0302_Setup-Hardening-Ubuntu.md)</div>
-->

