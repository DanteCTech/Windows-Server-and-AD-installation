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

