---
Title: Introduction To Cybersecurity Fundamentals
Status: true
marker:
  - "[[Cybersecurity Fundamentals]]"
tags:
Date: 2025.07.15
Time: 10:12
---
### Introduction to Cybersecurity Fundamentals

- [[#Threat Modeling]]

#### Overview
- **Purpose:** Understanding the foundational knowledge acquired during the first two years of a BTech program, which is essential for grasping how computers and networks operate.
- **Importance:** Abstracting the teaching process is not feasible; hence, a solid understanding of these fundamentals is expected.
#### Legal Requirements

- **Key Regulations:**
    - Information Technology Act (ITA)
    - Digital Personal Data Protection Act (DPDA)
    - General Data Protection Regulation (GDPR)

#### Human Aspects

- **Trust and Awareness:** Essential components in cybersecurity, focusing on the end-user's role.
- **Cybersecurity Risk Management:** Involves identifying, assessing, and mitigating risks associated with information security.

#### Threat Modeling
- **Definition:** A structured approach to identifying security requirements, threats, vulnerabilities, and prioritizing remediation methods.
- **Objective:** Understand and communicate threats and mitigations to protect valuable assets.
##### Components of Threat Modeling
- **Scope:** Description of the subject being modeled.
- **Assumptions:** Conditions that can be verified or challenged as the threat landscape evolves.
- **Threats:** Potential threats to the system.
- **Mitigations:** Actions to mitigate identified threats.
- **Validation:** Methods to validate the model and the effectiveness of actions taken.
##### Applications
- Applicable to software, applications, systems, networks, distributed systems, IoT devices, and business processes.
##### Attack Trees
- **Definition:** Diagrams representing attacks on a system in a tree structure.
- **Structure:**
    - **Root:** The goal of the attack.
    - **Leaves:** Methods to achieve the goal.
- **Usage:** Each goal is represented as a separate tree, resulting in a set of attack trees for system threat analysis.
#### Example of Threat Modeling
- **Scenario:** Protecting a diamond ring from theft.
    - **Vulnerabilities:** Identify when and how the ring might be removed or stolen.
    - **Attack Tree:** Build a tree of potential attacks and choose the most efficient and probable path.
#### Defense Mechanisms
- **Budgeting:** Evaluate the cost-effectiveness of security measures.
    - **Example:** Implementing RFID anti-theft measures for lab mice.
        - **Cost Analysis:** Weigh the cost of security implementation against potential losses.
## Deliverables
- Presentation
- One hack and an entire report on it
- Movie Reports

---

# Our Love with Internet

*(Doom Scrollers, Multiple Apps, Rabbit Share, etc.)*

## Scenario 1 – Insider Bank Data Theft

* You are a **bank employee**.
* **Russian hackers** bribe you to steal bank data.
* You **FTP the data** to a U.S. server data bucket.
* **No logs recorded**.
* Money laundering chain: Russians → Dude in Germany → Dude in UK → You receive money in a 5th country.
* **Catching the culprit is very hard** because:

  * Multi-country involvement.
  * Cross-jurisdictional transfers.
  * Insider access hides footprints.
* **Prevention is more effective**:

  * Make the sensitive data difficult to extract or use.
  * Deploy monitoring & strict access controls.

---

## Nation-State Cyber Threats

* **Main threats**: State and Nation-sponsored attacks.
* **Example – Iran Nuclear Program**:

  * Iran wanted to build nuclear weapons.
  * Their nuclear facilities had an **air-gapped system** (isolated from the internet).
  * Still compromised via an **insider using USB-based malware payload** (e.g., *Stuxnet*).
  * Shows how **air-gaps are not foolproof** if insiders are compromised.

---

## Real-World Cybersecurity Cases

### Ashley Madison (Dating Website)

* Tagline: *“Life is short. Have an affair.”*
* They offered a **\$20 plan to delete user data**.
* Data was **not actually deleted**.
* Users registered with **personal emails**.
* Massive breach exposed identities.
* **Consequences**:

  * Blackmail, reputational damage.
  * Some users committed **suicide** due to exposure.
* Lesson: **Leaving a service ≠ security**.

---

### Health Data Breaches

* **If health data leaks** (e.g., terminal illness):
  * Insurance premiums may spike.
  * Individuals face discrimination.
  * Exploited for fraud and blackmail.

---

### Capital One (Banking)

* Breach exploited an **Apache server vulnerability**.
* Compromised **100 million card details**.
* Lessons:

  * Keep infrastructure patched.
  * Vulnerabilities in open-source software can have massive consequences.

---

## Major Breaches Table

| Organization  | Data Breach Date | What Was Compromised?                                                                 | Impact                                                       | Current Status                            |
| ------------- | ---------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------ | ----------------------------------------- |
| Medibank      | Oct 2022         | 9.7B Customer Records: Names, Birth Dates, Passport Info, Medical Claims, Health Data | Insurance spam, Passport fraud, Premium hikes                | Facing legal actions & investigations     |
| Optus         | 2022             | Customer data via **exposed API (coding error)**                                      | Tens of millions impacted, regulatory & business scrutiny    | Facing legal action                       |
| Canva         | May 2019         | 4M accounts                                                                           | Password security improved post-breach                       | Secured                                   |
| Microsoft     | Jan 2021         | 250M support case logs (email addresses, IPs, case descriptions)                      | Customer data exposure, phishing risks                       | Secured                                   |
| Facebook      | Apr 2019         | 540M records incl. user IDs, passwords, phone numbers (publicly exposed on cloud DB)  | Identity theft, phishing, privacy risks                      | Data taken down, regulatory scrutiny      |
| LinkedIn      | Jun 2021         | 700M profiles (92% of all users) scraped                                              | Data sold online, used for targeted phishing & spam          | Still circulating                         |
| JW Marriott   | Nov 2018         | 500M guest records: names, passport numbers, payment info                             | Hotel guests exposed to fraud & identity theft               | Ongoing lawsuits                          |
| Home Depot    | Sep 2014         | 56M payment card details via POS malware                                              | Major financial fraud, lawsuits, credit monitoring costs     | Settled                                   |
| AIIMS (India) | Nov 2022         | 3-4M patient records + hospital system disruption                                     | Healthcare paralysis, ransomware attempt, data exposure      | Investigation ongoing                     |
| Cosmos Bank   | Aug 2018         | ₹94 crore stolen via **ATM malware + SWIFT transfer**                                 | Coordinated global heist, ATMs drained in multiple countries | FIR filed, partial recovery, RBI scrutiny |

---

## Key Lessons

* **Insider threats** are as dangerous as external hackers.
* **Air-gaps are not foolproof** – physical access can still bypass them.
* **Data deletion promises must be verifiable** (Ashley Madison).
* **Health data is highly sensitive** – leaks can change people’s lives.
* **Patching & monitoring open-source systems is critical** (Capital One).
* **Mass breaches show repeated patterns**:

  * Weak APIs, misconfigurations, unpatched vulnerabilities.
  * Data often ends up in black markets.

---






### References

- **Date:** July 15, 2025
- **Time:** 10:12