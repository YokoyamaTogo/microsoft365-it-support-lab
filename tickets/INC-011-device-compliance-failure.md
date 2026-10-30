# INC-011: Device Compliance Failure

## Ticket Information

- Ticket ID: INC-011
- Type: Incident tabletop exercise
- Exercise date: October 30, 2026
- Status: Closed — Tabletop exercise completed; no live incident reproduced
- Priority: No live incident priority assigned; fictional scenario involved one user with a meeting in two hours and working document access
- Environment: Microsoft Intune lab tenant; no device enrolled during this exercise

## Issue Description

Fictional intake: Jim reports that a Windows device displays a noncompliant status. In the fictional scenario, Company Portal displayed a noncompliant message. Jim was using a company-issued PC on home Wi-Fi and needed SharePoint documents for a meeting in two hours. He could open SharePoint and the required documents; no other affected users were reported. The onset remained unspecified. An actual compliance failure or access block has not been reproduced.

## Verified Lab Baseline

The following facts are based on learner-reported portal observations, not independent inspection:

- The Intune All devices view displayed `No devices found`; its filter state was not recorded.
- `LAB-W7-Windows-Compliance` was created and its saved settings were checked: minimum OS version `10.0.22631.0`, mark device noncompliant immediately, and no assignments.
- `LAB-W7-Windows-Pilot` was created and its saved settings were checked: quality update deferral 2 days, feature update deferral 7 days, auto install at maintenance time, active hours 08:00–18:00, deadline settings not configured, and no assignments.
- The test user's Microsoft Intune service was enabled.
- The enrollment user group contained only Jim. Following instructions to select MDM user scope Some, the learner confirmed that the intended group was saved.
- Only the default Windows platform restriction was listed. Windows MDM and personally owned enrollment were allowed, with no minimum or maximum OS version specified.

## Investigation

The following steps were discussed in a role-play; these are fictional responses and proposed investigations, not device observations:

1. Asked about ownership and location; the simulated user reported a company-issued PC on home Wi-Fi.
2. Asked for the displayed message and urgency; the simulated user reported noncompliance and a meeting in two hours.
3. Requested a SharePoint access check; the simulated user could view the required documents. Noncompliance alone was not treated as proof of an access block.
4. Discussed checking Company Portal details or using Intune device compliance reports to identify the failing setting. The scenario supplied an OS minimum-version failure, not an actual portal result.
5. Explained comparing the actual OS version with the assigned policy requirement and checking the last check-in before deciding on remediation.

No actual device or assigned compliance report was inspected.

## Root Cause

Not established in the live lab. An OS below the required minimum was discussed as a hypothetical cause; no device-version comparison was performed.

## Actions

Discussed a remediation plan: confirm the intended policy and OS version, review update controls and prerequisites, schedule an approved OS update around business needs, restart as required, and synchronize and reassess compliance. If policy values or assignments are incorrect, investigate and correct them rather than lowering requirements merely to clear a warning.

No incident remediation or OS update was performed. Policy creation and enrollment preparation preceded this tabletop scenario and are not evidence of a resolved incident.

## Verification

Device enrollment, policy delivery, compliance evaluation, and application access recovery have not been tested.

## Outcome

Closed at the learner's request after completing the tabletop discussion. Verified policy setup and the fictional investigation are documented separately. Device enrollment, remediation, and compliance recovery remain untested; this closure does not claim a resolved live incident.

## Evidence and Limitations

Evidence consists of learner-reported portal observations in chat. No raw exports or identifying screenshots are included. The existing VM's suitability for supported Intune enrollment remains unconfirmed. The compliance and update policies remain unassigned; the enrollment user-group setting remains configured. No rollback or device enrollment was reported.
