# Task 3: Security Posture Assessment

## Overview

This task involved conducting a comprehensive security posture assessment of the Microsoft 365 environment and producing a board ready document covering six critical areas of security governance. The assessment was based on live data retrieved directly from the Microsoft Defender portal and the SharePoint tenant.

## Live Secure Score

The Microsoft Secure Score for the tenant was retrieved directly from security.microsoft.com/securescore and found to be 45.98 out of 100, equating to 125.53 out of 273 available points. The breakdown by category revealed critical gaps particularly in the Data category which scored 0 percent, meaning no data protection controls of any kind were active in the tenant.

The score was compared against the peer average of 45.96 for organisations of similar size and the industry best practice target of 65 to 75, confirming the tenant was significantly below the recommended baseline.

## Six Assessment Areas

### Security Posture and Secure Score
Evaluated 12 Microsoft 365 security controls including MFA enforcement, Conditional Access, Microsoft Defender, Privileged Identity Management, Data Loss Prevention, and retention labels. The majority were found to be missing or only partially configured.

### Information Security Policy
Produced a complete 10 section Information Security Policy document that is GDPR compliant and suitable for board approval. The policy covers governance, acceptable use, access control, data classification, incident management, GDPR obligations, business continuity, third party access, and security awareness training.

### Policy Document Inventory
Conducted a live search of the SharePoint tenant for all six required IT policies. The search confirmed that all six policies were completely absent from the tenant with no documents found in any repository.

### Incident Response Maturity
Assessed the organisation against a five level maturity model across seven capability domains. All domains scored at Level 0 meaning no incident response capability existed. The organisation had no P1 to P4 classification framework, no escalation matrix, and no incident logging system.

### GDPR Compliance Checklist
Evaluated 14 GDPR controls across data retention and breach notification. The majority were missing. The organisation had no retention labels configured in Exchange, SharePoint, or Teams, and no documented process for detecting or reporting a personal data breach within the GDPR required 72 hour window.

### Risk Findings and Recommendations
Produced a 14 risk register with Critical, High, and Medium ratings and a detailed 30 60 90 day remediation roadmap projecting Secure Score improvement from 45.98 to 76 to 87 after full implementation.

## Documents Produced

A full Security Posture Assessment report covering all six areas with evidence from the live tenant, a standalone Information Security Policy document, a Policy Inventory report with SharePoint search evidence, and an Incident Response Maturity Assessment with proposed frameworks.

## Tools Used

Microsoft Secure Score portal, Microsoft Defender portal, SharePoint Online, Microsoft Purview, Azure Active Directory

## What I Learned

This task developed my ability to assess an organisation's security posture using Microsoft native tooling, interpret Secure Score data and benchmarks, identify governance gaps, and communicate findings in a format suitable for non technical stakeholders and board level audiences.
