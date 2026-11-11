# Penetration Testing Preparation & Reconnaissance

Environment setup, scope validation and **passive** attack surface mapping, following the OWASP Web Security Testing Guide (WSTG).

| Item | Detail |
|---|---|
| Author | Hrishikesh Agarwal |
| Date | 9 November 2026 |
| Platform | Kali GNU/Linux Rolling 2026.3 (VirtualBox) |
| Tools | Burp Suite Community 2026.10.1, OWASP ZAP 2.17.0, Firefox ESR 153.4.0, Wappalyzer, WhatWeb 0.6.4, curl 8.22.0, Shodan |
| Testing type | Passive reconnaissance only. No exploitation, brute force, fuzzing or active scanning |

## Important notice

Authorization fields are still **Pending** and the recon in Task 3 was demonstrated on public practice sites (google.com, wappalyzer.com), not an assigned application. This repo is a preparation and tool-validation exercise. Do not test any system without written permission.

## Structure

```
Pentest_Project/
├── 01_Setup/             project notes, tool versions
├── 02_Scope/             authorization, scope matrix, asset inventory, risk log, URL validation, WSTG plan
├── 03_Reconnaissance/    fingerprinting, page/endpoint inventory, Shodan and ZAP findings
├── 04_Burp_Evidence/     sanitized HTTP samples
├── 05_Screenshots/       evidence screenshots (add your own)
├── 06_Reports/           attack surface map, final PDF report
└── 07_Logs/              command and session logs
```

## Workflow

1. **Task 1 - Environment setup:** Kali update, tools, Burp proxy (127.0.0.1:8080), Firefox proxy, Burp CA.
2. **Task 2 - Scope validation:** authorization, scope matrix, asset inventory, risk log, WSTG test plan, URL/redirect check.
3. **Task 3 - Reconnaissance:** fingerprinting, Burp traffic capture, endpoint mapping, Shodan, ZAP passive alerts.
4. **Task 4 - Documentation:** `06_Reports/reconnaissance_report.pdf`.

## Rules applied

- No active scans, brute force, exploitation, fuzzing or intrusive testing
- Burp Intercept off during normal browsing
- No guessing hidden URLs or directory discovery
- No state-changing or modified replayed requests without approval
- Redact passwords, tokens, personal data and session cookies from all evidence
- ZAP for passive analysis only

## Status

15 complete, 6 partial, 2 pending of 23 checklist items (see report section 11).

## Next steps

1. Get written authorization and rules of engagement.
2. Replace `example.com` placeholders with real approved assets.
3. Re-run URL validation on the assigned URL.
4. Use a dedicated Firefox testing profile for the Burp CA.
5. Collect at least ten sanitized HTTP samples from the assigned app.
6. Remove the Burp CA and reset proxy settings when finished.
