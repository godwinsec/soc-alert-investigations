```text
Received: from SJ0PR06MB6767.namprd06.prod.outlook.com (2603:10b6:a03:286::13)
 by DM6PR06MB4091.namprd06.prod.outlook.com with HTTPS; Wed, 6 Dec 2023
 17:07:20 +0000

Received: from TY2PR0101CA0005.apcprd01.prod.exchangelabs.com
 by SJ0PR06MB6767.namprd06.prod.outlook.com with Microsoft SMTP Server;
 Wed, 6 Dec 2023 17:07:19 +0000

Received: from TYZPR01MB4137.apcprd01.prod.exchangelabs.com
 by TY2PR0101CA0005.outlook.office365.com;
 Wed, 6 Dec 2023 17:07:18 +0000

Received: from DM6NAM04FT068.eop-NAM04.prod.protection.outlook.com
 by DS7PR03CA0035.outlook.office365.com;
 Wed, 6 Dec 2023 17:07:15 +0000

Authentication-Results:
 spf=softfail (sender IP is 183.56.179.169);
 dkim=none;
 dmarc=none

Received-SPF: SoftFail (sasktel.net discourages use of 183.56.179.169)

Received: from mail.yobow.cn (183.56.179.169)
 by mail.protection.outlook.com;
 Wed, 6 Dec 2023 17:07:14 +0000

Reply-To: <agentcynthiajamescontact01@[gmail].com>
From: "Mrs Janet Yellen" <p.chambers@[redacted].net>
Subject: Attention Dear Beneficiary
Date: Wed, 6 Dec 2023 05:00:12 -0800
Content-Type: text/html; charset="Windows-1251"
Content-Transfer-Encoding: 7bit
Message-ID: <redacted>
```

## Lab Questions and Answers

### 1. What is the status of SPF, what does it mean, and why did it occur?
SPF validation resulted in **SoftFail**. The sending IP address (183.56.179.169) is not authorized to send email on behalf of the domain `sasktel.net`, indicating sender domain spoofing.

---

#### Why it occurred:
The email claims to be from sasktel.net, but it originated from 183.56.179.169, which is not listed in the domain’s SPF record.

---


### 2. What is the sender’s IP address?
183.56.179.169 
found in : 
Received: from mail.yobow.cn (183.56.179.169)
X-Sender-IP: 183.56.179.169


---

### 3. Are DKIM and DMARC set up?
DKIM and DMARC are not configured for this email, as indicated by `dkim=none` and `dmarc=none`.

---

### 4. What is the domain name of the mail server closest to the sender?
mail.yobow.cn

---

### 5. What is the reported date of this email?
Wed, 6 Dec 2023 05:00:12 -0800

---

### 6. What is the email address of the sender and when was the domain created?
The sender email address is `p.chambers@[redacted].net`. The domain `sasktel.net` was created on 5 April 2000, according to WHOIS records.


---

### 7. If the recipient were to reply to this email, who would it be sent to?
Replies would be sent to `agentcynthiajamescontact01@[gmail].com`.

---

### 8. What is the subject line of this email?
Attention Dear Beneficiary

---

### 9. If the email failed to deliver, who would receive the error message?
Non-delivery reports would be sent to the address specified in the Return-Path header. Return-Path: p.chambers@[sasktel].net



---

### 10. How many Content-Type values are present and how will the message be rendered?
One Content-Type is present: `text/html`. The message would be rendered as HTML.

---

### 11. What is the Message-ID for this email?
The Message-ID has been redacted for public documentation.

---

### 12. The recipient is instructed to email two individuals. Who are they?
- Cynthia James – `agentcynthiajamescontact01@[gmail].com`  
- P. Chambers – `p.chambers@[redacted].net`

---

### 13. When was the root domain of the mail server created and which country is it located in?
The root domain is `yobow.cn`. Domain age and country require OSINT analysis.

---

### 14. Has the root domain been involved in any other phishing-related activity?
Additional OSINT analysis is required to determine prior phishing activity.

---

### 15. Has the sender IP been reported for spam previously?
Reputation analysis is required to determine prior spam activity.

---

### Bonus: Is the sender IP part of a VPN service?
The sender IP appears to belong to a hosting provider rather than a consumer VPN service.

---

### 16. If you received this email, what would your next steps be?
The email would be reported as phishing, quarantined, and escalated for further investigation. Sender IPs and domains would be blocked as appropriate.
