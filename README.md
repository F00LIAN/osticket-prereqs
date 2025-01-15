<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

Before you begin, ensure you have:
- A Microsoft Azure Virtual Machine running Windows 10.
- Admin access to the VM
- An active internet connection
- Basic knowledge of IIS and MySQL
- Downloaded the [osTicket Installation Files](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)

<h2>Installation Steps</h2>

### 1. Set Up Azure Virtual Machine
<p>
<img src="https://github.com/user-attachments/assets/c76018a6-f669-49be-9882-d019dbbc34e7" height="80%" width="80%" alt="Azure VM image"/>
</p>
<p>
Create a Windows 10 virtual machine in Microsoft Azure.
Use a dedicated resource group for organizational purposes.
Ensure no additional virtual networks are specified unless needed. 
</p>
<br />

### 2. Access VM and Download Installation Files 
<p>
<img src="https://github.com/user-attachments/assets/bd1733e5-3f88-43dd-83b0-7538666c3a27" height="80%" width="80%" alt="Remote Connect"/>
</p>
<p>
Log into the VM using Remote Desktop.
Download and extract the osTicket Installation Files
</p>
<br />

### 3. Enable IIS and CGI Features
<p>
<img src="https://github.com/user-attachments/assets/f8890b7f-f5d7-4fc8-84bd-9e7f2cd574c3" height="80%" width="80%" alt="Enable IIS and CGI"/>
</p>
<p>
Open the Control Panel → Programs → Turn Windows Features On or Off.
Expand World Wide Web Services → Application Development Features.
Enable CGI.
Restart the machine if prompted.
</p>
<br />

### 4. Install Prerequisite Programs
<p>
<img src="https://github.com/user-attachments/assets/4b868305-1330-46bc-96a9-53455c86aa05" height="50%" width="50%" alt="Install Programs"/>
</p>
<p>
Install PHP Manager for IIS.
Install Rewrite Module.
Extract and move the php-7.3.8-nts-Win32-VC15-x86.zip file to C:\PHP.
Install VC_redist.x86.exe.
Install MySQL 5.5.62.
</p>
<br />

### 5. Configure MySQL Server
<p>
<img src="https://github.com/user-attachments/assets/b4e62953-c03c-42f9-93a8-9cf45806a780" height="80%" width="80%" alt="Configuring MySQL"/>
</p>
<p>
Run the MySQL installer and follow the default setup process.
Launch the Configuration Wizard and select Standard Configuration.
Create a root username and password (both set to "root" for this setup).
</p>
<br />

### 6. Configure PHP in IIS
<p>
<img src="https://github.com/user-attachments/assets/5287aa0c-bc96-44be-8ba1-2dd576f20266" height="80%" width="80%" alt="Register PHP Version on IIS Manager"/>
</p>
<p>
Open IIS Manager → PHP Manager.
Click Register new PHP version and navigate to C:\PHP\php-cgi.exe.
Restart IIS using the left-side menu in IIS Manager.
</p>
<br />

### 7. Install osTicket
<p>
<img src="https://github.com/user-attachments/assets/5401ec68-6d70-4b68-b9ab-276bf25cb98b" height="80%" width="80%" alt="Installation Steps"/>
</p>
<p>
Extract osTicket-v1.15.8.zip and copy the upload folder to C:\inetpub\wwwroot.
Rename the upload folder to osTicket.
Restart IIS.
</p>
<br />

### 8. Configure IIS for osTicket
<p>
<img src="https://github.com/user-attachments/assets/723822ba-1131-45b9-a821-794467a77d7c" height="80%" width="80%" alt="Installation Steps"/>
</p>
<p>
In IIS Manager, navigate to Sites → Default Web Site → osTicket.
Click *Browse :80 (http) to verify the installation.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/0bfba6da-35f7-47d0-9ea4-a5cf1b416740" height="80%" width="80%" alt="os-ticket-extensions"/>
</p>
<p>
In IIS Manager, navigate to Sites → Default Web Site → osTicket.
Click on PHP Manager ---> PHP Extensions (Enable and Disable Extensions). 
Enable PHP extensions:
php_imap.dll
php_intl.dll
php_opcache.dll
</p>
<br />

### 9. Rename and Assign Permissions
<p>
<img src="https://github.com/user-attachments/assets/ed86df0b-a033-40c4-8b8c-bac4a6dd50fa" height="80%" width="80%" alt="os-ticket-extensions"/>
</p>
<p>
Go to C:\inetpub\wwwroot\osTicket\include.
Rename ost-sampleconfig.php to ost-config.php.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/7b161c16-e311-4897-b85e-95996a0b1327" height="80%" width="80%" alt="os-ticket-extensions"/>
</p>
<p>
Right-click ost-config.php → Properties → Security → Advanced.
Disable inheritance and grant Full Control to Everyone.
</p>
<br />

### 10. Set Up the Database

<p>
<img src="https://github.com/user-attachments/assets/315aaaac-0ded-4a3d-854c-815dd3bdfa18" height="80%" width="80%" alt="Setup HeidiSQL"/>
</p>
<p>
Install HeidiSQL from the "osTicket-Installation-Files" folder. 
Create a new session using the MySQL root username and password. 
Connect to the IIS session and create a database named osTicket.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/d01f7721-6701-4507-9cb8-7f386229a6b3" height="80%" width="80%" alt="Configure MySQL"/>
</p>
<p>
Return to the osTicket installer in your browser.
Enter the required details (Helpdesk Name, Default Email, Admin Username, Password, and osTicket database settings).
Click Install Now to complete the setup.
</p>
<br />

### Verification of Success

<p>
<img src="https://github.com/user-attachments/assets/d22b31d5-9cd1-4544-b79f-08655d0d60d8" height="80%" width="80%" alt="Congratulations Page"/>
</p>
<p>
Upon successful installation, access the admin panel and user portal links provided.
Test the setup to ensure all features are functional.
</p>
<br />
