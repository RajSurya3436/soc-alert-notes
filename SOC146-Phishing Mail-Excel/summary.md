# SOC146 - Phishing Mail Detected - Excel 4.0 Macros

##  Event Details
- **Event ID:** 93  
- **Event Time:** June 13, 2021, 02:13 PM  
- **Rule:** SOC146 - Phishing Mail Detected - Excel 4.0 Macros  
- **Answer:** True Positive  
- **Severity:** High  
- **Playbook Checks:**
  - Check if someone opened the malicious file/URL  
  - Check if mail was delivered to the user  
  - Analyze URL/attachment  
  - Identify attachments or URLs in the email  

##  Analyst Note
The investigation revealed that the URL requests observed in the event were confirmed to be malicious. Associated IP addresses, when scanned using VirusTotal, were also flagged as malicious. Containment actions were taken promptly — the affected email with the malicious attachment was deleted, and no further signs of compromise were detected.

##  Editor Note
As a result of the sandbox analysis of the Excel file attached to the email, it was confirmed to be harmful. In the sandbox environment, C2 addresses were extracted. Upon searching these addresses in the log management system, it was found that they had been accessed, indicating that the malicious Excel file had been executed.

The responsible device was identified via Endpoint Management. Further investigation revealed that:
- The system's browser history and network connections showed communication with malicious C2 infrastructure.
- The device’s CMD history indicated execution of the `regsvr32` command, which is known to be exploited by Excel 4.0 macros.

##  Mitigation Actions
- The phishing email and its attachment were deleted.
- Malicious URLs and IPs were flagged for blocking.
- The infected device was isolated and scanned.
- No evidence of lateral movement or additional compromise was found.

##  Recommendations
- Block Excel 4.0 macro execution by default.
- Monitor for use of living-off-the-land binaries (LOLBins) like `regsvr32`.
- Provide phishing awareness training to users.