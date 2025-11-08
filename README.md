# BOTSv3 Investigation Report

My investigation and analysis of Splunk's Boss of the SOC v3 dataset, documenting a multi-stage cyberattack against Frothly Corporation.

## What This Is

A comprehensive security investigation covering 300+ questions across two series (200 & 300), analyzing AWS security incidents, cryptocurrency mining, and an APT campaign by the Taedonggang adversary group.

## Key Findings

- AWS credentials leaked to public GitHub repository
- S3 bucket misconfiguration exposing company data
- Cryptocurrency mining malware (Monero) on endpoints
- Macro-enabled phishing delivering W97M.Empstage malware
- PowerShell C2 beacon with AMSI bypass
- 8 customer emails exfiltrated
- Multi-platform compromise (Windows & Linux)

## Investigation Breakdown

**Day 1 (200 Series):** AWS infrastructure security
- IAM user activity and MFA compliance
- S3 bucket exposure incident
- Credential compromise via GitHub
- Cryptocurrency mining detection

**Day 2 (300 Series):** Advanced persistent threat
- Phishing and malware analysis
- Lateral movement investigation
- C2 infrastructure discovery
- Data exfiltration assessment

## Repository Structure

```
.
├── BOTSv3 Report.pdf       # Full investigation report
└── README.md             # This file
```

## Threat Actor

**Taedonggang Group** - North Korean nexus based on:
- NaenaraBrowser user agent (ko-KP locale)
- Naver.com email (hyunki1984@naver.com)
- APT-level tactics and sophistication

## Notable IOCs

**Network:**
- C2: 45.77.65.211/admin/get.php
- Ports: 3333, 1337

**Files:**
- hdoor.exe (MD5: 586EF56F4D8963DD546163AC31C865D7)
- Frothly-Brewery-Financial-Planning-FY2019-Draft.xlsm

**Compromised Accounts:**
- tomcat7 (Linux root)
- svcvnc (Windows admin)

**AWS:**
- AKIAJOGCDXJ5NW5PXUPA (leaked access key)

**Hosts:**
- BSTOLL-L, FYODOR-L, ABUNGST-L, hoth

## Tools Used

- Splunk for log analysis and correlation
- AWS CloudTrail, Windows Event Logs, Sysmon
- Network stream data (SMTP, HTTP)
- OSQuery, Symantec Endpoint Protection logs

## What I Learned

- Advanced Splunk query techniques
- Cloud security investigation (AWS)
- Malware analysis and PowerShell deobfuscation
- MITRE ATT&CK framework mapping
- Incident response methodology
- Threat actor attribution

## Resources

- BOTSv3 Dataset: https://github.com/splunk/botsv3
- Full report with screenshots and queries in `BOTSv3 Report.pdf`
