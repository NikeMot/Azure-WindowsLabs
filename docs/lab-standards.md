# Lab Standards

### Purpose

This document defines the standard expected for every lab in this repository.

The labs should develop real Windows and Azure administration competence, not just familiarity with menus or commands.

### Core Rule

Every lab must require the learner to:

* understand a scenario
* identify requirements
* work from one primary book source
* research supporting reference material only where relevant
* connect Windows behaviour to Modern Operating Systems theory where useful
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
* Microsoft Intune Cookbook for endpoint-management relevance
* Active Directory Administration Cookbook for AD-specific implementation
* Microsoft Learn for current procedures and supported syntax
* Modern Operating Systems, 5e for OS theory and system behaviour

Operating principles should come from:

* The Practice of System and Network Administration
* The Practice of Cloud System Administration

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

> Using the Windows Server 2022 and PowerShell server administration material as the primary guide, inspect the server with PowerShell, identify roles/features, network state, service state and operational risks, connect at least one finding to Modern Operating Systems theory, then decide whether the server is ready for the next infrastructure role.

A weak AI-assisted lab says:

> Ask AI how to fix the error.

A strong AI-assisted lab says:

> Use AI to generate three troubleshooting hypotheses from sanitised symptoms, reject unsafe or unsupported suggestions, verify the remaining hypotheses with Event Viewer, PowerShell, Azure Monitor, Intune or Entra evidence, and document what the AI missed.

### Role Split

| Role | Responsibility |
| --- | --- |
| Learner | Solve the technical lab, collect safe evidence, report issues encountered and answer seven reflection questions |
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
9. Implementation Tasks
10. Key Commands Used
11. Files, Resources or Objects Created or Changed
12. Verification Evidence
13. AI Assistance Used, if relevant
14. Diagram, if useful
15. Issues Encountered
16. Decisions Made
17. Security and Production Considerations
18. Final Outcome
19. What I Learned
20. What I Would Improve in Production
21. References Used
22. Completion Checklist
23. Seven Reflection Questions

### Evidence Standard

Each completed lab should include safe evidence such as:

* PowerShell command output
* Azure CLI command output
* Azure Portal setting descriptions
* Event Viewer findings
* Entra sign-in log findings
* Intune device compliance observations
* Azure Monitor or Log Analytics query results
* backup or restore verification
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
* If AI was used, what data would be unsafe to expose and how would AI use be governed?

### Upload Rule

When a new lab is created for this series, it should be added to the correct topic folder in this repository using the established naming convention.

Example:

```text
07-azure-core-administration/lab-01-deploy-secure-azure-vm.md
```
