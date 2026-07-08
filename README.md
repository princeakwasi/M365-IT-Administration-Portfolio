Microsoft 365 IT Administration Portfolio

Prince Emmanuel Boateng

This portfolio documents the practical IT administration work completed during the CareerLeap Academy IT Systems Administration programme. Every task in this repository was built and tested on a real Microsoft 365 tenant and demonstrates hands on experience with enterprise IT tools and automation.

---

 About Me

I am an MSc Computer Science student at Universität Passau, Germany, with over six years of experience in IT support, system administration, and Microsoft 365 administration. This portfolio showcases my ability to automate IT workflows, manage cloud infrastructure, enforce security compliance, and solve real world IT problems using Microsoft technologies.

---

Skills Demonstrated

Cloud Administration
Microsoft 365, Azure Active Directory, Microsoft Entra ID, Exchange Online, SharePoint Online, Microsoft Teams, OneDrive for Business

Automation and Scripting
PowerShell, Microsoft Graph API, Power Automate, ExchangeOnlineManagement module

**Device Management**
Microsoft Intune, Endpoint Manager, Compliance Policies, Configuration Profiles, BitLocker, Windows Hello for Business

Security and Compliance
Microsoft Secure Score, Microsoft Defender for Office 365, GDPR compliance, Data Loss Prevention, Retention Labels, Conditional Access, Privileged Identity Management

Identity Management
User lifecycle management, Group management, Licence assignment, Multi Factor Authentication, Self Service Password Reset

---

## Portfolio Structure

| Task | Title | Tools Used |
|------|-------|------------|
| Task 1 | Email to Ticket Automation | Power Automate, Microsoft Planner |
| Task 2 | Automated User Lifecycle Management | PowerShell, Microsoft Graph |
| Task 3 | Security Posture Assessment | Microsoft Secure Score, Microsoft Purview |
| Task 4 | Device Management with Intune | Microsoft Intune, VirtualBox, Windows 11 |
| Task 5 | Policy Roadmap | Microsoft Intune, Azure AD |
| Task 6 | Onboarding and Offboarding Automation | PowerShell, Microsoft Graph, Exchange Online |

---

Task Summaries

Task 1 Email to Ticket Automation
Built a Power Automate cloud flow that monitors a shared support mailbox and automatically creates a task in Microsoft Planner whenever an email arrives. The flow classifies each email by priority using keyword detection and routes it to the correct bucket with appropriate labels for team assignment, priority, type, and reporter.

Task 2 Automated User Lifecycle Management
Wrote a PowerShell script using the Microsoft Graph SDK to bulk create 10 user accounts across Finance and Business Intelligence teams. The script assigns Microsoft 365 Business Premium licences, adds users to the correct security groups based on department, provisions two shared mailboxes, and configures Self Service Password Reset for all new hires.

Task 3 Security Posture Assessment
Conducted a full security assessment of the Microsoft 365 tenant. Retrieved the live Secure Score of 45.98 out of 100 from the Microsoft Defender portal and compared it against industry benchmarks. Produced a board ready document covering security gaps, policy inventory, incident response maturity, GDPR compliance status, and a risk register with a 30 60 90 day remediation roadmap.

Task 4 Device Management with Intune
Activated Microsoft Intune on the tenant and configured the complete device management framework. Created a compliance policy requiring PIN and BitLocker encryption on all Windows devices, built two configuration profiles to enforce these settings automatically, and documented a four phase policy roadmap covering 13 policies from immediate deployment through to full governance within 90 days.

Task 5 Policy Roadmap
Built a structured device management policy roadmap covering four phases of deployment across all 10 company devices. Documented current active policies, planned security hardening policies, access control policies, and a full governance framework with KPIs and a wave based device enrollment schedule.

Task 6 Onboarding and Offboarding Automation
Developed a unified PowerShell script that handles both employee onboarding and offboarding from a single interactive menu. The onboarding workflow creates user accounts, assigns licences selected from the live tenant, adds users to groups fetched from Azure AD, sets line managers, and sends automated welcome emails. The offboarding workflow disables accounts, revokes all sessions, sets auto replies, removes group memberships and licences, and wipes company devices via Intune.

---

Certifications

Microsoft 365 Fundamentals (MS-900)

---

Contact

LinkedIn: www.linkedin.com/in/princeemmanuelboateng


