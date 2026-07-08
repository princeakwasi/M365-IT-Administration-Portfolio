# Task 6: Onboarding and Offboarding Automation

## Overview

This task involved building a unified PowerShell script that automates the complete employee lifecycle from joining the organisation to leaving it. The script uses Microsoft Graph API and Exchange Online to perform all provisioning and deprovisioning steps automatically from a single interactive menu.

## The Problem

Without automation, onboarding a new employee requires an IT administrator to manually create a user account, assign a licence, add the person to the right group, set their manager, send them their credentials, and notify their manager. Offboarding requires disabling the account, signing the person out of all devices and applications, setting an out of office reply, removing all access, and wiping company devices. Both processes are time consuming and prone to human error.

## The Solution

A single PowerShell script with an interactive menu that presents two options when launched. The administrator chooses Onboarding or Offboarding and the script handles the rest through a series of prompts and automated steps.

## How to Run

On Windows double click Run-UserManagement.bat which is included in this repository. On Mac double click Run-UserManagement.command. Both launchers check that PowerShell is installed and that the script file is in the same folder before running.

Alternatively run directly from PowerShell:

```powershell
cd path\to\script\folder
.\UserManagement.ps1
```

## Onboarding Workflow

When Onboarding is selected the script first asks how many employees to onboard with a maximum of 20 per run. For each employee it collects the following information through interactive prompts.

Full name, first name, and last name are collected first to identify the person. The administrator then creates a work email address for the new employee. A personal email address is collected to send the welcome email. Phone number, job title, and country are collected next. The country field uses fuzzy matching so even if the country name is spelled incorrectly the script finds the closest match and applies the correct ISO country code automatically.

The script then connects to the live Azure AD tenant and fetches all available groups, displaying them as a numbered list so the administrator simply presses a number rather than typing a group name. The same approach is used for licence selection where all available licences with remaining slots are listed by number. Line manager name and email are collected and finally a temporary password is entered or auto generated.

Before creating anything a confirmation screen displays all the entered details and asks the administrator to confirm. If anything is wrong the entry is cancelled without creating any accounts.

Once confirmed the script creates the user account, assigns the chosen licence, adds the user to the selected group, sets the line manager, sends a welcome email to the personal email address, and sends a notification email to the line manager. All actions are logged to a text file in the OnboardingLogs folder.

## Offboarding Workflow

When Offboarding is selected the script asks for the leaving employee email address and their manager email. It then looks up both users in Azure AD and displays a confirmation screen showing the employee full name, job title, department, and manager with a list of all actions that will be taken. The administrator must confirm before anything happens.

Once confirmed the script performs eight steps in sequence. It disables the account and resets the password to a random string. It revokes all active sign in sessions so the employee is immediately signed out of Teams, Outlook, SharePoint, and all other Microsoft 365 applications on every device. It sets an automatic reply on the mailbox redirecting contacts to the manager. It sets email forwarding to the manager. It removes all group memberships. It removes all licences. It retires all Intune managed devices. It updates the user profile to show Offboarded status. All actions and any errors are logged to the OffboardingLogs folder as both a text file and a JSON audit log.

## Key Features

The script fetches groups and licences live from the tenant so it works for any organisation without hardcoded values. The country name input uses fuzzy matching to accept any spelling variation. The confirmation screens for both onboarding and offboarding prevent accidental account creation or deletion. Multiple users can be onboarded in a single run with a full summary at the end showing success, failure, or cancellation for each employee.

## Files in This Folder

UserManagement.ps1 is the main script containing both the onboarding and offboarding workflows. Run-UserManagement.bat is the Windows launcher for double click execution. Run-UserManagement.command is the Mac launcher for double click execution.

## Required PowerShell Modules

```powershell
Install-Module Microsoft.Graph -Scope CurrentUser -Force
Install-Module ExchangeOnlineManagement -Scope CurrentUser -Force
```

## Permissions Required

The admin account used to run the script must have User Administrator, Licence Administrator, Groups Administrator, and Exchange Administrator roles in Azure AD.

## What I Learned

This was the most complex script I built during the programme. It taught me how to build interactive PowerShell menus, how to use Microsoft Graph API for user provisioning and deprovisioning, how to send emails programmatically through Graph, how to implement fuzzy string matching in PowerShell, how to fetch live tenant data and present it as interactive numbered lists, and how to structure a script that handles errors gracefully without stopping the entire process.
