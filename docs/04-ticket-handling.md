# Week 4 — Ticket Handling

Status: Two lab tickets completed based on learner-reported results on October 29, 2026. No independent cloud inspection was performed; screenshots and logs are not attached. This document covers the exercises defined for this lab, rather than an external curriculum.

## Objectives and Workflow

Practice handling a service request and an incident using the existing Microsoft 365 test environment:

1. Identify the request, affected account, and scope.
2. Check the initial state and available recovery methods.
3. Perform the required change or recovery.
4. Verify the resulting state or restored access.
5. Record the outcome, evidence basis, and unverified items before closing the ticket.

## REQ-004: Department Transfer

The fictional request was to transfer Emma Wilson from Sales to Marketing while retaining the existing account. Approval was assumed for the lab scenario.

The learner reported the initial state and confirmed the following state after the instructed changes:

| Item | Before | After |
|---|---|---|
| Department | Sales | Marketing |
| SG-Sales membership | Present | Absent |
| SG-Marketing membership | Absent | Present |

The instructed sequence updated Department, added and verified SG-Marketing membership, and then removed SG-Sales membership. The ticket was completed within the scope of department attributes and assigned group membership.

Department attributes and group membership require separate changes. Application access, resource permissions, existing sessions, and other access paths were not tested.

Full record: [REQ-004: Department Transfer](../tickets/REQ-004-department-transfer.md).

## INC-002: Forgotten Password

The fictional report was that Jim Hardway had forgotten his password but could still use Microsoft Authenticator. An actual forgotten password or initial failed sign-in was not independently established.

### Intake Questions Reviewed

| Question | Purpose |
|---|---|
| Which work account is affected? | Identify the correct account without requesting its password |
| Which screen blocks progress, and what does it say? | Distinguish password, account state, and MFA issues |
| Can the registered Authenticator app still approve notifications or provide a code? | Determine whether self-service recovery is available |

### Recovery and Verification

The learner used the existing self-service password reset (SSPR) configuration and reported:

- Successful password reset using an Authenticator app notification for identity verification.
- Successful sign-in with the new password.
- Successful access to My Account.

The instructed verification used a fresh private browsing window. A separate MFA challenge during the post-reset sign-in was not reported. The notification used for SSPR does not by itself prove MFA execution during that later sign-in.

Full record: [INC-002: Forgotten Password](../tickets/INC-002-forgotten-password.md).

## Completion Summary

| Exercise | Outcome | Verification scope |
|---|---|---|
| REQ-004 | Completed | Reported Department and group membership before and after the change |
| INC-002 | Resolved | Reported password reset, new-password sign-in, and My Account access |

Both tickets have documented outcomes. Week 4 is complete for these two exercises. Full offboarding, effective resource access after the transfer, and email service access were outside this week's scope.

Account identifiers, passwords, verification codes, and other authentication secrets are excluded from these public records.

## Related Material

- [Week 3: Authentication](03-authentication.md)
- [Week 5 Lesson: Exchange Online](../lessons/week05/README.md)
