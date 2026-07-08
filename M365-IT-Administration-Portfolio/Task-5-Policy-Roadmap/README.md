# Task 5: Device Management Policy Roadmap

## Overview

This task involved building a structured policy roadmap for the device management programme. The roadmap documents the current state of device policies, the planned expansion of controls across four phases, and the deployment schedule for enrolling all 10 company devices in Microsoft Intune.

## Current State

Three policies are active in the Intune tenant as of the completion of Task 4. These form Phase 1 of the roadmap and cover the minimum security baseline required before any device is handed to a staff member.

The Basic Compliance Policy enforces PIN, BitLocker, Firewall, Antivirus, and Defender requirements on all Windows devices. The PIN Enforcement Profile pushes Windows Hello for Business configuration to enrolled devices. The BitLocker Encryption Profile silently enables disk encryption and backs up recovery keys to Azure AD.

## Four Phase Roadmap

### Phase 1 Active Now
The three baseline policies are live and assigned to all devices. Any device that enrolls in Intune is immediately evaluated against these requirements.

### Phase 2 Security Hardening within 30 Days
A Windows Update Ring to ensure security patches are applied within seven days of release. A Microsoft Defender Antivirus Profile to enforce real time protection and cloud delivered protection. A Screen Lock Profile to automatically lock devices after five minutes of inactivity. A Firewall configuration profile as an additional enforcement layer.

### Phase 3 Access Control within 60 Days
A Conditional Access policy to block non compliant devices from accessing Microsoft 365 apps. An App Protection Policy to protect company data on personal mobile devices. A Device Restriction Profile to block USB storage and restrict unapproved applications. A Trusted Certificate Profile for secure access to internal services.

### Phase 4 Full Governance within 90 Days
A Compliance Monitoring Dashboard with weekly reports to the IT Lead. Automated remediation scripts to fix common compliance failures without manual intervention. A VPN Configuration Profile for remote workers. A quarterly device compliance review process.

## Device Enrollment Schedule

| Wave | Devices | Team | Timeline |
|------|---------|------|----------|
| Wave 0 | 2 VirtualBox VMs | IT Testing | Week 1 |
| Wave 1 | 3 Finance devices and IT Lead device | Finance and IT | Week 2 |
| Wave 2 | 1 Finance device | Finance | Week 3 |
| Wave 3 | 3 BI devices | Business Intelligence | Week 3 |
| Wave 4 | 1 BI device | Business Intelligence | Week 4 |
| Phase 3 Activation | All 10 devices | All teams | Week 7 to 8 |

## KPI Targets

Device enrollment rate of 100 percent within four weeks. Device compliance rate of 95 percent or above at any given time. BitLocker coverage of 100 percent across all enrolled devices. Security update compliance of 100 percent within seven days of each Microsoft release. Non compliant device remediation within 48 hours of detection.

## Tools Used

Microsoft Intune, Azure Active Directory, Microsoft Endpoint Manager, Microsoft Purview

## What I Learned

Building the policy roadmap taught me how to think strategically about device management beyond just the technical implementation. I developed the ability to phase security controls in a way that does not disrupt users, set measurable KPIs, and plan device deployments in waves that allow monitoring and adjustment between each rollout.
