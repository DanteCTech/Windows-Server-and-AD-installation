# Windows Server and AD installation
Using Oracle VirtualBox, I will demonstrate the installation for Windows Server 2022 and setup for Active Directrory. 
## Windows Server 2022 install
- Download Oracle Virtual box manager.
- Download an evaluation copy of Windows 2022 Server
- Hit new on the VM software to create the server and select the downloaded ISO <img width="798" height="367" alt="image" src="https://github.com/user-attachments/assets/dde0666e-32eb-4e64-8a74-372e16288262" />
- Select the proper image you'd like to install, then finish the windows setup process <img width="692" height="385" alt="image" src="https://github.com/user-attachments/assets/0a02fd4a-76b1-41db-b9c0-8da3f97cb369" />
- Once installed, setup your admin password and unlock your VM using the simulated keys.
- Here is the outlook on Server manager's interface! This will pop up on its own each time the VM is powered on. <img width="991" height="674" alt="image" src="https://github.com/user-attachments/assets/64ab7513-076e-4a01-97fe-d88f8df0d042" />

## Differences of Workgroups and Domains
The main difference between workgroups and domains is that in a workgroup, all computers work independently, no computer has control over any other computer. In a Domain, all the computers are controlled by the administrator. For workgroups, computers connected to your LAN at home are usually in a workgroup. Users will be able to create their own accounts on the devices and manage their own settings. Using a switch or a hub the users are also able to access local resources like printers. 
