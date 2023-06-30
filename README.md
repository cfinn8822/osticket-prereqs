
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In the this demonstration I am going to create a Resource group and Virtual Machine to use for the purpose of installing osTicket. I am going to list my prerequisites for installing the open-source help desk, as well as listing all the steps you need in order to do the same.
 


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Fundamentals from my pervious project 
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

1) The first thing you are going to want to do is create a Resource Group and Virtual Machine by going to "https://portal.azure.com".  
   - "Resource Group" can be named whatever you would like for this example
        
2) Setup your Virtual Machine with Windows 10 pro, version 22h2.Note you will want to create the (VM) with atleast 2 Vcpus and 8 to 16 gbs of memory.
3) Once you have created your Virtual Machine you will want to connect to it by opening your (RDC) Remote Desktop Connection tool.
   - You can find the "Remote Desktop Connection" tool by clicking the start button or windows tab and typing it into the search bar.
     
4) Copy and paste the public ip address of the (VM) you setup. Login by using the username and password you setup when making the (VM).

<img src=https://i.imgur.com/b4U8Aec.png.png height="50%" width="50%" alt="Disk Sanitization Steps"/>
 
5)Once you have connected to the (VM) you will want to go to your control panel.From there open Programs, then Turn Windows Features On or Off.

<img src=https://i.imgur.com/nYUueMt.png.png height="80%" width="80%" alt="Disk Sanitization Steps"/>

6)You will want to install/enable Internet Information Services (IIS) in Windows with CGI and Common HTTP Features.

  - World Wide Web-> Application Development->[x] CGI,[x] Common HTTP Features. *note make sure all common http features are checked.
  
<img src=https://i.imgur.com/8Aa1DZW.png.png height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 It should look something like this.
  
<img src="https://i.imgur.com/5cE7B8R.png.png" height="40%" width="80%" alt="Disk Sanitization Steps"/>
 
7)From the installtion files ,download and install PHP Manager for (IIS),(PHPManagerForIIS_V1.5.0.msi) Go through the install wizard and complete the install.

8)From the installtion files ,download and install the Rewrite Module.(rewrite_amd64_en-us.msi).

9)Create a folder on the C: Drive and call it (PHP).

10)From the installtion files, download PHP 7.3.8 (PHP-7.3.8-nts-win32-vc15-x866.zip) and unzip the contents into C:\PHP

 !! Attention !! If this happens, choose to"Keep" the file: 

<img src="https://i.imgur.com/sYQQREy.png.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>

11)Once you have downloaded and extracted the zip file into the PHP folder on the C:\ Drive,download and install the VC_redist.x86.exe from the installtion files.Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe

12)Download and install MYSQL5.5.62(mysql-5.5.62-win32.msi) and run the setup wizard:(Typical Setup->Launch Configuration Wizard) & after install (Standard Configuration)

*Make a new root password.

<img src="https://i.imgur.com/EL78CGb.png.png" height="60%" width="70%" alt="Disk Sanitization Steps"/>

13)Now that we have downloaded and installed the files,we now want to search for (IIS) in the windows search bar.Open (IIS) as an adminstatrator.

<img src="https://i.imgur.com/CHCT6xh.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

14)We will now want to register PHP from within (IIS).Click on the PHP Manager.

 - Register new PHP Version.

<img src="https://i.imgur.com/Yj6Kn49.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - You will now need to prodive a path to the PHP executable file (php-cgi.exe).Go to the C:\ Drive -> PHP -> click on the(php-cgi) file.

<img src="https://i.imgur.com/9Z3LfF1.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - Restart the IIS server.

<img src="https://i.imgur.com/wf8aZ2w.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

15)Now its time to install osTicket v1.15.8.Download osTicket from the installtion files folder.Extract and copy the "upload" folder to C:\\inetub\wwwroot.Rename "upload" file to "osTicket".

 - Name has to be "osTicket" spelled exactly the same or at the end of lab you will get a 404 error at the end of lab.
 - Reload the IIS again.

16)On the IIS page go to sites->default->osTicket- on the right side of page ,click "Browse *80".

<img src="https://i.imgur.com/G883nNR.png.png" height="60%" width="80%" alt="Disk Sanitization Steps"/>

-Some extensions are not enabled on the osTicket browser.

<img src="https://i.imgur.com/XWbtyB6.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

-To enable the extensions-Go back to the IIS,sites->default->osTicket- double click PHP Manager-Click"Enable or Disable an extension.

<img src="https://i.imgur.com/Nbo8wOL.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

-We will want to enable 3 extensions from here:

 - php_imap.dll
 - php_intl.dll
 - php_opcache.dll
   
<img src="https://i.imgur.com/aLyCZMY.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

17)Once we have those extensions enabled in IIS,we are going to want to rename one of the files in our osTicket folder.Go into the file explorer and search for C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

 - We are going to rename the ost-sampleconfig.php to ost-config.php

18)Now that we have renamed the file,right click on the file and go to properties.From there click security,advanced,and disable the inheritance.We will select Remove all inherited permissions from the object.

 - Now we add new permissions
 - Click add

<img src="https://i.imgur.com/b90NhHK.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - Select a principle

<img src="https://i.imgur.com/x1ELnYv.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - Type "Everyone" in the box.

<img src="https://i.imgur.com/E5PhpF2.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - Make sure Full Control and all the other boxes are checked

<img src="https://i.imgur.com/RW7x2HU.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

 - Click Apply and Ok

<img src="https://i.imgur.com/LFqOzoa.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

19)Once that is done we will continue to setup OS Ticketin the browser.Click continue on the browser page.Fill out the page as required except the database setting at the bottom of the page.

20)We will want to download and install HeidiSQL from the installation files.

<img src="https://i.imgur.com/lA4749A.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

21)When the program is open we will create a new session in it.

<img src="https://i.imgur.com/2J7gCKC.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

22)We want to make sure the username is root and the password is whatever you want it to be.

<img src="https://i.imgur.com/xB4abyq.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

23)Once we are connected to the session we will go back to the browser to finish setting everything up.Under the database settings in the browser the username will be"root" and the "password" will be whatever you would like.

24)We will now create a new database within HeidiSQL.In Heidi right click on the left side where is says"Unnamed",select "create new",and then select"database".Name the new database osTicket.Once we have the new database setup go back to the osTicket browser and under MySQL database type in osTicket.

<img src="https://i.imgur.com/EpsV0Gr.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

25)The last step is to do some clean up.We will want to delete the setup folder in our system. Delete:C:\inetpub\wwwwroot\osTicket\setup. Only delete the setup folder and nothing else.

26)We then will want to set the permissions back to "Read" only in the ost-config.php file.

<img src="https://i.imgur.com/YAEHPpx.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/6iGXmN7.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

27)Congrats if done successfully you should see the login prompt.

<img src="https://i.imgur.com/UkNmOAp.png.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>


