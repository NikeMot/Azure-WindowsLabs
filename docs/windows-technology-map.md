# Windows Technology Map

### Purpose

This document lists the Windows and Microsoft endpoint technologies that should appear across the `Azure-WindowsLabs` programme.

The aim is to become a practical Windows and Azure System Administrator, so the labs should cover both traditional Windows administration and modern cloud-managed Windows endpoint operations.

### Core Windows and Azure Administration Technologies

| Area | Technologies | Why it matters |
| --- | --- | --- |
| Windows Server administration | Windows Server roles, services, Event Viewer, Task Scheduler, Performance Monitor, Windows Firewall | Core server support, troubleshooting and operational evidence |
| Identity and directory services | AD DS, DNS, Group Policy, Kerberos, LDAP, OUs, users, groups, domain join | Foundation of traditional enterprise Windows administration |
| Remote administration | RSAT, Server Manager, Windows Admin Center, PowerShell Remoting, WinRM, RDP | Real admins manage servers remotely and need secure admin paths |
| Scripting and automation | Windows PowerShell 5.1, PowerShell 7, modules, scripts, scheduled tasks, error handling, logging | Reduces manual work and creates repeatable operational processes |
| File and access management | SMB shares, NTFS permissions, inheritance, auditing, DFS basics | Common sysadmin support area and good access-control practice |
| Endpoint deployment | Windows Autopilot, Autopilot device preparation, Enrollment Status Page, OOBE customisation | Modern cloud-based Windows provisioning without traditional imaging |
| Endpoint management | Microsoft Intune, configuration profiles, compliance policies, device actions, app deployment | Core modern workplace and endpoint admin skillset |
| Update management | Windows Update for Business, Windows Autopatch, update rings, feature updates, quality updates, driver/firmware updates | Keeps endpoints secure and supported with controlled rollout rings |
| Endpoint security | BitLocker, Windows LAPS, Windows Hello for Business, Defender for Endpoint concepts, security baselines | Protects devices, credentials, local admin access and data |
| Privilege management | Local Administrators group, Windows LAPS, Intune Endpoint Privilege Management | Teaches least privilege and controlled elevation |
| Cloud identity and device state | Microsoft Entra ID join, hybrid join, device registration, Conditional Access, sign-in logs | Connects Windows endpoint state to access control decisions |
| Azure infrastructure | Azure VMs, VNets, NSGs, storage, RBAC, Azure Monitor, Backup, Update Manager, Azure Arc basics | Connects Windows administration to cloud infrastructure operations |

### Autopilot Learning Outcomes

The Autopilot labs should teach how to:

* explain the difference between traditional imaging and Autopilot provisioning
* register or simulate device registration for Autopilot
* create deployment profiles
* understand OOBE customisation
* use Enrollment Status Page concepts
* assign devices to groups
* connect Autopilot to Intune enrolment
* understand Entra ID join versus hybrid join trade-offs
* troubleshoot provisioning and enrolment failures
* document production risks, licensing and rollback options

### Other Relevant Windows Technologies to Include

The programme should also include labs or lab sections for:

* Windows Admin Center
* RSAT
* PowerShell Remoting and WinRM
* Windows Firewall
* Windows Event Forwarding concepts
* Performance Monitor and Resource Monitor
* Task Scheduler
* Windows Update for Business
* Windows Autopatch
* BitLocker and recovery key handling
* Windows LAPS
* Windows Hello for Business
* Intune Endpoint Privilege Management
* Defender for Endpoint concepts
* Security baselines
* Local Group Policy versus domain Group Policy
* Microsoft Entra joined, hybrid joined and domain joined device models
* Azure Arc-enabled servers basics
* Azure Update Manager basics

### Placement in the Lab Series

| Technology | Primary folder |
| --- | --- |
| Windows Server roles, services and Event Viewer | `01-windows-server-foundations` |
| AD DS, DNS, Kerberos and GPO | `02-active-directory-dns-gpo` |
| PowerShell Remoting, scripting and reporting | `03-powershell-administration` |
| SMB, NTFS and access troubleshooting | `04-file-services-permissions` |
| Entra ID join, hybrid join and Conditional Access | `05-entra-id-identity` |
| Autopilot, Intune, Windows Update for Business, Autopatch, EPM | `06-intune-endpoint-management` |
| Azure VMs, VNets, RBAC, Azure Arc and Update Manager | `07-azure-core-administration` |
| BitLocker, LAPS, monitoring, backup, Defender concepts | `08-monitoring-backup-security` |
| End-to-end hybrid operations | `09-hybrid-operations-capstone` |

### Lab Design Rule

When a lab uses one of these technologies, it should not only explain what the product does. It should also require verification evidence, troubleshooting, and production reflection.

Example:

> Do not just create an Autopilot deployment profile. Explain what user/device problem it solves, what licence or tenant assumptions are required, how enrolment is verified, what could fail during OOBE, how the issue would be diagnosed, and what rollback or recovery path exists.
