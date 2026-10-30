# Windows Troubleshooting Lab

## Execution Status and Evidence

Partial completion as of October 30, 2026. Results are based on learner-supplied command outputs, screen text, and a Windows version screenshot in chat. No independent inspection of Azure or the guest operating system was performed. Raw evidence files are not attached.

## Environment and Provisioning

The learner reported creating an Azure virtual machine in West US 2 with size D2as_v6 after encountering size availability and quota restrictions in Canadian regions. The region display name was subsequently confirmed from the learner-supplied resource list. Deployment cost was not independently verified.

The Windows version dialog showed version 26H2, build 26300.9725. The reported image was Windows 11 Pro. A local Windows account was used for remote sign-in from a Mac. The learner reported limiting inbound destination port 3389 to their own source address. Other effective network rules were not inspected. A CA$50 budget was created; notification thresholds and billing terms remain unverified.

## Network Diagnostics

DNS (Domain Name System) translates names into addresses and other records. TCP (Transmission Control Protocol) establishes connections for data exchange.

| Check | Observed result | Scope |
|---|---|---|
| `ipconfig /all` | Ethernet showed automatic address configuration enabled, an IPv4 address, subnet mask, default gateway, and Azure-provided DNS server. | Configuration inspection only; environment-specific addresses and identifiers omitted. |
| `nslookup www.microsoft.com` | Default Azure DNS server returned aliases and IPv4/IPv6 addresses. | Successful lookup for the queried name. |
| `ping -n 4 www.microsoft.com` | Four replies, zero loss, minimum/maximum/average round-trip time of 5 ms. | Responses to these four probes. |
| `tracert -d -h 8 -w 1000 www.microsoft.com` | All eight stages timed out. | No route responses or destination completion observed within the configured limit; cause not established. |
| `Test-NetConnection www.microsoft.com -Port 443` | `TcpTestSucceeded : True`, using the Ethernet interface. | Successful TCP connection to the selected destination on port 443. |

The route-trace timeouts did not establish a connectivity outage: the destination answered ping and accepted a TCP connection in separate tests. These results do not verify web page retrieval, encrypted-session validation, application sign-in, or sustained network quality.

## Device Inspection

The learner reported that Device Manager displayed Microsoft Hyper-V Network Adapter with no visible warnings. No device configuration change was performed. This visual check does not establish that all possible driver or device faults are absent.

## Windows Firewall

`Get-NetFirewallProfile` showed Enabled True for Domain, Private, and Public. `Get-NetConnectionProfile` subsequently showed Ethernet classified as Public (October 30, 2026). The ActiveStore Remote Desktop group showed Shadow (TCP-In), User Mode (TCP-In), and User Mode (UDP-In) rules enabled, allowing inbound traffic for Domain, Private, and Public. Per-rule port and address conditions and other rules were not inspected. No firewall setting was changed.

## Troubleshooting Exercises

- [INC-007: Incorrect DNS query target](../tickets/INC-007-dns-resolution-failure.md): default-server lookup succeeded, an explicitly incorrect query target timed out, and default-server lookup succeeded again. Operating-system DNS settings were not intentionally changed.
- [INC-008: Controlled Print Spooler stop](../tickets/INC-008-windows-service-failure.md): Running / Automatic changed to Stopped / Automatic and returned to Running / Automatic. A service-stop event was not identified. An unrelated IsolationSession startup-type event was excluded.
- [INC-009: Windows Update investigation](../tickets/INC-009-windows-update-investigation.md): Windows Update displayed an up-to-date status. The only reported history entry was a successfully installed audio-processing driver update. No update failure was reproduced or repaired.

## Disk Space

On October 30, the learner supplied a C: volume capacity of 126.4 GiB and free space of 100.8 GiB, rounded to one decimal place using PowerShell's `1GB` divisor (2^30 bytes). This confirms available space at the time of inspection, not suitability for every future update.

## Shutdown Configuration

The learner reported auto-shutdown enabled at 04:00, with the preceding screen showing Pacific Time (US & Canada). Actual scheduled execution and notification settings were not verified.

After a manual stop from Azure portal, the learner confirmed `Stopped (deallocated)` on October 30. The resource list subsequently showed one each of Virtual machine, Public IP address, Network security group, Network Interface, Disk, and Virtual network, all in West US 2. Actual costs, disk type, public-address pricing tier, and cleanup needs remain unverified.

## Deferred Checks and Remaining Work

- Review remaining update diagnostic checks as needed.
- Cost review was deferred at the learner's request on October 30 because costs appeared not to have been reflected yet. No amount was captured; this is not evidence of zero cost.
- Review disk and public-address configuration and resource cleanup needs.
- Verify outstanding licensing and billing conditions before claiming those checks complete.

Manual deallocation was confirmed. Resource deletion and final cost review have not been reported. This document does not mark Week 5 complete.
