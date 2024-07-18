# Active Directory Home Lab

## Introduction
This repository provides scripts, configurations, and documentation to set up a basic virtual Active Directory environment. 
It is intended for educational purposes, allowing users to experiment with AD features and functionalities in a safe, isolated environment.
This lab is inspired by Madakor on YouTube.

## Home Lab Architecture

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

4. 


















