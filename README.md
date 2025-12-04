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

- Windows 11`</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Subscription
- OsTicket Download zip [File](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)

<h2>Installation Steps</h2>

<p>
<img width="1506" height="848" alt="image" src="https://github.com/user-attachments/assets/6109c9de-1418-475e-920c-bfd35a8c5736"
/>
</p>
<p>
Creating an Azure Virtual Machine

Within Azure, select Create a virtual machine > Set the Region > Choose the Image Windows 11 Pro (Platform the machine will run on) >
Choose an appropriate machine size: (2 vCPUs, 8 GiB memory for tutorial) > Set Username and Password > Check the licensing agreement box > Then review and create.
</p>
<br />

<p>
<img width="1599" height="835" alt="Screenshot 2025-11-27 125301" src="https://github.com/user-attachments/assets/35ce8d55-c3ec-492b-b7f2-ed1201fb550c" />
</p>
<p>
Logging into a virtual machine
  
Go to the virtual machine tab in Azure > Copy the Virtual machine’s Public IP address > open Remote Desktop > paste the IP > and log in with the previously created VM username and password
</p>
<br />

<p>
<img width="1599" height="837" alt="image" src="https://github.com/user-attachments/assets/375e140c-50fe-43a2-9399-60181ca086bb" />
</p>
<p>
Within the Virtual machine, open a web browser and download the osTicket installation zip file > 
Go to the file location > drag the folder to the desktop > and extract all onto the desktop 
</p>
<br />

<p>
<img width="1599" height="850" alt="image" src="https://github.com/user-attachments/assets/f89d2bd1-012d-4cb9-9694-6122d20398c3" />
</p>
<p>
Installing/ Enabling IIS in Windows With CGI
  
Open the Start menu and open the Control Panel 
Go to Programs > select “Turn Windows Features On or Off” > check the box “Internet Information Services
</p>
<br />

<p>
<img width="1599" height="839" alt="image" src="https://github.com/user-attachments/assets/f9cf2b69-4275-4fea-a258-a1582d778886" />
</p>
<p>
Select the plus icon next to (IIS) > “World Wide Web Services” > “Application Development Features, check the box “CGI”, > then press OK 
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/6517c43c-216e-4e39-ba13-8b8de0589605" />
</p>
<p>
Installing PHP Manager for IIS
  
Within the Unzipped osTicket folder, open the PHPManager file (PHPManagerForIIS_V1.5.0) and follow the on-screen instructions to install 
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/d8eb29b4-f453-4bdb-946e-cea3a715a165" />
</p>
<p>
Installing the Rewrite Module
  
Within the Unzipped osTicket folder, open the rewrite module file (rewrite_amd64_en-US) and follow the on-screen instructions to install
</p>
<br />

<p>
<img width="1599" height="892" alt="image" src="https://github.com/user-attachments/assets/291d0d20-c910-4621-8d0a-ea09f0a0569f" />
</p>
<p>
Creating the directory C:\PHP
  
Within File Explorer, open the C Drive (Windows (C:), and create a new folder named PHP
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/9704e5e3-a3a1-4d37-bb80-3862e492be28" />
</p>
<p>
Open the previously unzipped osTicket folder and extract the PHP zip
(php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder in the C drive you just created
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/6ebb08c2-fd01-48cd-b65e-aee591c817c5" />
</p>
<p>
Installing the VC Redistributable
  
Within the unzipped osTicket folder, open the VC redistributable (VC_redist.x86.) and follow the onscreen instructions
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/6436a0ef-4b13-44c7-924f-efccfe89b2de" />
</p>
<p>
Installing My Sequel
  
Within the unzipped osTicket folder, open the MySQL file (mysql-5.5.62-win32) > typical setup, and install 
Launch the configuration wizard > select the standard configuration >
Create a password > then continue the installation 
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/d55602ee-cbad-419d-8c32-504e95e8156c" />
</p>
<p>
In the Windows Start menu, open IIS (Internet Information Services) as an admin > Open the PHP manager > Select Register new PHP Version > then press the three dots to browse for php-cgi in the PHP folder, select it, then press ok
Click osticket-vm on the left side, and restart IIS by stopping and starting it
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/418a861d-57bc-4fcc-bf28-411d6979d0d6" />
</p>
<p>
Go back to the osTicket installation files folder and find the zipfile named (osTicket-v1.15.8) and extract all
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/1f17242b-d548-47ad-8b80-533ef915ffec" />
</p>
<p>
Find the new folder that is named (osTicket-v1.15.8) (NOT THE ZIP) and open it
In another tab, open the C Drive > inethub > finally wwwroot > copy the upload folder from the (osTicket-v1.15.8) into wwwroot > rename the upload folder to (osTicket) the same way
Restart IIS by stopping and restarting it
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/22a56412-8061-4c71-b233-1dde92b96bfe" />
</p>
<p>
Within IIS, go to sites > Default Website > then osTicket > and click Browse > this will open up osTicket within your browser
To enable extensions, in IIS, go to sites > Default Website > osTicket > open the PHP manager
Find "Enable or disable extensions."
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/87137148-f3b3-4b4f-92a5-1ca7a9c58573" />
</p>
<p>
Open file explorer > open C Drive > inetpub > wwwroot > osTicket > include > ost-sampleconfig.php
rename the ost-sampleconfig.php to ost-config.php
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/5a5f0c2a-5307-4a03-b8a5-b8461562514e" />
</p>
<p>
right click ost-sample config > Properties > security > advanced > disable inheritance

Then add > principle > everyone (For the tutorial) > Full control > apply > ok
</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/971076b8-aa70-4492-90ff-5ff41658c42e" />
</p>
<p>
In osTicket 
Fill in information for system settings and admin user

Open the desktop and find the osTicket installation folder
Find and Open Heidi SQL and follow the on-screen instructions
Select new, set the username (username should already be present due to a previous step)(MySQL Login info), and password > open
Right-click where it says unnamed > new > select database > name it “osTicket.”

</p>
<br />

<p>
<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/7ab8d88c-90ed-428c-a023-7c4f993f0cc3" />
</p>
<p>
Go back into your browser on the osTicket setup page > Name MySGL Database “osTicket.” > Log in using the MYSQL login info from before > then install
</p>
<br />
