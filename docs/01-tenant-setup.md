# Week 1 — Tenant Setup

Status: Lab activities reported by the learner on October 25, 2026. No independent inspection of the cloud environment was performed by the documentation assistant.

## Purpose and Environment

This lab models a fictional company, Contoso Ltd., to practice Microsoft 365 administration from a Mac browser. Microsoft 365 provides the productivity services and Microsoft Entra ID provides identity management. Azure will host Windows lab resources in a later phase.

The Microsoft 365 lab tenant and the existing Azure subscription use separate directories. No subscription directory transfer was performed.

## Management Portals

| Portal | Lab purpose |
|---|---|
| Microsoft 365 admin center | Review subscriptions, licenses, and users |
| Microsoft Entra admin center | Manage user properties and identities |
| Azure portal | Review the existing subscription and configure a budget |

## Completed Setup

1. Prepared a Microsoft 365 Business Premium account and accessed the management environment.
2. Configured and checked MFA for the administrator account.
3. Reviewed trial status, expiration, license quantity, and renewal conditions. Exact contract values were not captured in this report.
4. Reviewed license availability: 25 total and 24 available. The assignee of the used license was not recorded.
5. Created a test user, checked the intended username, and confirmed no administrator role or license assignment.
6. Set the test user's Department to Sales and Job title to Sales Representative, then checked the saved values.
7. Located an existing Azure subscription with Active status under a separate account and directory.
8. Created a subscription-level budget and reviewed its amount, currency, alert conditions, and recipients. Exact values were not captured; notification delivery was not tested.
9. Prepared a department and group design and an environment diagram.
10. Successfully signed in with the test user (learner-reported).

## Azure Subscription Creation Issue

An attempt to create a new Azure subscription failed during account eligibility/billing validation. The message directed the user to Azure Account Review. The exact cause was not established. An existing active subscription was selected for the lab instead; new subscription creation remains on hold.

## Security and Scope

- Administrator MFA was reported configured and checked.
- The test user remains without administrator roles and without a license assignment.
- Department attributes do not by themselves grant resource access.
- Budget alerts provide notifications; they do not automatically stop resource consumption.
- Account identifiers, payment details, passwords, and authentication secrets are excluded from this document.

## Remaining Verification

- Test-user sign-in succeeded; access to licensed services has not been verified.
- Administrator role and license assignment details have not been recorded.
- Budget notification delivery has not been tested.
- Security groups and memberships are planned for Week 2.
- No Windows VM deployment is recorded.

## Related Artifacts

- [Organization design](../architecture/company-scenario.md)
- [Environment diagram](../architecture/environment-diagram.md)
- [REQ-001: New Employee Account Setup](../tickets/REQ-001-new-employee.md)
