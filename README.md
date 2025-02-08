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

</p>
1) Firstly, create a resourse group and virtual network for the two virtual machines we're going to create.
</p>
<p>
<img src="https://i.imgur.com/Kg5eCfI.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/PSe5QH1.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />

<p>
2) The first VM we're creating is the domain controller, choose 'Windows Server' for the image. Also in the 'Networking' Tab of the creation, choose the virtual network you made previously.
</p>
<p>
<img src="https://i.imgur.com/Kg4eflv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/OV3haPW.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
3) The second VM will be our client machine for the domain, choose 'Windows 10' for the image with 2 virtual cpus. You also need to select the same virtual network you created beforehand in relation to the domain controller.
</p>
<p>
<img src="https://i.imgur.com/m9z8Kd0.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/tWFUl0J.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/CkuOCSl.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
4) Go to the domain controller's network settings and click it's network interface card. Change the NIC private IP Address to 'static'.
</p>
<p>
<img src="https://i.imgur.com/rGzyKBh.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/kcW38zQ.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
5) Now, sign into your domain controller VM, open and disable Windows Firewall (for testing connectivity).
</p>
<p>
<img src="https://i.imgur.com/mlsH9BZ.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/PixTx5K.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/h0QxLqe.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/HLkwtlP.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/YPMcMfT.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
6) Copy your domain controller's private ip address. aThen make your client VM's DNS server custom to be the private ip address of your domain controller.
</p>
<p>
<img src="https://i.imgur.com/PkT7AK1.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/6X7o8Fw.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/ry4Bb5I.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
7) Restart your client VM and sign in with Remote Desktop.
</p>
<p>
<img src="https://i.imgur.com/kTxwYro.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/EE20zzu.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
8) Run Powershell and ping your domain controller's private ip address to test it's connectivity.
  Run 'ipconfig /all' in Powershell to determine the client's DNS server and domain controller's private ip is the same.
</p>
<p>
<img src="https://i.imgur.com/7j95VDi.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/zrU9pLw.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/U3UeOgZ.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
9) Log into your domain controller, open Server Manager and 'Add roles and features'.
  Inside the wizard, select 'Active Directory Domain Services' in the 'Server Roles' Tab. 'Restart the destination server automatically' in the 'Confirmation' tab, and install.
</p>
<p>
<img src="https://i.imgur.com/xGXJlbZ.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/wT9nYwI.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/o4X2NM5.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/CNwYIX6.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/Q8k1Mms.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/nt7EAxU.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/G4Ms7us.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/BrjKsoW.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
10) Back in the Server Manager, click the flag notification at the top right and promote the server to a domain controller.
  Add a new forest and choose a root domain name, (I chose mydomain.com for the sake of lab practice).
  Choose a password for the domain and create a DNS delegation.
  Install Domain Services and let the VM restart.
</p>
<p>
<img src="https://i.imgur.com/adq9DF1.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/kFeKo7G.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/6f8ZCUg.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/5G5hsNu.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/CkjwRYx.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/OHTjQjr.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/7ACzvyo.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/5UwvocT.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/sFyw3Hh.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<br />
