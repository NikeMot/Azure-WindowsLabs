# Source-Led Lab Design Standard

### Purpose

This document defines how labs in `Azure-WindowsLabs` should be designed.

The lab series should not be a random checklist of Windows and Azure tasks. Each lab should be anchored to a specific source book section, then expanded into a realistic administration scenario.

### Primary Rule

Each lab must have one primary book source.

For the Windows administration track, the default primary source is:

```text
Windows Server 2022 and PowerShell
```

A lab should cover one meaningful unit from the primary book, such as one chapter, module, section or tightly related group of pages. The lab can be harder than the book, but it should clearly come from the book.

### Lab Count Rule

The core Windows/Azure administrator programme uses exactly:

```text
16 core labs
```

The Windows Server 2022 and PowerShell book has an eight-book structure, so the core plan uses:

```text
2 labs per book section = 16 core labs
```

After the 16 core labs, a separate block of exactly:

```text
8 drill labs
```

is used to reinforce and pressure-test the full skillset.

### Supporting Sources

Primary source:

* Windows Server 2022 and PowerShell

Supporting technical sources:

* Learn PowerShell in a Month of Lunches
* Learning Microsoft Azure
* Microsoft Intune Cookbook
* Active Directory Administration Cookbook
* Microsoft Learn documentation

Operating systems theory:

* Modern Operating Systems, 5e

Operating principles:

* The Practice of System and Network Administration
* The Practice of Cloud System Administration

The supporting sources should deepen the lab. They should not replace the primary source.

### Design Pattern

Each lab should follow this pattern:

1. Choose one primary source section from `Windows Server 2022 and PowerShell`.
2. Identify the real administration problem behind that section.
3. Turn the topic into a practical scenario.
4. Add PowerShell evidence and automation where appropriate.
5. Add Azure relevance where appropriate, but only if it naturally supports the lab.
6. Add Modern Operating Systems theory where it explains the underlying system behaviour.
7. Apply operational principles from the Practice books.
8. Include verification, troubleshooting and production considerations.
9. Ask the learner only seven reflection questions after completion.

### What This Means in Practice

A weak lab says:

> Check Windows Server information.

A source-led lab says:

> Using the Windows Server 2022 and PowerShell server-management material as the primary guide, build a server inventory and readiness assessment. Use PowerShell to collect evidence, identify configuration risks, connect the observations to OS concepts such as services, processes, filesystems or networking, explain what the server is ready for, and document what must be fixed before it becomes a domain controller, file server or Azure-connected server.

### Required Source Mapping

Every lab brief must include a source mapping table:

| Source role | Source | How it is used |
| --- | --- | --- |
| Primary guide | Windows Server 2022 and PowerShell | Main book section the lab is based on |
| PowerShell support | Learn PowerShell in a Month of Lunches | Used to understand commands, objects, pipeline or scripting |
| Azure support | Learning Microsoft Azure | Used only where cloud or hybrid relevance applies |
| OS theory | Modern Operating Systems, 5e | Used to explain processes, memory, filesystems, networking, virtualisation, security and reliability concepts |
| Operational principle | The Practice of System and Network Administration | Used for admin discipline, documentation, troubleshooting and service ownership |
| Cloud operations principle | The Practice of Cloud System Administration | Used for automation, reliability, monitoring, scaling, risk and operations thinking |
| Current procedure | Microsoft Learn | Used for current syntax, supported features and official guidance |

### Lab Completion Model

The learner solves the lab and sends:

* command output
* configuration evidence
* screenshots only if safe
* issues encountered
* fixes attempted
* final verification evidence
* answers to seven reflection questions

The assistant handles:

* final documentation
* source mapping
* verification tables
* production considerations
* upload to the correct GitHub folder

### Design Boundary

Labs should not become passive reading summaries.

The book provides the structure. The lab proves practical administration skill.

A completed lab should demonstrate:

* what was built or inspected
* why it matters operationally
* what evidence proves it works
* what could fail
* how it would be monitored or recovered
* how OS theory explains the behaviour
* how the knowledge would be explained in an interview
