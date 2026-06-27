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

### Job Skill Coverage Map

| Job requirement | Lab coverage |
| --- | --- |
| Manage and maintain Windows Server environments | Labs 01-04, 09-12, 15-16 |
| 90/100+ Windows Server estate mindset | Estate reporting, inventory, automation, monitoring and drill labs |
| Active Directory | Labs 05-07 and Drill D02 |
| DNS | Labs 07 and 09, plus Azure DNS/private networking comparisons where useful |
| FTP | Added to application services coverage; IIS/FTP deployment and troubleshooting should appear in application environment labs |
| IIS | Added to application services coverage; web application hosting, bindings, logs, app pools and troubleshooting should be included |
| Mail environments | Cover through mail-flow concepts, SMTP relay concepts, DNS records, service ownership and stakeholder communications; no production mailbox system is required unless explicitly added later |
| Application environments | IIS, service dependencies, logs, certificates, DNS, firewall, monitoring and runbooks |
| Production environment experience | Every lab must include monitoring, change/incident thinking, rollback and evidence |
| On-call rotation | Drill labs must include incident triage, severity, escalation and handover notes |
| Stakeholder communication | Drill labs and final documentation must include incident/update summaries |
| Physical data centres | Add theory and checklist coverage for racking, cabling, hardware, power, network ports and escalation; no physical hardware required |
| VMware | Covered through virtualisation labs, VM lifecycle, snapshots, resource allocation and comparison to Azure VMs |
| SAN storage | Covered through storage labs: block storage, LUN/datastore concepts, redundancy, multipath concepts, snapshots and backup thinking |
| Linux | Covered through cross-platform operations checks, Linux VM support basics, logs, services, networking and SSH comparisons |
| Microsoft certification desirable | Learner has passed AZ-104; labs should produce portfolio evidence beyond certification |
| VMware certification desirable | Not required, but labs should teach enough VMware vocabulary and VM operations to discuss intelligently |

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

The existing 16 core labs remain fixed, but the lab content must include job alignment:

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
| 13 | Add estate reporting for many servers and application services |
| 14 | Add remoting and safe administration patterns for production fleets |
| 15 | Add production-grade PowerShell automation for support tasks |
| 16 | Add integrated local/Azure operations, monitoring, stakeholder comms and on-call runbook |

### Drill Lab Adjustments

The 8 drill labs must prepare for the target job through realistic incidents:

| Drill | Job-style scenario |
| --- | --- |
| D01 | Timed estate readiness assessment for multiple Windows servers |
| D02 | Broken AD login affecting production users |
| D03 | File/app access denied with AD group and NTFS/share dependency |
| D04 | PowerShell automation task for server estate or IIS/app health |
| D05 | Application unreachable due to firewall/DNS/IIS/FTP/port issue |
| D06 | Backup/restore or snapshot misunderstanding during recovery |
| D07 | Hybrid Azure monitoring/backups/Arc readiness for Windows estate |
| D08 | Full on-call simulation: alert, triage, stakeholder update, fix, evidence, PIR notes |

### Qualification Standard

By the end of the 16 core labs and 8 drill labs, the learner should be able to credibly say:

> I have built and supported a realistic Windows infrastructure lab covering Windows Server administration, Active Directory, DNS, IIS/application services, file services, PowerShell automation, monitoring, backup/recovery, virtualisation concepts, SAN/storage concepts, Linux support basics, Azure/hybrid operations, incident response and production documentation.

The learner should not claim professional production ownership of 100+ real servers unless true, but should be able to demonstrate portfolio evidence that maps directly to the responsibilities of the target job.
