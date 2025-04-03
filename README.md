
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

[ade1](https://github.com/user-attachments/assets/d4fb92ed-bfff-4a5d-8360-129bbbc8e1d6)
![ade2](https://github.com/user-attachments/assets/4cf99ac6-b259-4c49-95f7-71f864e9f6e8)
![ade3](https://github.com/user-attachments/assets/094eb878-0b0f-474c-9902-4293cb6de831)
![a4](https://github.com/user-attachments/assets/693dddb3-c309-45e4-b363-98ff9a773473)
![ade5](https://github.com/user-attachments/assets/7e0a10f7-3440-4834-ab3c-5043f76a0e0a)

---

<h2> OSTicket Installation </h2>

Now that we are logged into our vm lets download osTicket. open the windows explorer and copy this [osTicket zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and extract files on the desktop. While that is happening we are going to install **IIS** with **CGI**. click start go to the control panel go to programs then click turn windows features on or off then go to  internet Information Services > world wide web servers > Application and development features then click CHI and OK. then in the osticket folder download php manager and Rewrite go through and accept everything. then go to the c drive and make a folder called `PHP`, thnen go to the zipped file click extract file and find the PHP file you just made. then install VC_redist.x86 and mysql do typical set up then launch the wizard and do standard config. **Do Not mess the part up it will ruin the entire lab use the same password and user or write it down**, I used the user nd password ROOT in all caps hit next then execute. Open IIS as an admin open php click register new php and find the folder on the C drive and open the folder and click the grey config and restart ISS. then go back into the installation folder and extrat all on the os ticket file open file copy the **upload** folder into c:\inetpub\wwwroot and change the name to this exactly **osTicket** and then reload ISS. In ISS open site open default website and browse os ticket and it should work.

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

Now that the site is up we need to make a few tweaks for the next lab. As you can see its missing some of the extensions. Go back to ISS and open PHP and enable the missing extensions. now we are going to go to www\root > osTicket > include > ost-sampleconfig.php and rename it to this exatcly **ost-config.php**. AFter youve renamed it right click it > properties > security > advanced > disable inheritance> remove > select principal > Enter EVeryone> and click full control. Now we can continue on the os ticket screen. name your help desk name and admin user name what ever you like. Now we have to intall HeidiSQL, open osTicket installation file and intall it. Next throught everthing and make sure the launch when done is checked. then open a new session and enter your password ROOT and the user lower case root and if that doesnt work youll have to restart the lab. If it worked a new screen should pop up the right click unnamed  then click create new and type in **osTicket** exactly. then go back on the os ticket tab  in the blank SQL Database put osTicket and root  as the SQL username and **ROOT** password  and click intall. it should give you a congradulations screen and then you can sign into our admin account with your staff control panel link and users withe the osTicket URL.
















