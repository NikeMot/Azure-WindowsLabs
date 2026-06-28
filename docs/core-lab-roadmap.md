# Core Lab Roadmap

### Purpose

This document defines the lab count and coverage model for the `Azure-WindowsLabs` programme.

The programme uses exactly **16 core source-led labs** and **8 final drill labs**. The series develops Windows Server administration, Active Directory, DNS, IIS/application support, PowerShell, Desired State Configuration (DSC), Azure/hybrid operations, monitoring, backup, security, production troubleshooting and SRE-style reliability practice.

### Lab Count Decision

| Phase | Lab count | Purpose |
| --- | ---: | --- |
| Core source-led labs | 16 | Cover the Windows Server 2022 and PowerShell structure plus job-aligned infrastructure operations |
| Drill labs | 8 | Reinforce everything through timed, production-style troubleshooting and automation scenarios |
| Total | 24 | Full Windows/Azure infrastructure and SRE-readiness programme |

### Core Lab Format

Every core lab has two parts:

| Part | Purpose |
| --- | --- |
| Part A — New Content | Learn and apply the new topic from the primary source section |
| Part B — Cumulative Drill | Reuse everything learned so far in a production-style scenario |

Every lab must also include a controlled break/fix cycle:

```text
Known-good state -> controlled fault -> detection -> diagnosis -> fix or rollback -> recovery verification -> prevention note
```

### Standards Used

| Standard | File |
| --- | --- |
| Two-part lab model | `docs/two-part-lab-model.md` |
| Break/fix standard | `docs/break-fix-standard.md` |
| Azure cloud parity | `docs/azure-cloud-parity-standard.md` |
| DSC standard | `docs/dsc-standard.md` |
| SRE capstone standard | `docs/sre-capstone-standard.md` |
| Target job alignment | `docs/target-job-alignment.md` |

### Source Model

| Source role | Source | Use |
| --- | --- | --- |
| Primary book | Windows Server 2022 and PowerShell | Main structure for the 16 core labs |
| PowerShell depth | Learn PowerShell in a Month of Lunches | Pipeline, scripting, remoting, functions, automation and DSC support |
| DSC guidance | Microsoft DSC / PowerShell DSC documentation | Desired state, idempotence, configuration documents, resources and drift remediation |
| Azure governance | Azure Machine Configuration / Azure Policy documentation | OS/application configuration governance for Azure and Arc-enabled machines |
| Azure support | Learning Microsoft Azure / Azure Cookbook | Compute, networking, storage, identity, monitoring, backup and hybrid relevance |
| Endpoint cloud management | Microsoft Intune Cookbook / Microsoft Learn | Intune, Autopilot, endpoint compliance and policy troubleshooting |
| Operating systems theory | Modern Operating Systems, 5e | Processes, memory, filesystems, networking, security and reliability concepts |
| Operations principles | Practice books | Service ownership, documentation, change control, reliability and incident response |

### Mandatory Production Anchors

| Anchor | Required coverage |
| --- | --- |
| IIS/application investigation | IIS, FTP, app pools, bindings, logs, ports, DNS and service dependencies |
| 100-server estate simulation | Inventory, ownership, criticality, patch, backup, monitoring and reporting |
| VMware/SAN/storage scenario | VM lifecycle, datastore/LUN concepts, snapshots, capacity and recovery reasoning |
| On-call communication pack | Severity, timeline, impact, stakeholder update, rollback and PIR notes |
| DSC drift detection and remediation | Desired state, compliance check, controlled drift, remediation and Azure Machine Configuration comparison |
| SRE reliability capstone | Service ownership, SLI/SLO, monitoring, response, recovery, PIR and reliability backlog |

### DSC Coverage Rule

DSC is mandatory in the programme.

The learner must be able to explain and/or demonstrate:

* desired state versus imperative scripting
* idempotence
* configuration drift
* DSC resources and configuration documents
* local compliance validation
* configuration-as-code in source control
* drift remediation
* Azure Machine Configuration and Azure Policy comparison
* SRE relevance through drift detection and toil reduction

DSC should appear gradually:

| Lab stage | DSC emphasis |
| --- | --- |
| Labs 01-10 | No heavy DSC; build enough Windows/PowerShell context first |
| Lab 11 | Introduce baseline and desired-state thinking |
| Lab 13 | Add estate compliance reporting concepts |
| Lab 14 | Introduce DSC with remoting/configuration-management patterns |
| Lab 15 | Build DSC-style automation or validation workflow |
| Lab 16 | Use DSC/drift thinking in the SRE capstone |
| Drills D04, D07, D08 | Use DSC or Azure Machine Configuration in automation, hybrid governance and reliability scenarios |

### Core Labs: 16 Labs

| Lab | Primary coverage | Lab title | Part A — New Content | Part B — Cumulative Drill |
| --- | --- | --- | --- | --- |
| 01 | Windows Server and PowerShell foundations | Windows Server and PowerShell Foundation | Inspect one Windows Server with PowerShell, transcript evidence and OS theory | Repeat server inspection from memory and produce a readiness note |
| 02 | Server Manager, roles and admin model | Server Roles, Features and Remote Administration | Inspect roles/features, Server Manager, RSAT/remote admin and Azure management comparison | Re-run Lab 01 readiness checks, then add role/feature and remote admin evidence |
| 03 | Installation, storage and server configuration | Windows Server Storage and Filesystem Administration | Configure/inspect disks, volumes, NTFS and Azure managed disk comparison | Drill storage capacity, SAN/LUN/datastore and snapshot-vs-backup reasoning |
| 04 | Updates, services and performance basics | Patching, Services and Performance Readiness | Assess updates, services, hotfixes, performance counters and Azure Update Manager | Drill service health, performance and patch-state evidence |
| 05 | Active Directory foundations | Build the First Domain Controller | Install/configure AD DS intentionally and verify domain/DNS health | Drill server checks plus AD health and replication-style evidence |
| 06 | Users, groups, OUs and delegation | AD Object Administration and Delegated Access | Build OU/group/user/delegation model with PowerShell and CSV validation | Drill joiner/mover/leaver workflow and access verification |
| 07 | DNS and Group Policy | DNS, Group Policy and Client Behaviour | Configure DNS/GPO and compare GPO with Intune policy models | Drill DNS/GPO plus application and mail-flow record reasoning |
| 08 | File services, IIS and FTP | File Services, Shares, IIS and FTP Access | Configure file services plus IIS/FTP concepts where appropriate | Drill file/app access, IIS binding/log and FTP port reasoning |
| 09 | Networking and remote access | Windows Networking and Application Connectivity | Configure firewall/remote admin/network diagnostics for RDP, WinRM, IIS/FTP/app access | Drill application connectivity using DNS, firewall, service state and NSG-style thinking |
| 10 | Virtualisation and hybrid readiness | VMware, Hyper-V and Azure VM Operations | Compare VM lifecycle, checkpoints/snapshots, datastores, vNICs and Azure VM concepts | Drill VM/storage/network readiness through a simulated capacity or configuration issue |
| 11 | Security and local protection | Windows Security Baseline and Desired State Thinking | Apply/verify hardening, LAPS concepts, least privilege, auditability and desired-state baseline thinking | Drill security/configuration drift finding, privilege review and remediation note |
| 12 | Backup, recovery and operational resilience | Backup, Restore and Recovery Readiness | Prove backup/restore thinking, snapshot distinction and Azure Backup comparison | Drill recovery scenario with stakeholder update, rollback plan and storage/SAN reasoning |
| 13 | PowerShell administration | PowerShell Objects, Pipeline and Estate Compliance Reporting | Build structured reports using objects, pipeline, CSV/JSON, configuration state and Azure-shaped output | Drill a 100-server estate simulation with inventory, role, patch, backup, app, monitoring and compliance reporting |
| 14 | Remoting, modules and DSC | PowerShell Remoting, Admin Tooling and DSC | Use remoting/module patterns, transcripts, errors, safe admin boundaries and introduce DSC validation | Drill fleet administration plus desired-state drift detection |
| 15 | PowerShell scripting, DSC and automation | Production-Style PowerShell and DSC Automation | Build reusable support automation with parameters, validation, logging, idempotence and DSC/configuration-as-code thinking | Drill estate automation for IIS/app health, services, disk, patch, backup or DSC drift checks |
| 16 | Integrated Windows/Azure/SRE operations | SRE-Style Windows Service Reliability Capstone | Operate a Windows/IIS service with AD, DNS, storage, monitoring, backup, DSC/drift detection, Azure/hybrid comparison and PowerShell automation | Final cumulative SRE drill: service health issue, configuration drift hypothesis, SLI/SLO evidence, triage, mitigation, stakeholder update, recovery, PIR and reliability backlog |

### Drill Labs: 8 Labs

| Drill | Title | Purpose |
| --- | --- | --- |
| D01 | Timed 100-Server Estate Readiness Assessment | Assess a simulated 100-server estate and map findings to Azure VM or Arc evidence |
| D02 | Broken AD Login Drill | Diagnose user login failure across AD, DNS, GPO, Entra comparison and local client evidence |
| D03 | File or App Access Denied Drill | Troubleshoot NTFS/share/group membership/IIS app access and map equivalent Azure Files thinking |
| D04 | PowerShell and DSC Estate Automation Drill | Build an admin/configuration validation script using logs, desired-state thinking and Azure-shaped output |
| D05 | IIS/FTP/Application Unreachable Drill | Diagnose blocked or broken application access across DNS, firewall, IIS/FTP, service state and NSG-style reasoning |
| D06 | VMware/SAN/Backup Recovery Drill | Resolve a storage/snapshot/backup misunderstanding and produce recovery evidence |
| D07 | Azure Hybrid Readiness and Machine Configuration Drill | Map local server state to Azure Monitor, Backup, Arc, Machine Configuration, Azure Policy, Update Manager and governance readiness |
| D08 | Final SRE Production Incident Capstone | Operate a simulated Windows/IIS service through a reliability incident: SLI/SLO check, alert, configuration drift check, triage, mitigation, recovery, stakeholder update, PIR and reliability backlog |

### Required Final Portfolio Artefacts

By the end of the 16 core labs and 8 drill labs, the repository should contain or generate:

* server estate inventory report
* IIS outage runbook
* AD login failure runbook
* DNS/mail-flow troubleshooting checklist
* backup/restore evidence report
* patching/change plan
* on-call incident report
* stakeholder update examples
* PowerShell automation scripts
* DSC desired-state or compliance artefact
* configuration drift break/fix evidence
* Azure Machine Configuration comparison notes
* Azure/cloud parity comparison notes
* VMware/SAN/storage incident notes
* Linux support quick-check notes
* SRE service overview
* service dependency map
* SLI/SLO definition
* incident timeline
* post-incident review
* reliability improvement backlog

### Completion Rule

Do not expand the core programme beyond 16 labs. Do not reduce it below 16 unless the user explicitly changes the scope.

After the 16 core labs, create the 8 drill labs as a separate phase.

Each core lab has Part A for new content and Part B for cumulative drilling. Each lab remains source-led, practical, evidence-based and completed through the learner workflow: solve the lab, send evidence, answer seven questions, then the assistant documents and uploads the final version.
