# Core Lab Roadmap

### Purpose

This document defines the lab count and coverage model for the `Azure-WindowsLabs` programme.

The core programme uses exactly **16 source-led labs**. These labs cover the Windows Server 2022 and PowerShell book structure, while integrating PowerShell automation, Azure cloud parity, Intune, Autopilot, Modern Operating Systems theory, and operational principles from the Practice books.

After the 16 core labs, the programme adds exactly **8 drill labs** to reinforce, combine and pressure-test the skills.

### Lab Count Decision

| Phase | Lab count | Purpose |
| --- | ---: | --- |
| Core source-led labs | 16 | Cover the main Windows Server 2022 and PowerShell content and the wider Windows/Azure admin stack |
| Drill labs | 8 | Reinforce everything through troubleshooting, automation, timed builds and mixed scenarios |
| Total | 24 | Full learning path before moving into a new specialist series |

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

### Core Labs: 16 Labs

The Windows Server 2022 and PowerShell book has an eight-book structure. The core programme maps to that structure as **two labs per book**. Where the exact internal book title differs from the topic name below, the lab should still follow the corresponding section of the source book.

| Lab | Primary coverage | Lab title | Main outcome | PowerShell / automation emphasis | Azure / cloud parity | Modern OS theory link |
| --- | --- | --- | --- | --- | --- | --- |
| 01 | Book 1 — Windows Server and PowerShell foundations | Windows Server and PowerShell Foundation | Understand the server as an admin target | Discovery commands, objects, transcript evidence | Compare local VM/server inspection with Azure VM inventory, resource metadata and Azure Arc representation | OS identity, boot state, kernel/user space, services |
| 02 | Book 1 — Server Manager, roles and admin model | Server Roles, Features and Remote Administration | Safely inspect and manage roles/features without random installs | `Get-WindowsFeature`, Server Manager comparison, remote admin notes | Compare Server Manager/RSAT with Azure portal, Azure Bastion, Arc extensions and VM run command concepts | System services, privilege boundaries, remote management |
| 03 | Book 2 — Installation, storage and server configuration | Windows Server Storage and Filesystem Administration | Configure and verify disks, volumes and filesystem state | Disk/volume cmdlets, reporting script | Compare local disks with Azure managed disks, snapshots, data disks, temporary disks and Azure Files | Filesystems, metadata, block devices, persistence |
| 04 | Book 2 — Updates, services and performance basics | Patching, Services and Performance Readiness | Assess update state, services and performance counters | Service reports, hotfix checks, PerfMon/PowerShell evidence | Compare local patching with Azure Update Manager, automatic VM guest patching, hotpatching and Azure Monitor metrics | Scheduling, resource usage, CPU/memory/I/O bottlenecks |
| 05 | Book 3 — Active Directory foundations | Build the First Domain Controller | Install AD DS intentionally and verify domain health | AD DS install evidence, AD cmdlets, DNS checks | Compare AD DS with Entra ID, Entra Domain Services and hybrid identity assumptions | Authentication, naming, distributed systems dependencies |
| 06 | Book 3 — Users, groups, OUs and delegation | AD Object Administration and Delegated Access | Build OU/group model and administer users safely | Bulk user/group scripts, CSV import, validation | Compare AD users/groups/delegation with Entra users, groups, Azure RBAC and PIM concepts | Identity, authorisation, access control models |
| 07 | Book 4 — DNS and Group Policy | DNS, Group Policy and Client Behaviour | Configure DNS and GPO, verify client application | GPO reports, DNS cmdlets, client verification | Compare GPO with Intune configuration profiles, settings catalog, security baselines and Autopilot-targeted device setup | Name resolution, policy application, caching |
| 08 | Book 4 — File services and permissions | File Services, Shares and NTFS Access | Build least-privilege file access and troubleshoot denial | Share/NTFS commands, access report script | Compare SMB/NTFS with Azure Files, identity-based access and private endpoint concepts | Filesystem permissions, ACLs, inheritance |
| 09 | Book 5 — Networking and remote access | Windows Networking and Secure Remote Administration | Configure/administer network profile, firewall and remote management | Firewall rules, WinRM checks, network diagnostics | Compare Windows Firewall/WinRM/RDP with NSGs, ASGs, Bastion, VPN/Private Link and Network Watcher concepts | TCP/IP, ports, sockets, remote procedure concepts |
| 10 | Book 5 — Virtualisation/hybrid readiness | Hyper-V or VM Operations and Azure Readiness | Understand VM operations, checkpoints and cloud migration readiness | VM inventory, checkpoint notes, Azure mapping | Compare Hyper-V/local VM operations with Azure VMs, images, availability zones, disks, snapshots and Azure Arc | Virtualisation, isolation, resource scheduling |
| 11 | Book 6 — Security and local protection | Windows Security Baseline | Apply and verify local security controls | Security policy export, local users/groups, firewall audit | Compare local hardening with Defender for Cloud, Azure Policy, Intune security baselines, LAPS and Conditional Access signals | Protection rings, least privilege, attack surface |
| 12 | Book 6 — Backup, recovery and operational resilience | Backup, Restore and Recovery Readiness | Prove backup/recovery thinking before critical roles | Backup checks, recovery notes, restore validation | Compare local recovery with Azure Backup, Recovery Services vault, Azure VM backup and restore validation | Reliability, failure modes, durable storage |
| 13 | Book 7 — PowerShell administration | PowerShell Objects, Pipeline and Reporting | Produce admin reports from server/AD/Azure-style data | Objects, pipeline, formatting, CSV/JSON export | Produce local and Azure-shaped reports using Azure CLI/Az concepts, Resource Graph-style thinking and Log Analytics evidence | Processes, streams, structured data |
| 14 | Book 7 — PowerShell remoting and modules | PowerShell Remoting and Admin Tooling | Use remoting/module patterns safely | Remoting, modules, error handling, transcripts | Compare PowerShell Remoting with Azure Run Command, Automation runbooks, Arc extensions and managed identity boundaries | Remote execution, trust boundaries, network services |
| 15 | Book 8 — PowerShell scripting and automation | Production-Style PowerShell Automation | Build reusable admin script with parameters, validation and logging | Functions, parameters, idempotence, logging, errors | Convert local automation thinking into Azure CLI/Az PowerShell, Azure Automation, GitHub Actions or Functions design | Automation safety, state management, failure handling |
| 16 | Book 8 — Integrated Windows/Azure operations | Windows Server to Azure Operations Bridge | Connect local admin thinking to Azure monitoring, identity, backup or governance | Azure CLI/PowerShell mapping, KQL starter, runbook | Implement or design cloud parity across Azure Monitor, Backup, Update Manager, Arc, Entra, Intune, Autopilot and governance | Cloud abstraction, monitoring, distributed reliability |

### Dedicated PowerShell Standard

PowerShell is not treated as a side skill. It appears in every core lab and becomes the main technical focus in Labs 13 to 16.

By the end of the 16 core labs, the learner should be able to:

* discover commands with `Get-Command` and `Get-Help`
* understand objects and pipeline behaviour
* filter, sort, select and format output correctly
* export evidence to CSV, JSON and text
* query Windows Server state repeatably
* use AD, DNS, networking and firewall cmdlets
* write scripts with parameters and validation
* handle errors intentionally
* create logs and transcripts
* write basic functions
* avoid unsafe automation
* explain idempotence and rollback thinking
* compare local PowerShell administration with Azure CLI, Az PowerShell and cloud runbook patterns
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

### Modern Operating Systems Standard

Modern Operating Systems, 5e is used as a theory reference across the labs. It should not become a separate passive reading exercise.

Use it to explain:

| Concept | Applied in labs |
| --- | --- |
| Processes and services | Windows services, startup behaviour, failures and service recovery |
| Memory and resource management | Performance readiness, monitoring, capacity, VM sizing |
| Filesystems | NTFS, shares, permissions, backup and restore |
| Virtualisation | Hyper-V, VM checkpoints, Azure VMs and cloud abstraction |
| Networking | DNS, TCP/IP, firewall, WinRM, RDP and Azure networking |
| Security | ACLs, privileges, identity, isolation and attack surface |
| Reliability | Backups, monitoring, incident response, failure domains |

### Drill Labs: 8 Labs

The drill block starts only after the 16 core labs are complete.

| Drill | Title | Purpose |
| --- | --- | --- |
| D01 | Timed Server Readiness Assessment | Repeat Lab 1 style inspection quickly and accurately from a fresh VM, then map findings to Azure VM or Arc evidence |
| D02 | Broken AD Login Drill | Diagnose user login failure across AD, DNS, GPO, Entra comparison and local client evidence |
| D03 | File Access Denied Drill | Troubleshoot NTFS/share/group membership access issue and map the equivalent Azure Files access model |
| D04 | PowerShell Automation Drill | Build a working admin script under constraints using logs, validation and Azure-shaped output |
| D05 | Network and Firewall Drill | Diagnose blocked remote admin or application connectivity across Windows Firewall and NSG-style thinking |
| D06 | Backup and Restore Drill | Prove recovery of a file, config or server role state and compare with Azure Backup restore evidence |
| D07 | Azure Hybrid Readiness Drill | Map local server state to Azure Monitor, Backup, Arc, Update Manager and governance readiness |
| D08 | Final Mixed Operations Drill | Combine Windows Server, AD, PowerShell, Azure, Intune, Autopilot, monitoring, security and AI-assisted review |

### Completion Rule

Do not expand the core programme beyond 16 labs. Do not reduce it below 16 unless the user explicitly changes the scope.

After the 16 core labs, create the 8 drill labs as a separate phase.

Each lab remains source-led, practical, evidence-based and completed through the learner workflow: solve the lab, send evidence, answer seven questions, then the assistant documents and uploads the final version.
