---
Title: Cybersecurity Fundamentals Lab 2
Status: 
marker:
  - "[[CyberSec Fundamentals Index]]"
  - "[[Cybersecurity Fundamentals]]"
tags:
  - BTech
Date: 2025.07.22
Time: 10:49
---
# Cybersecurity Fundamentals Lab 2

## Aim 
To study MITRE att&ck framework and cyber skill chain 

## A little introduction
* **MITRE ATT\&CK®** = MITRE *Adversarial Tactics, Techniques, and Common Knowledge*.
* It’s a **curated knowledge base** of real-world cyber adversary behavior.
* Models the **attack lifecycle** and targeted platforms.
* Uses a **common taxonomy** for offensive and defensive understanding.
* Core components:
  * **Tactics** – short-term adversary goals (columns).
  * **Techniques** – methods used to achieve those goals (cells).
  * **Metadata** – documented real-world usage and defenses.

## A table of Attacks
Consider : Operation Silent Vault is a fictional cyber-attack scenario in which a financially motivated threat actor group targets a mid-sized bank’s online customer portal. Their objective is to steal customer login credentials through phishing and malware and then perform unauthorized financial transactions. 

Identify the various tactics and techniques that threat actor group may use. Prepare a table as shown below

| **Tactic** (MITRE Category) | **Technique** (ID & Name)                                 | **Description**                                                                                |
| --------------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Reconnaissance**          | **T1592 – Gather Victim Identity Information**            | Threat actor gathers employee names, emails, or job roles to craft targeted phishing messages. |
| **Resource Development**    | **T1583.001 – Acquire Infrastructure: Domains**           | Attacker registers a fake banking domain similar to the target’s for phishing emails.          |
| **Initial Access**          | **T1566.002 – Phishing: Spearphishing Link**              | Victim receives an email containing a malicious link leading to a credential-harvesting page.  |
| **Execution**               | **T1204.002 – User Execution: Malicious File**            | Victim downloads and runs malware disguised as a bank security update.                         |
| **Persistence**             | **T1053.005 – Scheduled Task/Job: Scheduled Task**        | Malware creates a scheduled task to maintain access even after reboot.                         |
| **Privilege Escalation**    | **T1055 – Process Injection**                             | Malware injects into legitimate processes to escalate privileges and evade detection.          |
| **Defense Evasion**         | **T1027 – Obfuscated Files or Information**               | Malware code is obfuscated to avoid signature-based antivirus detection.                       |
| **Credential Access**       | **T1056.001 – Input Capture: Keylogging**                 | Malware logs keystrokes to capture banking login credentials.                                  |
| **Discovery**               | **T1083 – File and Directory Discovery**                  | Malware searches for configuration files or stored credentials on the victim’s device.         |
| **Lateral Movement**        | **T1021.001 – Remote Services: Remote Desktop Protocol**  | Attacker pivots into other systems in the bank’s internal network using stolen credentials.    |
| **Collection**              | **T1114.002 – Email Collection: Remote Email Collection** | Attacker collects customer communications from compromised bank employee accounts.             |
| **Command and Control**     | **T1071.001 – Application Layer Protocol: Web Protocols** | Malware communicates with the attacker’s server using HTTPS to blend with normal traffic.      |
| **Exfiltration**            | **T1041 – Exfiltration Over C2 Channel**                  | Stolen credentials and transaction data are sent out over the established C2 channel.          |
| **Impact**                  | **T1657 – Financial Theft**                               | Attacker uses stolen credentials to initiate fraudulent wire transfers.                        |

---

## **Part 1 – Countermeasures Table**

| **Kill Chain Stage**            | **Scenario Description**                                                                                                    | **Countermeasures**                                                                                                                                                                                                                              |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1. Reconnaissance**           | Attackers identify the bank’s technology stack using passive scanning (e.g., Shodan, WHOIS, LinkedIn employees).            | - Monitor for abnormal queries to public services (threat intel feeds). <br> - Limit public exposure of infrastructure details. <br> - Remove unnecessary technical info from websites/employee profiles. <br> - Enable domain privacy on WHOIS. |
| **2. Weaponization**            | They create a custom phishing email with a malicious PDF containing an exploit for an unpatched Adobe Reader vulnerability. | - Keep software patched and updated. <br> - Use sandboxing to test email attachments before delivery. <br> - Deploy endpoint protection with exploit prevention.                                                                                 |
| **3. Delivery**                 | Phishing email sent to bank employees from spoofed `"compliance@banking.gov"`.                                              | - Implement DMARC, DKIM, and SPF to prevent spoofing. <br> - Use advanced email filtering and phishing detection. <br> - Conduct regular phishing awareness training for staff.                                                                  |
| **4. Exploitation**             | Employee opens the attachment, triggering code execution that installs a backdoor.                                          | - Apply security patches promptly. <br> - Disable automatic execution of macros/scripts in documents. <br> - Deploy EDR (Endpoint Detection & Response) to detect suspicious activity.                                                           |
| **5. Installation**             | Malware installs a RAT and establishes persistence via registry keys.                                                       | - Restrict write permissions to registry autorun locations. <br> - Monitor persistence mechanisms (scheduled tasks, registry keys). <br> - Use application whitelisting to block unapproved binaries.                                            |
| **6. Command and Control (C2)** | RAT communicates with a command server using DNS tunneling.                                                                 | - Monitor and block abnormal DNS traffic patterns. <br> - Implement DNS filtering and logging. <br> - Use network anomaly detection systems.                                                                                                     |
| **7. Actions on Objectives**    | Attackers capture login credentials and initiate unauthorized wire transfers.                                               | - Enforce multi-factor authentication (MFA). <br> - Monitor transactions for anomalies. <br> - Implement role-based access control. <br> - Use behavior analytics to detect suspicious account activity.                                         |

---

## **Part 2 – Cyber Kill Chain → MITRE ATT\&CK Mapping**

| **Kill Chain Stage**            | **MITRE Tactic**                   | **MITRE Technique**                                                                                                                                  |
| ------------------------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Reconnaissance**           | **Reconnaissance**                 | **T1592 – Gather Victim Identity Information** (collecting employee details), **T1590 – Gather Victim Network Information** (scanning Shodan, WHOIS) |
| **2. Weaponization**            | **Resource Development**           | **T1587.001 – Develop Capabilities: Malware** (craft malicious PDF)                                                                                  |
| **3. Delivery**                 | **Initial Access**                 | **T1566.002 – Phishing: Spearphishing Link/Attachment**                                                                                              |
| **4. Exploitation**             | **Execution**                      | **T1203 – Exploitation for Client Execution** (PDF exploit)                                                                                          |
| **5. Installation**             | **Persistence**                    | **T1547.001 – Boot or Logon Autostart Execution: Registry Run Keys / Startup Folder**                                                                |
| **6. Command and Control (C2)** | **Command and Control**            | **T1071.004 – Application Layer Protocol: DNS**, **T1090 – Proxy** (DNS tunneling)                                                                   |
| **7. Actions on Objectives**    | **Credential Access** / **Impact** | **T1056.001 – Input Capture: Keylogging** (credential theft), **T1657 – Financial Theft** (unauthorized transfers)                                   |

---
## Questions and answers

**1. Compare and contrast ATT\&CK framework and Cyber Kill Chain**

* **Scope:**

  * *Cyber Kill Chain* – Linear, high-level attack progression model (7 stages).
  * *MITRE ATT\&CK* – Detailed, non-linear knowledge base of adversary tactics/techniques.
* **Focus:**

  * *Kill Chain* – Overall phases from intrusion to impact.
  * *ATT\&CK* – Specific techniques, procedures, and mappings to real-world threats.
* **Usage:**

  * *Kill Chain* – Strategic view for detection points in the attack lifecycle.
  * *ATT\&CK* – Tactical/technical mapping for detection, hunting, and testing.
* **Detail Level:**

  * *Kill Chain* – Broad stage descriptions.
  * *ATT\&CK* – Granular behaviors, IDs, mitigation, detection guidance.

---

**2. How Cyber Kill Chain complements MITRE ATT\&CK in threat detection & response**

* Kill Chain = **macro-level** map of attacker journey.
* ATT\&CK = **micro-level** library of how each stage is executed.
* Together:

  * Kill Chain shows **where** in the lifecycle the attack is.
  * ATT\&CK shows **how** the attacker is operating at that stage.
  * Improves detection coverage, prioritization, and incident response playbooks.

---

**3. “Command and Control over DNS” (T1071.004)**

* **Kill Chain Stage:** Command and Control (C2).
* **Effective Countermeasures:**

  * Monitor for unusual DNS query volumes and patterns.
  * Use DNS filtering/blocking for suspicious domains.
  * Implement network anomaly detection.
  * Restrict and log external DNS requests.

---

**4. Why early detection (Reconnaissance & Delivery) is more cost-effective**

* Earlier disruption = **less attacker foothold**, less cleanup needed.
* Prevents **data theft, system compromise, and financial loss** before damage occurs.
* Cost to remediate increases **exponentially** with each stage progressed.
* Early stages often leave **more visible, low-cost detection opportunities** (email filters, intel monitoring).

---

**5. Variants of the MITRE ATT\&CK framework**

* **Enterprise ATT\&CK** – TTPs for Windows, macOS, Linux, cloud, and enterprise systems.
* **Mobile ATT\&CK** – TTPs for Android and iOS attacks.
* **ICS ATT\&CK** – TTPs for Industrial Control Systems and OT environments.
* **PRE-ATT\&CK** *(now merged into Enterprise)* – TTPs for pre-compromise activities (planning, reconnaissance).

---


# References


###### Information
- date: 2025.07.22
- time: 10:49