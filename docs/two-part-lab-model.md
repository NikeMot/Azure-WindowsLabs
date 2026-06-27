# Two-Part Lab Model

### Purpose

Every core lab in this programme must now have two parts.

The first part teaches and applies new content from the primary source. The second part drills everything learned so far through a cumulative production-style scenario.

### Core Rule

Each core lab must follow this structure:

| Part | Name | Purpose |
| --- | --- | --- |
| Part A | New Content | Learn and apply the new Windows Server, PowerShell, Azure, operating system or production operations topic |
| Part B | Cumulative Drill | Reuse and test everything learned from previous labs, including troubleshooting, evidence capture, automation and communication |

### Part A: New Content

Part A should be source-led.

It should include:

* the primary Windows Server 2022 and PowerShell book section
* the new concept or feature being introduced
* implementation tasks
* PowerShell evidence
* Azure or cloud parity mapping where relevant
* Modern Operating Systems theory where useful
* production and operational relevance

Part A answers:

> What new capability am I learning in this lab?

### Part B: Cumulative Drill

Part B should be cumulative and job-like.

It should include skills from all previous labs, not only the current lab.

It should force the learner to practise:

* server inspection
* PowerShell evidence collection
* troubleshooting
* service checks
* logs and event review
* DNS/network reasoning
* security or access review
* Azure/local comparison
* documentation
* production judgement
* incident or change communication where relevant

Part B answers:

> Can I still perform the skills from earlier labs under a new scenario?

### Cumulative Difficulty Rule

The drill section becomes harder as the series progresses.

| Lab range | Part B drill expectation |
| --- | --- |
| Labs 01-04 | Drill server inspection, evidence capture, services, updates, storage and networking basics |
| Labs 05-08 | Add AD, DNS, GPO, users/groups, file services, IIS/FTP and access troubleshooting |
| Labs 09-12 | Add networking, firewall, VMware/SAN concepts, security, backup, recovery and production incident thinking |
| Labs 13-16 | Add estate-scale PowerShell, automation, Azure/hybrid operations, monitoring, runbooks and stakeholder communications |

### Required Production Anchors

The following anchors must appear in the core labs and/or the final drill block:

1. IIS/application outage investigation
2. 100-server estate simulation with PowerShell reporting
3. VMware/SAN/storage incident simulation
4. On-call incident communication pack

These are mandatory because they map directly to the target production infrastructure job.

### Required Evidence Outputs

Across the two parts of each lab, collect evidence such as:

* command output
* scripts or snippets used
* service status
* event logs
* IIS logs where relevant
* DNS or networking checks
* AD object or policy evidence where relevant
* Azure CLI, Az PowerShell, Azure Monitor or portal evidence where relevant
* incident notes where relevant
* change or rollback notes where relevant

### Learner Workflow

The learner still does not manually write the final report.

The learner should:

1. Complete Part A.
2. Complete Part B.
3. Send safe evidence for both parts.
4. Answer exactly seven reflection questions.

The assistant should:

1. Convert the evidence into the final documentation.
2. Separate Part A and Part B clearly.
3. Add verification tables.
4. Add production considerations.
5. Upload the completed lab to the correct GitHub folder.

### Seven Reflection Questions

The seven reflection questions stay the same. Do not add more questions because a lab has two parts.

1. What problem did this lab solve?
2. What was the most important thing you configured, changed or proved?
3. What evidence proves the lab worked?
4. What issue or mistake did you encounter, and how did you fix or investigate it?
5. What would be risky about doing this in production?
6. What would you monitor, back up or document in a real environment?
7. What did you learn that you could explain in an interview?
