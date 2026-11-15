# Troubleshooting Notes

## Issue: PC01 Could Not Reach DC01

### Symptoms

PC01 was unable to successfully ping the domain controller.

### Troubleshooting Steps

1. Checked IP configuration using ipconfig /all.
2. Verified the VirtualBox network adapters.
3. Confirmed that both systems were on the same private network.
4. Verified that PC01 was using DC01 as its DNS server.
5. Tested connectivity using ping.
6. Tested DNS resolution using nslookup.

### Resolution

The VirtualBox network configuration and DNS settings were corrected.

Afterward:

ping 192.168.56.10

and:

ping dc01.adlab.local

were successful.

### Lesson Learned

Domain environments depend heavily on correct DNS configuration. A client should normally use the domain controller's DNS server rather than a public DNS server.
