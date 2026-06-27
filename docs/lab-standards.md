# Lab Standards

### Purpose

This document defines the standard expected for every lab in this repository.

The labs should develop real Windows and Azure administration competence, not just familiarity with menus or commands.

### Core Rule

Every lab must require the learner to:

* understand a scenario
* identify requirements
* research the reference material
* make technical decisions
* implement the solution
* use AI critically where it is relevant and safe
* verify the result with evidence
* troubleshoot at least one realistic issue where appropriate
* answer exactly seven reflection questions after solving the lab

The learner should focus on solving the lab. The final documentation should be produced from the learner's evidence and answers.

### Lab Difficulty Standard

Labs should be harder than the source material.

A weak lab says:

> Create an Active Directory user.

A strong lab says:

> HR provides starters, movers and leavers. Design the OU and group model, automate account changes, apply access control, verify login, intentionally break one user's access, diagnose the issue and document the operational improvement.

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
3. Reference Material
4. Requirements
5. Constraints
6. Assumptions
7. Expected Environment or Target State
8. Deliverables
9. Implementation Tasks
10. Key Commands Used
11. Files, Resources or Objects Created or Changed
12. Verification Evidence
13. Diagram
14. Issues Encountered
15. Decisions Made
16. Security and Production Considerations
17. Final Outcome
18. What I Learned
19. What I Would Improve in Production
20. References Used
21. Completion Checklist
22. Seven Reflection Questions

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

* the primary book or chapter used
* supporting book sections
* relevant Microsoft Learn documentation
* any operating systems theory reference used
* any AI documentation or AI tool guidance used
* why the reference was relevant

### Production Standard

Every final lab document should answer:

* What risk does this configuration introduce or reduce?
* How would this be monitored?
* How would this be backed up or recovered?
* What would need approval in production?
* What evidence would be needed for audit or incident review?
* What could fail and how would it be detected?
* If AI was used, what data would be unsafe to expose and how would AI use be governed?

### Upload Rule

When a new lab is created for this series, it should be added to the correct topic folder in this repository using the established naming convention.

Example:

```text
07-azure-core-administration/lab-01-deploy-secure-azure-vm.md
```
