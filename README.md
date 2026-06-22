# M57-Jean Digital Forensic Investigation

## Overview
This repository documents my forensic examination of the M57-Jean case — a classic digital forensics scenario involving the exfiltration of confidential employee data from a corporate laptop. The case was solved independently as part of my self-directed DFIR learning journey.

---

## Case Background
M57.Biz is a fictional startup company. A confidential spreadsheet containing the names, salaries, and Social Security Numbers of 9 employees was found publicly posted on a competitor's website. The spreadsheet had only existed on the laptop of Jean, the company's CFO. Jean claimed she had no idea how the data left her machine.

The objective was to determine how the data was stolen — and whether Jean was truly innocent.

---

## Tools Used
| Tool | Purpose |
|---|---|
| Autopsy 4.x | Primary forensic analysis |
| FTK Imager | Evidence verification |
| CyberChef | Data decoding and analysis |

---

## Artifacts Analyzed
| Artifact | Count |
|---|---|
| Email Messages | 261 |
| USB Device Attached | 14 |
| Recent Documents | 9 |
| Web Downloads | 3 |
| Web Search History | 238 |
| Shell Bags | 42 |

---

## Key Findings
- The attacker was an external threat operating through `tuckgorge@gmail.com`
- A fake internal identity (`alex@m57.biz`) was created to initiate contact with Jean
- The attacker spoofed the company president's email (`alison@m57.biz`) to add authority to their requests
- The real Alison always used the display name **AlisonM57** — any email without this was the attacker
- Jean was deceived through social engineering and is determined to be an **innocent victim**
- The exfiltrated file `m57biz.xls` was sent via email on **July 20, 2008 at 07:28**

---

## Attack Timeline
| Date & Time (PKST) | Event |
|---|---|
| 2008-07-18 | AIM downloaded on Jean's workstation |
| 2008-07-20, 05:31 | Jean sends "which email address are you using?" |
| 2008-07-20, 05:32 | Attacker (as Alex) begins sending emails to Jean |
| 2008-07-20, 05:39 | Attacker switches to alison@m57.biz identity |
| 2008-07-20, 07:22 | tuckgorge@gmail.com requests the file masked as alison@m57.biz |
| 2008-07-20, 07:26 | USB device connected to Jean's workstation |
| 2008-07-20, 07:28 | Jean sends m57biz.xls to attacker |
| 2008-07-20, 11:03 | Attacker replies "Thanks!" confirming receipt |
| 2008-07-21 | Real Alison raises alarm — identity had been spoofed |

---

## Repository Contents
