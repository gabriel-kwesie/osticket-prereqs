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

- Microsoft Azure Subscription
- OsTicket Download Files
- 

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Creating an Azure Virtual Machine

Within Azure, select Create a virtual machine > Set the Region > Choose the Image Windows 10 Pro (Platform the machine will run on) >
Choose an appropriate machine size: (2 vCPUs, 8 GiB memory for tutorial) > Set Username and Password > Check the licensing agreement box > Then review and create.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Logging into and downloading osTicket 
  
Copy the Virtual machine’s Public IP address > open Remote Desktop > paste the IP > and log in with the previously created VM username and password
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the Virtual machine, open a web browser and download the osTicket installation zip file > 
Go to the file location > drag the folder to the desktop > and extract 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Installing/ Enabling IIS in Windows With CGI
  
Open the Start menu and open the Control Panel 
Go to Programs > select “Turn Windows Features On or Off” > check the box “Internet Information Services
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select the plus icon next to (IIS) > “World Wide Web Services” > “Application Development Features, check the box “CGI”, > then press OK 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Installing PHP Manager for IIS
  
Within the Unzipped osTicket folder, open the PHPManager file (PHPManagerForIIS_V1.5.0) and follow the on-screen instructions to install 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Installing the Rewrite Module
  
Within the Unzipped osTicket folder, open the rewrite module file (rewrite_amd64_en-US) and follow the on-screen instructions to install
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Creating the directory C:\PHP
  
Within File Explorer, open the C Drive (Windows (C:), and create a new folder named PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the previously unzipped osTicket folder and extract the PHP zip
(php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder in the C drive you just created
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Installing the VC Redistributable
  
Open the VC redistributable (VC_redist.x86.exe.) and follow the onscreen instructions
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Installing My Sequel
  
Open the MySQL file (mysql-5.5.62-win32) > typical setup, and install 
Launch the configuration wizard > select the standard configuration >
Create a password > then continue the installation 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS (Internet Information Services) as an admin > Open the PHP manager > Select Register new PHP Version > then press the three dots to browse for php-cgi, select it, then press ok
Click osticket-vm on the left side, and restart IIS by stopping and starting it
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Installing osTicket
  
Go back to the osTicket installation files folder and find the zipfile named (osTicket-v1.15.8) and extract all
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Find the new folder that is named (osTicket-v1.15.8) (NOT THE ZIP) and open it
Open the C Drive > inethub > finally wwwroot > copy the upload folder from the (osTicket-v1.15.8) into wwwroot > rename the folder to (osTicket) the same way
Restart IIS by stopping and restarting it
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites > Default Website > then osTicket > and click Browse > this will open up osTicket within your browser
To enable extensions, in IIS, go to sites > Default Website > osTicket > open the PHP manager
Find "Enable or disable extensions."
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename: ost-config.php
  
Open file explorer > open C Drive > inetpub > wwwroot > osTicket > include > ost-sampleconfig.php
rename the ost-sampleconfig.php to ost-config.php
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Giving access to osTicket 
Properties > security > advanced > disable inheritance

Then add > principle > everyone (For the tutorial) > Full control > apply > ok
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In osTicket 
Fill in information for system settings and admin user

Open the desktop and find the osTicket installation folder
Find and Open Heidi SQL and follow the on-screen instructions
Select new, set the username (username should already be present due to a previous step)(MySQL Login info), and password > open
Right-click where it says unnamed > create new > select database > name it “osTicket.”

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back into your browser on the osTicket setup page > Name MySGL Database “osTicket.” > Log in using the MYSQL login (Lab used login info) > then install
</p>
<br />
