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

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/fc6a339a-c711-4f38-84b7-a0b43751a684" 
         height="80%" width="80%" alt="step1" />
</p>
<p>
1. Log In
First, I go to the Azure Portal and log in with my Azure account. Once I’m in, I’m ready to start creating the VM.

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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
