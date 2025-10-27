<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial demonstrates the complete setup and configuration process for hosting the osTicket Helpdesk System on a Microsoft Azure Virtual Machine (VM) using Remote Desktop Protocol (RDP).<br />


<h2>Environments and Technologies Used</h2>

- Deployed a Windows Server 2021 virtual machine using Azure Compute Services.
- Accessed and managed the VM via Remote Desktop Protocol (RDP).

- Installed and configured IIS, PHP, and MySQL to build a complete web hosting environment.
- Deployed and hosted osTicket for a cloud-based helpdesk and ticket management system.
- Demonstrated practical skills in server configuration, troubleshooting, and cloud service hosting.


<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Create and Configure Azure Virtual Machine
- Connect to the VM via Remote Desktop (RDP)
- Install IIS (Internet Information Services)
- Install PHP and C++ Redistributable
- Install and Configure MySQL
- Download and Configure osTicket
- Access osTicket via Browser
<h2>Configuration Steps</h2>

<img width="1880" height="812" alt="image" src="https://github.com/user-attachments/assets/21a5f03c-c98e-4276-8de3-1fb40649e7b0" />

Steps (1): 
Create and Configure Azure Virtual Machine 
(1) Logged into the Azure Portal.
(2) Selected Create a Resource → Virtual Machine. 
(3) Configured basic settings: 
    .Image: Windows Server 2021 Datacenter (Gen2) 
    .Size:Standard_B2s (2 vCPUs, 8 GB RAM) 
    .Authentication: Username and Password 
    .Inbound Ports: RDP (3389) and HTTP (80) 
Clicked Review + Create → Create.

<img width="521" height="492" alt="image" src="https://github.com/user-attachments/assets/74a0330a-7673-47e0-b039-6e0219c5e0e9" />

Step 2: 
Connect to the VM via Remote Desktop (RDP)
(1) Downloaded the .rdp connection file from Azure Portal.
(2) Opened it using Remote Desktop Connection on local PC.
(3) Entered VM credentials to log in remotely.
(4) Verified successful remote connection.


<img width="555" height="496" alt="image" src="https://github.com/user-attachments/assets/f9f77f17-b534-41ea-b4b3-48163554a3b4" />


Step 3a:
Install / Enable IIS in Windows WITH CGI (Common Gateway Interface): CGI is a critical IIS feature that allows the web server to communicate with external applications, such as PHP, to generate dynamic web content. In other words, CGI acts as a “translator” between IIS and the PHP scripts running behind osTicket. CGI is a dependents the osTicket needs for part of the World Wide Web Server: 
Go to Windows Features - World Wide Web Server - Application Development Features - CGI and click OK. to activate the CGI.


<img width="730" height="865" alt="image" src="https://github.com/user-attachments/assets/44e7af34-6c1a-4583-b012-b2689990dc5d" />


Step 3b:
This is the default IIS welcome page, which confirms that the World Wide Web Server (IIS) is active and functioning correctly after installing and enabling the CGI feature.


<img width="617" height="472" alt="image" src="https://github.com/user-attachments/assets/8bb472ef-a6cc-477c-a6ba-4b1e75a6bab4" />


Step 3c:
 IIS URL Rewrite Module installer package for 64-bit Windows systems, This is the IIS URL Rewrite Module, a Microsoft extension for Internet Information Services (IIS) that allows you to define rules for modifying (rewriting or redirecting) incoming web requests.
. Example: turning http://example.com/page?id=1 into http://example.com/page/1.



<img width="1414" height="580" alt="image" src="https://github.com/user-attachments/assets/ad2b5d60-d8c5-43b3-8ca9-523f9bb9962f" />



Step 3d: 
Install IIS (Internet Information Services)
(1) Opened Server Manager → Add Roles and Features.
(2) Selected Web Server (IIS).
(3) Expanded World Wide Web Services → Application Development Features.
(4) Checked CGI and other required options.
(5) Clicked Install, waited for completion, and verified by visiting:
The IIS welcome page confirmed a successful installation.



<img width="598" height="376" alt="image" src="https://github.com/user-attachments/assets/268e75a5-307b-428a-b063-38230eaef17c" />


Step 4a:
Install Microsoft Visual C++ Redistributable:
The Microsoft Visual C++ Redistributable provides essential runtime libraries required for running applications like PHP, IIS extensions, and osTicket on Windows.
This step ensures all required dependencies are available on your Azure Virtual Machine.
(1) Determine System Type:
    .On the Windows Server VM, right-click the Start Menu and select System.
    .Under Device specifications, check whether your operating system type is 64-bit (x64) or 32-bit (x86).
This will determine which redistributable package you need to install.
(2) Download the Redistributable:
    .Visit the official Microsoft download page:
     Microsoft Visual C++ Redistributable Latest Supported Downloads
    .Scroll to the Visual Studio 2015–2022 section.
    .Download the correct installer for your system:
     -VC_redist.x64.exe → for 64-bit systems
     -VC_redist.x86.exe → for 32-bit systems
(3) Run the Installer
.Locate the downloaded file (typically in your Downloads folder).
.Right-click the file and choose Run as administrator.
.Accept the license terms and conditions.
.Click Install.
(4) Verify Installation:
.Open Control Panel → Programs → Programs and Features.
.Look for the following entries:
-Microsoft Visual C++ 2015–2022 Redistributable (x64)
-Microsoft Visual C++ 2015–2022 Redistributable (x86)
.Confirm that the version matches the one you installed.
Restart the VM. Your Azure Virtual Machine is now equipped with the Microsoft Visual C++ runtime


<img width="617" height="507" alt="image" src="https://github.com/user-attachments/assets/41840ae8-7bbd-49ee-a655-811a424abbb6" />

Step 4b:
Install and Configure PHP
The PHP installation enables dynamic web content to run on IIS (Internet Information Services). osTicket relies on PHP to process its backend scripts and interact with the MySQL database.
(1) Download PHP for Windows:
.Go to the official PHP for Windows website:
https://windows.php.net/download/
.Under the Thread Safe section, select the latest x64 version compatible with your environment.
(Example: PHP 8.2 or 8.3 for Windows x64 Thread Safe)
.Download the .zip package — not the installer.
(2) Extract and Organize PHP Files:
.Create a folder for PHP on your system:
.Extract the downloaded .zip file into the C:\PHP directory.
.Confirm that php.exe and php-cgi.exe are inside the folder.
(3)Configure PHP in the System Path:
.Open Control Panel → System and Security → System → Advanced system settings.
.Click Environment Variables.
.Under System Variables, find Path → click Edit → click New.
.Add the path: C:\PHP
.Click OK to save all changes.
.To verify, open Command Prompt and type: php -v
-You should see your PHP version displayed.
(4) Configure PHP in IIS:
.Open IIS Manager (inetmgr from Run).
.Click on your Server Name in the left panel.
.Double-click Handler Mappings.
.On the right panel, select Add Module Mapping.
-Request Path: *.php
-Module: FastCgiModule
-Executable: C:\PHP\php-cgi.exe
-Name: PHP_via_FastCGI
.Click OK, then click Yes to confirm the creation of the FastCGI application.
(5)Configure PHP.ini File:
.Navigate to your PHP directory (C:\PHP).
.Locate php.ini-development and rename it to: php.ini
.Open php.ini in Notepad (Run as Administrator).
.Find and enable the following extensions by removing the semicolon (;) at the start of each line: 
-extension=mysqli
-extension=curl
-extension=gd
-extension=mbstring
-extension=intl
-extension=xml
.Save and close the file.


<img width="622" height="468" alt="image" src="https://github.com/user-attachments/assets/32343641-6e2e-4db3-bb10-1b7fe196c4a0" />


<img width="626" height="473" alt="image" src="https://github.com/user-attachments/assets/895c6098-9c2e-4a44-8b09-135daaf9eff4" />


<img width="625" height="476" alt="image" src="https://github.com/user-attachments/assets/90cf3323-d95e-49a3-b61e-a2b3c8176f6f" />


Step 5a:
Install and Configure MySQL
MySQL is the database management system used by osTicket to store and retrieve ticketing data, user details, and system configurations.
In this step, you’ll install, configure, and verify MySQL on your Windows Server (Azure VM).
(1)Download MySQL Installer
.Visit the official MySQL downloads page:
https://dev.mysql.com/downloads/installer/
.Choose MySQL Installer for Windows (select the Community Edition).
.Download the Windows (x64) MSI Installer.
.Save it to your VM’s Downloads folder.
(2)Run the MySQL Installer
.Locate the downloaded installer (mysql-installer-community-x.x.x.msi).
.Right-click and select Run as administrator.
.Choose Server Only setup type and click Next.
.Follow the prompts and accept the license agreement.
.Click Execute to begin installation.
(3)Configure MySQL Server:
.In the Configuration section:
-Choose Standalone MySQL Server / Classic MySQL Replication.
-Select Development Computer as the configuration type.
-Leave port 3306 as default.
.Choose Authentication Method:
-Select Use Strong Password Encryption for Authentication (RECOMMENDED).
.Set a root password (make sure to save it securely).
.Click Next → Execute to apply configuration settings.
.Once completed, click Finish.
(4)Verify MySQL Service:
.Open Services (press Windows + R, type services.msc).
.Locate MySQL in the list and ensure its Status shows Running.
.If not running, right-click MySQL → select Start.
(5)Configure a Database for osTicket:
.Open MySQL Command Line Client or MySQL Workbench.
.Log in using your root credentials.
.Create a new database and user for osTicket:"CREATE DATABASE osticket;
CREATE USER 'ostuser'@'localhost' IDENTIFIED BY 'Password123!';
GRANT ALL PRIVILEGES ON osticket.* TO 'ostuser'@'localhost';
FLUSH PRIVILEGES;"
.Verify the database was created:"SHOW DATABASES;"
(6)Test Database Connection:
.To ensure MySQL is working correctly: Open Command Prompt and type:"mysql -u ostuser -p"
.Enter the password you created.
.If you see the mysql> prompt, the database connection is successful.
(7)Optional Security Configuration:
-For production or long-term hosting environments:
.Disable remote root access:"UPDATE mysql.user SET Host='localhost' WHERE User='root';FLUSH PRIVILEGES;"
-Regularly back up the osTicket database using:"mysqldump -u ostuser -p osticket > C:\backups\osticket_backup.sql"
MySQL Server is now fully installed and configured on your Azure Virtual Machine.
You have successfully created a dedicated database and user for osTicket, preparing your system for the final deployment stage.


<img width="924" height="556" alt="image" src="https://github.com/user-attachments/assets/b671d73f-1cfb-4180-a999-0c41884eb5e7" />

5b:
Register PHP from within IIS:
This just means we are making the Web Server aware of the existence of PHP.
IIS is now fully aware of PHP and can process dynamic PHP scripts. This step ensures the web server can properly handle osTicket’s PHP-based components and serve dynamic pages to end users.


<img width="1419" height="675" alt="image" src="https://github.com/user-attachments/assets/60ebe993-523e-4689-938f-4c668ba0ffc9" />

5c:
Reload IIS (Open IIS, Stop and Start the server)


<img width="1017" height="871" alt="image" src="https://github.com/user-attachments/assets/c6850943-6e01-49b9-b0fa-0e6838fb94b6" />

(6) Accessing the osTicket Site via IIS 
1 Once osTicket is deployed in IIS:
. Open *IIS Manager* and navigate to the *Sites* node in the *Connections* panel.  
. Expand *Default Web Site* and locate the *osTicket* application.  
. In the *Actions* pane on the right, double-click *Browse *:80*.  
. The osTicket site will open in your default web browser, confirming that IIS is correctly serving the application on port 80. The osTicket site is now live locally through IIS, ready for database configuration and initial setup.


<img width="1188" height="855" alt="image" src="https://github.com/user-attachments/assets/28cbd351-db49-4a02-8113-284d4626ca2f" />



