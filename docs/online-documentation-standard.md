# Online Documentation Standard

### Purpose

Every lab in this repository must use current online documentation where the technology, command syntax, service behaviour or product guidance may change.

Books provide structure and depth. Online documentation provides currency.

### Core Rule

Each lab must include current online documentation in addition to book references when the lab uses Microsoft cloud, endpoint, PowerShell, DSC, Azure, Intune, Autopilot, Arc, monitoring, backup, policy, governance or SRE-style operations.

The preferred source is official vendor documentation.

For this programme, default to Microsoft Learn for Microsoft technologies.

### Documentation Freshness Rule

For each online source used, record:

| Field | Requirement |
| --- | --- |
| Source title | Name of the documentation page |
| Publisher | Microsoft Learn, vendor docs, GitHub docs, etc. |
| URL | Direct link to the documentation page |
| Accessed date | Date the page was checked |
| Last updated date | Record if shown on the page |
| Lab relevance | Why this page matters for the lab |
| Used for | Concept, procedure, command syntax, troubleshooting, comparison or verification |

If the documentation page has a visible **Last updated** date, include it in the lab report.

### Required Current Documentation Areas

Use current online documentation for these areas whenever they appear in a lab:

| Area | Preferred documentation |
| --- | --- |
| PowerShell DSC | Microsoft DSC / PowerShell DSC documentation |
| Azure Machine Configuration | Microsoft Learn Azure Machine Configuration documentation |
| Azure Policy | Microsoft Learn Azure Policy documentation |
| Azure Arc-enabled servers | Microsoft Learn Azure Arc documentation |
| Azure Monitor / Log Analytics | Microsoft Learn Azure Monitor documentation |
| Azure Backup | Microsoft Learn Azure Backup documentation |
| Azure Update Manager | Microsoft Learn Azure Update Manager documentation |
| Microsoft Intune | Microsoft Learn Intune documentation |
| Windows Autopilot | Microsoft Learn Autopilot documentation |
| Microsoft Entra ID | Microsoft Learn Entra documentation |
| Windows Server roles/features | Microsoft Learn Windows Server documentation where current behaviour matters |
| IIS | Microsoft Learn IIS / Windows Server documentation where current behaviour matters |
| GitHub Actions / GitHub repos | GitHub Docs |
| Security recommendations | Microsoft Learn, Microsoft Security documentation or official vendor guidance |

### Baseline Microsoft Learn Pages

These pages are baseline references for the programme. Check them again when writing or running the relevant lab.

| Topic | Current baseline documentation |
| --- | --- |
| Microsoft DSC overview | https://learn.microsoft.com/en-us/powershell/dsc/overview?view=dsc-3.0 |
| Azure Machine Configuration overview | https://learn.microsoft.com/en-us/azure/governance/machine-configuration/overview |
| Microsoft Intune overview | https://learn.microsoft.com/en-us/intune/fundamentals/what-is-intune |
| Windows Autopilot overview | https://learn.microsoft.com/en-us/autopilot/overview |
| Azure Arc-enabled servers overview | https://learn.microsoft.com/en-us/azure/azure-arc/servers/overview |
| Azure Update Manager overview | https://learn.microsoft.com/en-us/azure/update-manager/overview |
| Azure Backup overview | https://learn.microsoft.com/en-us/azure/backup/backup-overview |
| Azure Monitor overview | https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview |

### How to Use Online Docs in a Lab

Do not copy long documentation content into the lab.

Use online docs to verify:

* supported product behaviour
* current terminology
* command syntax
* service limitations
* prerequisites
* current feature names
* supported operating systems
* cloud governance models
* monitoring/backup/policy behaviour
* security or compliance requirements

### Evidence Requirement

The final lab report should include a documentation table like this:

| Source | Publisher | Last updated | Accessed | Used for |
| --- | --- | --- | --- | --- |
| Microsoft DSC overview | Microsoft Learn | 2025-06-09 | YYYY-MM-DD | DSC desired-state model and configuration documents |
| Azure Machine Configuration overview | Microsoft Learn | 2025-11-10 | YYYY-MM-DD | Azure Policy guest configuration and enforcement modes |

### Freshness Check Before Creating a New Lab

Before creating or updating a lab brief, check current online docs for any technology that has a high chance of changing.

At minimum, check online docs when the lab includes:

* Azure services
* Intune or Autopilot
* Entra ID
* DSC
* Azure Machine Configuration
* Azure Arc
* Azure Monitor
* Azure Backup
* Azure Update Manager
* GitHub Actions
* security/compliance guidance
* product names or features that may have changed

### Source Hierarchy

Use sources in this order:

1. Official Microsoft Learn or vendor documentation.
2. Official product GitHub repositories where Microsoft/vendor docs point to them.
3. Vendor blogs or technical community posts only when official docs are insufficient.
4. Third-party blogs only for troubleshooting context, never as the primary authority.

### Completion Rule

A lab that uses changing technologies is not complete unless it includes current online documentation evidence.

A completed lab should prove:

```text
Book structure -> current online documentation -> implementation -> break/fix -> verification -> production reflection
```
