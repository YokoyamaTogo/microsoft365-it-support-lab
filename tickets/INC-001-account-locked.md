# INC-001: User Account Locked or Disabled

## Ticket Information

- Type: Incident
- Environment: Microsoft 365 test tenant
- Status: Resolved (Lab Simulation)
- Report date: October 28, 2026
- Evidence: Learner-reported results; no screenshots or logs attached

## Issue Description

Jim Hardway could not sign in after the administrator deliberately disabled the test account. The page displayed: "Your account has been locked. Contact your support person to unlock it, then try again."

## Investigation and Cause

Compared sign-in behavior with the controlled Account enabled change. In this simulation, the cause was deliberate account disablement. No evidence established a password-attempt lockout; sign-in logs and error codes were not captured.

## Resolution and Verification

Re-enabled the account. The learner confirmed successful sign-in afterward.

## Lessons Learned

Check account state and the change history when investigating sign-in failures. A locked-account message alone does not distinguish all possible causes.
