# Lab Environment

Status: Initial diagram based on learner-reported setup. Planned components are labeled explicitly.

```mermaid
flowchart TD
    Mac[Mac browser] --> M365[Microsoft 365 admin center]
    Mac --> Entra[Microsoft Entra admin center]
    M365 --> Tenant[Microsoft 365 lab tenant]
    Entra --> Tenant
    Tenant --> Admin[Administrator account: MFA configured]
    Tenant --> Test[Test user: no administrator role, no license assigned]
    Tenant -. Planned organization .-> Departments[IT / Sales / Marketing / HR]
    Departments -. Planned security groups .-> Groups[SG-IT / SG-Sales / SG-Marketing / SG-HR]
    Mac --> Azure[Azure portal]
    Azure --> Subscription[Existing active subscription in separate directory: budget created]
    Subscription -. Planned for Week 5 .-> VM[Windows lab VM]
```

## Evidence and Limitations

- Microsoft 365 Business Premium account setup, administrator MFA, contract review, and test-user creation were reported complete by the learner.
- The learner confirmed an existing active Azure subscription in a directory separate from the Microsoft 365 lab and reported creating a budget on October 25, 2026. The learner reviewed the amount, currency, alert conditions, and recipients and reported no issues. Exact values are not recorded; notification delivery remains untested.
- The learner reported saving and checking the test user's Department (Sales) and Job title (Sales Representative). Security groups and memberships remain proposed.
- Test-user sign-in was reported successful on October 25, 2026. Access to licensed services remains unverified.
- No Windows VM deployment is recorded.
- Tenant identifiers and account names are omitted from this public diagram.
