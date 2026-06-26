# Repository Design Decision

### Purpose

This document explains why the `Azure-WindowsLabs` repository is structured around administration topics rather than individual tools.

The repository is intended to support a Windows and Azure System Administrator learning path. The structure should therefore reflect real operational responsibility areas: Windows Server, Active Directory, PowerShell, Entra ID, Intune, Azure, monitoring, backup, security, AI-assisted administration and hybrid operations.

### Decision

Use numbered topic folders in the format:

```text
01-topic-name-written-lowercase
```

Example:

```text
01-windows-server-foundations
02-active-directory-dns-gpo
03-powershell-administration
```

### Rationale

This convention keeps the repository:

* ordered
* readable
* easy to navigate
* aligned with a learning path
* suitable for portfolio review
* consistent with the existing infrastructure lab repository naming style

The folders are topics, not individual products or random labs. This helps show progression from foundational Windows administration to hybrid Microsoft cloud operations and safe AI-assisted administration.

### Topic Order

| Folder | Reason |
| --- | --- |
| `01-windows-server-foundations` | Windows Server is the base platform for many enterprise administration tasks |
| `02-active-directory-dns-gpo` | AD DS, DNS and Group Policy are core Windows sysadmin responsibilities |
| `03-powershell-administration` | PowerShell is the automation and evidence-gathering tool for Microsoft administration |
| `04-file-services-permissions` | File access issues are common in real support and sysadmin roles |
| `05-entra-id-identity` | Entra ID connects traditional administration to cloud identity |
| `06-intune-endpoint-management` | Intune represents modern Windows endpoint management |
| `07-azure-core-administration` | Azure introduces cloud compute, storage, networking, RBAC and governance |
| `08-monitoring-backup-security` | Operations work requires monitoring, backup, restore, alerting and security thinking |
| `09-hybrid-operations-capstone` | Final labs should combine Windows, identity, endpoint and Azure operations |
| `10-ai-assisted-admin-operations` | AI is a cross-cutting admin capability for scripting, troubleshooting, KQL, documentation, incident summaries and safe operational assistance |

### Folder Rules

Each topic folder should contain:

* a `README.md` explaining the topic
* one folder or markdown file per lab
* completed lab outputs
* verification evidence notes where safe
* links to supporting documentation where useful

Do not store book files, credentials, private tenant data, company data, sensitive screenshots or unsanitised AI prompts/outputs in the repository.

### Lab Naming Rule

Lab files should use this format:

```text
lab-01-short-lab-name.md
```

Example:

```text
01-windows-server-foundations/lab-01-build-windows-server-baseline.md
```

### Production Relevance

A real operations repository needs consistent structure because it becomes a source of evidence during troubleshooting, review, audit, onboarding and incident response. A predictable folder structure makes work easier to find and easier to maintain.

AI-assisted administration also needs structure because prompts, generated scripts and AI-supported decisions can introduce security, privacy, correctness and accountability risks if they are not reviewed and documented.
