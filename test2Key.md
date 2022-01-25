
# SSH Keys

<!-- ---------------------------------------------------------------------------- -->

### <u>SSH Key for One Remote Ubuntu Server</u>


1. Make a Private and Public Key pair of files

   keys  Make  Key  Robin.Mattern  Vultr-FormR0  nimda  ram doit

       ssh-keygen -t rsa -P '' -q -f "/c/Users/robin/.ssh/Robin.Mattern@Vultr-FormR0_nimda_ram_a210719_key" -C "Robin.Mattern@Vultr-FormR0_nimda_ram_a210719"

2. Show Key Files

   keys Show

       ls -l ~/.ssh/*_key*    # */


3. Set up an SSH Host Alias Name using a KeyFile

   keys  Set  Host  0  Vultr-FormR0:155.138.238.182  nimda  ram  doit

       nano ~/.ssh/config

          Host Vultr-FormR0-nimda-ram
            HostName       155.138.238.182
            IdentityFile   /C/Users/robin/.ssh/Robin.Mattern@Vultr-FormR0_nimda_ram_a210719_key
            IdentitiesOnly yes
            User           nimda
            Port           22
          # UpdatedOn      Mon Jul 19 2021 09:18:54 (Eastern Daylight Time)


4. Set up a SSH Host Alias using a Password

   keys  Set  Host  Vultr-FormR0:155.138.238.182  nimda  doit

       nano ~/.ssh/config

          Host Vultr-FormR0-nimda Vultr-FormR0-nimda-account
            HostName       155.138.238.182
            User           nimda
            Port           22
         #  Password       FormR!1234
         #  UpdatedOn      Mon Jul 19 2021 09:19:51 (Eastern Daylight Time)

5. Copy the Public Key

   keys  Copy  0

       cat "C:/Users/robin/.ssh/Robin.Mattern@Vultr-FormR0_nimda_ram_a210719_key.pub" | clip    # (8)

6. Paste the Public Key

       ssh Vultr-FormR0-nimda
       nano ~/.ssh/authorized_keys
       ctrl-v
       ctrl-x y <cr>
       exit

7. Test logging into Server with the SSH Key

   keys  Test  SSH  Vultr-FormR0-nimda-ram

       ssh Vultr-FormR0-nimda-ram


8. Add Key to BitVise

   - Open BitVise
   - Create a New Profile: Vultr-FormR0 (155.138.238.182) via Nimda-ram.tlp
   - Click on Client Key Manager
   - Import Private Key File: C:\Users\robin\.ssh\Robin.Mattern@Vultr-FormR0_nimda_ram_a210719_key
   - Close the Client Key Manager window
   - Enter Host IP Address: 155.138.238.182
   - Enter Username: nimda
   - Select Initial Method: Publickey
   - Select Client key: Profile 1
   - Click on Options Tab
   - Check Open Terminal and Open SFTP
   - Save Profile
   - Click on Login

<!-- ---------------------------------------------------------------------------- -->

### <u>SSH Key for All Repositories in your GitHub Account</u>

1. Make a Private and Public Key pair of files

   keys  Make  Key  Robin.Mattern  GitHub  doit

       ssh-keygen -t rsa -f "/c/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key" -C "Robin.Mattern@GitHub_a210715"


2. Show Key Files

   keys Show

       ls -l ~/.ssh/*_key*    # */


3. Set up an SSH Host Alias Name

   keys  Set  Host  5  doit

       nano ~/.ssh/config

           Host github-robin
              HostName       github.com
              IdentityFile   C:/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key
              IdentitiesOnly yes
              User           git
              Port           22
           #    UpdatedOn      Thu Jul 15 2021 10:24:38 (Eastern Daylight Time)


4. Copy the Public Key

   keys  Copy  5

       cat "C:/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key.pub"


5. Paste the Public Key

   - Log into GitHub with a browser
   - Goto you Account Settings, SSH and GPG keys
   - Paste the Public Key into the github.com account, robin.mattern


6. Test logging into GitHub with the SSH Key

   keys  Test  SSH  github-robin

       ssh github-robin


7. Clone a GitHub Repository

   gitr  clone  github-robin FormR0
   gitr  clone  github  5  FormR0 {branch}

       git clone github-robin:robinmattern/FormR0.git
       cd FormR0


8. Open Visual Studio code

       code .

   - Save the workspace: FormR0.code.workspace
   - Pull the current set of changes

<!-- ---------------------------------------------------------------------------- -->

### <u>SSH Key for One Repo in a Partner's GitHub Account</u>

1. Make a Private and Public Key pair of files

   keys  Make  Key  Robin.Mattern  GitHub  suzeeparker  doit

       ssh-keygen -t rsa -f "/c/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key" -C "Robin.Mattern@GitHub_a210715"


2. Show Key Files

   keys Show

       ls -l ~/.ssh/*_key*    # */


3. Set up an SSH Host Alias Name

   keys  Set  Host  5  doit

       nano ~/.ssh/config

           Host github-robin
              HostName       github.com
              IdentityFile   C:/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key
              IdentitiesOnly yes
              User           git
              Port           22
           #    UpdatedOn      Thu Jul 15 2021 10:24:38 (Eastern Daylight Time)


4. Copy the Public Key

   keys  Copy  5

       cat "C:/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key.pub" # (5)


5. Paste the Public Key

   - Log into GitHub with a browser
   - Goto you Account Settings, SSH and GPG keys
   - Paste the Public Key into the github.com account, robin.mattern


6. Test logging into GitHub with the SSH Key

   keys  Test  SSH  github-robin

       ssh github-robin


7. Clone a GitHub Repository

   gitr  clone  github-robin FormR0
   gitr  clone  github  5  FormR0 {branch}

       git clone github-robin:robinmattern/FormR0.git
       cd FormR0


8. Open Visual Studio code

       code .

   - Save the workspace: FormR0.code.workspace
   - Pull the current set of changes


<!-- ---------------------------------------------------------------------------- -->

### <u>SSH Key for New Repo in a Remote Server</u>

1. Log into Server with the SSH Key

   keys  SSH  Vultr-FormR0-nimda-ram

       ssh Vultr-FormR0-nimda-ram

2. Make a Private and Public Key pair of files

   keys  Make  Key  Robin.Mattern  GitHub  doit

       ssh-keygen -t rsa -f "/c/Users/robin/.ssh/Robin.Mattern@GitHub_a210715_key" -C "Robin.Mattern@GitHub_a210715"


3. Set up an SSH Host Alias Name

   keys  Set  Host  2  Vultr-FormR0  github  doit

       nano ~/.ssh/config

          Host Vultr-FormR0-github Vultr-FormR0-github-account
            HostName       github.com
            IdentityFile   /root/.ssh/Vultr-FormR0@GitHub_a210719_key
            IdentitiesOnly yes
            User           git
            Port           22
          # UpdatedOn      Mon Jul 19 2021 10:17:23 (EDT)


4. Copy the Public Key

   keys  Copy  2

        - cat "/root/.ssh/Vultr-FormR0@GitHub_a210719_key.pub"    # (2)


5. Paste the Public Key

   - Log into GitHub with a browser
   - Goto you Account Settings, SSH and GPG keys
   - Paste the Public Key into the github.com account, robin.mattern


6. Test logging into GitHub with the SSH Key

   keys  Test  SSH  github-robin

       ssh github-robin


7. Clone a GitHub Repository

   gitr  clone  Vultr-FormR0-github  {branch}

       git clone github-robin:robinmattern/FormR0.git
       cd FormR0




