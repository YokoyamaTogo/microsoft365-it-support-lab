# INC-008: Windows Service Failure — Controlled Print Spooler Stop

## Ticket Information

- Ticket ID: INC-008
- Type: Incident
- Environment: Azure-hosted Windows 11 lab virtual machine
- Status: Resolved (Lab Simulation)
- Report date: October 29, 2026
- Scope: Print Spooler service state; no printing test performed

## Issue Description

The learner deliberately stopped Print Spooler to practice checking and restoring a Windows service. This was a controlled service-stop simulation, not an unexpected crash or a reported printing outage.

## Investigation

1. `Get-Service Spooler | Select-Object Name, Status, StartType` showed `Running / Automatic` before the change.
2. `Get-Service Spooler -DependentServices` produced no displayed services.
3. Immediately before the stop command, `Get-Date -Format o` returned `2026-10-29T23:37:59.8811288-07:00`.
4. The learner ran `Stop-Service -Name Spooler -ErrorAction Stop` and confirmed `Stopped / Automatic`.
5. In Event Viewer, the learner inspected `Windows Logs > System` filtered to Service Control Manager. The supplied list contained Information events with Event ID 7040.
6. The 23:42:00 event described the IsolationSession service changing from demand start to auto start. It was excluded as evidence of the Print Spooler stop. No event corresponding to the Spooler stop was identified during this investigation; this does not establish that no such event was recorded.

## Root Cause

An intentional `Stop-Service` command stopped Print Spooler. Its startup type remained Automatic. No unexpected service failure or underlying software defect was established.

## Resolution

The learner ran the following command in Windows PowerShell:

```powershell
Start-Service -Name Spooler -ErrorAction Stop
```

## Verification

The learner then ran:

```powershell
Get-Service Spooler | Select-Object Name, Status, StartType
```

The supplied output showed `Spooler / Running / Automatic`, matching the baseline service state and startup type. No startup-type change was required. Service restoration was verified; actual printing and persistence after a Windows restart were not tested.

## Evidence

The learner supplied command outputs, the filtered event list, and one event's General text in chat. No independent inspection of the virtual machine was performed, and no raw event log or screenshots are attached to this ticket.

## Lessons Learned

Distinguish current service state from startup type: Automatic does not mean a service is currently running. Match an event's service name, message, and time to the action being investigated. Restore the original state and verify it even when the related event cannot be identified.
