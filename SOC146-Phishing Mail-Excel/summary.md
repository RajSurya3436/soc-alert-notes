# SOC146 - Phishing Mail Detected - Excel 4.0 Macros

## 📄 Event Details
- **Event ID:** 93  
- **Event Time:** June 13, 2021, 02:13 PM  
- **Rule:** SOC146 - Phishing Mail Detected - Excel 4.0 Macros  
- **Severity:** High  
- **Alert Level:** Security Analyst  

## 📧 Email Information
- **SMTP Address:** 24.213.228.54  
- **Source Address:** trenton@tritowncomputers.com  
- **Destination Address:** lars@letsdefend.io  
- **Subject Line:** RE: Meeting Notes  
- **Device Action:** Allowed  

## 🕵️ Investigation Summary
The investigation revealed that the **URL requests** observed in the event were **confirmed to be malicious**. Associated **IP addresses**, when scanned using **VirusTotal**, were also flagged as malicious.

Containment actions were taken promptly:
- The affected **email with the malicious attachment was deleted**.
- No further signs of compromise were detected in the environment.

## 🧪 Community Walkthrough
Sandbox analysis of the Excel file attached to the email confirmed it was malicious. During analysis:
- **C2 addresses** were extracted from the file.
- **Log Management** confirmed access to these C2 addresses, indicating the malicious Excel file was executed.
- The **source device** was identified as **LarsPRD** via Endpoint Management.
- Examination of **Browser History** and **Network Connections** showed communication with malicious IPs and domains.
- **CMD History** showed the execution of the `regsvr32` command, typically associated with Excel 4.0 macro-based execution.

## ✅ Mitigation Actions
- Deleted the phishing email and its attachment.
- Flagged and blocked the related malicious IPs and URLs.
- Contained the threat on the LarsPRD device.
- Verified no further malicious activity or lateral movement.

## 📌 Recommendations
- Block Excel 4.0 macros at both the endpoint and email gateway levels.
- Monitor for use of LOLBins (e.g., `regsvr32`) in user activity.
- Reinforce phishing awareness training for end-users.
