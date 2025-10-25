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

<img width="1897" height="687" alt="image" src="https://github.com/user-attachments/assets/f90725dc-7c62-47d9-9a0c-92012f6e48f6" />

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


<img width="1414" height="580" alt="image" src="https://github.com/user-attachments/assets/ad2b5d60-d8c5-43b3-8ca9-523f9bb9962f" />

Step 3: 
Install IIS (Internet Information Services)
(1) Opened Server Manager → Add Roles and Features.
(2) Selected Web Server (IIS).
(3) Expanded World Wide Web Services → Application Development Features.
(4) Checked CGI and other required options.
(5) Clicked Install, waited for completion, and verified by visiting:
The IIS welcome page confirmed a successful installation.

<img width="1188" height="855" alt="image" src="https://github.com/user-attachments/assets/28cbd351-db49-4a02-8113-284d4626ca2f" />

Admin Panel  dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

<img width="1218" height="479" alt="image" src="https://github.com/user-attachments/assets/900f37ab-15bc-4ad6-8883-136e039a7d95" /> 

Roles

<img width="1207" height="482" alt="image" src="https://github.com/user-attachments/assets/57cebfb9-0bd3-4ee9-8716-bb67235866be" />
3 SLA was successfully Created

<img width="1202" height="563" alt="image" src="https://github.com/user-attachments/assets/97aaf870-1065-4c0b-9d3c-f62ddc3bb38c" />
Help Topic was successfully Created
