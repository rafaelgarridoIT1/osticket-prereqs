# osticket-prereqs

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- VC_redistx86
- MySQL 5.5.62
- Rewrite Module
- Heidi SQL

<h2>Installation Steps</h2>

<h2>Setting Up osTicket on Azure VM</h2>

1. Create Virtual Machine in Azure:
- Log in to Azure Portal.
- Create a new VM with Windows Server.
![image](https://github.com/user-attachments/assets/3ef6412d-12eb-4197-b368-5145b66ebf51)

- Connect to your VM using the Remote Desktop with the public IP address form the VM. (for mac user use the "windows app")
![image](https://github.com/user-attachments/assets/d5754cfa-60fa-45e3-80a9-0498054b379a)

- login with the same login credentials used to create the VM.
   
![image](https://github.com/user-attachments/assets/871155b7-1c14-4160-ab8f-5d96b6a90f9f)

2. Download the osTicket-Installation-Files.zip

- Inside your VM download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)and unzip it onto your desktop. we will use the files to download osticket.
![image](https://github.com/user-attachments/assets/3b361ac4-d206-4ee9-bc24-bb7dfd7f2a20)

3. Enable ISS with CGI

- Go to the Control Panel and open the programs applet. Under programs, select "Turn Windows features on or off".


![image](https://github.com/user-attachments/assets/a1f6a130-c77b-4975-8c5d-7617ee57589c)


- enable (internet information services) World Wide Web Services -> Application Development Features -> enable (CGI)


![image](https://github.com/user-attachments/assets/33e9c604-072b-4a04-9276-8eead0f6ea34)


- Test if the changes were applied succesfully, type 127.0.0.1 on your browser and the page below should appear.


![image](https://github.com/user-attachments/assets/53698717-7b46-4a56-a0b8-a78511406fcd)

4. Download and install PHP manager from the osTicket-Installation-Files
- (PHPManagerForIIS_V1.5.0.msi)

![image](https://github.com/user-attachments/assets/92eee3dd-bac3-4db0-b58e-ff75e6caa7a4)

5. Download and Install the Rewrite Module

- (rewrite_amd64_en-US.msi) from the osTicket-Installation-Files

![image](https://github.com/user-attachments/assets/294e336b-3eb7-4d03-a561-4171b080ad47)


6. Creat a directoy in the C drive 

- Go to file explorer and creat the directory C:\PHP


![image](https://github.com/user-attachments/assets/61df1d0c-6c8a-4094-a42a-12445ed66dcd)

7. From the osTicket-Installation-Files intall(php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP

- From osTicket-Installation-Files unzip the content into the newly created C:\PHP


![image](https://github.com/user-attachments/assets/a25b7d28-338a-4f58-be0d-f055e645b7c7)

8. Download and Install the (VC_redist.x86.exe) 

- install from the osTicket-Installation-Files

![image](https://github.com/user-attachments/assets/9a70d19f-c771-458f-a446-97f976109788)

9. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

- install from the osTicket-Installation-Files

- select the following configurations;

  ->Typical setup

  ->launch configuration


  ->Standard configuration

  ![image](https://github.com/user-attachments/assets/0c20332f-c755-4b52-a890-baca66a769b0)

 - the user for this service is going to (username:root) (password:root) for my sql server


![image](https://github.com/user-attachments/assets/4ca0c95e-e6a3-4fc4-9d8d-d4c3059c281c)

10. Launch IIS as an administrator

- Search for IIS in the windows search bar and right click it and select open as administrator


![image](https://github.com/user-attachments/assets/a9393ae1-8b51-42be-9de6-f9199259fd50)

11. Register PHP from within lIS
- open the PHP manager
- Register new PHP version


![image](https://github.com/user-attachments/assets/961bd3e9-90c0-4dca-a8ad-d69eeb9dfee9)

-browse (...)

- go to your C drive

- PHP folder

- php-cgi


![image](https://github.com/user-attachments/assets/3d145a38-bc83-4973-aa9d-0689354e6cce)

12. Reload IIS (Open IIS, Stop and Start the server)

 -The restart button can be found on the right side of the window
 
![image](https://github.com/user-attachments/assets/eb54573c-2f93-4b3d-85ff-b4eaf8a36a3d)

13. Download and install osTicket

-from the osTicket-Installation-Files unzip or extract the (osTicketv1.15.8)

![image](https://github.com/user-attachments/assets/cddae31a-a0f3-47e6-91ab-95726e5302e6)

-after extracting the folder click on the folder and then copy the "upload" folder into "c: linetpub\wwwroot"






- open file explorer
- C drive
- inetpub
- wwwroot


![image](https://github.com/user-attachments/assets/66ceebec-3b93-4cf8-a458-c6536cadc124)

- Within "c: linetpub|wwwroot", Rename "upload" to "osTicket"

![image](https://github.com/user-attachments/assets/739a5d7c-0720-4e75-9196-6b6004b6696a)

14. Reload IIS as admin (Open IIS, Stop and Start the server)

 -The restart button can be found on the right side of the window
 
![image](https://github.com/user-attachments/assets/eb54573c-2f93-4b3d-85ff-b4eaf8a36a3d)

15. Launch osTicket

 -On the left hand side of IIS, Expand on the VM name -> Sites - > Default Website -> osTicket

- click on browse *:80(http)

![image](https://github.com/user-attachments/assets/aa9aa5fc-f23e-405b-85bb-da33911e545f)


- This should then lead to your browser opening osTicket.


![image](https://github.com/user-attachments/assets/2a283552-dc7b-41cb-938c-1cb8b14258aa)

16. Enable extensions

- open IIS, sites -> Default -> osTicket
- Double-click PHP Manager

![image](https://github.com/user-attachments/assets/93f46eaa-236b-4042-ac82-ee41364d959f)


Click “Enable or disable an extension”

- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll

![image](https://github.com/user-attachments/assets/60d0a97e-4f66-44a2-8f85-241360305bcb)

17.Refresh osTicket

- Refresh the osTicket site in your browser, some extensions will now appear active 

![image](https://github.com/user-attachments/assets/8e5412dc-6974-40d3-979f-a773280450cc)

18.Change ost-config.ph  


- Rename: ost-config.php

From: C:\inetpub|wwwrootlosTicket\includelost-sampleconfig.php


To: C. linetpubiwwwrootlos Ticketinclude lost-config.php

- rename "ost-sampleconfig.ph" to "ost-config.ph"


![image](https://github.com/user-attachments/assets/7ebb49ac-8bf3-41aa-930f-386232fd9444)

22. Change ost-config.ph permissions

- Change ost-config.php permissions by right clicking and selecting

- Properties -> Security -> Advance -> Disable inheritance

- Disable inheritance -> Remove All


![image](https://github.com/user-attachments/assets/c7794c10-8331-45a4-a8c5-db3433a37310)

- New Permissions -> Everyone -> All|

go to add-> select principal-> Everyone-> click full access-> apply-> ok

![image](https://github.com/user-attachments/assets/a6ee49cd-67a1-4cc0-89df-62e42b4ddcf1)

23. Continue osTicket installation

- Continue the osTicket installer on your browser by filling the first half of the page.

![image](https://github.com/user-attachments/assets/4e0ec4d0-ce87-4fc0-a182-799813e568b1)

24. Download and install Heidi SQL from the osTicket-Installation-Files

![image](https://github.com/user-attachments/assets/2ae5184e-755d-43d8-a198-681c9c92248d)

- Open Heidi SQL and create a new session 
- fill in username and password as root

username:root 


password:root 

- then click open

![image](https://github.com/user-attachments/assets/ae9c7868-3225-4bd2-81cb-030ccb11d160)

25. Create new database

- On the left side of the window, right click on "Unnamed" and click create new database and name it "osTicket".

![image](https://github.com/user-attachments/assets/e45954d5-7f17-43b4-a7ea-7e11bb973f62)

26. Finish signing in database settings

- Then go back to your osTicket browser and fill up the missing credentials. It should look something like this.

- install now 
  
![image](https://github.com/user-attachments/assets/c5d403ab-5b25-416f-90df-305620b5b653)



27. Finalize osticket installation


![image](https://github.com/user-attachments/assets/39fb604c-fd30-4b47-8899-45e1ef2ac436)


Congratulations you just installed osTicket
