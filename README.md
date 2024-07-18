# Active Directory Home Lab

## Introduction
This repository provides scripts, configurations, and documentation to set up a basic virtual Active Directory environment. 
It is intended for educational purposes, allowing users to experiment with AD features and functionalities in a safe, isolated environment.
This lab is inspired by Madakor on YouTube.

## Home Lab Architecture
![lab-arch](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/lab-arch.png)

## Prerequisites

- Virtual Box 8.0
- Windows Server 2019 ISO
- Windows 10 Image

## Procedures

### Domain Controller Set Up

1. In Virtual Box, create a VM and boot from the Windows Server 2019 installation media.
<br />

![Windows Server 2019 Install](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/windows-server-install.png)

3. Go to Settings > About, rename the server to DC.
<br />

![Rename PC](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/rename-pc.png)

4. Go to Network Connections, select the internal ethernet adapter, set a static ip of 172.16.0.1/24. Also. configure the DNS server as the loopback address 127.0.0.1.
<br />

![static-ip](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/static-ip-assignment.png)

5. Install the Active Directory Domain Service on the Windows Server. Set the root domain name to mydomain.com. 
<br />

![install ad](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/install-ad.png)
<br />

![root domain name](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/root-domain-name.png)

6. In Active Directory Users and Computers, create an organization unit called _ADMINS.
<br />

![create-admin-ou](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/create-ou-admins.png)

7. Create an admin user using my name. Confirm the admin user creation.
<br />

![create admin user](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/create-admin-user.png)
<br />

![confirm admin](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/confirm-admin.png)

8. Edit the admin user properties, add the admin user as a member of Domain Admins.
<br />

![member of admin](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/member-of.png)

9. Install remote access server role.
<br />

![remote-access](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/remote-access.png)

10. Enable network address translation.
<br />

![nat](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/nat.png)

11. Install DHCP Server.
<br />

![dhcp](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/dhcp.png)

12. Define a dhcp pool (172.16.0.100-200/24)
<br />

![dhcp-pool](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/dhcp-pool.png)

13. Verify the dhcp set up.
<br />

![verrify-dhcp](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/verify-dhcp-pool.png)

14. Create more than 1000 users using a PowerShell Script. Verify the user creation.
<br />

![create-users](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/create-users.png)


### Client PC Set Up

1. Install Windows 10 Home Pro.
<br />

![windows-10-install](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/win-10-install.png)

2. Join the client PC to the domain (mydomain.com)
<br />

![join-domain](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/join-domain.png)

3. Back to the Windows Server, verify the new computer association in the domain controller. 
<br />

![verify-computer](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/verify-computer.png)

4. Sign in to the client PC using one of the account.
<br />

![sign-in-client](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/sign-in-client.png)

5. Verify the Client in Cmd by whoami.
<br />

![whoami](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/whoami.png)

6. Verify Client Network Configuration by ipconfig/all
<br />

![ip-config](https://github.com/yukwokto/active-directory-home-lab/blob/main/img/ipconfig.png)


## The End



