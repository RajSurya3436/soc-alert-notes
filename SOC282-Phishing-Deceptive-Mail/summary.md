# SOC282 - Phishing Alert - Deceptive Mail Detected

## Event Details
- **Event ID:** 257  
- **Event Time:** May 13, 2024, 09:22 AM  
- **Rule Triggered:** SOC282 - Phishing Alert - Deceptive Mail Detected  
- **Final Verdict:** True Positive  
- **SMTP IP:** 103.80.134.63  
- **Subject:** Free Coffee Voucher  
- **Device Action:** Allowed  

## Investigation Summary
This alert was triggered by a suspicious email with the subject line "Free Coffee Voucher." The message appeared to be a lure-based phishing attempt aimed at tricking the user into clicking a potentially malicious link.

Key findings from the investigation:

- The sender’s domain (`coffeeshooop.com`) was spoofed and unrelated to any known legitimate organization.
- The IP address **103.80.134.63** was analyzed in **VirusTotal** and found to have a history of **spam and phishing** activity.
- The embedded phishing URL was submitted to **Hybrid Analysis**, which flagged the page as **deceptive** and used for **credential harvesting**.
- Email header inspection revealed **SPF/DKIM authentication failures** and no links pointing to official services.
- Although the device action was marked as "Allowed", the email content and behavior aligned with known phishing techniques.

## Tools Used
- VirusTotal – IP and domain reputation analysis  
- Hybrid Analysis – URL behavior and sandbox evaluation  
- Email header inspection tools  

## Verdict
- **Risk Level:** Medium  
- **Classification:** Phishing (Credential Harvesting / Fake Offer)  
- **Action Taken:** 
  - Sender IP and domain were blacklisted  
  - Email was reported internally  
  - Awareness guidance provided to the end-user  

## Notes
This case highlights the importance of analyzing low-effort phishing emails that may bypass automated filters but still pose a threat to unaware users. Continuous training and detailed inspection remain critical in identifying and mitigating such social engineering attacks.
