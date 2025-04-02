
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

First ope azure and navigate to virtual machines, create a virtual machine, name the resouce group what you like, chose what region you like and make sure it is imaging `Windows 10 Pro` and you are using a good size i reccomend 2vcpus or higher. then create a user name and password I used labuser and Cyberlab123! as mine. Once your virtual machine is up  go to its home screen and locate the public ip address, then log into it with Remote desktop(RDP).

---



---

<h2> OSTicket Installation </h2>

Now that we are logged into our vm lets download osTicket. open the windows explorer and copy this [osTicket zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and extract files on the desktop. While that is happening we are going to install **IIS** with **CGI**. click start go to the control panel go to programs then click turn windows features on or off then go to  internet Information Services > world wide web servers > Application and development features then click CHI and OK. then in the osticket folder download php manager and Rewrite go through and accept everything. then go to the c drive and make a folder called `PHP`, thnen go to the zipped file click extract file and find the PHP file you just made. then install VC_redist.x86 and mysql do typical set up then launch the wizard and do standard config. **Do Not mess the part up it will ruin the entire lab use the same password and user or write it down**, I used the user nd password ROOT in all caps hit next then execute. OPen IIS as an admin open php click register new php and find the folder on the C drive and open the folder and click the grey config and restart ISS. then go back into the installation folder and extrat all on the os ticket file open file copy the upload folder into c:\inetpub\wwwroot and change the name to this exactly **osTicket** and then reload ISS. In ISS open site open default website and browse os ticket and it should work.

<h2>OsTicket Configuration</h2>

Now that the site is up we need to make a few tweaks for the next lab. As you can see its missing some of the extensions. Go back to ISS and open PHP and enable the missing extensions. now we are going to go to www\root > osTicket > include > ost-sampleconfig.php and rename it to this exatcly **ost-config.php**. AFter youve renamed it right click it > properties > security > advanced > disable inheritance> remove > select principal > Enter EVeryone> and click full control. Now we can continue on the os ticket screen. name your help desk name and admin user name what ever you like. Now we have to intall HeidiSQL, open osTicket installation file and intall it. Next throught everthing and make sure the launch when done is checked. then open a new session and enter your password ROOT and the user lower case root and if that doesnt work youll have to restart the lab. If it worked a new screen should pop up the right click unnamed  then click create new and type in **osTicket** exactly.
















