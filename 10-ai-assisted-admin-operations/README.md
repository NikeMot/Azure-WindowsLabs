# 10 — AI-Assisted Administration Operations

### Purpose

This topic covers practical, safe and evidence-based use of AI for Windows and Azure system administration.

The aim is not to become a machine learning engineer. The aim is to become an administrator who can use AI tools to speed up investigation, scripting, documentation, query writing and operational analysis without weakening verification or security.

### Focus Areas

* AI-assisted troubleshooting
* AI-assisted PowerShell scripting
* AI-assisted KQL query generation
* Azure Copilot concepts
* Microsoft Security Copilot concepts
* GitHub Copilot for scripts and documentation
* prompt design for infrastructure administration
* responsible AI use
* sanitising prompts and evidence
* verifying AI-generated commands
* documenting AI assistance in lab outputs
* production governance for AI tools

### Example Labs

* Use AI to draft a Windows Server troubleshooting checklist, then validate it manually
* Use AI to draft a PowerShell health-check script and harden it through testing
* Use AI to generate KQL queries for Azure Monitor, then verify and improve them
* Use Azure Copilot-style prompts to investigate an Azure VM or networking issue
* Use AI to summarise a mock incident timeline from sanitised logs
* Compare AI-generated runbooks with manually written runbooks
* Review an AI-generated PowerShell script for safety, idempotence and error handling
* Build an AI usage policy for a small infrastructure team

### Reference Material

* The Practice of Cloud System Administration
* Learn PowerShell in a Month of Lunches
* Learning Microsoft Azure
* Microsoft Learn Azure Copilot documentation
* Microsoft Learn Microsoft Security Copilot documentation
* Microsoft Learn Azure AI Foundry / Azure OpenAI documentation
* GitHub Copilot documentation
* Internal repo standard: `docs/ai-usage-standard.md`

### Production Notes

AI-assisted administration must consider:

* data classification
* prompt hygiene
* secrets handling
* tenant and subscription privacy
* change control
* human review
* auditability
* hallucination risk
* command/script safety
* rollback and recovery
* approved tooling

### Completion Standard

A lab in this folder is only complete when the AI-assisted output has been independently verified with real commands, logs, documentation or system state.
