# Azure and Windows System Administration Labs

### Overview

The `Azure-WindowsLabs` repository contains hands-on labs for developing practical Windows Server, Azure, identity, endpoint management, automation, monitoring, backup, security and operational troubleshooting skills.

This repository is designed to support my development toward Windows System Administrator, Azure Administrator, Cloud Support Engineer, Infrastructure Operations Engineer and Junior Platform/SRE-style roles.

The labs are not intended to be copy-paste tutorials. Each lab should require research, decision-making, implementation, verification, troubleshooting, documentation and production reflection.

### Lab Design Philosophy

The primary design guide for this repository is **The Practice of Cloud System Administration**. The labs should therefore focus on operational competence, not just product configuration.

Each lab should develop the ability to:

* understand the business or operational scenario
* design a sensible technical approach
* implement the solution safely
* automate where appropriate
* verify the final state with evidence
* troubleshoot realistic faults
* document decisions and trade-offs
* explain the production relevance
* identify what would need to improve in a real organisation

### Skills Covered

| Area | Status | Topics |
| --- | --- | --- |
| Windows Server foundations | Not started | installation, roles, services, patching, local administration |
| Active Directory, DNS and Group Policy | Not started | AD DS, domain controllers, OUs, users, groups, DNS, GPOs |
| PowerShell administration | Not started | objects, pipeline, scripting, reporting, automation, remoting |
| File services and permissions | Not started | shares, NTFS, access control, inheritance, auditability |
| Entra ID identity administration | Not started | users, groups, roles, MFA, SSPR, sign-in logs, Conditional Access basics |
| Intune endpoint management | Not started | enrolment, compliance, configuration profiles, app deployment, troubleshooting |
| Azure core administration | Not started | resource groups, RBAC, VNets, VMs, storage, NSGs, cost controls |
| Monitoring, backup and security operations | Not started | Azure Monitor, Log Analytics, alerts, backup, restore, hardening, incident response |
| Hybrid operations capstone | Not started | end-to-end Windows, identity, endpoint and Azure operations |

### Repository Structure

| Path | Purpose |
| --- | --- |
| `docs/` | General documentation, standards, lab template, repository decisions and operating rules |
| `01-windows-server-foundations/` | Windows Server installation, configuration, roles, services and base administration |
| `02-active-directory-dns-gpo/` | Active Directory Domain Services, DNS, OUs, users, groups and Group Policy |
| `03-powershell-administration/` | PowerShell fundamentals, automation, reporting, remoting and safe admin scripting |
| `04-file-services-permissions/` | File shares, NTFS permissions, inheritance, access troubleshooting and audit evidence |
| `05-entra-id-identity/` | Cloud identity administration with Entra ID, MFA, SSPR, roles and sign-in investigation |
| `06-intune-endpoint-management/` | Intune device management, compliance, configuration, application deployment and endpoint support |
| `07-azure-core-administration/` | Azure compute, storage, networking, RBAC, governance and cost-aware administration |
| `08-monitoring-backup-security/` | Monitoring, logging, backup, restore, alerting, security hardening and incident response |
| `09-hybrid-operations-capstone/` | Full hybrid Microsoft operations scenarios and final assessment labs |

### How to Use This Repository

Each topic folder contains lab outputs for that topic. Each lab should follow the standard template in `docs/lab-output-template.md`.

Each lab write-up should include:

* scenario
* reference material
* requirements
* constraints and assumptions
* implementation tasks
* key commands used
* files, resources or objects created
* verification evidence
* diagram where useful
* issues encountered
* decisions made
* security and production considerations
* final outcome
* learning reflection
* production improvements
* references used
* completion checklist
* reflection questions

### Reference Stack

The core reference stack for this repository is:

* The Practice of Cloud System Administration
* Windows Server 2022 and PowerShell
* Active Directory Administration Cookbook
* Learn PowerShell in a Month of Lunches
* Microsoft Intune Cookbook
* Learning Microsoft Azure
* Operating Systems references for theory and troubleshooting depth
* Microsoft Learn and official Microsoft documentation for current implementation guidance

### Security and Privacy Notes

This repository must not contain:

* passwords
* API keys
* SSH private keys
* `.env` files
* tenant secrets
* access tokens
* Azure subscription identifiers where unnecessary
* private IP information from real environments
* company data
* screenshots containing sensitive user, tenant, subscription or account information
* book PDFs or EPUBs
* copyrighted material

### Portfolio Goal

The final portfolio should show that I can build, support, troubleshoot and document a realistic Microsoft infrastructure environment across Windows Server, Active Directory, PowerShell, Entra ID, Intune and Azure.
