# Active-Directory
Setup Active Directory and maintain users
Active Directory with PowerShell
<h1>Setup Active Directory Lab</h1>

<h2>Environments and Technologies Used</h2>

- Active Directory
- OracleBox (Virtual Machines/Computer)
- PowerShell
- Windows Server

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Accomplishments of the Lab Performed</h2>
- Active Directory Administration
- PowerShell
- Automated Provision, maintaining and deprovisioning user accounts
- Setting up Remote Access Server aka RAS features to support NAT slash PAT
- Implementation and maintenance of Windows DNS and DHCP services
- Configuration of Windows File Servers with implementation of quotas and NTFS permsissions.


<h2>STEPS FOR THE ACTIVE DIRECTORY LAB</h2>

- ACTIVE DIRECTORY ADD USERS WITH POWERSHELL

- Download and install Oracle VirtualBox and the ExtensionPack- this will run the Virtual Machines - after pics, continue default settings
- Download a Windows 10 ISO and a Server 2019 ISO 64-bit edition - to install the 2 operating systems on 2 separate virtual machines
once everything is downloaded and installed, going to create first virtual machine which will be the domain controller[NAT pic in network] = house the Active Directory. This virtual machine will have 2 Network Adapters ; 1 is going to be used to connect to the outside internet and the 2 connects to the internal virtual box private network.[network changed to internal]
- Install service 2019 on virtual machine [pic of the file choose virtual option]start - and assign ip addressing for the internal network -[network icon] [change adapter options][ethernet 1 home address][renamed internet and internal][add IP address for the internal] the external will automatically get ip addressing from home network {rename ] RESTART machine
- Name the server and then we’re going to install Active Directory 
- Create domain and configure NAT [couple of pics add roles, including active directory domain services][yellow flag] [mydomain.com]and routing so clients on the private network can reach the internet through the domain controller 
RAS/NAS[add roles and features again][remote access] [install routing][tools routing and remote access][configure and enable] [internet]
- Set up a DHCP on the domain controller so it can automatically get an IP address [add roles again][dhcp server] Tools, dhcp [ip address range]
- Run powershell script https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbVQzcXFkQ3EzTnVXOVdKZEhVNXMzdE1zbVRMd3xBQ3Jtc0tuTlVxa280NGFucVVpOG5NRnpIUmZFdzQyYWtocGNqZmV5SDJxQ3gySTBLaVJBNnl1Ykw1STVoZGJvOVFXNnpoejJ5ZDY4MWNGODdFdzNyY2I1eWhYWVJUVmxISU8xVmU5NElTWC16R1ZMQm5RZjNtRQ&q=https://github.com/joshmadakor1/AD_PS/archive/refs/heads/master.zip&v=MHsI8hJmggI on domain controller that will automatically create 1000 users in Active Directory [caution internet] save on desktop - script and a list of 1000 names - go to powershelgl, open file, open users, [powershell script] [set unrestricted] - must enable to use powershell [bunch of users inside active directory user]
- Create another virtual machine and install Windows 10 on it will be connected to the private virtual box network - this will be named Client1 [client1] [client1 internal network] add file and choose windows iso to open Client1 - windows 10 Pro - will restart - create user no password [change name to client1 mydomain.com] restart 
- Login to Client1 with one of the domain accounts [other user]
