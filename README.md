<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployment and Configuration </h1>

Building on the first project that set up our simulated Active Directory environment, we now move to the next step in our tutorial series. Welcome to the "Active Directory Deployment and Configuration" project, where we explore the details of deploying and refining an Active Directory system. This project is designed to impart a fundamental understanding of Active Directory services, emphasizing key aspects such as installation, forest creation, user account administration, domain integration, and customized Remote Desktop access.
</p>

<h2>Key Objectives:</h2>

Active Directory Installation
-  Configure and install Active Directory services on the designated Domain Controller virtual machine.

Forest Creation
- Establish a new Active Directory forest.

Administrator Account Creation
- Create and administer user accounts with administrative privileges for effective management of the Active Directory environment.

Domain Joining
- Integrate the Client-01 virtual machine into the established domain, ensuring seamless communication with the Active Directory infrastructure.

Remote Desktop Setup
- Configure Remote Desktop access specifically tailored for non-administrative users, enhancing user accessibility while maintaining security protocols.




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Configuration Steps</h2>

<h3>Step 1: Install Active Directory in DC-01</h3>

- In the Server Manager dashboard, click Add roles and features and continue the setup
  
![image](https://github.com/TechwTre/configure-ad/assets/126909509/f7d04c78-25d7-4b33-b44f-32e07f5e1288)
</p>
<br />

Select Active Directory Domain Services and finish the installation 
</p>

<h3>Step 2: Promote DC-01 to Domain Controller </h3>

- Once the installation is done, notice the flag on the top left of the Server Manager
- Click on the flag and promote DC-01 to Domain Controller.

![image](https://github.com/TechwTre/configure-ad/assets/126909509/310f6513-bd03-407e-b362-53cc8f86c04f)
</p>
<br />

-  We will now add a new Forest and set the Root domain name to “mydomain.com”
<p>
  
![image](https://github.com/TechwTre/configure-ad/assets/126909509/c1f6fbb6-70d8-40e1-9ac5-c4512e3cd7be)
</p>
<br />

- Finish setup and restart DC-01
- Log back in with “your username"@mydomain.com

<h3>Step 3: Creating an Admin in Active Directory </h3>

- Once DC-01 has rebooted, click on tools and select Active Directory Users and Computers
- Right click on mydomain.com and select new and click on Organizational Unit

![image](https://github.com/TechwTre/configure-ad/assets/126909509/ad63487b-5a4a-4b8e-bff6-476cce6be242)
</p>
<br />

We will be creating an OU named _EMPLOYEES and _ADMINS 
</p>

![image](https://github.com/TechwTre/configure-ad/assets/126909509/2f2c4428-e563-4a84-9c37-ece85e0f5372)
</p>
<br />

Right click on Users and create a new user named Jane Doe with the username jane_admin
</p>

![image](https://github.com/TechwTre/configure-ad/assets/126909509/ba885afa-1362-4fec-8046-db5de0b74b3b)
</p>
<br />

Now we will turn Jane Doe into an admin by right clicking her name and adding her to the “Domain Admins” Security Group
</p>

![image](https://github.com/TechwTre/configure-ad/assets/126909509/e1c2ae4f-d0da-4b80-b152-9838ef5dda89)
</p>
<br />

Logout of DC-01 and log back in with Jane Doe’s credentials
</p>

![image](https://github.com/TechwTre/configure-ad/assets/126909509/854401e3-e322-4545-a842-545a2696944e)
</p>
<br />

<h3>Step 4: Join Client-01 to domain</h3>

For Client-01 to join the domain, we first have to set it’s DNS server as DC-01’s private address.
</p>

- In the Azure Portal, select Client-01 -> Networking -> Network interface and click on DNS servers

![image](https://github.com/TechwTre/configure-ad/assets/126909509/89dab9af-6460-49cb-96e1-395c49ed7901)
</p>
<br />

Select a custom DNS server and type in the private ip address of DC-01 and restart Client-01
</p>

![image](https://github.com/TechwTre/configure-ad/assets/126909509/1b67e90e-6bb5-4b99-80e9-1290e3db94c8)
</p>
<br />

Now log back in to Client-01 using your original admin credentials. Click start and go to Settings > Rename this PC (advanced) > Change and add “mydomain.com” and login with the admin credentials previously created (jane_admin) 
</p>

![image](https://github.com/TechwTre/configure-ad/assets/126909509/5a24a834-d8f8-47d6-b31a-bee6633d9df9)
</p>
<br />

Once Client-01 has been added, the VM will restart.
</p>

<h3>Step 5: Setup Remote Desktop for non-administrative users </h3>

- Log back into Client-01 using jane_admin and open Settings > Remote Desktop> User Accounts and click “Select users that can remotely access this PC”
- Add Domain Users

![image](https://github.com/TechwTre/configure-ad/assets/126909509/e5a31a67-2d14-498d-afe9-bc6f2b914f8b)
</p>
<br />

This will allow normal users to login to Client-01
</p>

<h2>Lesson Learned</h2>

We've successfully concluded the Active Directory Deployment and Configuration phase. Through configuring Active Directory on the Domain Controller, we established our infrastructure by creating a forest, administrator account, and ultimately integrating Client-01 into the domain. In the upcoming project, we'll be generating users and simulating various Active Directory scenarios.
</p>
<br />
