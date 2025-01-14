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

<p>
<img src="https://github.com/user-attachments/assets/c76018a6-f669-49be-9882-d019dbbc34e7" height="80%" width="80%" alt="Azure VM image"/>
</p>
<p>
Go to Azure and create a virtual machine configured with Windows 10. Make sure to create a specific resource group for this project so we can organize this versus other projects. Lastly, since we are not creating anymore than one machine we do not need to specify a virtual network. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, Log in to the VM via remote desktop and install the following files in the Virtual Machine: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/f8890b7f-f5d7-4fc8-84bd-9e7f2cd574c3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable **IIS services for CGI** on the Virtual Machine. This will allow the virtual machine to act as a server on the loopback address of 127.0.0.1, giving us the ability to self host the OS-Ticket application. Go to the Control Panel ---> Programs ---> Turn Windows Features On or Off ---> World Wide Web Services ---> Application Development Features ---> CGI (ENABLE THIS)
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/4b868305-1330-46bc-96a9-53455c86aa05" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files.zip folder setup the files in this order: 1. Install PHP Manager for IIS 2. Install the Rewrite Module 3. Unzip the PHP 7.3.8 folder (php-7.3.8-nts-Win32-VC15-x86.zip) and save on c-drive "C:\PHP" folder 4. Install the VC_redist.x86.exe 5. Install MySQL 5.5.62
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/4b868305-1330-46bc-96a9-53455c86aa05" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files.zip folder setup the files in this order: 1. Install PHP Manager for IIS 2. Install the Rewrite Module 3. Unzip the PHP 7.3.8 folder (php-7.3.8-nts-Win32-VC15-x86.zip) and save on c-drive "C:\PHP" folder 4. Install the VC_redist.x86.exe 5. Install MySQL 5.5.62
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/4b868305-1330-46bc-96a9-53455c86aa05" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files.zip folder setup the files in this order: 1. Install PHP Manager for IIS 2. Install the Rewrite Module 3. Unzip the PHP 7.3.8 folder (php-7.3.8-nts-Win32-VC15-x86.zip) and save on c-drive "C:\PHP" folder 4. Install the VC_redist.x86.exe 5. Install MySQL 5.5.62
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/4b868305-1330-46bc-96a9-53455c86aa05" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files.zip folder setup the files in this order: 1. Install PHP Manager for IIS 2. Install the Rewrite Module 3. Unzip the PHP 7.3.8 folder (php-7.3.8-nts-Win32-VC15-x86.zip) and save on c-drive "C:\PHP" folder 4. Install the VC_redist.x86.exe 5. Install MySQL 5.5.62
</p>
<br />
