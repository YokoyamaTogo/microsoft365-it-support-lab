# INC-007: DNS Resolution Failure — Incorrect Query Target

## Ticket Information

- Ticket ID: INC-007
- Type: Incident
- Environment: Azure-hosted Windows 11 lab virtual machine
- Status: Resolved (Lab Simulation)
- Report date: October 29, 2026
- Scope: Command-specific DNS query failure

## Issue Description

A DNS (Domain Name System) lookup for `www.microsoft.com` timed out when an incorrect server address was explicitly supplied to `nslookup`. This was a controlled exercise, not a reported production outage. Windows-wide DNS settings were not intentionally changed.

## Investigation

| Stage | Command | Observed result |
|---|---|---|
| Baseline | `nslookup www.microsoft.com` | Default server `168.63.129.16` returned aliases and IPv4/IPv6 addresses. |
| Simulated failure | `nslookup -timeout=2 -retry=1 www.microsoft.com 192.0.2.1` | Repeated `DNS request timed out` messages, ending with `Request to UnKnown timed-out`. |
| Verification | `nslookup www.microsoft.com` | Default server `168.63.129.16` returned aliases and IPv4/IPv6 addresses again. |

`192.0.2.1` was used as a documentation-only address, not as a functioning lab DNS server. The timeout establishes that no response was obtained within the query's waiting period. It does not establish that the queried name does not exist or identify the exact packet-drop location.

## Root Cause

The failing command explicitly selected an incorrect DNS query target. The default-server lookup succeeded before and after the failure. No Windows-wide resolver outage was established.

## Resolution

Removed the explicit server argument and repeated the lookup using the default DNS server. No operating-system configuration change or DNS cache clearing was required.

## Verification

The final lookup returned the name `e13678.dscb.akamaiedge.net`, aliases including `www.microsoft.com`, and IPv4/IPv6 addresses. The query succeeded despite the server label `UnKnown` and the response label `Non-authoritative answer`.

Verification covers this DNS lookup only. Browser access, application connectivity, and system-wide DNS configuration comparison were not tested in this ticket.

## Evidence

The learner supplied the three command outputs in chat. The results above summarize those outputs; no independent inspection of the virtual machine was performed. No screenshots or raw log files are attached. Returned destination addresses may change and are not fixed acceptance criteria.

## Lessons Learned

Compare the same name using the default server and an explicitly selected server. Distinguish a response timeout from a response stating that the name does not exist. Describe a command-specific simulation accurately rather than claiming to have repaired an operating-system-wide outage.
