# Ticket 03 - HR Folder Access

## Issue

A user was able to access the HR shared folder even though the user was not a member of the HR security group.

## Environment

Windows Server

Active Directory

Active Directory Security Groups

NTFS Permissions

Windows File Sharing

Share: \\DC01\Company

## Troubleshooting

I reviewed the user's Active Directory group membership.

The user was not a member of the HR security group but was still able to access the restricted HR folder.

I then reviewed:

Active Directory group membership

Share permissions

NTFS permissions

Access assigned to the HR folder

## Root Cause

The permissions applied to the folder allowed access that was broader than intended.

## Resolution

I corrected the permissions so that access to the HR folder was limited to authorized users.

The configuration was changed to better follow the principle of least privilege.

## Verification

I tested the folder permissions again using an account that should not have HR access.

The unauthorized account was no longer able to access the restricted folder.

## What I Learned

Group membership alone does not guarantee that a resource is properly secured.

Both share permissions and NTFS permissions should be reviewed when troubleshooting access to Windows file shares.

## Skills Demonstrated

Active Directory

Security groups

NTFS permissions

Share permissions

Access control

Principle of least privilege

Troubleshooting
