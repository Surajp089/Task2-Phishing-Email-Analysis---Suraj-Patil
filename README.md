# Phishing Email Analysis – Task 2

  
## Task: Analyze a Phishing Email Sample  
## Date: August 2025

---

## Objective:
To analyze a suspicious phishing email and identify red flags using tools like VirusTotal, MXToolbox, and header analyzers. The goal is to understand how phishing works and how to detect it effectively.

---

## Tools Used: 
MXToolbox, Google Header Analyzer, VirusTotal, CheckPhish, Gmail Header Analyzer, Hybrid Analysis

## Step By Step Analysis

## Sample Phishing Email
Subject: Urgent Action Required – Account Suspension Notice

Dear User,

We have detected unusual activity in your account. To ensure the security of your information, we have temporarily suspended access to your account.

Please open the attached document and follow the instructions to verify your identity and restore access:

📎 Attachment: Account_Verification_Form.zip

Failure to complete verification within 24 hours will result in permanent suspension.

Thank you for your cooperation,  
Security Team – [YourServiceName]

support@secure-update-login.com

### 2. **Check for Email Spoofing**
- Domain: `secure-update-login.com` is not affiliated with any trusted service.
- MXToolbox showed missing SPF, DNS, and DMARC records → **Spoofing likely**.

### 3. **Header Analysis (Google MessageHeader Tool)**
- Return-Path mismatches sender
- Source IP traced to suspicious Russian host
- Authentication results: **SPF: softfail, DNS: fail, DMARC: fail**

### 4. **Attachment & Link Scan (VirusTotal/Hybrid Analysis)**
- File: `Account_Verification_Form.zip` containing dummy `verify.exe`
- Scan result: **0/60 engines flagged it**
- Explanation: Undetected doesn’t mean safe. Many phishing attachments are **new or obfuscated**, and rely on user interaction.
-Link :- http://secure-update-login.com/verify
- VirusTotal scan showing 1/97 detection by ESET
Explanation that even 1 flagged vendor is a red flag

### 5. **Urgency and Threat Tactics**
- Language like “urgent”, “24 hours”, “account suspended” creates pressure.
- A classic social engineering tactic.

### 6. **Mismatched or Masked URLs**
- Hovering on link: Appears like a trusted domain but redirects elsewhere.
- In this case, the domain is fake and unauthenticated.

### 7. **Poor Language or Grammar**
- No personalization ("Dear User")
- Missing branding and signature
- Basic formatting – signs of a mass phishing email

### 8. **Summary of Threat Indicators**
- Spoofed email domain
- Failed email authentication (SPF/DKIM/DMARC)
- Attachment that could carry malware
- Social engineering and urgency
- VirusTotal didn’t flag it – but it’s still dangerous

---

## Tools Used

| Tool               | Purpose                                 |
|--------------------|-----------------------------------------|
| MXToolbox          | Check DNS records & domain legitimacy   |
| Google Header Analyzer | Trace sender IP, header info        |
| VirusTotal         | Scan link and file (attachment)         |
| CheckPhish.ai      | Detect phishing pages                   |
| Hybrid Analysis    | Analyze file behavior       |

---

## Screenshots Included:
- Account_Verification_Form.zip Scanning in Virustotal
- Checking email header from gmail for reference
- Checking Suspicious link on Virus Total
- Email Header Analyzing using Google Admin Toolbox
- MXToolBox Analyzing Senders Email
- Hybrid Analysis of ZIP attachment
---

## Files in This Repo:
- `README.md` ← This file  
- `Task2 Phishing Email Analysis.PDF` ← Full PDF Report  
- `Account_Verification_Form.zip` ← Simulated phishing attachment  
- `Screenshots` ← Scan result  






