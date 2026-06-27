# Target Job Alignment

### Purpose

This document aligns the `Azure-WindowsLabs` programme to the target production infrastructure role described by the learner.

The target role is Windows-heavy, production-focused and infrastructure-oriented. AWS is intentionally ignored for this programme because the learner wants Windows, Azure and hybrid Microsoft infrastructure coverage instead.

### Target Role Summary

The lab series should prepare the learner to discuss, demonstrate and evidence capability in:

* managing and maintaining Windows Server environments
* supporting a 24/7 production environment
* working in a team of infrastructure engineers
* supporting medium to high complexity systems and applications
* managing or supporting Mail, DNS, FTP, IIS and application environments
* participating in on-call rotations
* understanding physical data centre tasks such as cabling, racking and hardware awareness
* communicating incidents, changes and events to stakeholders, teams and leadership
* administering Active Directory
* understanding VMware and virtualisation operations
* understanding SAN storage concepts
* supporting Linux basics alongside Windows
* documenting production-quality evidence

### Ignored Requirement

| Job requirement | Treatment |
| --- | --- |
| AWS EC2 | Ignored for this lab series. Azure VM and hybrid Azure operations are used instead. |

### Two-Part Training Rule

Each core lab now has two parts:

| Part | Purpose |
| --- | --- |
| Part A | Learn and apply new content from the current primary source section |
| Part B | Drill everything learned so far through a job-style scenario |

This matters for the target job because production infrastructure roles require recall under pressure, not just one-off completion of tutorials.

### Job Skill Coverage Map

| Job requirement | Lab coverage |
| --- | --- |
| Manage and maintain Windows Server environments | Labs 01-04, 09-12, 15-16, with cumulative drilling in every Part B |
| 90/100+ Windows Server estate mindset | 100-server estate simulation, inventory, automation, monitoring and drill labs |
| Active Directory | Labs 05-07, cumulative drills from Lab 05 onward, and Drill D02 |
| DNS | Labs 07 and 09, repeated in application, mail-flow and connectivity drills |
| FTP | Application services coverage; IIS/FTP deployment and troubleshooting in core and drill labs |
| IIS | Web hosting, bindings, logs, app pools, certificates, app outage triage and runbook output |
| Mail environments | Mail-flow concepts, SMTP relay concepts, DNS records, service ownership and stakeholder communications |
| Application environments | IIS, service dependencies, logs, certificates, DNS, firewall, monitoring and runbooks |
| Production environment experience | Every lab must include monitoring, change/incident thinking, rollback and evidence |
| On-call rotation | Part B cumulative drills and Drill D08 must include triage, severity, escalation and handover notes |
| Stakeholder communication | Cumulative drills and final documentation must include incident/update summaries |
| Physical data centres | Add theory and checklist coverage for racking, cabling, hardware, power, network ports and escalation; no physical hardware required |
| VMware | Covered through virtualisation labs, VM lifecycle, snapshots, resource allocation and comparison to Azure VMs |
| SAN storage | Covered through storage labs: block storage, LUN/datastore concepts, redundancy, multipath concepts, snapshots and backup thinking |
| Linux | Covered through cross-platform operations checks, Linux VM support basics, logs, services, networking and SSH comparisons |
| Microsoft certification desirable | Learner has passed AZ-104; labs should produce portfolio evidence beyond certification |
| VMware certification desirable | Not required, but labs should teach enough VMware vocabulary and VM operations to discuss intelligently |

### Mandatory Production Anchors

The following four anchors are mandatory.

| Anchor | Minimum evidence |
| --- | --- |
| IIS/application outage lab | IIS site/app pool/binding evidence, IIS logs, service checks, DNS and firewall/port checks, outage runbook |
| 100-server estate simulation | Inventory CSV, generated PowerShell reports, server role/criticality/owner/patch/backup/monitoring fields |
| VMware/SAN/storage incident simulation | VM lifecycle notes, datastore/LUN/capacity scenario, snapshot versus backup explanation, escalation/recovery note |
| On-call incident communication pack | Severity, incident timeline, impact statement, stakeholder update, escalation note, fix summary, rollback plan, PIR notes |

### New Coverage Requirements

The 16 core labs and 8 drill labs must include these additional job-specific themes:

1. **Application services**
   * IIS installation/configuration
   * websites, bindings and app pools
   * IIS logs
   * FTP service concepts
   * certificates and ports
   * service dependencies
   * app outage troubleshooting

2. **Mail/DNS/application operations**
   * DNS records that affect mail/app access
   * SMTP relay concepts
   * mail-flow troubleshooting vocabulary
   * service ownership and escalation boundaries
   * communicating user impact

3. **VMware and virtualisation**
   * VM lifecycle
   * snapshots/checkpoints
   * CPU/memory allocation
   * datastore concepts
   * vSwitch/network adapter concepts
   * comparison with Hyper-V and Azure VMs

4. **SAN and storage operations**
   * local disks versus shared storage
   * LUN/datastore concepts
   * block versus file storage
   * redundancy and failure domains
   * backup versus snapshot distinction
   * storage monitoring and capacity risk

5. **Linux support basics**
   * SSH access
   * systemd services
   * journal/log inspection
   * disk and memory checks
   * IP/DNS troubleshooting
   * package/update awareness
   * comparison with Windows service/logging model

6. **Production and on-call operations**
   * severity classification
   * incident timeline
   * escalation decision
   * stakeholder update
   * post-incident notes
   * change approval
   * rollback plan
   * monitoring and alert evidence

7. **Physical data centre awareness**
   * racking/cabling theory
   * patch panel and switch-port awareness
   * power, redundancy and labelling
   * hardware fault escalation
   * why remote hands instructions must be precise

### Lab Roadmap Adjustments

The existing 16 core labs remain fixed, but the lab content must include job alignment and cumulative Part B drilling:

| Lab | Added job alignment |
| --- | --- |
| 01 | Treat server inspection as estate-readiness evidence for a 90/100+ server environment |
| 02 | Add Server Manager/remote admin thinking for managing many servers |
| 03 | Add SAN, datastore, block/file storage and capacity-risk concepts |
| 04 | Add production patching, service ownership and performance monitoring |
| 05 | Add AD health, replication concepts and operational evidence |
| 06 | Add delegated access and joiner/mover/leaver operational workflow |
| 07 | Add DNS records relevant to apps and mail-flow concepts |
| 08 | Add file services plus FTP/IIS content where appropriate |
| 09 | Add firewall/port troubleshooting for IIS, FTP, RDP, WinRM and application access |
| 10 | Add VMware vocabulary, VM lifecycle, snapshots, datastores and Azure VM comparison |
| 11 | Add Windows hardening, LAPS, least privilege and production auditability |
| 12 | Add backup/restore versus snapshot, SAN failure thinking and DR communication |
| 13 | Add 100-server estate reporting for many servers and application services |
| 14 | Add remoting and safe administration patterns for production fleets |
| 15 | Add production-grade PowerShell automation for support tasks |
| 16 | Add integrated local/Azure operations, monitoring, stakeholder comms and on-call runbook |

### Drill Lab Adjustments

The 8 drill labs must prepare for the target job through realistic incidents:

| Drill | Job-style scenario |
| --- | --- |
| D01 | Timed 100-server estate readiness assessment |
| D02 | Broken AD login affecting production users |
| D03 | File/app access denied with AD group and NTFS/share dependency |
| D04 | PowerShell automation task for server estate or IIS/app health |
| D05 | Application unreachable due to firewall/DNS/IIS/FTP/port issue |
| D06 | VMware/SAN/backup or snapshot misunderstanding during recovery |
| D07 | Hybrid Azure monitoring/backups/Arc readiness for Windows estate |
| D08 | Full on-call simulation: alert, triage, stakeholder update, fix, evidence, rollback plan and PIR notes |

### Qualification Standard

By the end of the 16 core labs and 8 drill labs, the learner should be able to credibly say:

> I have built and supported a realistic Windows infrastructure lab covering Windows Server administration, Active Directory, DNS, IIS/application services, file services, PowerShell automation, monitoring, backup/recovery, virtualisation concepts, SAN/storage concepts, Linux support basics, Azure/hybrid operations, incident response and production documentation.

The learner should not claim professional production ownership of 100+ real servers unless true, but should be able to demonstrate portfolio evidence that maps directly to the responsibilities of the target job.
