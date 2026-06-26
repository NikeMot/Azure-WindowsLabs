# AI Usage Standard

### Purpose

This document defines how AI should be used across the `Azure-WindowsLabs` programme.

AI is included because modern Windows and Azure administrators increasingly use AI assistants for documentation, troubleshooting, scripting, query generation, security analysis and operational summarisation. The goal is not to become a machine learning engineer. The goal is to become an administrator who can use AI safely, critically and productively.

### Core Principle

AI may assist the work, but it must not replace understanding, verification or accountability.

Every AI-assisted lab must still require:

* manual understanding of the system being changed
* verification using real tools and evidence
* review of AI-generated commands or scripts before execution
* documentation of what AI was used for
* acknowledgement of uncertainty, risk and limitations

### Suitable AI Uses

AI can be used for:

* explaining unfamiliar error messages
* generating first-draft PowerShell or Azure CLI commands
* helping write KQL queries
* summarising Event Viewer, Entra, Intune or Azure Monitor findings
* producing incident timelines from sanitised evidence
* improving runbooks and troubleshooting checklists
* reviewing scripts for obvious mistakes
* generating test cases or validation checks
* comparing implementation options
* helping write clear documentation after the technical work is understood

### Unsafe AI Uses

AI must not be used to:

* run unreviewed commands in a live environment
* generate scripts that are executed without testing
* paste secrets, tokens, passwords, tenant IDs or company data into an AI tool
* make access-control decisions without administrator review
* replace official Microsoft documentation for current product behaviour
* bypass change control or security review
* invent evidence for a lab
* mark a lab complete without real verification

### AI Evidence Standard

When AI is used in a lab, record:

| Item | Description |
| --- | --- |
| AI tool used | Example: Microsoft Copilot, Azure Copilot, GitHub Copilot, Security Copilot, ChatGPT |
| Purpose | What the AI was used for |
| Prompt summary | A short sanitised summary, not secrets or full private context |
| Output accepted | What was used from the AI response |
| Output rejected | What was wrong, risky, incomplete or not used |
| Human verification | How the final result was checked independently |

### AI Tools Relevant to This Learning Path

| Tool / capability | Why it matters for Windows and Azure administration |
| --- | --- |
| Azure Copilot | Helps with Azure navigation, resource questions, troubleshooting, query generation and operational guidance |
| Microsoft Security Copilot | Relevant to security investigation, incident response, KQL, policy analysis and security posture review |
| GitHub Copilot | Useful for PowerShell, scripts, documentation, repository hygiene and lab automation |
| Microsoft 365 Copilot concepts | Useful for productivity, summarisation and stakeholder reporting, where licensed |
| Azure AI Foundry / Azure OpenAI concepts | Useful for understanding how enterprise AI services are deployed, governed, secured and monitored in Azure |
| KQL-assisted investigation | Useful for Azure Monitor, Log Analytics, Microsoft Sentinel concepts and operational evidence |

### Cross-Cutting Lab Placement

AI should appear in the following ways:

| Lab area | AI integration |
| --- | --- |
| Windows Server foundations | Use AI to explain event logs, but verify with Event Viewer and PowerShell |
| Active Directory, DNS and GPO | Use AI to draft troubleshooting hypotheses, but prove with AD, DNS and GPO tools |
| PowerShell administration | Use AI to draft scripts, then review, test and improve them manually |
| File services and permissions | Use AI to build an access-denied troubleshooting checklist from sanitised symptoms |
| Entra ID identity | Use AI to summarise sign-in failure patterns from sanitised evidence |
| Intune endpoint management | Use AI to reason through compliance or Autopilot failure scenarios |
| Azure core administration | Use Azure Copilot-style prompts for resource explanation, cost awareness and troubleshooting |
| Monitoring, backup and security | Use AI to draft KQL, incident notes and recovery runbooks, then validate all outputs |
| Hybrid operations capstone | Use AI as a junior assistant, not the decision maker, and document where it helped or failed |

### Required AI Reflection Questions

When AI is used in a lab, answer these questions:

1. What did AI help with?
2. What did AI get wrong or omit?
3. What evidence proved the final answer was correct?
4. What would be unsafe to give to an AI tool in production?
5. How would AI use be governed in a real organisation?
6. Did AI reduce work, improve quality, or introduce risk?

### Production Considerations

In production, AI use must be governed by:

* data classification
* privacy rules
* tenant and subscription boundaries
* access control
* audit logging
* human review
* approved tools
* prompt and output handling
* change management
* secure handling of generated scripts and commands

AI should improve operational quality. It should not weaken security, evidence standards or administrator accountability.
