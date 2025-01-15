<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Virtual Machine
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

### Get Started with Azure VM
<p>
<img src="https://github.com/user-attachments/assets/c76018a6-f669-49be-9882-d019dbbc34e7" height="80%" width="80%" alt="Azure VM image"/>
</p>
<p>
Go to Azure and create a virtual machine configured with Windows 10. Make sure to create a specific resource group for this project so we can organize this versus other projects. Lastly, since we are not creating anymore than one machine we do not need to specify a virtual network. 
</p>
<br />

### Login to the VM and Install Folder 
<p>
<img src="https://github.com/user-attachments/assets/bd1733e5-3f88-43dd-83b0-7538666c3a27" height="80%" width="80%" alt="Remote Connect"/>
</p>
<p>
Next, Log in to the VM via remote desktop and install the following files in the Virtual Machine: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD 
</p>
<br />

### Enable the IIS server on the VM 
<p>
<img src="https://github.com/user-attachments/assets/f8890b7f-f5d7-4fc8-84bd-9e7f2cd574c3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable **IIS services for CGI** on the Virtual Machine. This will allow the virtual machine to act as a server on the loopback address of 127.0.0.1, giving us the ability to self host the OS-Ticket application. Go to the Control Panel ---> Programs ---> Turn Windows Features On or Off ---> World Wide Web Services ---> Application Development Features ---> CGI (ENABLE THIS)
</p>
<br />

### Open the ZIP file and Install Programs in Order
<p>
<img src="https://github.com/user-attachments/assets/4b868305-1330-46bc-96a9-53455c86aa05" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files.zip folder setup the files in this order: 1. Install PHP Manager for IIS 2. Install the Rewrite Module 3. Unzip the PHP 7.3.8 folder (php-7.3.8-nts-Win32-VC15-x86.zip) and save on c-drive "C:\PHP" folder 4. Install the VC_redist.x86.exe 5. Install MySQL 5.5.62
</p>
<br />

### Configure MySQL 
<p>
<img src="https://github.com/user-attachments/assets/b4e62953-c03c-42f9-93a8-9cf45806a780" height="80%" width="80%" alt="Configuring MySQL"/>
</p>
<p>
After installing MySQL go through the typical setup with default settings and launch the configuratuion wizard after installing. In the configuration wizard go through the **standard configuration** and create a username and password (ideally both "root") for MySQL server. 
</p>
<br />

### Register PHP from within IIS, then Reload IIS
<p>
<img src="https://github.com/user-attachments/assets/5287aa0c-bc96-44be-8ba1-2dd576f20266" height="80%" width="80%" alt="Register PHP Version on IIS Manager"/>
</p>
<p>
Open IIS Manager and find the PHP Manager. Register a new PHP version by going clicking 'Register new PHP version'. You will be prompted to load in an executable file which will be stored in our existing c-drive located in the folder: 'C:\PHP\php-cgi.exe'.

Next, navigate to the left side bar on the IIS Manager and click on the server in use. Then click 'restart'. 
</p>
<br />

### Install osTicket, Browse the 127 local-host, and Enable Extensions
<p>
<img src="https://github.com/user-attachments/assets/5401ec68-6d70-4b68-b9ab-276bf25cb98b" height="80%" width="80%" alt="Installation Steps"/>
</p>
<p>
From the osTicket-Installation-Files.zip folder unzip "osTicket-v1.15.8.zip" and copy the "upload" folder into "c:\inetpub\wwwroot". Once this is complete, please rename "upload" to "osTicket". We do this because . The Reload IIS (Open IIS Manager and Restart the server)
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/723822ba-1131-45b9-a821-794467a77d7c" height="80%" width="80%" alt="Installation Steps"/>
</p>
<p>
Navigate to the IIS Manager and Click on the os-ticket server on the left hand pane. Navigate to Sites ---> Default Web Site ---> osTicket and click "Browse *:80(http)"
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/0bfba6da-35f7-47d0-9ea4-a5cf1b416740" height="80%" width="80%" alt="os-ticket-extensions"/>
</p>
<p>
Navigate to the IIS Manager and Click on the os-ticket server on the left hand pane. Navigate to Sites ---> Default Web Site ---> osTicket, once arrived click on PHP Manager ---> PHP Extensions (Enable and Disable Extensions). Then enable the following extensions: 
  1. php_imap.dll
  2. php_intl.dll
  3. php_opcache.dll
</p>
<br />

### Rename ost-config.php and Assign Permissions
<p>
<img src="https://github.com/user-attachments/assets/ed86df0b-a033-40c4-8b8c-bac4a6dd50fa" height="80%" width="80%" alt="os-ticket-extensions"/>
</p>
<p>
Navigate to the file explorer to the directory "C:\inetpub\wwwroot\osTicket\include" and rename "ost-sampleconfig.php" to ost-config.php"
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/7b161c16-e311-4897-b85e-95996a0b1327" height="80%" width="80%" alt="os-ticket-extensions"/>
</p>
<p>
Assign Permissions to new "ost-config.php" to all. Right Click on "ost-config.php" ---> Properties ---> Security ---> Advanced. Disable inherentence for everyone and add a user to "EVERYONE" to have full control. This is not good practice but for the lab it works. 
</p>
<br />

### Continue Setup on OsTicket and Verify URL

<p>
<img src="https://github.com/user-attachments/assets/315aaaac-0ded-4a3d-854c-815dd3bdfa18" height="80%" width="80%" alt="Setup HeidiSQL"/>
</p>
<p>
From the "osTicket-Installation-Files" folder, install _HeidiSQL_ and create a new session with the username and password of "root". Connect to the IIS Session and create a database called "osTicket".
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/d01f7721-6701-4507-9cb8-7f386229a6b3" height="80%" width="80%" alt="Configure MySQL"/>
</p>
<p>
Go back to OsTicket installer page and continue with setup. Provide Name, Email, Admin User, and Database Settings from the HeidiSQL instance we created in the step before. Do not forget Admin USERNAME and PASSWORD. Then click INSTALL NOW!
</p>
<br />

### Verification of Success

<p>
<img src="https://github.com/user-attachments/assets/d22b31d5-9cd1-4544-b79f-08655d0d60d8" height="80%" width="80%" alt="Congratulations Page"/>
</p>
<p>
OsTicket will promptly congratulate you on the installation and provide links to the control panel and page. 
</p>
<br />
