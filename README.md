
# SIEM PoC – Detection of Unauthorized SSH Access Attempts (ISMS Perspective)

This repository contains a Proof of Concept (PoC) study demonstrating how unauthorized access attempts via SSH can be detected on a SIEM platform and how this detection can be evaluated as a control evidence within the scope of the Information Security Management System (ISMS).

This study aims to demonstrate how a technical alarm generated at the SOC level can be interpreted within the framework of the ISO/IEC 27001:2022 standard.

> ⚠️ This PoC was conducted entirely in a personal lab environment for educational and self-improvement purposes.

---

> 📄 This repo was created to technically support the SIEM PoC work described in the Medium article on the same topic.  
> You can access the Medium article here:  
> 🔗 [(https://medium.com/@didem.kis/bir-siem-alarmı-bgysde-nasıl-kontrol-kanıtına-dönüşür-b7bb04bc289c)]


---

## Scenario Summary

- Multiple failed login attempts were made to the SSH service on the Windows 10 system.
- These attempts were logged in the Windows Security Event Log.
- The logs were sent to the SIEM platform and generated an alarm when the defined threshold was exceeded.
- The goal is to detect unauthorized access attempts at an early stage.

---

## Log Source Used

- Log Source: Windows Security Event Log  
- Event ID: **4625** (Failed Logon)  
- Logon Type: **3** (Network / SSH)

---

## SIEM Detection Logic

Within the scope of this PoC, repeated failed login attempts for the same user account within a short period of time were detected. An alarm was generated when the defined threshold value was exceeded.

The detailed detection logic is shared under the `splunk/` directory.

---

## Correlation with ISO/IEC 27001:2022

This PoC study can be correlated with the following controls under ISO/IEC 27001:2022 Annex A:

- **A.5.15 – Access Control**  
  Detection and monitoring of unauthorized access attempts

- **A.8.15 – Logging**  
  Logging of authentication activities

- **A.8.16 – Monitoring Activities**  
  Monitoring and analyzing security events

- **A.5.25 – Information Security Incident Management**  
  Detecting unauthorized access attempts at an early stage and feeding them into incident management processes

---

## Intended Outcome

This study demonstrates:

- How an alarm generated on SIEM can be positioned as a security control within the scope of BGYS,
- How it can provide evidence for audit and risk management processes.

---

## Disclaimer

This PoC study was conducted entirely in a personal lab environment for educational purposes. It has not been applied to real systems or production environments.

