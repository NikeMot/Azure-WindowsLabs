# Azure and Windows System Administration Labs

### Overview

The `Azure-WindowsLabs` repository contains hands-on labs for developing practical Windows Server, Azure, identity, endpoint management, automation, monitoring, backup, security, SRE-style reliability, AI-assisted administration and operational troubleshooting skills.

This repository is designed to support my development toward Windows System Administrator, Azure Administrator, Cloud Support Engineer, Infrastructure Operations Engineer and Junior Platform/SRE-style roles.

The labs are not intended to be copy-paste tutorials. Each lab should require research, decision-making, implementation, verification, troubleshooting, documentation, production reflection and deliberate break/fix practice.

### Target Job Alignment

The lab programme is aligned to a Windows-heavy production infrastructure role involving Windows Server administration, Active Directory, DNS, IIS/application support, FTP concepts, mail/DNS operations, VMware, SAN storage, Linux basics, production on-call, stakeholder communication and physical data-centre awareness.

AWS EC2 is intentionally ignored for this programme. Azure VM and hybrid Microsoft infrastructure are used instead.

Detailed job alignment is tracked in `docs/target-job-alignment.md`.

### SRE Capstone Direction

The capstone is SRE-related.

The final core lab and final drill should simulate operating a production Windows/IIS service, not merely configuring infrastructure. The capstone should include service ownership, dependency mapping, SLI/SLO thinking, monitoring, alerting, incident triage, stakeholder communication, rollback/recovery, post-incident review, reliability improvements and PowerShell automation.

Detailed SRE capstone rules are tracked in `docs/sre-capstone-standard.md`.

### Lab Design Philosophy

This repository is source-led.

The core lab series is built from **Windows Server 2022 and PowerShell** as the primary source. The book has an eight-book structure, so the programme uses exactly **16 core labs**, with two labs mapped to each book section.

Every core lab has two parts:

| Part | Purpose |
| --- | --- |
| Part A — New Content | Learn and apply the new topic from the primary source section |
| Part B — Cumulative Drill | Drill everything learned so far in a realistic production-style break/fix scenario |

Every lab must include the break/fix chain:

```text
Known-good state -> deliberate failure -> detection -> diagnosis -> fix -> recovery verification -> prevention note
```

After the 16 core labs, the programme adds exactly **8 drill labs** to reinforce and pressure-test the full skillset. Drill D08 is the final SRE production incident capstone.

Each lab should develop the ability to:

* understand the business or operational scenario
* work from one primary book section
* design a sensible technical approach
* implement the solution safely
* deliberately break a controlled lab component
* detect, diagnose and fix the failure
* automate where appropriate
* use AI critically where it improves investigation, scripting or documentation
* verify the final state with evidence
* troubleshoot realistic faults
* document decisions and trade-offs
* explain the production relevance
* identify what would need to improve in a real organisation

### Mandatory Production Anchors

The programme must include five hard production anchors:

| Anchor | Purpose |
| --- | --- |
| IIS/application outage investigation | Prepare for IIS, FTP, ports, certificates, bindings, logs and application support |
| 100-server estate simulation with PowerShell reporting | Prepare for 90/100+ Windows Server estate thinking |
| VMware/SAN/storage incident simulation | Prepare for VMware, datastore, LUN, snapshot, backup and capacity-risk discussions |
| On-call incident communication pack | Prepare for severity, stakeholder update, escalation, rollback and PIR communication |
| SRE-style reliability capstone | Prepare for service ownership, SLI/SLO thinking, reliability improvement and toil reduction |

### Skills Covered

| Area | Status | Topics |
| --- | --- | --- |
| Windows Server foundations | Not started | installation, roles, services, patching, local administration, Event Viewer, Windows Firewall, controlled break/fix |
| Active Directory, DNS and Group Policy | Not started | AD DS, domain controllers, OUs, users, groups, DNS, GPOs, Kerberos, domain join, identity/access faults |
| PowerShell administration | Not started | objects, pipeline, scripting, reporting, automation, remoting, error handling, automation failures |
| File services and permissions | Not started | shares, NTFS, SMB, access control, inheritance, auditability, access troubleshooting |
| Application services | Not started | IIS, FTP concepts, app pools, bindings, ports, certificates, logs, app support and outage triage |
| Mail and DNS operations | Not started | DNS records, mail-flow concepts, SMTP relay concepts, service ownership and escalation boundaries |
| Virtualisation and storage | Not started | VMware concepts, Hyper-V comparison, VM lifecycle, snapshots, datastores, SAN concepts and capacity risk |
| Linux support basics | Not started | SSH, systemd, logs, disk/memory checks, IP/DNS troubleshooting and service comparison with Windows |
| Entra ID identity administration | Not started | users, groups, roles, MFA, SSPR, sign-in logs, Conditional Access, Entra joined and hybrid joined devices |
| Intune endpoint management | Not started | Autopilot, device enrolment, Enrollment Status Page, compliance, configuration profiles, app deployment, device sync, troubleshooting |
| Modern Windows endpoint technologies | Not started | Windows Update for Business, Windows Autopatch, BitLocker, Windows LAPS, Windows Hello for Business, Endpoint Privilege Management, security baselines |
| Azure core administration | Not started | resource groups, RBAC, VNets, VMs, storage, NSGs, cost controls, Azure Arc and Update Manager basics |
| Production operations | Not started | on-call, incident triage, severity, escalation, change control, stakeholder updates and post-incident notes |
| Monitoring, backup and security operations | Not started | Azure Monitor, Log Analytics, alerts, backup, restore, hardening, incident response, operational evidence |
| SRE-style capstone | Not started | service ownership, dependency mapping, SLIs/SLOs, alerting, incident response, PIR, toil reduction and reliability backlog |
| AI-assisted administration operations | Not started | Azure Copilot, Security Copilot, GitHub Copilot, KQL assistance, script review, incident summaries, responsible AI use |

### Repository Structure

| Path | Purpose |
| --- | --- |
| `docs/` | General documentation, standards, lab template, repository decisions and operating rules |
| `01-windows-server-foundations/` | Windows Server installation, configuration, roles, services and base administration |
| `02-active-directory-dns-gpo/` | Active Directory Domain Services, DNS, OUs, users, groups and Group Policy |
| `03-powershell-administration/` | PowerShell fundamentals, automation, reporting, remoting and safe admin scripting |
| `04-file-services-permissions/` | File shares, NTFS permissions, inheritance, access troubleshooting and audit evidence |
| `05-entra-id-identity/` | Cloud identity administration with Entra ID, MFA, SSPR, roles and sign-in investigation |
| `06-intune-endpoint-management/` | Intune, Autopilot, compliance, configuration, application deployment, Windows update management and endpoint support |
| `07-azure-core-administration/` | Azure compute, storage, networking, RBAC, governance and cost-aware administration |
| `08-monitoring-backup-security/` | Monitoring, logging, backup, restore, alerting, security hardening and incident response |
| `09-hybrid-operations-capstone/` | SRE-style Windows/Azure service reliability capstone and final assessment labs |
| `10-ai-assisted-admin-operations/` | Safe and practical use of AI for scripting, troubleshooting, KQL, documentation and operational analysis |

### Lab Roadmap

The roadmap is tracked in `docs/core-lab-roadmap.md`.

| Phase | Lab count | Purpose |
| --- | ---: | --- |
| Core source-led labs | 16 | Cover the Windows Server 2022 and PowerShell book structure and the wider Windows/Azure production infrastructure stack |
| Drill labs | 8 | Reinforce everything through troubleshooting, automation, timed builds and mixed production scenarios |
| Total | 24 | Complete programme before starting the next specialist series |

The two-part lab model is tracked in `docs/two-part-lab-model.md`.

The break/fix rule is tracked in `docs/break-fix-standard.md`.

### How to Use This Repository

Each topic folder contains lab outputs for that topic. Each lab should follow the standard template in `docs/lab-output-template.md`.

Each lab write-up should include:

* scenario
* source mapping
* requirements
* constraints and assumptions
* Part A new content tasks
* Part B cumulative drill tasks
* break/fix exercise
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
* seven reflection questions

When AI is used in a lab, the lab must also record the tool used, the purpose, what was accepted, what was rejected and how the result was independently verified.

### Reference Stack

The core reference stack for this repository is:

* Windows Server 2022 and PowerShell
* Learn PowerShell in a Month of Lunches
* Learning Microsoft Azure
* Active Directory Administration Cookbook
* Microsoft Intune Cookbook
* Modern Operating Systems, 5e
* The Practice of System and Network Administration
* The Practice of Cloud System Administration
* Microsoft Learn and official Microsoft documentation for current implementation guidance
* SRE capstone standard
* Break/Fix Lab Standard
* Microsoft Learn Azure Copilot, Security Copilot and Azure AI Foundry documentation
* GitHub Copilot documentation

### Windows Technology Map

The detailed Windows technology coverage is tracked in `docs/windows-technology-map.md`. That document explicitly includes Windows Autopilot, Windows Autopatch, Windows Update for Business, BitLocker, Windows LAPS, Windows Hello for Business, Endpoint Privilege Management, security baselines, Azure Arc and related endpoint administration technologies.

### AI Usage Standard

The safe use of AI across this repository is tracked in `docs/ai-usage-standard.md`. AI may assist troubleshooting, scripting, KQL, documentation and incident analysis, but it must not replace verification, official documentation or administrator accountability.

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
* unsanitised AI prompts or outputs containing sensitive information

### Portfolio Goal

The final portfolio should show that I can build, support, troubleshoot, automate and document a realistic Microsoft infrastructure environment across Windows Server, Active Directory, DNS, IIS/application services, file services, PowerShell, VMware/SAN concepts, Linux basics, Entra ID, Intune, Autopilot, modern Windows endpoint management, Azure, monitoring, backup, production operations, SRE-style reliability practices, break/fix troubleshooting, operating systems fundamentals and safe AI-assisted administration.
