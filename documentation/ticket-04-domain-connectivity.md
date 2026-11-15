# Ticket 04 - Domain Connectivity and DNS

## Issue

PC01 was unable to properly communicate with the domain controller, DC01.

This affected communication with the adlab.local domain.

## Environment

DC01

IP Address: 192.168.56.10

Role: Domain Controller

Role: DNS Server

Domain: adlab.local

PC01

IP Address: 192.168.56.20

DNS Server: 192.168.56.10

Operating System: Windows 11

Domain: adlab.local

## Troubleshooting

I first checked the Windows network configuration using:

```powershell
ipconfig /all
```

I then tested connectivity to the domain controller:

```powershell
ping 192.168.56.10
```

I tested communication using the domain controller's hostname:

```powershell
ping dc01.adlab.local
```

I also checked DNS name resolution:

```powershell
nslookup dc01.adlab.local
```

In addition to Windows networking settings, I reviewed the network adapters configured in Oracle VirtualBox.

## Root Cause

The issue was related to the virtual network configuration and DNS settings.

For Active Directory to function properly, PC01 needed network connectivity to DC01 and needed to use the domain controller as its DNS server.

## Resolution

I corrected the VirtualBox network configuration and confirmed that PC01 was configured to use:

192.168.56.10

as its DNS server.

## Verification

After correcting the configuration:

```powershell
ping 192.168.56.10
```

was successful.

I then tested:

```powershell
ping dc01.adlab.local
```

and confirmed that the hostname successfully resolved to DC01.

## What I Learned

This issue demonstrated how important DNS is in an Active Directory environment.

A Windows computer can have basic network connectivity while still experiencing domain-related problems if DNS is configured incorrectly.

It also reinforced the importance of checking network configuration systematically rather than changing multiple settings at once.

## Skills Demonstrated

DNS troubleshooting

TCP/IP networking

Windows networking

Active Directory

VirtualBox networking

ipconfig

ping

nslookup

Root-cause analysis
