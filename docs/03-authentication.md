# Week 3 — Authentication

Status: Results reported by the learner on October 29, 2026. A pasted sign-in event list and retrieval error were reviewed; no independent cloud inspection was performed. Raw logs, account identifiers, IP addresses, tokens, and recovery addresses are excluded.

## MFA and Registration

- Confirmed Password and Microsoft Authenticator in a non-administrator test user's Security info.
- Completed Authenticator authentication and reached My Account.
- Registered Authenticator again during a subsequent sign-in and reached My Account. The administrator-side Require re-register MFA action was instructed but not separately confirmed.

## Self-Service Password Reset

- Assigned Microsoft 365 Business Premium to the test user.
- Initially observed SSPR set to None and one method required to reset. Enabling SSPR for the existing IT security group was instructed; the saved scope was not separately reported.
- Confirmed Microsoft Authenticator and Email OTP enabled for All users in Authentication methods policies.
- Observed Authenticator notification and code options in the reset workflow.
- Added a recovery email method and successfully reset the password using email verification.
- Confirmed sign-in with the new password and Authenticator.

Email verification was used for SSPR, not as a sign-in MFA method for the member account. One required reset method does not require registering both email and Authenticator.

## Sign-In Logs

- Opened sign-in event lists and individual authentication details.
- Observed Success, Interrupted, and Failure events. Investigation of interruption and failure causes was skipped at the learner's request.
- One successful event showed Single-factor authentication with no authentication events triggered. That event alone does not establish whether MFA occurred elsewhere in the session.
- My Sign-ins retrieval failed with HTTP 429 and “The request was throttled.” Events later became visible in the admin center. The earlier admin-center empty results were not conclusively attributed to the same cause.
- No matching service-health notice was found by the learner.

## Conditional Access

Created `LAB-Require-MFA-Jim-ReportOnly` for one non-administrator test user. The instructed configuration targeted All resources and required multifactor authentication; the policy was confirmed as Report-only.

| Verification | Observed result |
|---|---|
| What If: target user | Policies that will apply |
| What If: another test user | Policy did not apply |
| Actual sign-in event, October 29 at 09:56:12 UTC | Mfa; Report-only: User action required |

The actual event required additional user action to satisfy the policy's MFA control if enforced. Report-only evaluated the policy without issuing its own MFA challenge or blocking access. What If simulation and actual sign-in evaluation were verified separately.

Security defaults was previously confirmed enabled, and it also appeared in a reviewed sign-in event. Disabling it was not instructed or reported.

## Limits

- Conditional Access enforcement and a Conditional Access sign-in block were not tested.
- A real lost-phone incident was not reproduced.
- Interrupted and failed sign-in root causes remain uninvestigated.
- The report-only event is separate from a later sign-in reported at 03:08 Vancouver time.
