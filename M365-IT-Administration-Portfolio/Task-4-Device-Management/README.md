# Task 4: Device Management with Microsoft Intune

## Overview

This task involved setting up Microsoft Intune on the tenant to manage 10 Windows devices that had been procured for staff. The objective was to ensure every device was security compliant before being handed to employees, with a minimum requirement that every device has a PIN and BitLocker encryption enabled.

## What Was Built

### Objective 1 Activate Intune
Confirmed Microsoft Intune was active in the Microsoft 365 Business Premium tenant by accessing the Intune admin centre at endpoint.microsoft.com.

### Objective 2 Allow Devices to Enroll
Configured three settings to enable automatic device enrollment. MDM user scope was set to All in Azure AD Mobility settings, device join was enabled for all users in Azure AD Device settings, and Windows MDM was confirmed as Allowed in Intune enrollment restrictions.

### Objective 3 Compliance Policy
Created a compliance policy targeting Windows 10 and later devices. The policy requires BitLocker encryption, a password to unlock the device, a minimum password length of six characters, Windows Firewall enabled, antivirus active, and Microsoft Defender Antimalware running. Any device failing these requirements is marked Non Compliant.

### Objective 4 Configuration Profiles
Created two configuration profiles to actively push the required settings to devices rather than just checking compliance.

The PIN Enforcement Profile uses the Settings Catalog to enable Windows Hello for Business with a minimum PIN length of six digits. The BitLocker Encryption Profile uses the Endpoint Protection template to silently enable BitLocker on the C drive and automatically back up the recovery key to Azure AD so IT can recover any device remotely.

### Objective 5 Policy Roadmap
Documented a four phase policy roadmap covering 13 policies across immediate deployment, security hardening within 30 days, access control within 60 days, and full governance within 90 days.

### Objectives 6 to 9 VM Enrollment and Compliance Verification
Created Windows 11 Pro virtual machines in VirtualBox as test devices, joined them to Azure AD which triggered automatic Intune enrollment, verified both devices appeared in the Endpoint Manager portal with MDM management confirmed, and verified compliance status against the policy.

## Compliance Policy Settings

| Setting | Requirement |
|---------|-------------|
| BitLocker | Required |
| Password to unlock | Required |
| Minimum password length | 6 characters |
| Simple passwords | Blocked |
| Firewall | Required |
| Antivirus | Required |
| Microsoft Defender | Required |

## Tools Used

Microsoft Intune, Azure Active Directory, Microsoft Endpoint Manager, VirtualBox, Windows 11 Pro

## What I Learned

This task gave me hands on experience configuring enterprise device management from scratch. I learned how to set up MDM auto enrollment, the difference between compliance policies and configuration profiles, how BitLocker recovery keys are stored in Azure AD, and how to troubleshoot common Intune enrollment errors.
