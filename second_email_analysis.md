## Introduction

### Description
This project documents a second hands-on phishing email investigation conducted as part of a structured email analysis lab. The objective was to analyze a suspicious email using header inspection and OSINT techniques, identify indicators of malicious activity, and assess the overall risk in a manner consistent with Tier 1 SOC triage.

### Objective
The goals of this investigation were to:

- Analyze a suspicious email in a different attack scenario
- Identify malicious indicators within headers and embedded links
- Determine whether the email required escalation or could be safely closed

  ## Email Artifact Reviewed (What Was Analyzed)

This analysis was performed on the raw `.eml` content (opened in a text editor). The investigation focused on the following sections of the email:

### 1) Message Routing & Origin (Received chain)
- Reviewed the `Received:` headers to identify the sending infrastructure and trace the message path through Microsoft/Outlook protection layers.
- Confirmed the sending IP address observed in header authentication results:
  - `40.107.215.98`

### 2) Email Authentication Results
- Extracted results from:
  - `Authentication-Results:`
  - `ARC-Authentication-Results:`
  - `Received-SPF:`
- Observed SPF results tied to the sender domain:
  - `smtp.mailfrom=comunidadeduar.com.ar`
  ![SPF authentication result showing pass](email_analysis_screenshots/em4.png)

### 3) Sender/Recipient Metadata
Reviewed core identity and tracking fields:
- `From:` `nuthostsrl.SaintU74045Walker@comunidadeduar.com.ar`
- `To:` `Phishingisfun@hotmail.com`
- `Subject:` `We locked your account for security reason - Fri, September 08, 2023 10:11 AM`
- `Date:` `Fri, 8 Sep 2023 10:11:07 +0500`
- `Return-Path:` `nuthostsrl.SaintU74045Walker@comunidadeduar.com.ar`
- `Message-ID:` `<lCoLrriMV1genj0ZtZQMKEVTBnhfL56Wal3quBo1vU@mail-pf1-f856.outlook.office365.com>`

### 4) MIME Structure (Content-Type and Attachments)
- Identified the email as a multipart message:
  - `Content-Type: multipart/mixed; boundary="NextPart_1_..."`

- Confirmed the message contained:
  - An HTML body part (`Content-Type: text/html`)
  - An attachment delivered as base64 with a PDF filename:
    - `Detailsdisable-262340.pdf`

### 5) Embedded Link in HTML Body (User Interaction Risk)
- Extracted the link destination present in the email body:
  - `script.google.com` (Google Apps Script URL)
 
  ### Impersonation Indicators (Evidence)
- The email content impersonates Amazon, but the sender domain is `comunidadeduar.com.ar`.
- The call-to-action link directs to `script.google.com` rather than an Amazon-owned domain.


