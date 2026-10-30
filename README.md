# Microsoft 365 IT Support Home Lab

A hands-on learning portfolio covering Microsoft 365 identity administration, authentication, Windows troubleshooting, Microsoft Graph PowerShell, and Intune configuration. The project models support work for a fictional small business, Contoso Ltd., and supports preparation for IT Support and Service Desk roles.

**Status:** In progress. The repository contains 11 simulated support tickets, lab reports, and learning materials. Reusable PowerShell scripts and interview materials are still planned.

## Lab Environment

| Component | Purpose |
|---|---|
| Mac | Browser-based cloud administration and PowerShell 7 |
| Microsoft 365 Business Premium lab tenant | Licensing and Microsoft 365 administration |
| Microsoft Entra ID | Users, groups, roles, MFA, SSPR, and Conditional Access |
| Microsoft Graph PowerShell | Read-only user and direct group membership queries |
| Azure Windows VM | Windows service, DNS, network, and update diagnostics |
| Microsoft Intune | Compliance policy, update ring, and enrollment configuration |

The Azure subscription and Microsoft 365 tenant use separate directories. The Windows VM was last confirmed stopped and deallocated; related Azure resources remain, and final cost review and cleanup are pending.

## Practical Work

| Area | Work performed | Verification scope |
|---|---|---|
| User and group administration | Created five test users and department groups; changed department and membership; invited a guest | Account and membership observations; effective resource access was not tested |
| Least privilege | Temporarily assigned Password Administrator and removed it | Compared password-reset operation availability before, during, and after role assignment |
| Account recovery | Disabled and restored a test account; completed self-service password resets | Confirmed restored sign-in and My Account access |
| Authentication | Registered Authenticator and reviewed sign-in events | Selected authentication results reviewed; failed-event root causes remain uninvestigated |
| Conditional Access | Created a policy in Report-only mode | Compared target and non-target users in What If and reviewed an actual report-only evaluation; enforcement was not tested |
| Windows troubleshooting | Queried DNS, tested connectivity, restored Print Spooler, and inspected update and firewall state | DNS lookup and service recovery verified within each ticket's scope; no Windows Update failure reproduced |
| Access audit | Retrieved users and direct group members with Graph PowerShell | Matched two group members against portal observations; CSV export and effective-access testing were omitted |
| Endpoint management | Created and checked an Intune compliance policy and update ring; prepared enrollment scope | Saved configuration checked; policies remain unassigned and no device was enrolled |

## Lab Reports

- [Tenant setup](docs/01-tenant-setup.md)
- [Identity management and least privilege](docs/02-identity-management.md)
- [MFA, SSPR, and Conditional Access](docs/03-authentication.md)
- [Ticket handling: department transfer and password recovery](docs/04-ticket-handling.md)
- [Windows and Azure troubleshooting](docs/05-windows-troubleshooting.md)
- [ITSM workflow and Graph PowerShell access audit](docs/06-itsm-workflow.md)
- [Intune configuration and compliance tabletop exercise](tickets/INC-011-device-compliance-failure.md)

## Support Ticket Portfolio

Ticket numbers follow the lab's exercise sequence. Each record describes its own evidence, outcome, and limitations.

| Ticket | Scenario | Outcome |
|---|---|---|
| [REQ-001](tickets/REQ-001-new-employee.md) | New employee account setup | Account creation and sign-in scope completed |
| [REQ-002](tickets/REQ-002-group-membership.md) | Group membership change | Lab simulation completed |
| [REQ-003](tickets/REQ-003-offboarding.md) | Employee offboarding | Partial simulation: account disablement and restoration only |
| [REQ-004](tickets/REQ-004-department-transfer.md) | Department transfer | Department and group membership changes completed |
| [REQ-005](tickets/REQ-005-user-access-audit.md) | User access audit | Direct membership verification completed |
| [INC-001](tickets/INC-001-account-locked.md) | Account locked or disabled | Controlled account-disable scenario resolved |
| [INC-002](tickets/INC-002-forgotten-password.md) | Forgotten password | SSPR and subsequent sign-in completed |
| [INC-007](tickets/INC-007-dns-resolution-failure.md) | DNS query failure | Incorrect query target tested; default-server lookup verified |
| [INC-008](tickets/INC-008-windows-service-failure.md) | Windows service failure | Controlled Print Spooler stop and recovery verified |
| [INC-009](tickets/INC-009-windows-update-investigation.md) | Windows Update investigation | State inspected; no failure reproduced |
| [INC-011](tickets/INC-011-device-compliance-failure.md) | Device compliance failure | Tabletop exercise completed; no live incident reproduced |

## Repository Guide

| Location | Contents |
|---|---|
| [Organization scenario](architecture/company-scenario.md) | Fictional company and department design |
| [Environment diagram](architecture/environment-diagram.md) | Initial setup diagram; an update to reflect later lab work is pending |
| [Lab reports](docs/) | English records of performed exercises and verification limits |
| [Support tickets](tickets/) | Simulated requests, incidents, investigations, and a tabletop exercise |
| [Learning materials](lessons/) | Primarily Japanese explanations and guided exercises; instructions are not evidence of execution |
| [Learning plan](plan.md) | Eight-week roadmap and intended deliverables |

## Evidence and Scope

This is a personal learning environment. Company scenarios and support requests are fictional. Lab reports are based on learner-reported portal observations, shared screen text, and selected command outputs; the documentation assistant did not independently inspect the cloud environment. Raw screenshots and logs are not attached to the current lab reports.

Configuration checks, executed troubleshooting, proposed actions, and tabletop discussion are distinguished in the individual records. A closed exercise does not necessarily mean a live incident was reproduced or resolved. Earlier reports describe the state at the time of each exercise and may differ from later configuration.

AI assistance was used for explanations, command preparation, and documentation. The learning focus is selecting useful checks, interpreting results, verifying changes, and explaining the limits of the evidence.

Public records omit tenant identifiers, real account addresses, credentials, authentication secrets, and environment-specific network identifiers. New screenshots and exports should be reviewed before publication.

## Remaining Portfolio Work

- Update the environment diagram and add a dedicated endpoint-management report.
- Build and validate three reusable PowerShell scripts with execution instructions and error handling.
- Create a skills matrix and English interview scenarios grounded in the completed exercises.
- Review documentation and any future evidence files before publication.
- Review Azure costs and remove resources that are no longer needed.

Exchange Online, SharePoint, Teams, Autopilot, and Defender for Endpoint appear in the learning plan or materials. Their operational exercises are not claimed as completed in this portfolio.
