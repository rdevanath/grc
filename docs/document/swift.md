---
tags:
  - Frameworks & Standards
---

# SWIFT – Secure Financial Messaging

* SWIFT **(Society for Worldwide Interbank Financial Telecommunication)** is the global network that enables banks and financial institutions to exchange standardized, secure financial messages (e.g., payment instructions, securities trades, FX confirmations).

* It doesn’t move money itself; it transmits the instructions that allow institutions to settle transactions.

## SWIFT CSP – Customer Security Programme

* **What it is:** A cybersecurity initiative launched in 2016 after high-profile fraud incidents.

* **Purpose:** To strengthen the overall security of the SWIFT ecosystem by ensuring that member institutions protect their local environments (not just the central SWIFT network).

* **Scope:** Covers governance, risk management, and operational security practices for all SWIFT users.

* **Requirement:** Institutions must self-attest annually to their compliance with CSP standards, and some must undergo independent assessments.

## CSCF – Customer Security Controls Framework

The SWIFT Customer Security Controls Framework (CSCF) is part of the _SWIFT Customer Security Programme (CSP)_. It was developed by the **Society for Worldwide Interbank Financial Telecommunication (SWIFT)** to strengthen cybersecurity across its global financial messaging network.

Who Governs It?

* **Governing Body:** The CSP is governed by SWIFT (Society for Worldwide Interbank Financial Telecommunication), a member-owned cooperative headquartered in Belgium.

* **Oversight:** SWIFT’s Board of Directors and cybersecurity teams oversee the development and enforcement of the CSP and CSCF.

* **Compliance:** Institutions must **self-attest annually** to their compliance, and some are required to undergo **independent assessments.**

Where Is It Applicable?

The CSP applies to all institutions that use the SWIFT network, including: Banks, Brokerages, Clearing houses, Payment service providers, Central banks.

It is globally applicable, covering over 11,000 institutions in more than 200 countries. Whether a small regional bank or a multinational financial giant, any entity connected to SWIFT must comply with the CSCF controls.

## Objectives

The CSCF is structured around three overarching objectives:

1. **Secure your environment** – Protect the local SWIFT infrastructure.

2. **Know and limit access** – Control who and what can access SWIFT systems.

3. **Detect and respond** – Monitor for suspicious activity and respond to incidents.

These objectives are supported by **8 core principles** and **32 detailed security controls**.

Key Components:

* **Mandatory Controls:** These are baseline security requirements that all SWIFT users must implement. They cover areas like access control, malware protection, and secure communication.

* **Advisory Controls:** These are best practices that SWIFT recommends but does not require. They help institutions go beyond the minimum and improve their overall security posture.

## Control List

The SWIFT Customer Security Controls Framework (CSCF) includes 32 controls—20 mandatory and 12 advisories—organized under 8 security principles to protect institutions using the SWIFT network.

1. **Restrict Internet Access**

    1.1. No direct internet access to SWIFT systems _(Mandatory)_

    1.2. Operating system privileged account control _(Mandatory)_

    1.3A. Secure internet access points _(Advisory)_

2. **Protect Critical Systems from General IT Environment**

    2.1. Segregate SWIFT systems from general IT _(Mandatory)_

    2.2. Reduce shared use of SWIFT components _(Mandatory)_

    2.3A. Protect SWIFT components from malware _(Advisory)_

    2.4. Application whitelisting _(Mandatory)_

3. **Reduce Attack Surface and Vulnerabilities**

    3.1. Timely application of security updates _(Mandatory)_

    3.2. System hardening _(Mandatory)_

    3.3A. Remove unnecessary software/services _(Advisory)_

4. **Physically Secure the Environment**

    4.1. Restrict physical access _(Mandatory)_

    4.2. multi-factor authentication _(Mandatory)_

    4.3A. Monitor physical access _(Advisory)_

5. **Prevent Compromise of Credentials**

    5.1. Logical access control _(Mandatory)_

    5.2. Password policy enforcement _(Mandatory)_

    5.3A. Privileged access management _(Advisory)_

6. **Detect and Respond to Anomalies**

    6.1. Logging and monitoring _(Mandatory)_

    6.2. Detect anomalous activity _(Mandatory)_

    6.3A. Centralized log collection _(Advisory)_

    6.4A. Behavioural monitoring _(Advisory)_

    6.5A. Intrusion detection _(Advisory)_

7. **Plan for Incident Response and Information Sharing**

    7.1. Cyber incident response plan _(Mandatory)_

    7.2A. Information sharing with SWIFT community _(Advisory)_

8. **Ensure Integrity of Software and Data**

    8.1. Software integrity validation _(Mandatory)_

    8.2. Database integrity checks _(Mandatory)_

    8.3A. Cryptographic file validation _(Advisory)_

    8.4A. Secure backup and recovery _(Advisory)_

## Why It Matters for Compliance

Any institution using the SWIFT network must demonstrate compliance with the CSCF. This includes:

•	Annual self-attestation of compliance status.

•	Independent assessments (mandatory for some users).

•	Ongoing updates as the framework evolves to address emerging threats.

Non-compliance can lead to reputational damage, regulatory scrutiny, or even restricted access to the SWIFT network.

## RBI's Recognition and Oversight of SWIFT

Reserve Bank of India (RBI) has officially recognized SWIFT and mandated Indian banks to comply with its security standards. RBI has issued guidelines and taken enforcement actions to ensure SWIFT-related operational controls are implemented across Indian financial institutions.

* **Official Recognition:** RBI acknowledges SWIFT as a critical infrastructure for international financial messaging and has issued multiple circulars since 2016 to strengthen its security environment in Indian banks.

* **Compliance Mandate:** RBI requires all banks using SWIFT to implement specific operational and cybersecurity controls, aligned with SWIFT’s Customer Security Controls Framework (CSCF).

* **Monitoring and Enforcement:** RBI monitors compliance through inspections and has imposed penalties on banks failing to meet SWIFT-related requirements.