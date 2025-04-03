
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Environments Used </h2>
<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2> Virtual Machine set up </h2>

1.	Open Azure and navigate to Virtual Machines.

	2.	Click Create a Virtual Machine.

	3.	Choose or create a Resource Group (name it as you prefer).

	4.	Select your desired Region.

	5.	Under Image, choose Windows 10 Pro.

	6.	Select an appropriate size—I recommend at least 2 vCPUs for better performance.

	7.	Create a Username and Password (e.g., labuser and Cyberlab123!).

	8.	Complete the remaining settings as needed, then click Create to deploy the virtual machine.

	9.	Once the VM is up and running, navigate to its home screen and locate the Public IP Address.

	10.	Use Remote Desktop (RDP) to connect to the virtual machine using the public IP, along with the username and password you created.

---

 
![ade1](https://github.com/user-attachments/assets/d4fb92ed-bfff-4a5d-8360-129bbbc8e1d6)
![ade2](https://github.com/user-attachments/assets/4cf99ac6-b259-4c49-95f7-71f864e9f6e8)
![ade3](https://github.com/user-attachments/assets/094eb878-0b0f-474c-9902-4293cb6de831)
![a4](https://github.com/user-attachments/assets/693dddb3-c309-45e4-b363-98ff9a773473)
![ade5](https://github.com/user-attachments/assets/7e0a10f7-3440-4834-ab3c-5043f76a0e0a)

---

<h2> OSTicket Installation </h2>

1.	Download and Extract osTicket

	- Open Windows Explorer and copy this link into the address bar:
osTicket zip

	- Download and extract the files to the Desktop.

2.	Install IIS with CGI

	- Click Start, then open the Control Panel.
	- Go to Programs, then click Turn Windows features on or off.
	- Navigate to:
Internet Information Services (IIS) > World Wide Web Services > Application and Development Features.

	- Check the box for CGI, then click OK.

3.	Install PHP Manager and Rewrite

	- Inside the osTicket folder, download PHP Manager and URL Rewrite.
	- Follow the installation prompts and accept all terms.

4.	Set Up PHP
	- Navigate to the C:\ drive and create a new folder named PHP.
	- Go back to the downloaded zip file, extract its contents, and find the PHP folder.
	- Move the extracted PHP files into C:\PHP.

5.	Install Required Dependencies
	-	Install VC_redist.x86.
	- Install MySQL using the Typical Setup option.
	- Launch the MySQL Configuration Wizard and select Standard Configuration.
	- Important: Use the same Username and Password for MySQL (e.g., ROOT in all caps).
	- Click Next, then Execute to complete the setup.

6.	Configure IIS for PHP
	- Open IIS as Administrator.
	- Click PHP Manager, then select Register New PHP Version.
	- Locate the PHP folder on the C:\ drive, open it, and select the php-cgi.exe file.
	- Click OK, then restart IIS.

7.	Configure osTicket in IIS
	- Go back to the osTicket installation folder and extract all files.
	- 	Open the extracted folder and copy the upload folder to:
C:\inetpub\wwwroot.
	- Rename the folder to osTicket (exact spelling, including capitalization).
	- Restart IIS.

8.	Launch osTicket
	-	In IIS, open Sites, then select Default Web Site.
	-	Click Browse osTicket, and it should open successfully.

---
![ade6](https://github.com/user-attachments/assets/26d615d1-f899-4432-bafa-0bd76f8f80f9)
![ade6 (1)](https://github.com/user-attachments/assets/de7f3a89-dd50-4527-b187-e0b8c4bc872a)
![ade9](https://github.com/user-attachments/assets/8c73396f-63af-4535-9a69-0c8b041ae979)
![ade10](https://github.com/user-attachments/assets/2c7da748-63d7-49ea-8882-5c7a4eeae58c)
![ade11](https://github.com/user-attachments/assets/6d4ee13f-838e-4a11-bef3-9d1a9c19bfe3)
![ade12](https://github.com/user-attachments/assets/ed13d3c1-cee8-494b-95b2-36945b7ef696)
![a15](https://github.com/user-attachments/assets/9609f915-8e98-4b72-97f0-61c6fba8e239)
![a16](https://github.com/user-attachments/assets/8ab6b478-9a95-4c34-bb4a-7db6d3b2c854)



---
![ade13](https://github.com/user-attachments/assets/324e4773-3f9a-4128-bdca-f91a2ad8b29e)
![ade14](https://github.com/user-attachments/assets/9acf49ef-33d3-443f-a5eb-ca3281de93e6)
![ade15](https://github.com/user-attachments/assets/06ad3091-f990-42d4-9d33-2b72a2811321)
![ade16](https://github.com/user-attachments/assets/2a23b13b-b6a8-4392-91d6-5cacddb3937e)
![ade17](https://github.com/user-attachments/assets/8679b806-a1e0-4c9c-8d73-37b7329f8836)
![ade18](https://github.com/user-attachments/assets/4ee9906a-88cd-416d-9c59-ae99587ab691)
![ade19](https://github.com/user-attachments/assets/49b376de-8ee2-4c60-9a86-196e72d18268)





---

<h2>OsTicket Configuration</h2>

-	Enable Missing PHP Extensions

	- Open IIS and navigate to PHP Manager.
	- Enable any missing extensions listed on the osTicket installation page.

- Rename and Configure ost-config.php

	-	Navigate to: C:\inetpub\wwwroot\osTicket\include.
	- 	Find ost-sampleconfig.php and rename it to ost-config.php (exact spelling).
	- Right-click the file and select Properties.
	- Go to Security > Advanced.
	- Click Disable Inheritance, then Remove all entries.
	- Click Select a Principal, type Everyone, then check Full Control.
	- Click OK to apply the changes.

- Complete osTicket Installation

	- 	On the osTicket setup screen, enter a Help Desk Name and Admin Username of your choice.

- Install HeidiSQL

  - Open the osTicket installation folder and install HeidiSQL.
	 - Follow the installation steps and ensure Launch when done is checked.
 	- Open HeidiSQL and create a new session.
 	- Enter:
	  - Username: root
	  -	Password: ROOT (all caps)
 	-	If it does not connect, restart the lab and try again.

- Create the osTicket Database

	-	Once connected, right-click Unnamed and select Create New > Database.
	- Name it osTicket (exact spelling).

-	Finalize osTicket Setup

	- Go back to the osTicket setup tab.
	- In the SQL Database field, enter osTicket.
	- For SQL Username, enter root.
	- For Password, enter ROOT (all caps).
	- Click Install.
	- If successful, you should see a Congratulations screen.

- Access osTicket Admin Panel

	- Use the Staff Control Panel link to log in as an admin.
	- Regular users can access osTicket via the main URL.














