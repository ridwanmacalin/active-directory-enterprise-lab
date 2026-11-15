# Active Directory Enterprise Home Lab

## Overview

This project documents a Windows Active Directory home lab built to simulate a small business IT environment.

The goal of the lab was to gain hands-on experience with Windows Server, Active Directory, DNS, Group Policy, user administration, file permissions, and troubleshooting common IT support issues.

## Environment

- Windows Server
- Windows 11
- Oracle VirtualBox
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy
- NTFS Permissions
- Windows File Sharing

## Lab Systems

### DC01

**Purpose:** Domain Controller and DNS Server

- IP Address: `192.168.56.10`
- Domain: `adlab.local`
- DNS: `127.0.0.1`

### PC01

**Purpose:** Domain-joined Windows 11 client

- IP Address: `192.168.56.20`
- DNS Server: `192.168.56.10`
- Domain: `adlab.local`

## Tasks Completed

- Installed and configured Windows Server
- Configured a static IP address
- Installed Active Directory Domain Services
- Created the `adlab.local` domain
- Configured DNS
- Joined PC01 to the domain
- Created Active Directory users
- Created security groups
- Configured shared folders
- Configured NTFS and share permissions
- Created and applied Group Policy settings
- Reset user passwords
- Unlocked user accounts
- Tested access to network resources
- Troubleshot network and DNS issues

## Users Created

Example user accounts created in Active Directory:

- Sarah
- Mike
- John

These accounts were used to test authentication, group membership, permissions, password resets, and account lockouts.

## File Sharing and Permissions

Created a company network share:

```text
\\DC01\Company
```

Subfolders included:

- Public
- HR

The Public folder was used for general shared access.

The HR folder was restricted using Active Directory security groups and NTFS permissions so that only authorized users could access sensitive resources.

## Group Policy

Created and linked Group Policy settings within the domain.

Group Policy was used to practice centralized administration and managing settings for domain users and computers.

## Troubleshooting

During the lab, I encountered an issue where PC01 could not properly communicate with the domain controller.

I investigated:

- IP configuration
- VirtualBox network adapters
- DNS configuration
- Network connectivity
- Domain name resolution

Commands used included:

```powershell
ipconfig /all
ping 192.168.56.10
ping dc01.adlab.local
nslookup dc01.adlab.local
```

After correcting the network and DNS configuration, PC01 successfully communicated with DC01 and resolved the domain name.

## Help Desk Scenarios

I also practiced several common IT support scenarios within the lab:

- [Password Reset](documentation/ticket-01-password-reset.md)
- [Account Unlock](documentation/ticket-02-account-unlock.md)
- [HR Folder Access and Permissions](documentation/ticket-03-hr-folder-access.md)
- [Domain Connectivity and DNS Troubleshooting](documentation/ticket-04-domain-connectivity.md)

Detailed ticket-style documentation is available in the `documentation` folder.

## What I Learned

This project helped me understand how Windows infrastructure components work together in a domain environment.

Key lessons included:

- Active Directory relies heavily on DNS
- Domain clients should use the domain DNS server to locate domain services
- Security groups can be used to manage access to company resources
- NTFS and share permissions both affect access to network folders
- Incorrect network configuration can prevent domain communication
- Troubleshooting should follow a structured process of identifying, testing, resolving, and verifying an issue

## Skills Demonstrated

- Active Directory administration
- Windows Server administration
- Windows 11 support
- DNS configuration and troubleshooting
- User and group management
- Password resets
- Account unlocks
- Group Policy
- NTFS permissions
- Network file sharing
- TCP/IP troubleshooting
- Command-line troubleshooting
- Technical documentation
- Help desk troubleshooting

## Future Improvements

Future additions to this project may include:

- PowerShell automation
- Automated employee onboarding
- Employee offboarding workflow
- Additional departments and security groups
- Password and account lockout policies
- Software deployment through Group Policy
- Microsoft 365 and Microsoft Entra ID integration
