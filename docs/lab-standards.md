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
* verify the result with evidence
* troubleshoot at least one realistic issue where appropriate
* document production considerations
* reflect on what would change in a real organisation

### Lab Difficulty Standard

Labs should be harder than the source material.

A weak lab says:

> Create an Active Directory user.

A strong lab says:

> HR provides starters, movers and leavers. Design the OU and group model, automate account changes, apply access control, verify login, intentionally break one user's access, diagnose the issue and document the operational improvement.

### Required Lab Sections

Each lab should follow `docs/lab-output-template.md` and include:

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
22. Reflection Questions

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

### Reference Standard

Each lab should identify:

* the primary book or chapter used
* supporting book sections
* relevant Microsoft Learn documentation
* any operating systems theory reference used
* why the reference was relevant

### Production Standard

Every lab should answer:

* What risk does this configuration introduce or reduce?
* How would this be monitored?
* How would this be backed up or recovered?
* What would need approval in production?
* What evidence would be needed for audit or incident review?
* What could fail and how would it be detected?

### Upload Rule

When a new lab is created for this series, it should be added to the correct topic folder in this repository using the established naming convention.

Example:

```text
07-azure-core-administration/lab-01-deploy-secure-azure-vm.md
```
