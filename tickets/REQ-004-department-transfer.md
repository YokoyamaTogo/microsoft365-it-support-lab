# REQ-004: Department Transfer

## Ticket Information

- Type: Service Request
- Environment: Microsoft 365 test tenant
- Status: Completed (Lab Simulation — department and group membership scope)
- Report date: October 29, 2026
- Evidence: Learner-reported before/after results; no screenshots or logs attached

## Request

Transfer fictional employee Emma Wilson from Sales to Marketing while retaining the existing account. Approval was assumed for this lab scenario.

## Actions and Verification

The learner reported the following initial state, then confirmed the saved state after the instructed changes:

| Item | Before | After |
|---|---|---|
| Department | Sales | Marketing |
| SG-Sales membership | Present | Absent |
| SG-Marketing membership | Absent | Present |

The instructed sequence was to update Department, add and verify SG-Marketing membership, then remove SG-Sales membership. The final state was reported complete; no independent cloud inspection was performed.

## Scope and Lessons Learned

Department attributes and assigned group membership require separate changes. This ticket verifies the reported attribute and membership state. Resource permissions, effective application access, existing sessions, and other access paths were not tested.
