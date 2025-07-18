# Incident Summary Report

**Incident ID:** 86  
**Detection Rule:** SOC141 – Phishing URL Detected  
**Severity:** High  
**Status:** Contained  
**Date/Time:** March 22, 2021 – 09:23 PM  
**Analyst Verdict:** True Positive

---

## Summary

A phishing attempt was detected from an internal host targeting a user-specific email address. The destination was a suspicious foreign domain likely used for spear-phishing. The request was blocked at the network perimeter, and no indicators of compromise were found on the source machine. The incident has been contained.

---

## Response and Containment

- Connection was blocked at the perimeter
- Domain added to blocklist
- Affected host scanned; no compromise detected
- No further related activity observed
- User awareness measures initiated

---

## Playbook Actions

- Has Anyone Accessed IP/URL/Domain? (+5 Points)  
- Analyze URL Address (+5 Points)

---

## Analyst Note

The event was identified as a targeted phishing attempt. The affected system made a request to a suspicious domain, which was blocked. No malicious activity was found on the endpoint, and the incident has been fully contained.

---

## Tags

`phishing` `spear-phishing` `SOC141` `contained` `high-severity`
