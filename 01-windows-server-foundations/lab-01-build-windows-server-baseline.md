# Lab 01 — Build a Windows Server Baseline

## Status

Assigned lab brief. Final documentation will be completed after the learner submits evidence and answers the seven reflection questions.

## Estimated Time

```text
60 to 90 minutes maximum
```

## Scenario

You have joined an infrastructure team that is preparing a Windows Server 2022 VM for future administration, Active Directory, PowerShell, monitoring and hybrid cloud labs.

Before the server can be used for anything more advanced, you need to prove that you can inspect it, understand its current state, capture baseline evidence, identify operational risks and recover from one simple service failure.

This is not an Active Directory lab yet. This lab is about building a clean operational baseline.

## Primary Skill

Windows Server baseline inspection and evidence capture using PowerShell.

## Source Mapping

| Source | Usage |
| --- | --- |
| Windows Server 2022 and PowerShell | Primary source for server inspection and PowerShell administration basics |
| Learn PowerShell in a Month of Lunches | Supporting source for command discovery, formatting, pipelines and exports |
| Modern Operating Systems | Supporting source for services, processes, resource usage and OS state |
| The Practice of System and Network Administration | Supporting source for baselines, evidence, repeatability and operational documentation |

## Required Outcome

By the end of the lab, you should have:

1. inspected the Windows Server 2022 VM
2. captured OS, hardware, network, service, update and feature evidence
3. created a small PowerShell baseline script
4. simulated one controlled service failure
5. diagnosed and recovered the service
6. collected enough safe evidence for final documentation

## Constraints

* Required work must fit inside 60 to 90 minutes.
* Do not install Active Directory Domain Services in this lab.
* Do not join a domain in this lab.
* Do not expose RDP or WinRM to the public internet.
* Do not include passwords, product keys, private IP ranges from real workplaces, tenant IDs, subscription IDs, private keys or company data in the evidence.
* Screenshots are optional. PowerShell evidence is preferred.
* If Windows Updates require a long download or reboot cycle, record update state only and move patching to a later lab.

## Assumptions

* You already have a Windows Server 2022 VM installed.
* You can sign in with a local administrator account.
* You can open PowerShell as Administrator.
* The server is a lab VM, not a production machine.

## Target State

| Area | Target |
| --- | --- |
| Server identity | Server name recorded; rename only if safe and quick |
| OS state | Edition, version, build and install date captured |
| PowerShell state | PowerShell version captured |
| Network state | IP address, gateway and DNS configuration captured |
| Storage state | Volumes and free space captured |
| Feature state | Installed Windows roles/features captured |
| Service state | Running/stopped service summary captured |
| Update state | Recent hotfix/update state captured |
| Remote management | WinRM/RDP state inspected, not blindly opened |
| Break/fix | One safe service stopped, diagnosed and recovered |
| Evidence | Saved under `C:\LabEvidence\Lab01` |

## Required Tasks

### Part A — Build the Server Baseline

Run PowerShell as Administrator.

#### 1. Create an evidence folder and start a transcript

```powershell
New-Item -Path "C:\LabEvidence\Lab01" -ItemType Directory -Force
Start-Transcript -Path "C:\LabEvidence\Lab01\lab01-transcript.txt" -Force
```

#### 2. Capture basic server identity and OS information

```powershell
hostname
$PSVersionTable.PSVersion
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber, OsArchitecture, CsManufacturer, CsModel, CsTotalPhysicalMemory
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, BuildNumber, InstallDate, LastBootUpTime
```

Save useful output to evidence files:

```powershell
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber, OsArchitecture, CsManufacturer, CsModel, CsTotalPhysicalMemory |
    Out-File "C:\LabEvidence\Lab01\os-summary.txt"

Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, BuildNumber, InstallDate, LastBootUpTime |
    Out-File "C:\LabEvidence\Lab01\os-cim-summary.txt"
```

#### 3. Capture network configuration

```powershell
Get-NetIPConfiguration
Get-DnsClientServerAddress -AddressFamily IPv4
Test-NetConnection 8.8.8.8
```

Save the output:

```powershell
Get-NetIPConfiguration | Out-File "C:\LabEvidence\Lab01\network-configuration.txt"
Get-DnsClientServerAddress -AddressFamily IPv4 | Out-File "C:\LabEvidence\Lab01\dns-client-servers.txt"
Test-NetConnection 8.8.8.8 | Out-File "C:\LabEvidence\Lab01\internet-connectivity-test.txt"
```

#### 4. Capture storage and installed feature state

```powershell
Get-Volume
Get-WindowsFeature | Where-Object Installed -eq $true
```

Save the output:

```powershell
Get-Volume | Out-File "C:\LabEvidence\Lab01\volume-summary.txt"
Get-WindowsFeature | Where-Object Installed -eq $true | Out-File "C:\LabEvidence\Lab01\installed-windows-features.txt"
```

#### 5. Capture service and update state

```powershell
Get-Service | Group-Object Status
Get-Service | Sort-Object Status, Name | Select-Object Status, Name, DisplayName
Get-HotFix | Sort-Object InstalledOn -Descending | Select-Object -First 10
```

Save the output:

```powershell
Get-Service | Group-Object Status | Out-File "C:\LabEvidence\Lab01\service-status-summary.txt"
Get-Service | Sort-Object Status, Name | Select-Object Status, Name, DisplayName | Out-File "C:\LabEvidence\Lab01\services-list.txt"
Get-HotFix | Sort-Object InstalledOn -Descending | Select-Object -First 10 | Out-File "C:\LabEvidence\Lab01\recent-hotfixes.txt"
```

#### 6. Inspect remote management state safely

```powershell
Test-WSMan localhost
Get-NetFirewallRule -DisplayGroup "Remote Desktop" | Select-Object DisplayName, Enabled, Profile
```

Save the output:

```powershell
Test-WSMan localhost | Out-File "C:\LabEvidence\Lab01\winrm-local-test.txt"
Get-NetFirewallRule -DisplayGroup "Remote Desktop" | Select-Object DisplayName, Enabled, Profile | Out-File "C:\LabEvidence\Lab01\rdp-firewall-state.txt"
```

Do not enable broad inbound access just to complete the lab. Inspection is enough for Lab 01.

#### 7. Create a simple baseline script

Create this file:

```text
C:\LabEvidence\Lab01\Get-ServerBaseline.ps1
```

Use this script:

```powershell
$OutputPath = "C:\LabEvidence\Lab01"

$Baseline = [ordered]@{
    ComputerName = $env:COMPUTERNAME
    CapturedAt = Get-Date
    PowerShellVersion = $PSVersionTable.PSVersion.ToString()
    OperatingSystem = Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, BuildNumber, LastBootUpTime
    Network = Get-NetIPConfiguration | Select-Object InterfaceAlias, IPv4Address, IPv4DefaultGateway, DNSServer
    Volumes = Get-Volume | Select-Object DriveLetter, FileSystemLabel, FileSystem, SizeRemaining, Size
    InstalledFeatures = Get-WindowsFeature | Where-Object Installed -eq $true | Select-Object Name, DisplayName, InstallState
    ServiceSummary = Get-Service | Group-Object Status | Select-Object Name, Count
    RecentHotfixes = Get-HotFix | Sort-Object InstalledOn -Descending | Select-Object -First 10
}

$Baseline | ConvertTo-Json -Depth 5 | Out-File "$OutputPath\server-baseline.json"
$Baseline | Out-File "$OutputPath\server-baseline-readable.txt"

Write-Host "Baseline captured to $OutputPath"
```

Run it:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process -Force
& "C:\LabEvidence\Lab01\Get-ServerBaseline.ps1"
Get-ChildItem "C:\LabEvidence\Lab01"
```

### Part B — Controlled Break/Fix Drill

You will simulate a safe service failure and recover it.

Use the Print Spooler service because it is usually safe in a lab VM and easy to restart.

#### 1. Prove the service state before the fault

```powershell
Get-Service Spooler | Tee-Object "C:\LabEvidence\Lab01\spooler-before.txt"
```

#### 2. Introduce the controlled fault

```powershell
Stop-Service Spooler
Get-Service Spooler | Tee-Object "C:\LabEvidence\Lab01\spooler-stopped.txt"
```

#### 3. Inspect service control events

```powershell
Get-WinEvent -LogName System -MaxEvents 50 |
    Where-Object { $_.ProviderName -eq "Service Control Manager" } |
    Select-Object TimeCreated, Id, ProviderName, LevelDisplayName, Message |
    Out-File "C:\LabEvidence\Lab01\service-control-manager-events.txt"
```

#### 4. Recover the service

```powershell
Start-Service Spooler
Get-Service Spooler | Tee-Object "C:\LabEvidence\Lab01\spooler-recovered.txt"
```

#### 5. Stop the transcript

```powershell
Stop-Transcript
Get-ChildItem "C:\LabEvidence\Lab01" | Select-Object Name, Length, LastWriteTime
```

## Evidence to Send After Solving

Send the following evidence back to the assistant:

| Evidence | Required |
| --- | --- |
| `Get-ChildItem C:\LabEvidence\Lab01` output | Yes |
| `os-summary.txt` | Yes |
| `network-configuration.txt` | Yes |
| `service-status-summary.txt` | Yes |
| `server-baseline-readable.txt` or `server-baseline.json` | Yes |
| `spooler-before.txt` | Yes |
| `spooler-stopped.txt` | Yes |
| `spooler-recovered.txt` | Yes |
| Any error messages encountered | Yes, if applicable |
| Screenshots | Optional |

## Seven Reflection Questions

After solving the lab, answer only these seven questions:

1. What problem did this lab solve?
2. What was the most important thing you configured, changed or proved?
3. What evidence proves the lab worked?
4. What issue or mistake did you encounter, and how did you fix or investigate it?
5. What would be risky about doing this in production?
6. What would you monitor, back up or document in a real environment?
7. What did you learn that you could explain in an interview?

## Optional Stretch Task

Only do this if the required work is complete and you are still inside the 90-minute timebox.

Create a second script called:

```text
C:\LabEvidence\Lab01\Test-ServerBaseline.ps1
```

It should check:

* whether the server has at least one IPv4 address
* whether the system drive has more than 10 GB free
* whether the Spooler service is running after recovery
* whether WinRM responds locally

This stretch task is not required for Lab 01 completion.

## Completion Standard

The lab is complete when:

* the baseline evidence folder exists
* the baseline script runs successfully
* server identity, OS, network, storage, feature, service and update evidence is captured
* the Spooler controlled fault is introduced and recovered
* safe evidence is ready to send
* the seven reflection questions are answered
