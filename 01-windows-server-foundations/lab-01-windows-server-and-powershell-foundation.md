# Lab 01 — Windows Server and PowerShell Foundation

## 1. Lab Summary

**Lab:** Lab 01 — Windows Server and PowerShell Foundation  
**Topic area:** Windows Server foundations  
**Primary guide:** Windows Server 2022 and PowerShell  
**Difficulty:** Foundational, but operationally demanding  
**Status:** Not started

### Objective

Use the Windows Server 2022 and PowerShell book as the primary guide to understand your existing Windows Server 2022 VM as an operating system, an administration target, and a future infrastructure role server.

The point of this lab is not to perform a generic baseline. The point is to learn how a Windows administrator uses PowerShell to inspect, understand, verify and document a server before trusting it for Active Directory, DNS, file services, Azure connectivity or automation.

---

## 2. Scenario

You have been given an existing Windows Server 2022 VM.

Before it is allowed to host infrastructure roles, you need to prove that you understand the server from an administrator's perspective: OS identity, PowerShell environment, installed roles/features, services, networking, update state, firewall state, local access and event logs.

Your manager gives you this requirement:

> Use Windows Server 2022 and PowerShell as your main guide. Produce a technical readiness assessment of this server. Prove what the server is, how it is configured, what is safe to change now, what should wait until later labs, and what evidence supports your conclusion.

---

## 3. Source Mapping

| Source role | Source | How it is used |
| --- | --- | --- |
| Primary guide | Windows Server 2022 and PowerShell | Main structure for Windows Server administration, discovery and PowerShell-based inspection |
| PowerShell support | Learn PowerShell in a Month of Lunches | Helps explain command discovery, objects, pipeline, formatting and repeatable evidence collection |
| Azure support | Learning Microsoft Azure | Used only to explain why this server may later become an Azure-connected or hybrid administration target |
| Operational principle | The Practice of System and Network Administration | Used for documentation, repeatability, troubleshooting discipline, service ownership and operational readiness |
| Cloud operations principle | The Practice of Cloud System Administration | Used for reliability thinking, automation, monitoring, risk reduction and evidence-based operations |
| Current procedure | Microsoft Learn | Used for current Windows Server, PowerShell, Firewall, Windows Update and Event Log guidance |
| AI standard | `docs/ai-usage-standard.md` | Used only if AI is used to explain errors or review evidence |

---

## 4. Requirements

| ID | Requirement | Status |
| --- | --- | --- |
| R1 | Identify the server OS, build, hostname, workgroup/domain state and PowerShell version | Not started |
| R2 | Explain what PowerShell tells you that the GUI alone does not | Not started |
| R3 | Review installed roles and features without installing new infrastructure roles | Not started |
| R4 | Inspect networking, DNS client state and outbound connectivity | Not started |
| R5 | Confirm Windows Firewall state without disabling it | Not started |
| R6 | Review local users and local administrator membership | Not started |
| R7 | Inspect running/stopped services and recent critical/error logs | Not started |
| R8 | Check update/hotfix state and identify whether restart or patching is required | Not started |
| R9 | Create a short server readiness assessment | Not started |
| R10 | Decide what this VM is ready for next | Not started |

---

## 5. Constraints

You must not:

* install AD DS yet
* install DNS Server yet
* promote the server to a domain controller yet
* install random roles or features just to make the lab look bigger
* disable Windows Firewall
* expose confidential values or sensitive screenshots
* rely only on GUI evidence when PowerShell can prove the state
* treat the lab as complete without verification evidence

---

## 6. What You Are Learning

This lab should teach you:

* how to interrogate a Windows Server using PowerShell
* how Windows Server exposes system state through services, features, network configuration and event logs
* why a sysadmin must understand the current state before changing a server
* why evidence matters in infrastructure operations
* why documentation is part of administration, not an afterthought
* how PowerShell supports repeatable administration
* how operational principles apply before cloud or identity complexity is added

---

## 7. Target State

By the end, you should know and be able to prove:

* what the server is called
* what OS/build it runs
* what PowerShell version is available
* what roles/features are installed
* what network configuration it has
* whether it has outbound connectivity
* whether the firewall is enabled
* who has local administrator access
* whether there are recent critical/error events worth investigating
* whether updates/hotfixes need attention
* whether the server is ready for the next lab

---

## 8. Implementation Tasks

### Task 1 — Prepare evidence capture

Create an evidence folder and start a PowerShell transcript.

```powershell
New-Item -Path C:\Ops\Lab01 -ItemType Directory -Force
Start-Transcript -Path C:\Ops\Lab01\lab-01-transcript.txt
```

### Task 2 — Identify the server and PowerShell environment

```powershell
hostname
$PSVersionTable
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber, OsArchitecture, CsName, CsDomain, CsWorkgroup, CsManufacturer, CsModel, CsProcessors, CsTotalPhysicalMemory
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, BuildNumber, InstallDate, LastBootUpTime
```

### Task 3 — Inspect installed roles and features

```powershell
Get-WindowsFeature | Where-Object Installed -eq $true | Select-Object Name, DisplayName, InstallState
Get-WindowsFeature | Select-Object Name, DisplayName, InstallState
```

In your notes, identify whether AD DS, DNS, DHCP, File Services, IIS or Hyper-V appear installed.

### Task 4 — Inspect networking and connectivity

```powershell
Get-NetAdapter
Get-NetIPConfiguration
Get-DnsClientServerAddress
Get-NetConnectionProfile
Test-NetConnection 8.8.8.8
Test-NetConnection microsoft.com -Port 443
```

Decision: should this VM stay on DHCP for now, or should it receive a static IP before AD DS/DNS labs?

### Task 5 — Inspect Windows Firewall state

```powershell
Get-NetFirewallProfile | Select-Object Name, Enabled, DefaultInboundAction, DefaultOutboundAction
```

### Task 6 — Review local access

```powershell
Get-LocalUser | Select-Object Name, Enabled, LastLogon
Get-LocalGroupMember Administrators
```

### Task 7 — Inspect services and event logs

```powershell
Get-Service | Sort-Object Status, Name | Select-Object Status, Name, DisplayName
Get-WinEvent -FilterHashtable @{LogName='System'; Level=1,2; StartTime=(Get-Date).AddDays(-7)} -MaxEvents 20 | Select-Object TimeCreated, Id, ProviderName, LevelDisplayName, Message
Get-WinEvent -FilterHashtable @{LogName='Application'; Level=1,2; StartTime=(Get-Date).AddDays(-7)} -MaxEvents 20 | Select-Object TimeCreated, Id, ProviderName, LevelDisplayName, Message
```

### Task 8 — Check update and hotfix state

```powershell
Get-HotFix | Sort-Object InstalledOn -Descending | Select-Object -First 10
Get-ComputerInfo | Select-Object OsHotFixes
```

### Task 9 — Create a server readiness assessment

Create:

```text
C:\Ops\Lab01\server-readiness-assessment.md
```

Use this structure:

```text
# Server Readiness Assessment

Hostname:
OS and build:
PowerShell version:
Domain/workgroup state:
Installed roles/features:
Network state:
Firewall state:
Local administrator notes:
Update/hotfix state:
Event log findings:
Risks or issues:
Ready for next lab: Yes/No
Next recommended lab:
```

Then stop the transcript:

```powershell
Stop-Transcript
```

---

## 9. Evidence I Need Back From You

Send useful outputs from the commands above and the content of:

```text
C:\Ops\Lab01\server-readiness-assessment.md
```

Also send short notes on:

* what the primary source section helped you understand
* whether the server is clean enough for the next lab
* any error or confusing output you saw

---

## 10. Decisions to Make During the Lab

| Decision | Options |
| --- | --- |
| Hostname | Keep current name or rename later using a clean convention |
| Server readiness | Ready for next lab or needs remediation first |
| Network model | DHCP for now or static IP before AD DS/DNS |
| Role installation | No roles in Lab 1; roles begin in later source-led labs |
| Update action | Install now, defer, or document pending state |
| AI use | No AI, or AI only for explaining sanitised errors |

---

## 11. Production Thinking

Think about:

* why administrators inspect before changing systems
* why PowerShell evidence is more repeatable than screenshots
* why installed roles/features matter for risk and troubleshooting
* why firewall state should not be weakened casually
* why local administrator membership matters
* why event logs are operational evidence
* why patch state should be known before adding roles
* why documentation helps future incident response
* why Azure or hybrid work should wait until the local server foundation is understood

---

## 12. Completion Checklist

* [ ] Evidence folder created
* [ ] PowerShell transcript started
* [ ] Server identity captured
* [ ] OS/build captured
* [ ] PowerShell version captured
* [ ] Domain/workgroup state captured
* [ ] Installed roles/features reviewed
* [ ] Network configuration reviewed
* [ ] Connectivity tested
* [ ] Firewall state reviewed
* [ ] Local users reviewed
* [ ] Local administrators reviewed
* [ ] Services reviewed
* [ ] System event logs reviewed
* [ ] Application event logs reviewed
* [ ] Update/hotfix state checked
* [ ] Server readiness assessment created
* [ ] Transcript stopped
* [ ] No sensitive data exposed
* [ ] Seven reflection questions answered

---

## 13. Seven Reflection Questions

After completing the lab, answer only these seven questions and send them with your evidence:

1. What problem did this lab solve?
2. What was the most important thing you configured, changed or proved?
3. What evidence proves the lab worked?
4. What issue or mistake did you encounter, and how did you fix or investigate it?
5. What would be risky about doing this in production?
6. What would you monitor, back up or document in a real environment?
7. What did you learn that you could explain in an interview?
