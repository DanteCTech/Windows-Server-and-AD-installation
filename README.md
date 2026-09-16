# Windows Server and AD installation
Using Oracle VirtualBox, I will demonstrate the installation for Windows Server 2022 and setup for Active Directrory. 
## Windows Server 2022 install
- Download Oracle Virtual box manager.
- Download an evaluation copy of Windows 2022 Server
- Hit new on the VM software to create the server and select the downloaded ISO
  

 <img width="798" height="367" alt="image" src="https://github.com/user-attachments/assets/dde0666e-32eb-4e64-8a74-372e16288262" />


- Select the proper image you'd like to install, then finish the windows setup process
  
 <img width="692" height="385" alt="image" src="https://github.com/user-attachments/assets/0a02fd4a-76b1-41db-b9c0-8da3f97cb369" />
 
- Once installed, setup your admin password and unlock your VM using the simulated keys.
- Here is the outlook on Server manager's interface! This will pop up on its own each time the VM is powered on.

 <img width="991" height="674" alt="image" src="https://github.com/user-attachments/assets/64ab7513-076e-4a01-97fe-d88f8df0d042" />

## Workgroups and Domains
To simplify, workgroups are decentralized, peer to peer and local accounts only. While a Domain is a centralized environment, domain users can authenticate with unique login credentials on domain joined computers where that user is permitted to log on.

A workgroup is a logical network more suited for the home environment. Each device has its own local accounts, and multiple users can use the same device with different local logins. The only connection each device has in the workgroup is the network all of them are connected to. This is ideal for the home environment where the family has individual devices such as computers that are uniquely configured to a different person in that household.

A domain is a logical network that is suited for companies that have plenty of employees onboard. This allows for admins who maintain the domain controller to create and manage user and accounts in active directory. Once a user has their login credentials and permissions set, they will be able to log into any computer within that domain that is within their privilege to log in-to. Those users and computers can then be further organized into what are called organizational units(OU). The administrator can apply and configure GPOs to the OUs to allow or restrict access to certain features, enforce password policies, configure windows settings etc. 

### Server setup
First, though not required I will start with changing the hostname to something that is easily memorable. We will use DC-ADMIN.
Once you change the name the machine must do a restart to finalize the switch. 

<img width="1025" height="696" alt="VM domain name" src="https://github.com/user-attachments/assets/9a2d3f06-23f1-4421-92c0-e547357cd6aa" />

Once it is verified that the hostname is changed we can configure our IP and DNS.

I will need to set a static IP address and a preferred DNS address. The reason why we have to set up the DNS address is because AD DS utilizes DNS in order to perform various functions such as authentication. When we download the DNS role/tools onto the server, plenty of records will be written to the server for the server's DNS functions. To set this up, follow these steps:

- Navigate to the Control Panel.
- Go into network & internet.
- Click on ethernet.
There you'll see IP assignment and you can toggle this from auto to manual. 
I can now give my server a static IP address, subnet mask, and a DNS server address.
The DNS server address will be the server so I used my server's IP address as the DNS server address. A loopback address can also be used.
Note: the computers that will set up in my company will need to utilize the correct DNS server address.

 <img width="513" height="633" alt="Untitled" src="https://github.com/user-attachments/assets/e2ae9a9f-a10b-42dc-9fe5-7aeac02c1126" />



Now I will jump into configuring the Active Directory Domain Server on my VM. 
- On the Server manager window, select " Add roles and Features". If it is your first time, a help wizard will appear to guide you through the steps. 

 <img width="812" height="695" alt="VM ROLE setup" src="https://github.com/user-attachments/assets/de7709bf-7e7b-4e69-9045-c274ead3341e" />

- Select "Role Based or Featured based installation".
  
 <img width="779" height="310" alt="VM install role" src="https://github.com/user-attachments/assets/239cf842-6bda-4ed6-b122-0a753b461e0a" />

- The Server Selection tab will let me choose my server to install roles and features to. I highlighted my computer and hit next.
- The Server Roles tab shows all the roles you can install to the server. I will flag the Active Directory Domain Services option. Flagging the role will action a pop-up that will show me all the required features/tools that will be install with AD DS. Press add features and next.
- The Confirmation tab will show the roles and features that will be installed. Once completed restart the machine.
- Once my system has re-booted, I will promote my server to Domain Controller.

 <img width="1027" height="695" alt="VM promote" src="https://github.com/user-attachments/assets/c6ee5848-9710-4543-a3b8-ae50f537e1c9" />

 ### Deployment Configuration
Now that the Deployment Configuration is displayed, I am going to flag the option to add a new forest. This will allow me to set up our domain controller in a new domain. There are two other options:
Add a domain controller to an existing domain. This will make the forest fault tolerant.
Add a new domain to an existing forest.
Note: both these options were not chosen due to the fact that I am setting everything up from scratch. Ground zero!
I am now able to name the Root Domain. For this, I re-named to be DC.local.

 <img width="751" height="358" alt="VM deployment" src="https://github.com/user-attachments/assets/7ac3a104-83e6-4e3b-95a1-5d7de467bae2" />

 I kept all the default boxes checked outside of changing the DSRM password and NetBIOS Domain Name and finalized the installation.
 The Machine will have to reboot once more.

 <img width="1005" height="470" alt="VM server finished" src="https://github.com/user-attachments/assets/e3e6f0bc-4eb1-41a6-b77e-1f7f277f27c3" />


Completed! We have Active Directory Domain Server installed on our Windows 2022 OS VM. 
