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
