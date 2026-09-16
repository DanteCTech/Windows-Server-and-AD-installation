# Windows Server and AD installation
Using Oracle VirtualBox, I will demonstrate the installation for Windows Server 2022 and setup for Active Directrory. 
## Windows Server 2022 install
- Download Oracle Virtual box manager.
- Download an evaluation copy of Windows 2022 Server
- Hit new on the VM software to create the server and select the downloaded ISO <img width="798" height="367" alt="image" src="https://github.com/user-attachments/assets/dde0666e-32eb-4e64-8a74-372e16288262" />
- Select the proper image you'd like to install, then finish the windows setup process <img width="692" height="385" alt="image" src="https://github.com/user-attachments/assets/0a02fd4a-76b1-41db-b9c0-8da3f97cb369" />
- Once installed, setup your admin password and unlock your VM using the simulated keys.
- Here is the outlook on Server manager's interface! This will pop up on its own each time the VM is powered on. <img width="991" height="674" alt="image" src="https://github.com/user-attachments/assets/64ab7513-076e-4a01-97fe-d88f8df0d042" />

## Workgroups and Domains
To simplify, workgroups are decentralized, peer to peer and local accounts only. While a Domain is a centralized environment, domain users can authenticate with unique login credentials on domain joined computers where that user is permitted to log on.

A workgroup is a logical network more suited for the home environment. Each device is independently configured to a sole user and cannot be seamlessly transfered from one device to the next. The only connection each device has in the workgroup is the network all of them are connected to. This is ideal for the home environment where the family has individual devices such as computers that are uniquely configured to a different person in that household.

A domain is a logical network that is suited for companies that have plenty of employees onboard. This allows for admins who maintain the domain controller to register users and computers to the server. Once a user has their login credentials and permissions set, they will be able to log into any computer within that domain that is within their privilege to log in-to. Those users and computers can then be further organized into what are called organizational units(OU). The administrator can apply and configure GPOs to the OUs to allow or restrict access to certain features, enforce password policies, configure windows settings etc. 
