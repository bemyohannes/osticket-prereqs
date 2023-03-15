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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/MyrnTfm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1.	Install and enable IIS (Internet Information Services) with CGI:

-	Right click Windows icon in taskbar >
-	Click “run” >
-	type “control panel” and click “OK” >
-	Click “Programs” >
-	Under “Programs and Features” click “Turn Windows features on or off” >
-	Select “Internet Information Services” and also expand it >
-	Expand “World Wide Web Services” >
-	Expand “Application Development Features” >
-	Select “CGI” and click “OK”

2.	Download and install PHP Manager for IIS:

-	From the Installation Files, download and install the PHP Manager (PHPManagerForIIS_V1.5.0.msi) and Rewrite Module (rewrite_amd64_en-US.msi) files

3.	Create C:\PHP directory:

-	Open File Explorer from the taskbar and go to the (C:) drive >
-	Create a new folder called “PHP”

</p>

<p>
<img src="https://i.imgur.com/Ziv2YC2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
-	From the Installation Files, download PHP file (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP  by right-clicking on the file from “Downloads,” clicking “Extract All” and selecting C:\PHP as the destination
</p>

<p>
<img src="https://i.imgur.com/VSuAahZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/weTuzlG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
4.	From the Installation Files, download and install VC_redist.x86.exe

5.	From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
</p>

<p>
6.	Registering PHP:

-	In the taskbar search, type “iis” > click “Run as Administrator” for the IIS App > double-click “PHP Manager” > under PHP Setup, click “Register new PHP version” > click the ellipses (…) > (C:) drive > PHP > php-cgi > click Open > click OK
</p>

<p>
<img src="https://i.imgur.com/mzUohrR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
-	Web server should now be restarted: click the name of the server (VM-osTicket) on the left under Connections and then click Restart on the right under Actions
</p>

<p>
<img src="https://i.imgur.com/6eAwqly.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
7.	Installing osTicket:

-	From the Installation Files, download osTicket (osTicket v1.15.8)
-	Open the zipped osTicket file from “Downloads” and extract the “upload” folder into the c:\inetpub\wwwroot pathway >
-	Within c:\inetpub\wwwroot, rename “upload” to “osTicket”
</p>
  
<p>
<img src="https://i.imgur.com/0dAZAU1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
-	Web server should now be restarted from IIS. Follow the step above under part (6)
</p>

<p>

-	From IIS we will enable several extensions: in IIS under connections expand Sites > expand Default Web Site > click osTicket > on the right under Manage Folder, click “Browse *:80 (http)”, which will open the osTicket interface in a new tab in your web browser

-	Within the osTicket folder in IIS, click “PHP Manager” > under “PHP Extensions” click “Enable or disable an extension” > enable the following extensions by clicking them and then clicking “enable” on the right under “Actions”

  <p>
    php_imap.dll
  </p>

  <p>
    php_intl.dll
  </p>

  <p>
    php_opcache.dll
  </p>

</p>
  
<p>
<img src="https://i.imgur.com/hIU9U5i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
-	Referesh the osTicket site in your web browser and observe the changes. You should see something similar to the following:
</p>

<p>
<img src="https://i.imgur.com/UrEl4JX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
8.	Renaming a PHP file and Assigning Permissions:

-	From within the C:\inetpub\wwwroot\osTicket\include pathway rename the “ost-sampleconfig” PHP file to “ost-config” >
-	Right-click the “ost-config” file and click Properties > Security > Advanced > Disable Inheritance > click “Remove all inherited permissions…” > click Add > click “Select a principal” > type “everyone” as the object name > “Check Names”> OK > Full Control > OK > Apply > OK > OK

9.	osTicket Installation, Continued:

-	Within the osTicket site in the browser, at the bottom of the page, click “Continue”>
-	 Enter a helpdesk name and default email >
-	Fill out the information under “Admin User” >

Before we fill out the information under “Database Settings” we will first need to download and install HeidiSQL from the Installation Files, which will allow us to connect to the MySQL database that we installed in part (5)

-	After downloading and installing, open HeidiSQL and click “New” icon on the bottom left-hand corner and provide the username and password that was used when setting-up MySQL > click Open > right-click “Unnamed” > Create new > Database > name it “osTicket” > OK

</p>

<p>
<img src="https://i.imgur.com/dFCRCkn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Go back to osTicket site and enter the database name of the database that was just created and the MySQL username and password under “Database Settings” > click “Install Now” 
</p>

<p>
<img src="https://i.imgur.com/BRioBvQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Congratulations! Hopefully it installed with no errors! 
</p>

<p>
10.  The final step is to do some cleanup:

-	Delete the “setup” folder from the C:\inetpub\wwwroot\osTicket pathway. BE CAREFUL not to delete the entire pathway; ONLY delete the “setup” folder from within the “osTicket” folder in the pathway
-	Finally, from the C:\inetpub\wwwroot\osTicket\include\ost-config.php pathway, right-click the ost-config.php file > Properties > Security > Advanced > select Everyone > Edit > check only “Read & execute” and “Read” > OK > Apply > OK > OK 
 
</p>
