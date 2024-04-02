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

- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
- Install Web Platform Installer
- Install osTicket v1.15.8
- Download and Install HeidiSQL
- Created database for "osTicket
- Clean up
- Change File Permissions

<h2>Installation Steps</h2>

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/25239267-f8d8-4fd2-ac4d-4dd1726c4824)

</p>
<p>
Step 1: We can do a quick search for Virtual Machine and as we create the virtual machine, we will have the option to create the Resource Group. Here we select Create New to name the name the Resource Group 'RG-osTicket' and build out the Virtual Machine (VM) with the provided settings pictured (Above).
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/8e2d32f8-4202-40b6-b859-74e6846098f9)

</p>
<p>
Be sure to check the box recognizing 'I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights.' or else you will receive a validation error message when you choose to 'Review + Create'. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/4eab6508-bc90-421a-b7c1-b4607856e4a7)

</p>
<p>
We will need connect to our Virtual Machine with Remote Desktop using the VM's public IP address. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/bdd479a6-d084-4784-aa57-b7caf99605ac)

</p>
<p>

To connect to the virtual machine, we search on the local machine for 'Remote Desktop Connection' and the following window opens and you can now copy and paste the public IP address into the provided space. Then press the Connect button. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/40d6a5dd-9d39-4961-acda-801158df40cb)

</p>
<p>
Once you are connected and inside the virtual machine we will need to install the Web Platform Installer. To install the Web Platform Installer we will search for the Control Panel --> under programs select Uninstall a Program. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/feb677c2-6238-4b58-8a38-7d528f5ce837)


</p>
<p>
After we've reached the next page, we can now select to Turn Windows features on or off --> then enable the 'Internet Information Services' (IIS) from the available services. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/93b1ef3d-da44-4cf0-bc5b-2109f3802efa)


</p>
<p>
Now we can download and install Web Platform Installers. Web Platform Installers (WebPI) provides a simplified installation workflow for installing common open source web applications and web platform technologies. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/fe66e424-3737-4fee-ada3-0f3e3adb2fda)


</p>
<p>
Once WebPI is installed, we can now add MySQL 5.5 database, PHP 5.6.31, and the various verisons of between PHP (x86) 7.0 and 7.3.(Above and Below)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/ebdb6dfc-9e33-4f37-8ba1-e5a137f5d88d)





![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/08b252f1-bcf9-4bda-9eb0-7d5d4ae6482f)


</p>
<p>
MySQL 5.5 will require a name and password, root and Password1 respectively when you try to install. Make note of the name / password in a text file as you will need it again later on in the installation process.(Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/967f1a7a-6e1b-4cf4-b390-25e4e8cb20ea)


</p>
<p>
If necessary, fix any failures (download from within lab files: Fix any failures in the installation by going to Google Drive to download and install PHP 7.3.8, PHP Manager, and Microsoft Visual C++ 2009 Redistributable Package.

From the downloaded files, we can now install and extract the osTicket file. Extract and copy the “upload” folder INTO c:\inetpub\wwwroot 3. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”(Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/c69562e9-60be-4032-8773-64005d4e88d6)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/9f41d4ee-cd47-47b9-9e5e-41ed25fb15f9)



</p>
<p>
-Reload IIS (Open IIS, Restart the server)** 1. Go to sites -> Default -> osTicket 2. On the right, click Browse *:80. (Above)
</p>
<br />


<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/6c4e1ea0-bf5f-4527-b985-d4327895916c)


</p>
<p>
Once browse: 80 is selected a browser window will open presenting osTicket installer page along with the recommendation/prerequisites of use. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/151fefea-4173-4c14-8399-9b67d53465ec)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/12b6dd8d-1c6c-43b3-953f-96eabaffda44)



</p>
<p>
Next we'll go back to IIS, sites -> Default -> 1. osTicket 2. Double-click PHP Manager 3. Click Enable or disable an extension 1. Enable: php_imap.dll 2. Enable: php_intl.dll 3. Enable: php_opcache.dll - (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/eb88d52b-7b68-4e5e-b999-1f73bcf1e04b)


</p>
<p>
Refresh the osTicket site in your browser to see what has changed after enabling the PHP extensions. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/f9fd1cfa-a19f-4103-a1cd-c70a45246213)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/dc056301-fc32-4b1e-8884-284066d11801)



</p>
<p>
 Rename: From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php ---> To: C:\inetpub\wwwroot\osTicket\include\ost-config.php. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/906c7294-196b-4c8c-81f5-10f5c8ef5b23)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/95f16c7b-99b0-4da7-ac73-f09acc37e61f)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/57e5abb9-c900-439a-95ce-85009399ca82)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/f1c66e35-25cf-4531-832f-8d69f942377e)





</p>
<p>
Assign Permissions: ost-config.php To change the permissions, right-click ost-config --> select 'properties' --> select the 'Security' tab at the top --> select the 'Advanced' button1. Disable inheritance -> Remove All 2. New Permissions -> Everyone -> All. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/178ccfc9-1a00-48b8-a082-942bf17fb3f5)


</p>
<p>
Then add new permissions for everyone and give Full Control.(Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/e69cbf8b-3409-4766-b3f1-5d8c38c3b112)


</p>
<p>
 After returning to the browser windows with osTicket installer and press 'Continue', you will now see the below form to complete before continuing. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/6376ed97-d200-4159-a8ef-074746d3abcb)


</p>
<p>
Download and install HeidiSQL from Google Drive using the provided defaults that are available in the install wizard. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/955d9ff1-c07e-41a2-a779-03404cf10dea)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/4c719f92-01cd-4e7c-a5c1-927ac12696f4)



</p>
<p>
Next we will do the following in HeidiSql:

1.Create a new session, username:root/password:Password1
2.Connect to the session
3.Create a database called “osTicket”. (Above)
</p>
<br />

<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/dfe6d937-d7f0-409f-9459-0e3ae4c63fc8)




</p>
<p>
Created database for "osTicket": (Above)
</p>
<br />
<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/2a17fc0e-e618-4509-a60b-d81acd4e0c66)





</p>
<p>
After the database is created, we can now enter those details into osTicket Installer

(MySQL Username: root)
(MySQL Password: Password1)
(Click “Install Now!”)
Congratulations, hopefully it is installed with no errors!. (Above)
</p>
<br />
<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/7edad007-c926-492f-b1c0-48eae8bdc0f4)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/7e25a9b3-41f6-4830-83fc-948f2491372a)





</p>
<p>
Results below are from of choosing for "Your Staff Control Panel" or "Your osTicket URL:" (Above)
</p>
<br />
<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/ced80421-6bcb-4402-a725-79d1a68d4389)




</p>
<p>
 "Your osTicket URL" will direct us to the "End User" Portal where Users can submit tickets for assistance from the help desk. (Above)
</p>
<br />
<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/7416b4c6-d78b-49a3-a01e-0f43d1345c94)




</p>
<p>
 - Clean up

1.Delete: C:\inetpub\wwwroot\osTicket\setup
2.Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
3.Login to the osTicket Admin Panel ([http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)). (Above)
</p>
<br />
<p>

![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/c15caeaf-2c9f-4bf8-b0a1-a1c2dabb34c9)![image](https://github.com/DariusEpps/osticket-prereqs/assets/161891928/7c593933-2cf4-4a66-8e08-3aa2730ddd60)





</p>
<p>
Set Permission to "Read" only can be acheived by choosing to right-click on 'ost-config.php' --> select properties --> select the 'Security' tab near the top --> then click the 'Advanced' button (not pictured below) --> once advanced settings is selected, you can now select the 'Everyone' principle and now we can select to choose 'Read' only as the preferred permission(s). (Above)
</p>
<br />
