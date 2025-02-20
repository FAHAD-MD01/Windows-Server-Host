# Windows-Server-Host

---

📌Deploy Windows Server on AWS EC2

Project Description:

This project provides a step-by-step guide to deploying a Windows Server on AWS EC2. The guide includes selecting an appropriate AMI, configuring security settings, connecting via RDP, and installing necessary software for server management.


------------------------------------

Prerequisites Used in it :

Before proceeding, ensure you have:

An AWS account

If u have any AWS acc then open the dashboard and Select the Service"Ec2"
         |
(Amazon EC2 (Elastic Compute Cloud) is a scalable cloud computing service that provides resizable virtual servers to run applications on AWS)

Basic understanding of EC2 and networking

A Windows system or RDP client to connect to the instance

------------------------------------

Installation Steps :

Step 1: Launch a Windows EC2 Instance

1. Log in to AWS Console


2. Navigate to EC2 Dashboard


3. Click on Launch Instance


4. Select an AMI: Choose an appropriate Windows Server AMI (e.g., Windows Server 2022)


5. Select an Instance Type (e.g., t2.micro for free tier)


6. Configure Instance Details, keeping default settings


7. Add Storage (default is 30GB for free tier)


8. Configure Security Group:

Allow RDP (3389) for remote access

Allow HTTP (80) and HTTPS (443) if needed



9. Click Launch and create/select a key pair


10. Wait for the instance to start




------------------------------------

Step 2: Connect to Windows EC2 Instance

Using Remote Desktop (RDP)

1. Go to the EC2 Dashboard


2. Select your Windows EC2 instance


3. Click on Connect → RDP Client


4. Download the Remote Desktop File


5. Click Get Password, upload your private key (.pem), and decrypt the password


6. Open Remote Desktop Connection (mstsc) on your local machine


7. Enter the Public IP Address of the EC2 instance


8. Use the Administrator username and decrypted password


9. Click Connect and accept any warnings




------------------------------------

Step 3: Configure Windows Server

1. Open Server Manager and configure roles as needed


2. Install necessary updates and software


3. Set up IIS for web hosting (if required):

Open Server Manager → Add Roles & Features

Install Web Server (IIS)



4. Enable remote management and additional security settings




------------------------------------

Commands Used

1. Check Network Configuration

ipconfig /all

2. Enable Remote Desktop via PowerShell

Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name 'fDenyTSConnections' -Value 0
Enable-NetFirewallRule -DisplayGroup "Remote Desktop"

3. Install IIS Web Server

Install-WindowsFeature -name Web-Server -IncludeManagementTools

4. Restart the Server

Restart-Computer -Force


------------------------------------

Usage Instructions

To Access via RDP: Use mstsc and the EC2 Public IP

To Host a Website: Place your files in C:\inetpub\wwwroot\

To Install Software: Use PowerShell or choco install <software>



------------------------------------

🎯 Conclusion

This guide helps deploy and configure a Windows Server on AWS EC2 efficiently. Further optimizations include configuring Active Directory, setting up domain controllers, and automating server maintenance.

------------------------------------🔗Thank You!

Thank you for exploring this project on deploying a Windows Server on AWS EC2. I hope this guide helps you set up and manage your cloud-based Windows environment efficiently.


Feel free to contribute, suggest improvements, or reach out for any querie


