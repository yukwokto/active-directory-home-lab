# Active Directory Home Lab

## Introduction
This repository provides scripts, configurations, and documentation to set up a basic virtual Active Directory environment. 
It is intended for educational purposes, allowing users to experiment with AD features and functionalities in a safe, isolated environment.
This lab is inspired by Madakor on YouTube.

## Home Lab Architecture
![lab-arch](https://github.com/yukwokto/active-directory-home-lab/)

## Prerequisites

- Virtual Box 8.0
- Windows Server 2019 ISO
- Windows 10 Image

## Procedures

### Domain Controller Set Up

1. In Virtual Box, create a VM and boot from the Windows Server 2019 installation media.
![Windows Server 2019 Install](https://github.com/yukwokto/active-directory-home-lab/)

2. Go to Settings > About, rename the server to DC.
![Rename PC](https://github.com/yukwokto/active-directory-home-lab/)

3. Go to Network Connections, select the internal ethernet adapter, set a static ip of 172.16.0.1/24. Also. configure the DNS server as the loopback address 127.0.0.1.
![static-ip](https://github.com/yukwokto/active-directory-home-lab/)

4. Install the Active Directory Domain Service on the Windows Server. Set the root domain name to mydomain.com. 
![install ad](https://github.com/yukwokto/active-directory-home-lab/)
![root domain name](https://github.com/yukwokto/active-directory-home-lab/)

5. In Active Directory Users and Computers, create an organization unit called _ADMINS.
![create-admin-ou](https://github.com/yukwokto/active-directory-home-lab/)

6. Create an admin user using my name. Confirm the admin user creation.
![create admin user](https://github.com/yukwokto/active-directory-home-lab/)
![confirm admin](https://github.com/yukwokto/active-directory-home-lab/)

7. Edit the admin user properties, add the admin user as a member of Domain Admins.
![member of admin](https://github.com/yukwokto/active-directory-home-lab/)


8. Install remote access server role.
![remote-access](https://github.com/yukwokto/active-directory-home-lab/)

9. Enable network address translation.
![nat](https://github.com/yukwokto/active-directory-home-lab/)

10. Install DHCP Server.
![dhcp](https://github.com/yukwokto/active-directory-home-lab/)

11. Define a dhcp pool (172.16.0.100-200/24)
![dhcp-pool](https://github.com/yukwokto/active-directory-home-lab/)

12. Verify the dhcp set up.
![verrify-dhcp](https://github.com/yukwokto/active-directory-home-lab/)

13. Create more than 1000 users using a PowerShell Script. Verify the user creation.
![create-users](https://github.com/yukwokto/active-directory-home-lab/)


### Client PC Set Up

1. Install Windows 10 Home Pro.
![windows-10-install](https://github.com/yukwokto/active-directory-home-lab/)

2. Join the client PC to the domain (mydomain.com)
![join-domain](https://github.com/yukwokto/active-directory-home-lab/)

3. Back to the Windows Server, verify the new computer association in the domain controller. 
![verify-computer](https://github.com/yukwokto/active-directory-home-lab/)

4. Sign in to the client PC using one of the account.
![sign-in-client](https://github.com/yukwokto/active-directory-home-lab/)

5. Verify the Client in Cmd by whoami.
![whoami](https://github.com/yukwokto/active-directory-home-lab/)

6. Verify Client Network Configuration by ipconfig/all
![ip-config](https://github.com/yukwokto/active-directory-home-lab/)






