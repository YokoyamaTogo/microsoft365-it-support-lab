# Week 6 — ITSM and PowerShell

Status: REQ-005 completed on October 30, 2026 within the agreed direct membership verification scope. This record is based on learner-reported results and shared PowerShell output.

## Workflow Practiced

1. Define a service request and its verification scope.
2. Establish the current membership in the admin portal.
3. Prepare PowerShell and authenticate to Microsoft Graph with delegated read permissions.
4. Retrieve users and direct group members.
5. Match identities by ID and compare the result with the portal.
6. Document the outcome and limitations, then close the request within the agreed scope.

## Verified Result

SG-Marketing contained Emma Wilson and Olivia Chen as direct members. Both retrieved user profiles had Department set to Marketing. Department and group membership were checked separately; the department value alone was not treated as evidence of membership.

See [REQ-005: User Access Audit](../tickets/REQ-005-user-access-audit.md) for the ticket record.

## Scope and Remaining Work

CSV delivery was omitted when closing REQ-005 by agreement with the learner. CSV export, error-handling exercises, reusable script deliverables, and optional Windows diagnostics remain unverified. INC-010 service degradation handling and the other Week 6 exercises have not been completed. This document does not mark the entire week complete.

## Learning Approach

The exercise emphasizes choosing the evidence needed to answer a request, interpreting results, and explaining verification limits. Command memorization is not a learning requirement; commands may be researched or generated with assistance and reviewed for purpose and scope before use.

Tenant identifiers, real account addresses, authentication data, and raw directory exports are excluded from this public record.
