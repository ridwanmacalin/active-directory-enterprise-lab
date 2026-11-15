# Ticket 04 - Domain Connectivity Issue

## Issue

PC01 was unable to communicate with the domain controller, DC01.

## Troubleshooting

I checked:

- IP configuration
- DNS settings
- VirtualBox network adapters
- Connectivity between PC01 and DC01

Commands used:

ipconfig /all

ping 192.168.56.10

nslookup dc01.adlab.local

## Resolution

I corrected the network and DNS configuration.

After the changes, PC01 was able to communicate with DC01 and resolve the domain name successfully.

## Skills Used

- DNS
- TCP/IP
- Windows networking
- Active Directory
- Network troubleshooting
