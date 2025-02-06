<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Active Directory Deployment Steps</h2>

<p>
<img src="https://i.imgur.com/Kg5eCfI.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/PSe5QH1.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
Firstly, create a resourse group and virtual network for the two virtual machines we're going to create.
</p>
<br />

<p>
<img src="https://i.imgur.com/Kg4eflv.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/OV3haPW.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first VM we're creating is the domain controller, choose 'Windows Server' for the image. Also in the 'Networking' Tab of the creation, choose the virtual network you made previously.
</p>
<br />

<p>
<img src="https://i.imgur.com/m9z8Kd0.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/tWFUl0J.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/CkuOCSl.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<p>
The second VM will be our client machine for the domain, choose 'Windows 10' for the image with 2 virtual cpus. You also need to select the same virtual network you created beforehand in relation to the domain controller.
</p>
<br />
