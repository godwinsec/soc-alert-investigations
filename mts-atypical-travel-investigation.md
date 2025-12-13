# Atypical Travel Alert Investigation

## Scenario Context
This investigation was performed by me as part of a simulated Managed Security Service Provider (MSSP) environment, where I operated in a Tier-1 SOC analyst role monitoring Maple Tax Solutions (MTS), a fictional financial services client using Microsoft 365 and Microsoft Entra ID.

The alert originated from Microsoft Entra ID Protection and was investigated using Microsoft Defender XDR.

---

## Incident Overview
- **Client:** Maple Tax Solutions (MTS)
- **Alert Name:** Atypical travel
- **Alert ID:** ade786069999ca66a5a2cdd57ca642a078cd9e81db
- **Severity:** Medium (incident correlated as High)
- **Detection Source:** Microsoft Entra ID Protection
- **Analyst:** Godwin Ifeanyi Uche
- **Date:** 12 Dec 2025

---

## Executive Summary
An Atypical Travel alert was generated for the account **SOC-86** after sign-in attempts were observed from geographically distant locations within an implausible time window. Post-authentication activity review revealed repeated successful logons and mailbox access activity. Based on the evidence, the activity was assessed as **most likely malicious**, indicating potential credential compromise.

---

## What Happened
Microsoft Entra ID Protection detected sign-ins for the same account from:
- **Warwickshire, United Kingdom** (IP: 86.163.148.43)
- **Atlanta, Georgia, United States** (IP: 216.131.75.80)

The time between these sign-ins makes legitimate travel impossible. Common VPN false positives were excluded by the detection logic.

---

## Evidence Observed

### Sign-In Details
| IP Address | Location | ISP / ASN |
|-----------|---------|-----------|
| 86.163.148.43 | UK (Warwickshire) | British Telecommunications |
| 216.131.75.80 | US (Atlanta) | NetProtect / Strong Technology LLC |

### Post-Sign-In Activity
- Multiple rapid successful logon events
- Access to Microsoft 365 and Exchange Online
- **MailItemsAccessed** activity observed
- Repeated authentication attempts from the same IP

No endpoint-level activity was associated with this alert.

---

## Contextual Analysis
The affected account (**SOC-86**) appears to be a non-user or service-style lab account without defined travel baselines. Such accounts are commonly targeted due to reduced monitoring and lack of consistent usage patterns. One of the IP addresses involved is associated with hosting or proxy infrastructure, increasing the risk profile.

---

## Assessment
- **Likelihood:** Most likely malicious
- **Rationale:**
  - Impossible travel pattern detected
  - Repeated successful authentications
  - Mailbox access observed
  - No business justification for cross-geographic access

---

## Recommended Actions (Not Executed)
- Force password reset for the affected account
- Revoke active authentication sessions
- Review account permissions and usage
- Confirm MFA enforcement
- Continue monitoring for additional identity-based alerts

---

## Status
Investigation complete.  
Case remains **open** per training instructions to allow peer review.
