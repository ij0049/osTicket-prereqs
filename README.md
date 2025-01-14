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

- Microsoft Azure
-  Remote Desktop


<h2>Installation Steps</h2>

<p>

![Image 1-14-25 at 11 46 AM](https://github.com/user-attachments/assets/0b64bb07-ad33-41d6-96e2-7befbb7f2b9c)

<p>
1. Log In First, I go to the Azure Portal and log in with my Azure account. Once I’m in, I’m ready to start creating the VM.

2. Start Creating the VM
On the left-hand side, I click on “Virtual Machines”. Then, I click on the “+ Create” button and choose “Azure Virtual Machine”. This is where I begin setting up my VM.

3. Fill Out the Basics
Next, I fill in the details for my VM:

I choose the subscription I want to use.
For the resource group, I either create a new one or pick an existing one.
I name the VM osticket-vm because that’s what I need for this project.
I select a region, like East US, because it’s closest to where I’m working.
For the image, I pick Windows 10 Pro, Version 21H2.
Then, I select a size with 4 vCPUs, like Standard_D4s_v3.
4. Set Up My Login Details
Now, I set up the admin account so I can log into the VM later:

For the username, I type labuser.
For the password, I use osTicketPassword1!.
5. Configure Networking
I make sure the VM has proper networking:

I let Azure create a virtual network for me or use an existing one.
I keep the default subnet.
I check that a public IP address is being created so I can connect to the VM.
I allow RDP (Remote Desktop Protocol) traffic so I can log in remotely.
6. Review and Create
Once I’ve filled out everything, I click “Review + Create” to see a summary of all my settings. If everything looks good, I hit “Create”, and Azure starts setting up my VM.

7. Connect to My VM
When the VM is ready, I go to the Virtual Machines section in Azure and select my VM, osticket-vm. From there:

I click on “Connect”, choose RDP, and download the RDP file.
I open the RDP file on my computer, enter the username (labuser) and password (osTicketPassword1!), and connect to the VM
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/f037d506-9aca-410a-9a39-ee0fa6e0d64b" 
     alt="image description" />

</p>
<p>
1. Get the RDP File
Once my VM is up and running in Azure, I go to the Azure Portal:

I click on "Virtual Machines" from the left-hand menu.
I select my VM (in this case, osticket-vm) from the list.
At the top, I click "Connect" and choose RDP.
Azure provides an RDP file for download. I click "Download RDP File" and save it to my computer.
2. Open the RDP File
I locate the RDP file I just downloaded (usually in my Downloads folder) and double-click it to open.

3. Enter My Credentials
A Remote Desktop Connection window pops up:

It asks for my login details. I type the username (labuser) and the password (osTicketPassword1!) that I set up when creating the VM.
I hit "OK" to proceed.
4. Handle Security Warnings
Sometimes, a security warning appears saying the identity of the remote computer can't be verified. I click "Yes" to continue, as I trust the Azure VM.

5. Access My VM
After a few seconds, the Remote Desktop window opens, and I’m now logged into my VM. I see the Windows 10 desktop, and I can start working on whatever I need.
</p>
<br />

<p>
<img src="https://i.imgur.com/M5MXUDi.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. Open IIS as an Admin First, I open the Internet Information Services (IIS) Manager as an Administrator: <br/>

I press the Windows key, type “IIS,” right-click on IIS Manager, and select Run as Administrator. I need to run IIS as Admin so I have the proper permissions to make changes to the server configuration. 

2. Register PHP in IIS To make PHP work with IIS, I need to register PHP:

In IIS Manager, I click on the server name (at the top of the left-hand menu). I double-click on PHP Manager in the middle panel. I click on “Register new PHP version” and browse to the PHP executable file: I select C:\PHP\php-cgi.exe. Registering PHP in IIS tells the server where to find PHP, which is needed to run the PHP-based osTicket application. 3. Reload IIS After registering PHP, I need to reload IIS to apply the changes:

In IIS Manager, I click on the server name. On the right-hand side, under Manage Server, I click Stop and then Start. Reloading IIS ensures all changes take effect. 

4. Unzip and Move osTicket Files Next, I set up the osTicket application files:

I go to the “osTicket-Installation-Files” folder and find osTicket-v1.15.8.zip. I right-click the file and extract it. Inside, I find a folder named upload. I copy the upload folder and paste it into C:\inetpub\wwwroot. The wwwroot folder is the default directory for websites hosted by IIS. Placing the upload folder here makes it accessible to IIS. 

5. Rename the Upload Folder Within C:\inetpub\wwwroot, I rename the folder upload to osTicket:

This makes the folder name match the application name for clarity and consistency. 

6. Reload IIS Again After adding the osTicket files, I reload IIS one more time:

Just like before, I click Stop and then Start in IIS Manager. This ensures IIS recognizes the new application and can serve it properly. 

7. Browse osTicket in IIS To check if osTicket is working:

In IIS Manager, I expand Sites -> Default Web Site -> osTicket. On the right-hand side, I click “Browse *:80”. This opens my default web browser and takes me to the osTicket setup page. 

Why Am I Doing This? IIS Setup: IIS is the web server that will host the osTicket application. It needs PHP to run osTicket because osTicket is built with PHP. Reloading IIS: After every major change (registering PHP or adding files), I reload IIS to ensure all changes are active.

Default Web Site: I’m placing the osTicket files in the wwwroot folder because it’s the default directory where IIS looks for web applications. Renaming the folder to “osTicket” makes it easy to identify. Browsing on Port 80: Clicking *“Browse :80” opens the osTicket web application in my browser, letting me confirm everything is set up and working correctly.
</p>
<br />


<p> 
<img src="https://i.imgur.com/11V6rho.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 

1. Enabling Necessary PHP Extensions First, I went to IIS, navigated to Sites > Default > osTicket, and double-clicked PHP Manager. From there, I selected Enable or disable an extension and enabled the following:

php_imap.dll: Required for email fetching functionality, which allows osTicket to handle emails from customers. 

php_intl.dll: Supports internationalization and localization, ensuring osTicket can handle multiple languages and regions effectively. 

php_opcache.dll: Improves PHP performance by caching scripts, which is essential for a responsive helpdesk system. After enabling these extensions, I refreshed the osTicket site in the browser to observe the changes and ensure everything was loading correctly.

2. Renaming Configuration File I renamed the sample configuration file to the actual config file:
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php To: C:\inetpub\wwwroot\osTicket\include\ost-config.php This step was necessary because osTicket requires ost-config.php to store database and system settings. Without this file properly named and configured, the installation cannot proceed.

3. Assigning Permissions to ost-config.php I modified the permissions for ost-config.php to enhance security: Disabled inheritance and removed all permissions. Assigned Everyone full permissions temporarily during the setup process. This was done to allow the system to write to the configuration file during the installation. Once the setup was complete, I would tighten the permissions again to prevent unauthorized modifications.

4. Setting Up the osTicket Database I installed HeidiSQL from the osTicket-Installation-Files folder to manage the database. Using HeidiSQL, I:

Created a new session with the credentials root/root. Connected to the session and created a database called osTicket. This database is crucial for storing all helpdesk-related data, including tickets, user information, and system settings.

5. Completing Installation in the Browser I returned to the osTicket setup page in my browser and completed the configuration:

Provided a name for the helpdesk and a default email address for customer communication. Entered the database details: MySQL Database: osTicket MySQL Username: root MySQL Password: root Clicked Install Now to finalize the installation.

6. Post-Installation Steps After successfully installing osTicket, I performed these cleanup tasks:
Deleted the Setup Directory: Removed C:\inetpub\wwwroot\osTicket\setup to prevent unauthorized reinstallation or access to the setup scripts. Secured the Configuration File: Set C:\inetpub\wwwroot\osTicket\include\ost-config.php to Read-only to prevent accidental or malicious modifications to the file. These steps are critical for securing the helpdesk system and ensuring it runs smoothly.

7. Accessing the Helpdesk I verified the installation by browsing to the following URLs:
Admin Panel: http://localhost/osTicket/scp/login.php End User Portal: http://localhost/osTicket/ Both pages loaded successfully, indicating the installation was complete and functional.





</p>
