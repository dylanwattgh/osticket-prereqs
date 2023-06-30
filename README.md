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

<h2>List of Prerequisites and Basic Steps</h2>

- Enable/Install IIS in Windows *WITH*
  - CGI and Common HTTP Features
  - IIS Managment Console
    
- Download/Install PHP Manager for IIS
- Download/Install Rewrite Module
- Create C:\PHP directory
- Download/Install PHP 7.3.8 and unzip into C:\PHP
  
- Download/Install VC_redist.x86
- Download/Install/Setup MySQL 5.5.62 
- Register PHP from within IIS
  
- Install OSTicket
- Set Permissions within OSTicket
- Install/Setup HeidiSQL

- Clean Up 


<h2>Installation Steps</h2>
<p><strong>
We start by mentioning that this is all done within Microsoft Azure using a virtual machine running Windows 10.</strong></p>
<br />

![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/25bf40c1-a820-46b5-a1b3-de47f94d8210)
<p>
We start within the VM and we navigate to Windows Features because we have to enable a few features here. Find IIS (Internet Information Services), then within the World Wide Web Services dropdown, we navigate to Application Development Features and select CGI. After that we can go back to the WWWS and find the Common HTTP Features dropdown, within here we check off all the boxes for simplicities sake. We can then press OK and windows will apply the changes that we've made.</p>
<br />

<p>
  
![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/49cac8af-54ee-4f23-a1b2-32b75b52066d) ![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/eb1b73b4-88d8-44a3-a8af-df3d3fcaa9df)</p>
<br />
<p>
  Next up, we need to install PHP Manager for IIS and Rewrite Module. After these have both been installed and setup we create a simple directory called C:\PHP. We then download PHP 7.3.8 which is a zip file, so we'll extract the contents into the PHP directory we just created.</p>
<br />

<p>
  
![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/d635461b-84cd-4ffc-9675-0c74c92a91f8) ![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/d3182510-1d72-44e9-8c46-cdaa23fff65f) 
![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/36561175-9d11-41a1-b69d-a7b493a227c1)</p>
<br />
<p>
  We then install and setup both VC_redist and MySQL 5.5.62. Once those have been setup, we open IIS as administrator and register PHP from within IIS. Then reload IIS.</p>
<br />

<p>
  
![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/ded861b4-170d-426d-8f16-1211e7197c97)
![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/82ebb6f0-5b09-45f2-a98e-5c0ddc1550f8) ![heidi osticket database](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/6aa771af-88d3-4bc8-b11a-e04b023346e9)</p>
<br />
<p>
  Now we finally install osTicket v1.15.8. We then extract the uploads folder and place it into C:\inetpub\wwwroot , then rename the uploads folder to 'osTicket'. Within IIS, we need to enable some extensions. Including  (php_imap.dll), (php_intl.dll), and (php_opcache.dll). </p>
<p>
  Also we need to rename ost-sampleconfig.php </p>
<p>
  From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php ------->
  To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
<p>
After this we install and setup HeidiSQL. Create a database names 'osTicket'. Then we can access our osTicket system through the browser links.</p>
<p>
  
  ![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/ff23b604-dd91-479c-9756-a81828a424b8) </p>
<br />



<p>
  
  ![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/a8a97e1e-21f3-4397-9155-3c915888e9e1) ![image](https://github.com/dylanwattgh/osticket-prereqs/assets/108493054/0d89d315-ff2e-41af-ba9e-3e7aae089e5c)
</p>
<br />
<p>
  Lastly we can delete C:\inetpub\wwwroot\osTicket\setup and set READ ONLY permissions to C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
<br />









