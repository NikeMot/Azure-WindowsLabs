# Lab Execution Workflow

### Purpose

This document defines how labs in `Azure-WindowsLabs` should be completed and documented.

The learner should focus on solving the lab. Documentation should be handled after the technical work is complete, using the learner's evidence and reflection answers.

### Role Split

| Role | Responsibility |
| --- | --- |
| Learner | Solve the lab, perform the technical work, troubleshoot issues, collect safe evidence and answer seven reflection questions |
| Assistant | Create the lab brief, interpret the evidence, write the final documentation, format the lab output, apply the repo template and upload the completed lab to the correct folder |

### Learner Workflow

For each lab, the learner should:

1. Read the lab brief.
2. Complete the technical tasks.
3. Capture safe evidence.
4. Note any issues or errors encountered.
5. Answer exactly seven reflection questions.
6. Provide the evidence and answers to the assistant.

The learner does not need to write the final lab report manually.

### Evidence to Send After Solving a Lab

Send whichever items are relevant:

* commands used
* PowerShell output
* Azure CLI output
* Event Viewer findings
* screenshots with sensitive details removed
* errors encountered
* fixes attempted
* final verification output
* files, scripts, resources or policies created
* anything that proves the lab worked

Do not send secrets, passwords, tokens, tenant IDs, subscription IDs, private keys, company data or private user data.

### Assistant Documentation Workflow

After the learner sends evidence and reflection answers, the assistant should:

1. Build the final lab document using `docs/lab-output-template.md`.
2. Convert raw evidence into concise verification tables.
3. Summarise commands and implementation steps clearly.
4. Write issues, decisions, security notes and production considerations.
5. Add the seven reflection answers.
6. Upload the completed lab to the correct topic folder.
7. Use the repository naming convention.

### Lab File Naming

Use:

```text
lab-01-short-lab-name.md
```

Example:

```text
01-windows-server-foundations/lab-01-build-windows-server-baseline.md
```

### Seven Reflection Questions

At the end of each lab, ask only these seven questions:

1. What problem did this lab solve?
2. What was the most important thing you configured, changed or proved?
3. What evidence proves the lab worked?
4. What issue or mistake did you encounter, and how did you fix or investigate it?
5. What would be risky about doing this in production?
6. What would you monitor, back up or document in a real environment?
7. What did you learn that you could explain in an interview?

### AI-Assisted Labs

If AI was used during the lab, include AI details inside the final documentation without asking extra reflection questions.

Capture:

* AI tool used
* what it helped with
* what was accepted
* what was rejected
* how the result was verified manually

### Completion Standard

A lab is complete when:

* the technical work is solved
* safe evidence is provided
* seven reflection questions are answered
* the final lab document is uploaded to the correct repository folder
* no secrets or private data are included
