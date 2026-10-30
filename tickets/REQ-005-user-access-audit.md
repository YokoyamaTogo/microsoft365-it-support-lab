# REQ-005: User Access Audit

## Ticket Information

- Type: Service Request
- Environment: Microsoft 365 test tenant
- Status: Closed (Lab Simulation — direct membership verification)
- Report date: October 30, 2026
- Evidence: Learner-reported portal results and PowerShell output shared during the exercise; no independent cloud inspection

## Request and Scope

A fictional Marketing manager requested verification of the direct members of SG-Marketing. Approval was assumed for the lab. The final agreed scope was to verify membership and document the result; CSV delivery was omitted by agreement with the learner.

## Investigation and Verification

1. The learner reported Emma and Olivia in the portal's SG-Marketing Members view.
2. PowerShell 7.6.6 was confirmed on macOS. Microsoft.Graph.Authentication, Microsoft.Graph.Users, and Microsoft.Graph.Groups were available at version 2.41.2.
3. Delegated Graph authentication was confirmed for the lab tenant with User.Read.All and GroupMember.Read.All scopes.
4. Get-MgUser returned seven users: five test members, one guest, and the lab administrator.
5. Get-MgGroupMember returned two direct members for the selected group.
6. Member IDs were matched against the retrieved user IDs. The resulting names agreed with the portal report.

| Direct member | Department |
|---|---|
| Emma Wilson | Marketing |
| Olivia Chen | Marketing |

## Outcome

Direct membership verification was completed. No account, license, or group membership changes were made as part of the audit. The learner requested closure after the membership comparison.

Requester response draft (not sent):

> SG-Marketing has two verified direct members: Emma Wilson and Olivia Chen. The portal membership and Microsoft Graph results agree. Access to individual files or applications was outside the audit scope.

## Limitations

CSV export and re-import were not performed. Nested membership, other access paths, and effective file or application permissions were not assessed. This result is a point-in-time membership check, not a complete access certification. Graph disconnection at the end of the session was not confirmed.
