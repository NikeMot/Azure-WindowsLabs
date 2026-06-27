# Azure Cloud Parity Standard

### Purpose

This document defines how Azure should be covered across the `Azure-WindowsLabs` programme.

The learner has already passed AZ-104, so Azure should not be treated as a basic theory add-on. The lab series should build practical parity between local Windows administration and Azure or hybrid administration.

### Core Rule

For every local Windows Server administration capability, ask:

> What is the Azure equivalent, Azure extension, or cloud-managed comparison?

Not every local task has a direct Azure replacement, but every relevant lab should include one of these:

* Azure equivalent
* Azure hybrid extension
* Azure management-plane comparison
* Azure monitoring or backup integration
* Intune, Autopilot, Entra ID, or cloud endpoint comparison
* Azure PowerShell or Azure CLI equivalent

### Cloud Parity Map

| Local Windows capability | Azure / cloud equivalent or extension | Lab expectation |
| --- | --- | --- |
| Local VM / Hyper-V VM | Azure VM, VM size, image, disk, NIC, NSG, VNet | Compare local VM concepts to Azure VM resources and cost/security boundaries |
| Local disks and volumes | Azure managed disks, data disks, snapshots, temporary disk | Compare persistence, performance, backup and failure behaviour |
| Local networking | Azure VNet, subnet, NIC, private IP, public IP, NSG, route table | Map IP, DNS and firewall decisions to Azure networking design |
| Windows Firewall | NSG, ASG, Azure Firewall concepts, Defender network recommendations | Explain host firewall versus network control plane |
| Local admin users/groups | Azure RBAC, Entra roles, VM local admin, PIM concepts | Compare OS-level privilege with Azure management-plane privilege |
| Windows services | Azure VM extensions, Azure Arc extensions, VM insights process/dependency monitoring | Explain how services are observed and configured in cloud/hybrid environments |
| Windows Update | Azure Update Manager, automatic VM guest patching, hotpatching, Autopatch for endpoints | Compare local patch state with centralized update governance |
| Event Viewer | Azure Monitor Agent, Log Analytics, KQL, VM insights | Export or map event evidence to cloud observability |
| Performance Monitor | Azure Monitor metrics, VM insights, alerts, workbooks | Compare local counters with cloud metrics and dashboards |
| Backup / restore | Azure Backup, Recovery Services vault, Azure VM backup, MARS agent | Prove recovery thinking locally and in Azure |
| AD DS | Microsoft Entra ID, Microsoft Entra Domain Services, hybrid identity concepts | Distinguish directory, identity and authentication models |
| Group Policy | Intune configuration profiles, settings catalog, security baselines | Compare domain policy with MDM cloud policy |
| Domain join | Entra join, hybrid join, Intune enrolment, Autopilot | Compare traditional join with modern provisioning |
| Local software deployment | Intune app deployment, WinGet, scripts, remediation | Compare manual install with managed endpoint deployment |
| Local admin password management | Windows LAPS with AD or Entra ID backup | Explain local privilege control in local and cloud-managed models |
| Manual endpoint build | Windows Autopilot and Autopilot device preparation | Compare imaging/building with cloud provisioning |
| Manual update rings | Windows Update for Business and Windows Autopatch | Compare local patching with staged cloud rollout rings |
| Scripted admin task | Azure Automation, Functions, GitHub Actions, Azure CLI / Az PowerShell | Compare local scripts with cloud runbooks and automation control |
| Local server inventory | Azure Arc-enabled servers, Azure Resource Graph, Log Analytics inventory | Represent local/hybrid machines in Azure governance and monitoring |

### Required Azure Coverage Across 16 Core Labs

Azure must appear throughout the 16 core labs, not only in the final lab.

| Core lab range | Azure coverage expectation |
| --- | --- |
| Labs 01-04 | Compare local server inspection, roles, storage, updates and performance with Azure VM, managed disk, Azure Monitor and Update Manager concepts |
| Labs 05-08 | Compare AD DS, DNS, GPO and file services with Entra ID, cloud identity, Intune configuration, Azure Files and private networking concepts |
| Labs 09-12 | Map local networking, firewall, security, backup and recovery to VNet, NSG, RBAC, Azure Backup, Azure Monitor and Azure Arc |
| Labs 13-16 | Use PowerShell/Azure CLI/Az concepts to automate, report, monitor and govern Windows/Azure resources |

### Intune and Autopilot Coverage

The series must cover modern endpoint administration through:

* Microsoft Intune device enrolment
* Windows Autopilot deployment profiles
* Autopilot device preparation concepts
* Enrollment Status Page
* Entra join versus hybrid join
* device compliance
* configuration profiles
* security baselines
* Windows Update for Business
* Windows Autopatch
* BitLocker policy and recovery key handling
* Windows LAPS
* Windows Hello for Business
* Endpoint Privilege Management concepts
* Intune reporting and troubleshooting

### Minimum Azure Practical Skills After the Core Labs

After the 16 core labs and before the 8 drill labs, the learner should be able to explain or perform:

* create and secure an Azure VM
* choose VM size, region, image, disk and networking options
* configure VNet, subnet, NIC, private IP, public IP and NSG rules
* compare Windows Firewall and NSGs
* use Azure RBAC correctly
* use Azure Monitor, Log Analytics and KQL for operational evidence
* use Azure Update Manager for update compliance thinking
* use Azure Backup and Recovery Services vault concepts
* understand Azure Arc-enabled servers for local/hybrid machines
* compare AD DS with Entra ID and hybrid identity
* compare GPO with Intune configuration profiles
* explain Autopilot as the cloud provisioning model for Windows clients
* explain Windows Autopatch and Windows Update for Business
* use Azure CLI, Az PowerShell or portal evidence appropriately
* avoid unnecessary cloud cost and clean up resources

### AZ-104 Assumption

The learner has passed AZ-104. Therefore labs should not waste time on basic certification definitions unless needed for recall.

Labs should instead require:

* implementation decisions
* troubleshooting
* cost awareness
* least privilege
* monitoring evidence
* backup and recovery thinking
* cloud/local comparison
* automation with PowerShell, Azure CLI, or Az PowerShell
* documentation suitable for portfolio and interview use

### Microsoft Learn Usage

Microsoft Learn should be used for current Azure, Intune, Autopilot and Windows cloud-management procedures because cloud services change frequently.

Use Microsoft Learn for:

* Azure VM current behaviour
* Azure Monitor and Log Analytics
* Azure Update Manager
* Azure Backup
* Azure Arc-enabled servers
* Microsoft Intune
* Windows Autopilot
* Windows Autopatch
* Windows Update for Business
* Microsoft Entra ID and Conditional Access

### Completion Standard

A lab with local Windows content is not fully designed until it has answered:

1. What is the local Windows implementation?
2. What is the Azure, Intune, Entra or hybrid equivalent?
3. What PowerShell or CLI evidence proves the local state?
4. What portal, CLI, KQL or policy evidence would prove the cloud state?
5. What changes when the workload moves from local VM to Azure or cloud management?
6. What cost, identity, security, monitoring or backup risk appears in the cloud version?
