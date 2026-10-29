# Week 2 — Identity Management

Status: Lab results reported by the learner on October 28, 2026. No independent cloud inspection was performed; screenshots and logs are not attached.

## Completed Activities

- Reused one existing test account and created four additional accounts, for five test users in total.
- Created four department security groups: SG-IT, SG-Sales, SG-Marketing, and SG-HR, and added members.
- Removed and re-added a test Sales user in SG-Sales.
- Created the Microsoft 365 group Software Developers.
- Reset Jim Hardway's password as the administrator, completed two-step authentication, and reached My Account.
- Disabled Jim's account, observed a sign-in rejection, re-enabled it, and confirmed successful sign-in.
- Confirmed Global Administrator on the administrator account and no assigned administrator roles on Jim before testing.
- Temporarily assigned Password Administrator to Jim, compared Reset password availability, and removed the role after testing.
- Invited an external user, confirmed external-user sign-in, and observed invitation state Accepted.

## Least Privilege Verification

| Jim's role state | Observation |
|---|---|
| No administrator role | Entra admin center and user list accessible; Reset password unavailable for another test user |
| Password Administrator assigned | Reset password became available |
| Role removed; browser reopened and signed in again | Reset password unavailable again |

The learner confirmed operation availability; execution of another user's password reset during the delegated-role test was not explicitly reported. The earlier administrator-performed password reset and subsequent Jim sign-in were confirmed separately.

## Authentication and Account State

Security defaults was confirmed Enabled and was left unchanged. Jim completed two-step authentication during sign-in testing. The exact registration method was not recorded.

During the deliberate account-disable test, the page displayed: "Your account has been locked. Contact your support person to unlock it, then try again."

The controlled change and successful recovery support account disablement as the cause in this simulation. The message alone does not establish a password-attempt lockout.

## Scope and Limitations

- Group creation and membership operations were learner-reported. The proposed configuration used assigned membership; every saved group property was not separately reported.
- Group membership does not automatically assign an administrator role or grant access to an unconfigured resource.
- Microsoft 365 group mailbox, SharePoint, and Teams access were not tested.
- Guest invitation acceptance and sign-in were verified; the saved User type value and access to shared resources were not separately reported.
- Session revocation and complete employee offboarding were outside this exercise.
- Account identifiers, external email addresses, passwords, and authentication secrets are excluded.

## Related Tickets

- [REQ-002: User Group Membership Change](../tickets/REQ-002-group-membership.md)
- [REQ-003: Employee Offboarding](../tickets/REQ-003-offboarding.md)
- [INC-001: User Account Locked or Disabled](../tickets/INC-001-account-locked.md)
