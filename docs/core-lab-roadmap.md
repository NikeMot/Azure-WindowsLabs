# Core Lab Roadmap

### Purpose

This document defines the lab count and coverage model for the `Azure-WindowsLabs` programme.

The core programme uses exactly **16 source-led labs**. These labs cover the Windows Server 2022 and PowerShell book structure, while integrating PowerShell automation, Azure cloud parity, Intune, Autopilot, Modern Operating Systems theory, job-aligned production operations and operational principles from the Practice books.

After the 16 core labs, the programme adds exactly **8 drill labs** to reinforce, combine and pressure-test the skills. The final drill is an SRE-style capstone.

### Lab Count Decision

| Phase | Lab count | Purpose |
| --- | ---: | --- |
| Core source-led labs | 16 | Cover the main Windows Server 2022 and PowerShell content and the wider Windows/Azure production infrastructure stack |
| Drill labs | 8 | Reinforce everything through troubleshooting, automation, timed builds and mixed production scenarios |
| Total | 24 | Full learning path before moving into a new specialist series |

### Two-Part Core Lab Model

Every core lab must have two parts:

| Part | Name | Purpose |
| --- | --- | --- |
| Part A | New Content | Learn and apply the new topic from the primary source |
| Part B | Cumulative Drill | Drill everything learned so far in a production-style scenario |

Detailed rules are tracked in:

```text
docs/two-part-lab-model.md
```

The seven reflection questions remain unchanged. Do not add extra reflection questions just because a lab has two parts.

### Source Model

| Source role | Source | Use |
| --- | --- | --- |
| Primary book | Windows Server 2022 and PowerShell | Main structure for the 16 core labs |
| PowerShell depth | Learn PowerShell in a Month of Lunches | Strong scripting, objects, pipeline, functions, remoting and automation practice |
| Azure support | Learning Microsoft Azure | Azure compute, networking, storage, identity, monitoring, backup and hybrid relevance |
| Azure implementation recipes | Azure Cookbook | Practical Azure implementation patterns and operational recipes |
| Endpoint cloud management | Microsoft Intune Cookbook | Intune, endpoint policies, compliance, app deployment and endpoint troubleshooting |
| Operating systems theory | Modern Operating Systems, 5e | Processes, memory, filesystems, virtualisation, networking, security and reliability concepts behind the admin work |
| Operational principles | The Practice of System and Network Administration | Documentation, troubleshooting, service ownership, change control and operational maturity |
| Cloud operations principles | The Practice of Cloud System Administration | Automation, reliability, monitoring, scaling, failure handling and cloud operations thinking |
| Current procedure | Microsoft Learn | Current Azure, Intune, Autopilot, Entra, Monitor, Backup, Arc and Update Manager guidance |
| SRE concepts | SRE capstone standard | Service reliability, SLI/SLO thinking, incident response, toil reduction and post-incident review |
| AI support | AI Usage Standard / Copilot documentation | Safe AI use for scripting, KQL, troubleshooting, documentation and review |

### Cloud Parity Rule

Because the learner has already passed AZ-104, Azure is treated as a practical administration layer throughout the programme, not as beginner theory.

For every local Windows capability, each relevant lab must ask:

```text
What is the Azure, Intune, Entra, Autopilot, Arc, Monitor, Backup, Update Manager, PowerShell or CLI equivalent?
```

The detailed mapping is tracked in:

```text
docs/azure-cloud-parity-standard.md
```

### Mandatory Production Anchors

The following anchors must be included in the 16 core labs and reinforced in the 8 drill labs:

| Anchor | Where it must appear | Purpose |
| --- | --- | --- |
| IIS/application outage investigation | Core Labs 08-09, Drill D05, Drill D08 | Prepare for IIS, FTP and application environment support |
| 100-server estate simulation with PowerShell reporting | Core Labs 13-15, Drill D01, Drill D04 | Prepare for 90/100+ Windows Server estate thinking |
| VMware/SAN/storage incident simulation | Core Labs 03, 10, 12, Drill D06 | Prepare for VMware, SAN, datastore, snapshot and storage-risk conversations |
| On-call incident communication pack | Core Labs 12, 16, Drill D08 | Prepare for on-call, stakeholder updates, escalation and PIR notes |
| SRE-style reliability capstone | Core Lab 16, Drill D08 | Prepare for SRE/platform-style service ownership, reliability and incident response |

### SRE Capstone Rule

The capstone must be SRE-related.

It must simulate operating a production service rather than only configuring infrastructure. The service should include Windows Server, AD/DNS dependency, IIS or application access, storage, monitoring, backup/recovery, Azure or hybrid comparison, incident response, stakeholder communication and PowerShell automation.

The detailed standard is tracked in:

```text
docs/sre-capstone-standard.md
```

The capstone must include:

* service overview
* dependency map
* SLI/SLO definition
* monitoring evidence
* alert or incident trigger
* incident timeline
* technical triage notes
* stakeholder update
* recovery or rollback plan
* post-incident review
* automation artefact
* reliability improvement backlog

### Core Labs: 16 Labs

The Windows Server 2022 and PowerShell book has an eight-book structure. The core programme maps to that structure as **two labs per book**. Where the exact internal book title differs from the topic name below, the lab should still follow the corresponding section of the source book.

| Lab | Primary coverage | Lab title | Part A: new content | Part B: cumulative drill |
| --- | --- | --- | --- | --- |
| 01 | Book 1 — Windows Server and PowerShell foundations | Windows Server and PowerShell Foundation | Inspect one Windows Server with PowerShell, transcript evidence and OS theory | Repeat server inspection from memory and produce a readiness note |
| 02 | Book 1 — Server Manager, roles and admin model | Server Roles, Features and Remote Administration | Inspect roles/features, Server Manager, RSAT/remote admin and Azure management comparison | Re-run Lab 01 readiness checks, then add role/feature and remote admin evidence |
| 03 | Book 2 — Installation, storage and server configuration | Windows Server Storage and Filesystem Administration | Configure/inspect disks, volumes, NTFS and Azure managed disk comparison | Drill server readiness plus storage capacity, SAN/LUN/datastore and snapshot-vs-backup reasoning |
| 04 | Book 2 — Updates, services and performance basics | Patching, Services and Performance Readiness | Assess Windows Update, services, hotfixes, performance counters and Azure Update Manager | Drill server/storage readiness plus service health, performance and patch-state evidence |
| 05 | Book 3 — Active Directory foundations | Build the First Domain Controller | Install/configure AD DS intentionally and verify domain/DNS health | Drill Labs 01-04 checks, then add AD health and replication-style evidence |
| 06 | Book 3 — Users, groups, OUs and delegation | AD Object Administration and Delegated Access | Build OU/group/user/delegation model with PowerShell and CSV validation | Drill previous checks plus joiner/mover/leaver workflow and access verification |
| 07 | Book 4 — DNS and Group Policy | DNS, Group Policy and Client Behaviour | Configure DNS/GPO and compare GPO with Intune policy models | Drill AD/user/DNS/GPO plus DNS records relevant to applications and mail-flow concepts |
| 08 | Book 4 — File services and permissions | File Services, Shares, IIS and FTP Access | Configure file services plus IIS/FTP concepts where appropriate | Drill access-denied troubleshooting plus app/file access, IIS binding/log and FTP port reasoning |
| 09 | Book 5 — Networking and remote access | Windows Networking and Application Connectivity | Configure firewall/remote admin/network diagnostics for RDP, WinRM, IIS/FTP/app access | Drill app unreachable scenario using DNS, firewall, service state, IIS/FTP and Azure NSG-style thinking |
| 10 | Book 5 — Virtualisation/hybrid readiness | VMware, Hyper-V and Azure VM Operations | Compare VM lifecycle, snapshots/checkpoints, datastores, vNICs and Azure VM concepts | Drill storage/network/server readiness through a simulated VM/datastore/capacity incident |
| 11 | Book 6 — Security and local protection | Windows Security Baseline | Apply and verify local hardening, LAPS concepts, least privilege and auditability | Drill previous infrastructure checks plus security finding, privilege review and remediation note |
| 12 | Book 6 — Backup, recovery and operational resilience | Backup, Restore and Recovery Readiness | Prove backup/restore thinking, snapshot distinction and Azure Backup comparison | Drill recovery incident with stakeholder update, rollback plan and storage/SAN failure reasoning |
| 13 | Book 7 — PowerShell administration | PowerShell Objects, Pipeline and Estate Reporting | Build structured reports using objects, pipeline, CSV/JSON and Azure-shaped output | Drill a 100-server estate simulation: inventory, role, patch, backup, app and monitoring report |
| 14 | Book 7 — PowerShell remoting and modules | PowerShell Remoting and Admin Tooling | Use remoting/module patterns, transcripts, errors and safe admin boundaries | Drill production fleet administration across simulated servers with remoting/run command comparison |
| 15 | Book 8 — PowerShell scripting and automation | Production-Style PowerShell Automation | Build reusable support automation with parameters, validation, logging and idempotence thinking | Drill estate automation for IIS/app health, services, disk, patch or backup checks |
| 16 | Book 8 — Integrated Windows/Azure/SRE operations | SRE-Style Windows Service Reliability Capstone | Define and operate a Windows/IIS service with AD, DNS, storage, monitoring, backup, Azure/hybrid comparison and PowerShell automation | Final cumulative SRE drill: service degradation or outage, SLI/SLO evidence, triage, mitigation, stakeholder update, rollback/recovery, PIR and reliability backlog |

### Dedicated PowerShell Standard

PowerShell is not treated as a side skill. It appears in every core lab and becomes the main technical focus in Labs 13 to 16.

By the end of the 16 core labs, the learner should be able to:

* discover commands with `Get-Command` and `Get-Help`
* understand objects and pipeline behaviour
* filter, sort, select and format output correctly
* export evidence to CSV, JSON and text
* query Windows Server state repeatably
* use AD, DNS, networking and firewall cmdlets
* inspect IIS, service, event log, disk, backup and estate health information
* write scripts with parameters and validation
* handle errors intentionally
* create logs and transcripts
* write basic functions
* avoid unsafe automation
* explain idempotence and rollback thinking
* compare local PowerShell administration with Azure CLI, Az PowerShell and cloud runbook patterns
* build an SRE-style health check or incident evidence collector
* use PowerShell evidence in operational documentation

### Azure Practical Standard

Azure must be covered thoroughly across the 16 labs.

By the end of the core labs, the learner should be able to explain and, where cost/licensing permits, perform:

* Azure VM creation and secure access
* VM image, size, region, disk and networking decisions
* VNet, subnet, NIC, private IP, public IP and NSG design
* Windows Firewall versus NSG boundaries
* Azure RBAC and management-plane privilege
* Azure Monitor, Log Analytics, KQL, metrics, alerts and workbooks
* Azure Update Manager and update compliance
* Azure Backup and Recovery Services vaults
* Azure Arc-enabled server onboarding concepts
* Defender for Cloud and Azure Policy concepts
* Entra ID, Conditional Access and hybrid identity comparisons
* Intune configuration profiles, compliance policies and security baselines
* Windows Autopilot and Autopilot device preparation concepts
* Windows Update for Business and Windows Autopatch
* Azure CLI, Az PowerShell and automation patterns
* cloud cost control and cleanup

### SRE Practical Standard

By the end of the capstone, the learner should be able to explain and demonstrate:

* service ownership
* dependency mapping
* basic SLI/SLO design
* availability and error-budget thinking
* monitoring and alert evidence
* incident severity and triage
* mitigation versus root-cause fix
* rollback/recovery planning
* post-incident review
* toil reduction through automation
* reliability improvement backlog

### Modern Operating Systems Standard

Modern Operating Systems, 5e is used as a theory reference across the labs. It should not become a separate passive reading exercise.

Use it to explain:

| Concept | Applied in labs |
| --- | --- |
| Processes and services | Windows services, IIS/app pools, startup behaviour, failures and service recovery |
| Memory and resource management | Performance readiness, monitoring, capacity, VM sizing |
| Filesystems | NTFS, shares, permissions, backup and restore |
| Virtualisation | VMware, Hyper-V, VM checkpoints, Azure VMs and cloud abstraction |
| Networking | DNS, TCP/IP, firewall, WinRM, RDP, IIS, FTP and Azure networking |
| Security | ACLs, privileges, identity, isolation and attack surface |
| Reliability | Backups, monitoring, incident response, failure domains |

### Drill Labs: 8 Labs

The drill block starts only after the 16 core labs are complete. These are full production simulations, not new theory labs.

| Drill | Title | Purpose |
| --- | --- | --- |
| D01 | Timed 100-Server Estate Readiness Assessment | Assess a simulated 100-server estate quickly and accurately, then map findings to Azure VM or Arc evidence |
| D02 | Broken AD Login Drill | Diagnose user login failure across AD, DNS, GPO, Entra comparison and local client evidence |
| D03 | File or App Access Denied Drill | Troubleshoot NTFS/share/group membership/IIS app access issue and map equivalent Azure Files access thinking |
| D04 | PowerShell Estate Automation Drill | Build a working admin script under constraints using logs, validation and Azure-shaped output |
| D05 | IIS/FTP/Application Unreachable Drill | Diagnose blocked or broken application access across DNS, firewall, IIS/FTP, service state and NSG-style reasoning |
| D06 | VMware/SAN/Backup Recovery Drill | Resolve a storage/snapshot/backup misunderstanding and produce recovery evidence |
| D07 | Azure Hybrid Readiness Drill | Map local server state to Azure Monitor, Backup, Arc, Update Manager and governance readiness |
| D08 | Final SRE Production Incident Capstone | Operate a simulated Windows/IIS service through degradation or outage: SLI/SLO check, alert, triage, mitigation, recovery, stakeholder update, PIR and reliability backlog |

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
