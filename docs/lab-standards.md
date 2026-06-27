# Lab Standards

### Purpose

This document defines the standard expected for every lab in this repository.

The labs should develop real Windows and Azure administration competence, not just familiarity with menus or commands.

### Core Rule

Every lab must require the learner to:

* understand a scenario
* identify requirements
* work from one primary book source
* complete Part A for new content
* complete Part B for cumulative drilling of everything learned so far
* perform a controlled break/fix exercise unless unsafe, destructive or irrelevant
* research supporting reference material only where relevant
* connect Windows behaviour to Modern Operating Systems theory where useful
* map local Windows administration to Azure, Intune, Entra, Autopilot or hybrid cloud equivalents where relevant
* make technical decisions
* implement the solution
* use PowerShell as a serious administration and automation tool
* use AI critically where it is relevant and safe
* verify the result with evidence
* troubleshoot at least one realistic issue where appropriate
* answer exactly seven reflection questions after solving the lab

The learner should focus on solving the lab. The final documentation should be produced from the learner's evidence and answers.

### Lab Count Standard

The main Windows/Azure administrator programme is:

| Phase | Count | Rule |
| --- | ---: | --- |
| Core source-led labs | 16 | Two labs per book section from the eight-book structure of Windows Server 2022 and PowerShell |
| Drill labs | 8 | Created after the 16 core labs to reinforce and pressure-test everything |
| Total | 24 | Full programme before beginning a new specialist series |

Do not expand the core programme beyond 16 labs unless the user explicitly changes the scope.

### Two-Part Lab Standard

Every core lab must use the two-part model from `docs/two-part-lab-model.md`.

| Part | Name | Requirement |
| --- | --- | --- |
| Part A | New Content | Introduce and practise the new topic from the primary book section |
| Part B | Cumulative Drill | Drill everything learned so far through a realistic production-style break/fix scenario |

Part B must become progressively harder as the series advances.

| Lab range | Cumulative drill expectation |
| --- | --- |
| Labs 01-04 | Server inspection, evidence capture, services, updates, storage, networking basics and simple controlled faults |
| Labs 05-08 | AD, DNS, GPO, users/groups, file services, IIS/FTP and access troubleshooting faults |
| Labs 09-12 | Networking, firewall, VMware/SAN concepts, security, backup, recovery and incident faults |
| Labs 13-16 | Estate-scale PowerShell, automation, Azure/hybrid operations, monitoring, runbooks, stakeholder communications and SRE-style break/fix incidents |

The seven reflection questions remain fixed. Do not add more reflection questions because a lab has two parts.

### Break/Fix Standard

Break/fix is mandatory because production infrastructure work is mostly diagnosis, recovery and prevention.

Every core lab should include a controlled fault, mainly in Part B, unless the fault would be unsafe, destructive or irrelevant.

Use `docs/break-fix-standard.md` as the detailed rule.

Every break/fix exercise should include:

1. proof the system worked before the fault
2. the controlled fault introduced
3. the user or service symptom
4. diagnostic evidence
5. root cause
6. fix or rollback
7. recovery verification
8. prevention or monitoring improvement
9. production risk note

### Source-Led Rule

Each lab should be anchored to one primary book section.

For the Windows administration track, the default primary source is:

```text
Windows Server 2022 and PowerShell
```

The lab should cover one meaningful unit from that book, such as one chapter, module, section or tightly related topic. The lab may be harder than the book, but it should clearly come from the book.

Supporting references may be used to deepen the lab:

* Learn PowerShell in a Month of Lunches for PowerShell technique
* Learning Microsoft Azure for Azure or hybrid relevance
* Azure Cookbook for practical Azure implementation patterns
* Microsoft Intune Cookbook for endpoint-management relevance
* Active Directory Administration Cookbook for AD-specific implementation
* Microsoft Learn for current procedures and supported syntax
* Modern Operating Systems, 5e for OS theory and system behaviour

Operating principles should come from:

* The Practice of System and Network Administration
* The Practice of Cloud System Administration

### Azure Cloud Parity Standard

Azure is a first-class part of the programme.

The learner has already passed AZ-104, so labs should not waste time on basic Azure definitions unless needed for recall. Labs should require cloud comparison, design judgement, implementation evidence or troubleshooting.

For each relevant local Windows task, the lab should ask:

```text
What is the Azure, Intune, Entra, Autopilot, Arc, Monitor, Backup, Update Manager, PowerShell or CLI equivalent?
```

Use `docs/azure-cloud-parity-standard.md` as the detailed mapping.

Every local Windows capability should be connected where relevant to:

* Azure VMs
* Azure managed disks
* Azure VNets, subnets, NICs, private IPs, public IPs and NSGs
* Azure RBAC and Entra ID
* Azure Monitor, Log Analytics, KQL and alerts
* Azure Update Manager
* Azure Backup and Recovery Services vaults
* Azure Arc-enabled servers
* Intune configuration profiles, compliance policies and security baselines
* Windows Autopilot and Autopilot device preparation
* Windows Update for Business and Windows Autopatch
* Azure CLI, Az PowerShell and automation patterns

### Job Alignment Anchors

The following anchors are mandatory because they directly map to the target production infrastructure job.

| Anchor | Evidence required |
| --- | --- |
| IIS/application outage investigation | IIS site/app pool/binding/log evidence, port/firewall/DNS checks, outage notes and runbook |
| 100-server estate simulation with PowerShell reporting | Inventory CSV, server-role mapping, criticality, patch/backup/monitoring status and generated reports |
| VMware/SAN/storage incident simulation | VM lifecycle notes, snapshot versus backup distinction, datastore/LUN/capacity issue and recovery/escalation notes |
| On-call incident communication pack | Severity, timeline, impact, stakeholder update, escalation, resolution, rollback and PIR notes |

These anchors should appear in both the core labs and the 8 drill labs.

### PowerShell Standard

PowerShell must be top-notch across the series.

Every core lab should include at least one meaningful PowerShell element:

* discovery command
* configuration check
* evidence capture
* report generation
* validation script
* troubleshooting query
* automation task
* error handling pattern
* transcript or logging practice
* Azure CLI or Az PowerShell comparison where cloud parity applies

Labs 13 to 16 should be heavily PowerShell-focused and should include scripting, automation, remoting, functions, parameters, logging, errors, idempotence and operational safety.

### Modern Operating Systems Standard

Modern Operating Systems, 5e should be used to explain the theory behind the practical Windows work.

Use it where relevant for:

* processes and services
* memory and resource management
* filesystems
* virtualisation
* networking
* security and access control
* reliability and failure modes

The OS theory must support the lab. It should not become passive reading detached from the practical task.

### Lab Difficulty Standard

Labs should be harder than the source material.

A weak lab says:

> Check server information.

A strong source-led lab says:

> Using the Windows Server 2022 and PowerShell server administration material as the primary guide, inspect the server with PowerShell, identify roles/features, network state, service state and operational risks, connect at least one finding to Modern Operating Systems theory, map the local task to Azure or hybrid cloud equivalents, then deliberately break one controlled element and recover it using evidence.

A weak AI-assisted lab says:

> Ask AI how to fix the error.

A strong AI-assisted lab says:

> Use AI to generate three troubleshooting hypotheses from sanitised symptoms, reject unsafe or unsupported suggestions, verify the remaining hypotheses with Event Viewer, PowerShell, Azure Monitor, Intune or Entra evidence, and document what the AI missed.

### Role Split

| Role | Responsibility |
| --- | --- |
| Learner | Solve Part A and Part B, collect safe evidence, report issues encountered and answer seven reflection questions |
| Assistant | Write the final documentation, apply the lab template, format evidence, add production considerations and upload the completed lab to the correct folder |

### Required Lab Sections

Each completed lab document should follow `docs/lab-output-template.md` and include:

1. Lab Summary
2. Scenario
3. Source Mapping
4. Requirements
5. Constraints
6. Assumptions
7. Expected Environment or Target State
8. Deliverables
9. Implementation Tasks: Part A and Part B
10. Break/Fix Exercise
11. Key Commands Used
12. Files, Resources or Objects Created or Changed
13. Verification Evidence
14. AI Assistance Used, if relevant
15. Diagram, if useful
16. Issues Encountered
17. Decisions Made
18. Security and Production Considerations
19. Final Outcome
20. What I Learned
21. What I Would Improve in Production
22. References Used
23. Completion Checklist
24. Seven Reflection Questions

### Evidence Standard

Each completed lab should include safe evidence such as:

* PowerShell command output
* Azure CLI command output
* Azure Portal setting descriptions
* Event Viewer findings
* Entra sign-in log findings
* Intune device compliance observations
* Azure Monitor or Log Analytics query results
* IIS logs where relevant
* DNS or network test output where relevant
* backup or restore verification
* break/fix baseline, fault, symptom, diagnosis, fix and recovery verification
* incident communication outputs where relevant
* screenshots only when they do not expose sensitive data

Do not include secrets, tenant identifiers, subscription IDs, private keys, tokens or company information.

### AI Evidence Standard

If AI is used in a lab, the final document should record:

| Item | Description |
| --- | --- |
| AI tool used | The tool used, such as Azure Copilot, Security Copilot, GitHub Copilot, ChatGPT or Microsoft Copilot |
| Purpose | What the tool was used for |
| Prompt summary | A short sanitised summary of the prompt |
| Output accepted | What was used from the AI response |
| Output rejected | What was incorrect, unsafe, irrelevant or unsupported |
| Human verification | How the result was verified without relying only on AI |

This should be captured without increasing the reflection question count beyond seven.

### Seven Reflection Questions

At the end of each lab, ask only these seven questions:

1. What problem did this lab solve?
2. What was the most important thing you configured, changed or proved?
3. What evidence proves the lab worked?
4. What issue or mistake did you encounter, and how did you fix or investigate it?
5. What would be risky about doing this in production?
6. What would you monitor, back up or document in a real environment?
7. What did you learn that you could explain in an interview?

### Reference Standard

Each lab should identify:

* the primary book section used
* supporting book sections, if used
* relevant Microsoft Learn documentation, if used
* Azure, Intune, Autopilot or Entra documentation used, if relevant
* Modern Operating Systems theory used, if relevant
* any AI documentation or AI tool guidance used
* why each reference was relevant

### Production Standard

Every final lab document should answer:

* What risk does this configuration introduce or reduce?
* How would this be monitored?
* How would this be backed up or recovered?
* What would need approval in production?
* What evidence would be needed for audit or incident review?
* What could fail and how would it be detected?
* What OS concept explains the behaviour or failure mode?
* What is the Azure, Intune, Entra or hybrid equivalent of this local capability?
* What earlier skills were drilled again in Part B?
* What broke, how was it diagnosed, how was it fixed, and how would recurrence be prevented?
* If AI was used, what data would be unsafe to expose and how would AI use be governed?

### Upload Rule

When a new lab is created for this series, it should be added to the correct topic folder in this repository using the established naming convention.

Example:

```text
07-azure-core-administration/lab-01-deploy-secure-azure-vm.md
```
