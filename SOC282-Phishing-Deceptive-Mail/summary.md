# SOC282 - Phishing Alert - Deceptive Mail Detected

## 📅 Event Details
- **Event ID**: 257  
- **Event Time**: May 13, 2024, 09:22 AM  
- **Rule Triggered**: SOC282 - Phishing Alert - Deceptive Mail Detected  
- **Final Verdict**: True Positive  
- **Source Address**: free@coffeeshooop.com  
- **Destination Address**: Felix@letsdefend.io  
- **Subject**: Free Coffee Voucher  
- **SMTP IP**: 103.80.134.63  
- **Device Action**: Allowed

## 🔍 Investigation Summary
This alert was triggered by a suspicious email with the subject line "Free Coffee Voucher." The message appeared to be a lure-based phishing attempt aimed at tricking the user into clicking a potentially malicious link.

Key findings from the investigation:
- The sender’s domain (`coffeeshooop.com`) was spoofed and unrelated to any known legitimate organization.
- The IP address `103.80.134.63` was analyzed in **VirusTotal** and found to have previous associations with spam and phishing activity.
- The phishing URL embedded in the email was submitted to **Hybrid Analysis**, which flagged the page as deceptive and used for potential credential harvesting.
- Header analysis showed authentication failures (SPF/DKIM), and there were no legitimate links pointing to official services.
- Despite the device action being "Allowed," the content and behavior matched phishing patterns.

## 🛠 Tools Used
- VirusTotal (IP and domain reputation)  
- Hybrid Analysis (URL behavior and sandbox results)  
- Header inspection tools

## ⚠️ Verdict
- **Risk Level**: High  
- **Classification**: Phishing (Credential Harvesting / Fake Offer)  
- **Action Taken**: Sender IP and domain were blacklisted. Email was reported internally. Awareness steps advised for end-user.

---

> 🔍 This case highlights the importance of analyzing low-effort phishing emails that may bypass automated filters but still pose a threat to unaware users.