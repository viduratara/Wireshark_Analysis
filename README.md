<img width="1672" height="814" alt="image" src="https://github.com/user-attachments/assets/123b758d-ec21-4cc1-b809-af29e376b512" />


# Wireshark Case Files

A series of network traffic investigations, done the way a SOC analyst would actually work a real alert — not just opening a pcap and clicking around.

Each case starts with a real (safe, published) incident scenario, and walks through triage, filtering, identifying the affected host and user, pulling out indicators of compromise, and writing up what I'd actually tell a security team to do about it.

## Why I built this

I wanted my Wireshark skills to go past "I know the tool" into "I can investigate something and explain what happened." Every case here follows the same process: start with statistics, narrow down to the suspicious traffic, confirm it, identify who and what was affected, then document it like it's going in front of an actual team.

## Cases

| # | Case | Type | Date | Write-up |
|---|------|------|------|----------|
| 1 | Lumma in the Room-ah | Malware C2 over HTTP | 2026-01-31 | [`2026-01-31:LUMMA_IN_THE ROOM-AH.md`](./2026-01-31:LUMMA_IN_THE%20ROOM-AH.md) |
| 2 | Easy As 123 | Malware C2 over HTTPS | 2026-02-28 | [`2026-02-28:EASY_AS_123.md`](./2026-02-28:EASY_AS_123.md) |
| 3 | First to Last | Network scan / attack pattern | 2026-08-09 | [`2026-08-09:FIRST_TO_LAST.md`](./2026-08-09:FIRST_TO_LAST.md) |

Each write-up follows the same structure so they're easy to compare across cases:

1. Scenario / what triggered the alert
2. Statistics-first triage (protocol hierarchy, conversations, IO graph)
3. Investigation timeline
4. Filters used, and why
5. Host and user identification
6. Indicators of compromise
7. MITRE ATT&CK mapping
8. Recommendation

## What this demonstrates

- Reading and filtering packet captures in Wireshark
- Triaging traffic using statistics views before going packet-by-packet
- Identifying infected hosts and user accounts from indirect evidence (NBNS, Kerberos, TLS SNI) when the payload itself is encrypted or not directly visible
- Extracting and documenting indicators of compromise
- Mapping observed behavior to MITRE ATT&CK techniques
- Writing incident reports that are clear enough for a non-technical reader to act on

## Tools

Wireshark, VirusTotal

## Source

All pcaps are training exercises from [malware-traffic-analysis.net](https://www.malware-traffic-analysis.net/), analyzed in an isolated VM. No real user data is involved.

---

More cases get added as I work through them — this is an ongoing series, not a one-time project.
