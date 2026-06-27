# Break/Fix Lab Standard

### Purpose

Break/fix is one of the most important parts of this lab series.

The learner should not only build working systems. They should deliberately break controlled parts of the lab environment, diagnose the symptoms, restore service and document prevention.

### Core Rule

Every lab must include a controlled break/fix element.

A lab cannot be marked complete with only successful build evidence. It must prove the learner can handle failure.

Every lab must include:

1. Build or inspect the working state.
2. Prove the working state.
3. Break something deliberately and safely.
4. Detect the failure.
5. Diagnose the fault domain.
6. Fix or roll back the issue.
7. Verify recovery.
8. Document the symptoms, cause, fix and prevention.

### Break/Fix Placement

Each core lab has two parts:

| Part | Break/fix expectation |
| --- | --- |
| Part A — New Content | Break something related to the new topic introduced in the lab |
| Part B — Cumulative Drill | Troubleshoot a fault that may require skills from previous labs as well as the current lab |

Part B should be the main operational break/fix exercise because it is where the learner practises realistic response under pressure.

### Break/Fix Flow

Each break/fix exercise should follow this flow:

1. Confirm the system works before breaking it.
2. Introduce one controlled fault.
3. Observe the symptom.
4. Collect evidence.
5. Form a hypothesis.
6. Test the hypothesis.
7. Fix or roll back the change.
8. Verify recovery.
9. Document root cause and prevention.
10. Explain production risk.

### Safe Fault Injection Examples

| Area | Controlled fault | Expected investigation |
| --- | --- | --- |
| Windows service | Stop a non-critical service or change startup type | `Get-Service`, Event Viewer, service restart, recovery notes |
| Windows Server readiness | Change a test setting, create missing evidence or simulate stale patch/reboot state | `Get-ComputerInfo`, hotfix checks, transcript review |
| IIS | Stop an app pool, change binding, break default document, block port 80/443 | IIS Manager, `Get-WebAppPoolState`, IIS logs, browser/curl test, firewall check |
| DNS | Create wrong record, remove test record, use wrong DNS client server | `Resolve-DnsName`, `nslookup`, DNS Manager, client cache |
| AD | Remove test user from test group, disable test account, wrong OU/GPO link | AD cmdlets, `gpresult`, event logs, sign-in/access test |
| GPO | Unlink a test GPO, apply to wrong OU, change filtering | `gpresult`, `Get-GPO`, policy application evidence |
| File services | Remove test NTFS permission or share permission | effective access, group membership, SMB/share test |
| Firewall | Add a temporary blocking rule for a lab port | `Test-NetConnection`, firewall rules, service status |
| Storage | Fill a test volume or reduce free space in a controlled folder | disk checks, alert threshold, cleanup/recovery |
| Backup/recovery | Delete a test file and restore it | restore evidence and recovery notes |
| PowerShell automation | Introduce bad input, missing file path, bad CSV, missing module or permission issue | parameter validation, error handling, logging |
| Azure | Misconfigure test NSG, tag, RBAC assignment, backup policy, alert rule or diagnostic setting | Azure CLI/portal evidence, rollback and cost/security notes |
| Intune/Autopilot | Simulate assignment/filter/profile mismatch or compliance issue | policy assignment reasoning, device status, reporting notes |
| Linux | Stop a test service or change a test config | `systemctl`, `journalctl`, `ss`, `curl`, rollback |
| VMware/virtualisation | Simulate snapshot misuse, resource pressure, virtual NIC issue or datastore capacity problem | VM notes, capacity evidence, rollback/escalation note |
| SAN/storage | Simulate LUN/datastore capacity, latency or snapshot-vs-backup confusion | storage map, capacity evidence, escalation note |
| Monitoring | Disable/misconfigure a test alert or remove log source | alert evidence, log source evidence, corrected rule |
| SRE capstone | Trigger service degradation or outage | SLI/SLO check, alert, incident timeline, mitigation, PIR |

### Unsafe Faults to Avoid

Do not deliberately:

* corrupt a domain controller
* delete critical AD objects without a restore plan
* lock yourself out of the only admin account
* disable all network access to a VM without console access
* delete cloud resources without export/backups where needed
* expose ports publicly without a reason
* disable security controls permanently
* break anything in a real work or company environment
* use destructive commands without a rollback path
* generate uncontrolled cloud cost

### Evidence Required

Each break/fix section must include:

| Evidence | Description |
| --- | --- |
| Working baseline | Proof the system worked before the fault |
| Fault introduced | What was changed or broken |
| Symptom | What failed from the user/service perspective |
| Detection method | How the issue was noticed |
| Diagnostic evidence | Commands, logs, screenshots or portal evidence used to diagnose |
| Hypothesis | What the learner thought was wrong and why |
| Root cause or likely cause | The actual or most likely reason for the failure |
| Fix or rollback | What restored service |
| Recovery verification | Proof the service worked again |
| Prevention | Monitoring, alert, policy, runbook or automation improvement |
| Production risk | Why this matters in a real environment |

### Required Documentation Fields

Every completed lab must include:

* Break/fix scenario
* Expected failure
* Actual symptoms
* Detection method
* Diagnostic evidence
* Root cause or likely cause
* Fix applied
* Verification after fix
* Production prevention
* What monitoring would catch this earlier

### Relationship to SRE

Break/fix work is how the learner practises reliability thinking.

Each break/fix should connect to at least one of these:

* incident detection
* fault isolation
* mitigation
* rollback
* monitoring gap
* runbook improvement
* toil reduction
* post-incident review
* reliability backlog item

### Minimum Standard by Lab Stage

| Lab range | Break/fix expectation |
| --- | --- |
| Labs 01-04 | Simple service, update, event log, storage, patch, reboot or network fault |
| Labs 05-08 | AD, DNS, GPO, file access, IIS or FTP fault |
| Labs 09-12 | Firewall, application connectivity, VMware/SAN, security, backup or recovery fault |
| Labs 13-16 | Automation, estate-scale reporting, Azure/hybrid monitoring or SRE incident fault |
| Drill labs | Timed production-style break/fix scenarios with evidence and communication |

### Completion Rule

A lab is not complete unless the learner can answer:

1. What worked before the fault?
2. What was broken?
3. What symptom appeared?
4. What evidence identified the fault?
5. What fixed it?
6. How was recovery verified?
7. How would this be prevented, monitored or documented in production?

These are not additional reflection questions. They are documentation prompts used by the assistant when writing the final lab report.

The final break/fix proof chain is:

```text
Known-good state -> deliberate failure -> detection -> diagnosis -> fix -> recovery verification -> prevention note
```
