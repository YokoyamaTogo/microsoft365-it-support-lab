# INC-002: Forgotten Password

## Ticket Information

- Type: Incident
- Environment: Microsoft 365 test tenant
- Status: Resolved (Lab Simulation)
- Report date: October 29, 2026
- Evidence: Learner-reported results; no screenshots or logs attached

## Issue Description

In the fictional ticket scenario, Jim Hardway forgot his password but could still use his registered Microsoft Authenticator app. An actual forgotten password or failed sign-in was not independently established.

## Resolution and Verification

Guided the learner through self-service password reset (SSPR) using the existing configuration. The learner confirmed:

1. Successful password reset using an Authenticator app notification for identity verification.
2. Successful sign-in with the new password.
3. Successful access to My Account.

The instructed verification used a fresh private browsing window. No independent cloud inspection was performed. A separate MFA challenge during the post-reset sign-in was not reported.

## Lessons Learned

When a registered verification method remains available, SSPR can restore access. Verify both password reset completion and a subsequent sign-in with the new password. An Authenticator notification used for SSPR does not by itself establish MFA execution during the later sign-in.
