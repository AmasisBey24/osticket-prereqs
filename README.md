<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

<ul>
<li>Microsoft Azure</li>
<li>Virtual Machine</li>
<li>osTicket Installation Files</li>
</ul>

<h2>Installation Steps</h2>

<p>
<h3>Step 1: Connect to Your Virtual Machine with Remote Desktop</h3>

- If you need help going to your virtual machine, please see my tutorial [here](https://github.com/AmasisBey24/configure-ad/blob/main/README.md)

<h3>Step 2: Install and Enable Internet Information Services (IIS)</h3>

Instructions

- Click the Start menu (bottom-left corner of the screen) and search for Control Panel.

- Open Control Panel, then select Programs.

- Click Uninstall a program.

- On the left side of the window, select Turn Windows features on or off.

- When the Windows Features window opens, locate and check Internet Information Services (IIS).

- Click OK and wait for Windows to apply the changes.

Expected Result:

- IIS is successfully installed on the system.

- The installation completes without errors.

✔️ You will verify IIS installation in a later step of the lab.


<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f4e62517659654c2e706e672e706e6713" src="https://github.com/user-attachments/assets/d5535b4c-b007-4047-8214-33a9125e16bf" />
</p>


<h3>Step 3: Download, Install, and Open the Web Platform Installer
</h3>

- osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
	- Download Web Platform Installer > select Download Anyway > at the top right, select Open File
	- Follow the prompt to install Web Platform Installer
	- Open the Web Platform Installer

<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f304f6e32764b642e706e6715" src="https://github.com/user-attachments/assets/0995ca7e-1288-4a57-bf7f-6bb2ad6ea095" />
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f56347039346d502e706e6714" src="https://github.com/user-attachments/assets/4156b49e-d1b9-45b9-9878-e8aadd9b35c2" />
</p>

- Once Web Platform Installer is open, go to the top right of the screen and search for MySQL 5.5
- Go to MySQL Windows 5.5 and click Add
- Go to the top right again and search for PHP
	- Adjust the list to Sort by "name"
- Add all simple versions of x86 PHP up until 7.3
- Select Install at the bottom of the screen and it will tell you to create a username and password to complete the installation

<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f755741566352472e706e6716 copy" src="https://github.com/user-attachments/assets/fbf9d04f-cc45-4ec3-bec2-f9c72e8bd5f5" />
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f4d516d5a6668742e706e6717" src="https://github.com/user-attachments/assets/5ba43587-082f-4db3-b044-c667a071eee0" />
</p>


  - Username: root
  - Password: Password1
- Follow the prompt to complete the installation
- You might get a message stating that "some products have failed to install"
	- Ignore that message and select Finish
- Download and install the following from within the lab files: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
  - PHP Version 7.3.8
  - PHP Manager 1.5.0 for IIS 10
  - Microsoft Visual C++ 2009 Redistributable Package


<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f7a415046526d552e706e67 copy" src="https://github.com/user-attachments/assets/a5594112-5c86-4390-8664-124218e3cbb7" />
 <img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f445569795164742e706e67 copy" src="https://github.com/user-attachments/assets/45fba877-6dab-479e-b2a0-c4f1f3168227" />

</p>


<h3>Step 4: Install osTicket v1.15.8</h3>
     
- Download osTicket (download from within lab files: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6))
- Right-click on the file and select Extract All
	- Open the new osTicket folder
		- Copy the Upload folder into C:\inetpub\wwwroot
		- Rename “Upload” to “osTicket”


<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f42704c38494a452e706e67" src="https://github.com/user-attachments/assets/f2e1d646-c9a5-463b-a6ab-b807517d9334" />
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f78534a4437796b2e706e67" src="https://github.com/user-attachments/assets/9313b36f-4228-4f16-862a-34979362befa" />
</p>
 
     

<h3>Step 5: Restart the IIS Server
</h3>

- Search for Internet Information Services (IIS) and select Open
	- Select Restart on the right-hand side 
- On the left side of the screen, select Virtualmachine > Sites > Default Website > osTicket
- On the right side of the screen, click “Browse *:80”
	- This should open osTicket in your web browser
- Before continuing, head back to IIS
- Open IIS


<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f4f70426b77776a2e706e67 copy" src="https://github.com/user-attachments/assets/26a40f52-b4b4-4dc9-8b70-818c17fda9b4" />
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f584e56534e69612e706e67 copy" src="https://github.com/user-attachments/assets/5f0cbcb8-dc22-4409-9039-cc01ac9bd806" />
</p>

<h3>Step 6: Enable Extensions in IIS
</h3>

- Go back to IIS > Sites > Default Web Site > osTicket
- Double-click PHP Manager
- Click “Enable or Disable an Extension” at the bottom of the screen under PHP Extensions
- Right-click and enable the following
    - php_imap.dll (Might be already enabled)
    - php_intl.dll
    - php_opcache.dll

 
     
 <p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f475166504f55382e706e67 copy 2" src="https://github.com/user-attachments/assets/7a2cb268-53d2-4afc-9bed-b28873bc8345" />
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f69434b367673742e706e67 copy" src="https://github.com/user-attachments/assets/9e89ff6e-3246-4775-9527-e07d98db2aa0" />
</p>

<h3>Step 7: Refresh the osTicket Site in Your Browser
</h3>

- Refresh the osTicket site adn observe the change
	- Intl Extension should now have a green checkmark next to it


<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f4279664e3246642e706e67 copy" src="https://github.com/user-attachments/assets/d425cac4-f790-4b40-b29f-4280474a2cd7" />



<h3>Step 8: Rename</h3>
 
- Open Windows Explorer and select C: > inetpub > wwwroot > osTicket > include
	- Rename the following file:
		- From: ost-SAMPLEconfig.php
		- To: ost-config.php


<p align="center">
<img width="80%" height="1274" alt="68747470733a2f2f692e696d6775722e636f6d2f444454523843442e706e67 copy" src="https://github.com/user-attachments/assets/85c9a9ff-6f50-48a5-8e48-4a65b65e7d3b" />

<h3>Step 9: Assign Permissions to ost-config.php</h3>

- Right-click ost-config.php 
- Open Properties > Security > Advanced > Permissions 
- Select Disable Inheritance > Remove all inherited permissions from this object 

<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f706346764b39642e706e67 copy" src="https://github.com/user-attachments/assets/fc0c2d55-93e1-441a-a3cb-bfe690a0fd26" />

- Afterwards, select Add > select Principal > type in "everyone" > select Check Names > select OK
	- Allow everyone full control (check all boxes) > Select apply > OK

<p align="center">
<img width="70%" height="70%" alt="68747470733a2f2f692e696d6775722e636f6d2f76556c707a54622e706e67 copy" src="https://github.com/user-attachments/assets/ce95a9fb-2490-4163-9743-dddb39b9e384" />
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f575a726b3146372e706e67 copy" src="https://github.com/user-attachments/assets/c9c1e66e-18c3-420a-a7b2-9a796baf9e1b" />
</p>

  
<h3>Step 10: Continue Setting Up osTicket in Browser</h3>

- Go back to the browser and click Continue
  - Name: Helpdesk
  - Email: whichever email you want
  - First Name: your first name
  - Last Name: your last name
  - Email Address: whichever email you want (needs to be different from the Helpdesk's default email)
  - Username: user_admin 
  - Password: Password1 
  
<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f31476670504c732e706e67 copy" src="https://github.com/user-attachments/assets/2065b12a-ad09-4792-b114-14beb9c807b9" />

<h3>Step 11: Download and Install HeidiSQL</h3>

- Head to osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
	- Download and install HeidiSQL
- Open HeidiSQL > Select "New" at the bottom-left corner of the screen
   - User: root
   - Password: Password
- Select Open
- On the left side, right-click Unnamed > select Create New > Database
- Name it “osTicket” and select OK

 <p align="center">
<img width="70%" height="70%" alt="68747470733a2f2f692e696d6775722e636f6d2f6d44425751356b2e706e67 copy" src="https://github.com/user-attachments/assets/0bf41b88-1715-4854-9008-980627ad1052" />
<img width="70%" height="70%" alt="68747470733a2f2f692e696d6775722e636f6d2f41444a595179422e706e67 copy" src="https://github.com/user-attachments/assets/9a07952a-e8f2-44a0-9d77-b6935620f8c6" />
</p>

<h3>Step 12: Continue Setting Up osTicket by Filling Out the Fields</h3>

- Go back to the browser
	- MySQL Database: osTicket (the one you just created in HeidiSQL)
	- MySQL Username: root
	- MySQL Password: Password1
	- Finally, click Install Now

<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f4e70716a3955732e706e67 copy" src="https://github.com/user-attachments/assets/2c7c6d42-0756-4ad8-b0ec-7bc2701dad29" />


🎉Congratulations! You have sucessfully installed osTicket adn all of its pre-requisite files!🎉

<p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f4635327970486e2e706e67 copy" src="https://github.com/user-attachments/assets/08733cbb-c682-49f1-88ea-3201619a0839" />

<h3>Tips!</h3>

- To create tickets as a user: http://localhost/osTicket/
- To log in as an Admin or helpdesk professional: http://localhost/osTicket/scp

<h3>Step 13: Post-Intallation Cleanup</h3>

- Go to C: > inetpub > wwwroot > osTicket > Setup
    - Delete the contents in the Setup folder
    - Afterwards, delete the Setup folder
- Go to C: > Inetpub > wwwroot > osTicket > Include
    - Right-click on ost-config.php 
    - Select Securities > Advanced > Click on "everyone" > edit to change permissions
	- Allow everyone to only have "Read and execute" permission, then select OK > Apply > OK
	
 <p align="center">
<img width="80%" height="80%" alt="68747470733a2f2f692e696d6775722e636f6d2f7775635433554e2e706e67 copy" src="https://github.com/user-attachments/assets/cab30ea4-9eb5-437d-9b85-5bb75f0b5dbe" />
<img width="70%" height="70%" alt="68747470733a2f2f692e696d6775722e636f6d2f6350537836564c2e706e67 copy" src="https://github.com/user-attachments/assets/250f9f22-078f-453a-b0ae-24e80cc26541" />
</p>	


✅Congratz! You have installed osTicket successfully!
