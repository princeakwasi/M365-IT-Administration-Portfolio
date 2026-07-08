# Task 2: Automated User Lifecycle Management

## Overview

This task required automating the complete provisioning process for 10 new employees across the Finance and Business Intelligence teams. Rather than creating each user manually through the Microsoft 365 Admin Centre, a PowerShell script was written using the Microsoft Graph SDK to handle the entire workflow in a single automated run.

## Problem Statement

Manually onboarding users through the admin portal is time consuming, error prone, and inconsistent. With 10 new hires across two departments, the risk of missing a step such as forgetting to assign a licence or adding a user to the wrong group was high. A scripted approach ensures every user goes through the same process without exceptions.

## What the Script Does

The script reads from a CSV file containing the details of all 10 new hires and for each user performs the following actions in sequence.

It creates the user account in Azure Active Directory with their display name, email address, department, job title, and usage location. It then assigns a Microsoft 365 Business Premium licence to the account. Based on the department field in the CSV it adds Finance team members to the Finance security group and Business Intelligence team members to the BI security group. Finally it provisions two shared mailboxes and grants each team full access to their respective mailbox.

## Self Service Password Reset

In addition to user provisioning, SSPR was configured for the organisation through the Azure AD portal. Authentication methods were set to require two methods including Microsoft Authenticator push notifications, Authenticator app codes, and SMS. Registration enforcement was enabled so all new users are prompted to register their authentication methods on first login.

## Technologies Used

PowerShell, Microsoft Graph PowerShell SDK, Exchange Online Management module, Azure Active Directory, Microsoft 365 Admin Centre

## Key Commands Used

```powershell
Connect-MgGraph
New-MgUser
Set-MgUserLicense
New-MgGroupMember
New-Mailbox
Add-MailboxPermission
```

## What I Learned

This task gave me practical experience writing production quality PowerShell using the Microsoft Graph SDK. I learned how to authenticate using delegated permissions, how to work with user objects in Azure AD, how to handle licence SKU IDs, and how to manage Exchange Online resources through PowerShell rather than the GUI.
