# Active Directory Enterprise Home Lab

## Overview

This project documents a Windows Active Directory home lab built to simulate a small business IT environment.

The goal of the lab was to gain hands-on experience with Windows Server, Active Directory, DNS, Group Policy, user administration, file permissions, and troubleshooting.

## Environment

- Windows Server
- Windows 11
- Oracle VirtualBox
- Active Directory Domain Services
- DNS
- Group Policy

## Lab Systems

### DC01
Purpose: Domain Controller

- IP Address: 192.168.56.10
- Domain: adlab.local
- DNS: 127.0.0.1

### PC01
Purpose: Domain-joined Windows 11 client

- IP Address: 192.168.56.20
- DNS: 192.168.56.10
- Domain: adlab.local

## Tasks Completed

- Installed Windows Server
- Configured a static IP address
- Installed Active Directory Domain Services
- Created the adlab.local domain
- Configured DNS
- Joined PC01 to the domain
- Created Active Directory users
- Created security groups
- Configured shared folders
- Configured NTFS permissions
- Created Group Policy settings
- Reset user passwords
- Unlocked user accounts
- Troubleshot network and DNS issues

## Users Created

Examples of user accounts created:

- Sarah
- Mike
- John

## File Sharing

Created a company shared folder:

\\DC01\Company

Subfolders included:

- Public
- HR

Access to the HR folder was restricted based on Active Directory group membership.

## Troubleshooting

During the lab, PC01 initially could not communicate with the domain controller.

I checked:

- IP configuration
- VirtualBox network adapters
- DNS settings
- Network connectivity

I used commands including:

```powershell
ipconfig /all
ping 192.168.56.10
ping dc01.adlab.local
nslookup dc01.adlab.local
