# SRE Capstone Standard

### Purpose

The capstone for this programme should be SRE-related.

The learner is aiming for Windows infrastructure roles now, but the longer-term direction includes SRE, platform and reliability engineering. The final capstone should therefore combine Windows administration with reliability practices.

### Core Rule

The capstone must simulate operating a production service, not merely configuring infrastructure.

It should require the learner to:

* define the service being supported
* understand its dependencies
* monitor service health
* detect failure
* triage an incident
* communicate impact
* restore service
* document evidence
* write a post-incident review
* identify reliability improvements
* automate at least one operational task

### Capstone Service Model

The capstone service should include:

| Layer | Example component |
| --- | --- |
| Identity | AD DS, Entra ID or access-control dependency |
| Name resolution | DNS records or DNS dependency |
| Application | IIS-hosted application, static site, API mock or app service equivalent |
| File/storage dependency | SMB share, local disk, Azure Files or managed disk concept |
| Network access | Windows Firewall, NSG-style thinking, ports, routing or remote access |
| Monitoring | Event Viewer, IIS logs, service status, Azure Monitor or Log Analytics |
| Backup/recovery | local backup, snapshot distinction, Azure Backup concept or restore evidence |
| Automation | PowerShell support script, report, health check or runbook |
| Communication | stakeholder update, escalation note and post-incident review |

### SRE Concepts to Include

The capstone should include practical versions of these concepts:

* service ownership
* service dependency mapping
* SLIs and SLOs
* availability target
* error budget concept
* monitoring and alerting
* incident severity
* incident timeline
* triage and mitigation
* rollback or recovery plan
* post-incident review
* toil reduction
* automation
* runbook improvement
* reliability risk register

### Required Capstone Artefacts

The capstone must produce the following artefacts:

| Artefact | Purpose |
| --- | --- |
| Service overview | Explains what service is being operated and why it matters |
| Dependency map | Shows AD/DNS/IIS/storage/network/Azure dependencies |
| SLI/SLO definition | Defines how service health is measured |
| Monitoring evidence | Proves how failure would be detected |
| Incident timeline | Shows what happened and when |
| Stakeholder update | Demonstrates communication to non-technical or leadership audience |
| Technical triage notes | Shows investigation steps and evidence |
| Recovery or rollback plan | Shows how service would be restored safely |
| Post-incident review | Captures cause, impact, fix and follow-up actions |
| Automation artefact | Reduces manual toil or improves repeatability |
| Reliability improvement backlog | Lists future improvements and risk reduction |

### Suggested Capstone Scenario

A suitable final scenario is:

> A business-critical internal web application hosted on Windows Server/IIS becomes unavailable during an on-call shift. The service depends on AD groups for access, DNS for name resolution, Windows Firewall/IIS bindings for connectivity, local or shared storage for content, and monitoring/backup for recovery. The learner must triage the incident, prove the fault domain, restore service or propose a safe rollback, communicate impact, and produce a post-incident review with reliability improvements.

### Azure and Hybrid Extension

The SRE capstone must include Azure or hybrid thinking.

At minimum, it should explain or demonstrate:

* how Azure Monitor or Log Analytics would collect service evidence
* how Azure Backup or Recovery Services would support recovery
* how Azure Arc could represent the server for governance and monitoring
* how Azure VM, NSG and managed disk equivalents differ from the local implementation
* how Entra ID, Intune, Autopilot or Conditional Access concepts may affect access or endpoint reliability

### PowerShell Requirement

The capstone must include at least one PowerShell automation artefact, such as:

* service health check script
* IIS/app pool status report
* disk and service monitoring script
* event log query script
* server estate report
* incident evidence collector
* restart-with-validation helper
* runbook validation script

The script should include parameters, clear output, logging or transcript evidence, and basic error handling where practical.

### What the Capstone Should Prove

The capstone should prove that the learner can:

* operate a Windows-based service
* reason across AD, DNS, IIS, firewall, storage, monitoring and backup
* use PowerShell to collect and automate evidence
* communicate during an incident
* think in reliability terms, not only administration tasks
* connect local operations to Azure/hybrid operations
* produce documentation suitable for portfolio and interview discussion

### Boundary

The capstone does not require real production traffic or real customers.

It should be honest: this is a simulated production service. The learner should not claim real SRE production ownership unless true.

The correct claim is:

> I completed a simulated SRE-style capstone operating a Windows/IIS service with AD, DNS, storage, monitoring, backup, Azure/hybrid comparison, incident response, stakeholder communication, post-incident review and PowerShell automation.
