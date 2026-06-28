# PowerShell Desired State Configuration Standard

### Purpose

PowerShell Desired State Configuration (DSC) must be included in this lab programme.

DSC belongs in the PowerShell, automation, Azure/hybrid and SRE reliability portions of the series because it teaches configuration-as-code, drift detection, repeatable server configuration and compliance thinking.

### Current Microsoft Documentation Position

Microsoft's current DSC documentation describes DSC as a declarative configuration platform where the state of a machine is described separately from the programming logic that enforces that state.

Current DSC uses configuration documents in JSON or YAML, supports declarative/idempotent resource invocation, and can run on Windows, Linux and macOS without external dependencies.

Azure Machine Configuration extends this idea into Azure and hybrid estates by using Azure Policy to audit or configure operating system and application settings for Azure and Arc-enabled machines.

### Core Rule

The lab series must include DSC in three ways:

1. **Local configuration-as-code** — define desired Windows Server state and test/apply it safely.
2. **Drift detection and break/fix** — deliberately change a configured setting, detect drift and restore the desired state.
3. **Azure/hybrid governance comparison** — compare local DSC thinking with Azure Machine Configuration, Azure Policy and Arc-enabled server management.

### Where DSC Appears

| Lab | DSC requirement |
| --- | --- |
| Lab 11 | Introduce configuration baseline thinking and compare hardening with DSC-style desired state |
| Lab 13 | Report on configuration state across a simulated estate |
| Lab 14 | Introduce DSC as a remoting/configuration-management pattern |
| Lab 15 | Build a small DSC-style configuration or configuration-check workflow |
| Lab 16 | Use DSC thinking in the SRE capstone for drift detection, reliability and recovery |
| Drill D04 | Include DSC or DSC-style validation in PowerShell estate automation |
| Drill D07 | Compare local DSC with Azure Machine Configuration and Azure Policy |
| Drill D08 | Use configuration drift as one possible SRE incident cause |

### Minimum Practical DSC Skills

By the end of the lab series, the learner should be able to explain and/or demonstrate:

* desired state versus imperative scripting
* idempotence
* configuration drift
* resources
* configuration documents
* test/get/set style thinking
* local configuration validation
* drift remediation
* configuration-as-code in source control
* difference between traditional PowerShell DSC and newer DSC command-line/configuration-document approaches
* how Azure Machine Configuration applies similar governance ideas through Azure Policy
* why DSC matters for reliability and compliance

### Suggested Local DSC Scenarios

Use safe, small examples such as:

| Scenario | Desired state |
| --- | --- |
| Windows feature state | A required feature is installed or absent |
| Service state | A service has the expected startup type and running/stopped state |
| File or folder state | A config folder exists with expected content |
| Registry setting | A lab registry key/value has an expected state |
| IIS setting | A test site/app pool exists and is configured as expected |
| Security baseline | A safe lab setting matches the intended baseline |

### Break/Fix Requirement

DSC must include break/fix practice.

Example flow:

1. Define a desired state.
2. Prove the system is compliant.
3. Deliberately introduce drift.
4. Detect the drift.
5. Restore the desired state.
6. Verify compliance again.
7. Document how monitoring or policy would catch the drift in production.

### Azure and Hybrid Comparison

When DSC appears, the lab should compare it with Azure/hybrid management.

Relevant comparisons:

| Local / PowerShell concept | Azure / hybrid equivalent |
| --- | --- |
| Desired server state | Azure Machine Configuration assignment |
| Local configuration check | Guest assignment compliance result |
| Configuration drift | Azure Policy non-compliance |
| Manual remediation | Apply and Monitor or Apply and Autocorrect mode |
| Local server | Azure VM or Arc-enabled server |
| Script/config in Git | Policy/configuration package in source control |

### SRE Relevance

DSC supports SRE-style work because it reduces configuration drift and manual toil.

In the SRE capstone, DSC thinking should be used to answer:

* What configuration state must the service depend on?
* How would drift be detected?
* How would drift affect the SLO?
* Could drift explain the outage?
* What configuration check should be automated?
* What runbook or remediation would reduce recurrence?

### Documentation Requirements

When a lab uses DSC, the final report should include:

* desired state definition
* current state evidence
* compliance or drift result
* fault/drift introduced
* remediation action
* recovery/compliance verification
* Azure Machine Configuration comparison
* production risk
* monitoring or policy improvement

### Boundaries

Do not overcomplicate early labs with DSC.

DSC should be introduced after the learner has enough Windows Server, PowerShell, services, roles, files, IIS, security and monitoring context to understand why configuration drift matters.

The main DSC depth should be in Labs 14-16 and the final drill labs.
