
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- My SQL
- Heidi SQL
- OS Ticket (v.1.15.8)
- Link To Downloads
  - https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

1) The first thing you are going to want to do is create a Virtual Machine by going to https://portal.azure.com/ .
2) Setup your Virtual Machine with Windows 10 pro, version 22h2.Note you will want to create the (VM) with atleast 2 Vcpus and 8 to 16 gbs of memory.
3) Once you have created your Virtual Machine you will want to connect to it by opening your (RDC) Remote Desktop Connection tool.
4) Copy and paste the public ip address of the (VM) you setup. Login by using the username and password you setup when making the (VM).
<p>
<img src=https://i.imgur.com/b4U8Aec.png
<p>
  
5)Once you have connected to the (VM) you will want to go to your control panel.From there open Programs, then Turn Windows Features On or Off.
<p>

<img src=https://i.imgur.com/nYUueMt.png.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>

6)You will want to install/enable Internet Information Services (IIS) in Windows with CGI and Common HTTP Features.
  -World Wide Web-> Application Development->[x] CGI,[x] Common HTTP Features. *note make sure all common http features are checked.

  </p>
<p>
<img src=https://i.imgur.com/8Aa1DZW.png.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
  </p>
<p>

  -To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 It should look something like this.
  
<img src="https://i.imgur.com/5cE7B8R.png.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  
7)From the installtion files ,download and install PHP Manager for (IIS),(PHPManagerForIIS_V1.5.0.msi) Go through the install wizard and complete the install.

8)From the installtion files ,download and install the Rewrite Module.(rewrite_amd64_en-us.msi).

9)Create a folderin the C: Drive and call it PHP

10)From the installtion files, download PHP 7.3.8 (PHP-7.3.8-nts-win32-vc15-x866.zip) and unzip the contents into C:\PHP

!! Attention !! If this happens, choose to"Keep" the file: 

<img src="https://i.imgur.com/sYQQREy.png.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />ereqs
