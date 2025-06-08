# active-directory-environment
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Domain Services Hosted in Microsoft Azure</h1>
This project walks you through creating an Active Directory domain controller and DNS services using Azure VMs to mimic a typical office network.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Core Phases of System Installation and Adjustment</h2>

- Create a Virtual Network
- Deploy a Windows Server VM 
- Install the Active Directory Domain Services 
- Promote the server to a Domain Controller
- Verify Active Directory and DNS functionality

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/7903b8c1-cb50-4453-aeb5-315175dee704" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connect to the VM using Remote Desktop (RDP) from your local machine. Open Server Manager, click on Add roles and features, and follow the wizard. Select Active Directory Domain Services and include the required features. Finish the wizard and allow the server to install the necessary components.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/cd4a0adf-aeed-4efa-9d74-440d9444f48f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Server Manager, you'll see a flag icon with a notification to promote the server. Click the notification and choose to add a new forest, then enter your domain name (e.g., corp.local). Select the option to install DNS, set a password for Directory Services Restore Mode, and proceed with the default settings. After the configuration is applied, the server will automatically restart.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/89db3be0-4d3c-41ef-860c-7059f768f40c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  After rebooting, open Server Manager > Tools, and check both Active Directory Users and Computers and DNS Manager to confirm your domain and DNS zones were created. If you’ve created a new domain user (in Active Directory Users and Computers), you can now use that account to join another VM to the domain. On a second VM in the same virtual network, open System Properties, click Change, select Domain, and enter the domain name. When prompted, enter the domain user's credentials — successful domain joining confirms that both AD and DNS are functioning properly.
</p>
</p>
<br />
