I suggest you to follow the steps mentioned below to uninstall MySQL from the device.

Step 1

Uninstall MySQL from Control Panel. To do so,

Go to Control Panel >Programs and Features > Select MySQL > Click on Uninstall.

After you have uninstalled MySQL through Add/Remove programs, you now need to remove the existing database information which includes your actual data.  If you need any of that data, be sure to back it up. Next you can delete the data directory.

Step 2

Run Command Prompt as Administrator and execute the following command to stop and remove MySQL service.

Net stop MySQL

Sc delete MySQL

Step 3

    Click on Start, type in Show hidden files and folders.

    Select the View tab and select Show hidden files and folders.

    Now explore the following locations and delete following folders.

    C:\Program Files\MySQL

    C:\Program Files (x86)\MySQL

    C:\ProgramData\MySQL

    And if exists, delete the folder from the location.

    C:\Users\[User-Name]\AppData\Roaming\MySQL