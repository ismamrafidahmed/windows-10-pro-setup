<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in Windows Server 2022 Virtual Machine </h1>
This tutorial outlines the implementation of on-premises Active Directory within Windows Server 2022 using VirtualBox<br />

<h2>Environments and Technologies Used</h2>

- VirtualBox
- Active Directory Domain Services
- Group Policy Management 

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro

<h2>Deployment and Configuration Steps Covered in This Section</h2>

- Windows 10 Installation & Setup

<h2>Deployment and Configuration Steps</h2>

Download Windows 10 ISO

Create a VM called “Client-1” with ISO attached, Windows 10 64-bit, 8 GB of RAM, 1 CPU, and 50GB for the virtual hard disk size

Change the shared clipboard and drag-drop setting for the VM to bidirectional 

Go to network settings, adapter 1, attached to: internal network, then start the VM

Once logged into the VM, open cmd and type ipconfig to see if you have an IP address, subnet mask, or default gateway assigned. Then, ping Google to see if your DNS server is working. 

Go to your network adapter settings on your client VM and change the IPV4 DNS IP address from auto to the IP address of the domain controller

Next, to join this VM to the domain, go to rename this pc (advanced), change, type “Client-1” for the computer name, type “mydomain.com” for member of: domain

![image](https://github.com/user-attachments/assets/d2698881-6e71-49fb-adcc-a8151393e47c)

Login to the domain as a previously created domain admin or user, then restart the VM

![image](https://github.com/user-attachments/assets/116669bb-4051-4da6-8147-7c5710901d0a)

Log into Client-1 as one of the domain users created earlier in the “_USERS” OU

![image](https://github.com/user-attachments/assets/7be8af01-927c-4157-8e58-9af344174635)

In the DC VM, go to DHCP settings. You will see that a lease with an expiration date is assigned to the Client-1 VM in “address leases.” 

![image](https://github.com/user-attachments/assets/0fc9dc35-b60e-48bc-842b-9180be90790b)

In the DC VM, if you go to ADUC and click on computers, you will also see the Client-1 computer there. 

![image](https://github.com/user-attachments/assets/bee55d31-bd76-4d6a-8213-7b68035f21ba)




