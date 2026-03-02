---
tags:
  - Frameworks & Standards
---

# PCI-DSS (Payment Card Industry Data Security Standard)

## Introduction

The PCI Data Security Standard v4.0 (published March 31, 2022) is an information security standard for businesses that handle payment card (both credit and debit) information. It was created by the PCI Security Standards Council that includes every major payment card company - Visa, MasterCard, Discover, American Express, JCB and UnionPay.

These businesses are expected to comply with PCI DSS, enforced through assessments via Self-Assessment Questionnaires (SQA) or Qualified Security Assessors (QSAs) and they can be fined or penalized if they don't.

The standard’s 12 requirements fall under six objectives:

1.	Build and maintain a secure network
    *	Install and maintain network security controls 
    *	Apply secure configurations to all system components

2.	Protect cardholder data
    *	Protect stored account data 
    *	Protect cardholder data with strong cryptography during transmission

3.	Maintain a vulnerability management program
    *	Protect all systems and networks from malicious software
    *	Develop and maintain secure systems and software

4.	Implement strong access controls
    *	Restrict access to system components and account data by business need-to-know 
    *	Identify users and authenticate access to system components
    *	Restrict physical access to cardholder

5.	Regularly monitor and test networks
    *	Log and monitor all access to system components and cardholder data
    *	Test security of systems and networks regularly

6.	Maintain an information security policy
    *	Support information security with organizational policies and programs

## Merchant Level

Annual transaction volume determines your merchant level (Level 1–4).

!!! info "Merchant Level"
    *	Level 1 - More than 6 million

    *	Level 2 - 1 to 6 million

    *	Level 3 - 20,000 to 1 million

    *	Level 4 - Fewer than 20,000

PCI DSS compliance assessment is fundamentally an annual requirement, but it includes mandatory quarterly components. 

* **Annually (Annual Assessment/Attestation):** All entities (merchants and service providers) must validate their compliance with PCI DSS requirements once a year.

    * **Level 1 Merchants/Service Providers:** Require a formal Report on Compliance (ROC) performed by a Qualified Security Assessor (QSA).

    * **Level 2-4 Merchants:** Generally, require a self-validated Self-Assessment Questionnaire (SAQ) and an Attestation of Compliance (AOC).
    
    * **Payment environment determines which SAQ type applies** depending on how a merchant accepts and processes cardholder data (e.g., e commerce, in store terminals, outsourcing, storage of card data, etc.).

* **Quarterly (Network Scans):** If you have external-facing IP addresses, you must conduct quarterly vulnerability scans performed by a PCI-approved scanning vendor (ASV).

* **Annual Penetration Testing:** In addition to the annual assessment, a penetration test of the network and applications is required at least annually. 

**Key Takeaway:** While you submit your formal compliance validation once a year, you must perform quarterly vulnerability scans to maintain that compliance throughout the year.

## Self Assessment Questionnaire (SAQ)

* It’s a validation tool created by the PCI Security Standards Council (PCI SSC).

* Merchants and service providers use it to self evaluate their compliance with the PCI DSS (Payment Card Industry Data Security Standard).

* Instead of always undergoing a full external audit, smaller or lower risk entities can complete the SAQ to demonstrate they meet PCI DSS requirements.

**What are SAQs for?**

* Compliance Reporting: They allow merchants/service providers to report their PCI DSS compliance status to their acquiring bank or payment brands.

* Risk Reduction: By answering the SAQ, organizations confirm they have the required security controls in place to protect cardholder data.

* Scoping Tool: Different SAQ types apply depending on how you handle cardholder data (e.g., e commerce only, in store terminals, fully outsourced processing).

* Alternative to Full Audit: For smaller merchants (PCI Level 2 - 4), SAQs replace the need for a full Report on Compliance (RoC) by a Qualified Security Assessor.

**How They Work**

* Each SAQ is a set of yes/no questions aligned to PCI DSS requirements.

* At the end, the merchant signs an Attestation of Compliance (AoC) confirming they meet the requirements.

* The completed SAQ is submitted to the acquiring bank or card brand as proof of compliance.

## Cardholder Data Environment

PCI DSS system categorization and scoping involve identifying the Cardholder Data Environment (CDE) and connected systems to determine applicable controls and SAQ type.

The CDE includes people, processes, and technology handling cardholder data (CHD) or Sensitive Authentication Data (SAD), plus connected systems. Start by inventorying all CHD/SAD flows, storage locations, and processing points using data discovery tools or diagrams. Connected systems (e.g., those sharing networks) must be scoped if they impact CDE security.

**Categorize Systems**

* **In-Scope (CDE Core):** Systems directly storing, processing, or transmitting CHD/SAD.

* **Connected-to-CDE:** Systems on the same network or with logical access to CDE; apply segmentation (e.g., firewalls) to limit scope.

* **Out-of-Scope:** Isolated systems with no CDE connectivity; verify annually via testing.

**Scoping Steps**

1.	Map data flow diagrams showing CHD entry, movement, and exit points.

2.	Segment networks to isolate CDE (Requirement 1).

3.	Select SAQ based on payment methods (e.g., SAQ A for fully outsourced CNP, SAQ D for others)

4.	Document scope in a report with diagrams and justifications

## Storing CHD & SAD

**1. Cardholder Data (CHD)**

Cardholder data can be stored by merchants if there is a legitimate business need and it is protected (typically via encryption). It includes:

* **Primary Account Number (PAN):** The unique 15- or 16-digit credit or debit card number.

* **Cardholder Name:** The name of the individual to whom the card was issued.

* **Expiration Date:** The month and year the card expires.

* **Service Code:** A three- or four-digit number in the magnetic stripe that specifies acceptance requirements and limitations for the card.

The full PAN _must_ be rendered unreadable if stored, using methods like encryption, truncation, or hashing. Name, expiration date, and service code are included only when linked with the full PAN.

**2. Sensitive Authentication Data (SAD)**

SAD is _highly sensitive_ information used to authorize transactions. According to PCI DSS version 4.0, SAD must never be stored after authorization, even if it is encrypted (except for issuers with justified needs under strict controls like strong cryptography). It includes: 

* **Full Track Data:** The complete data contained on the card's magnetic stripe or equivalent data on a chip.

* **Card Verification Codes:** Also known as CVV2, CVC2, CID, or CAV2, these are the 3- or 4-digit security codes printed on the front or back of the card.

* **PINs and PIN Blocks:** Personal Identification Numbers and the encrypted blocks of data used to transport them during a transaction.

## Tokenization

A data protection technique used in payment security.

* It replaces sensitive cardholder data (like the Primary Account Number, PAN) with a random, unique “token”.

* It is primarily used to secure transactions. By storing a token instead of a credit card number, a merchant reduces their "attack surface." If their database is breached, the tokens are worthless to hackers without access to the separate "token vault".

* The token has no exploitable value if intercepted — it _cannot_ be mathematically _reversed_ to reveal the original card number.

* The real card data is stored securely in a token vault (usually managed by a PCI DSS compliant provider) which is the only place the token can be mapped back to the original data.

* Merchants and systems then use the token instead of the actual card number for transactions, recurring billing, or analytics.

**Benefits of Tokenization**

* Reduces PCI DSS scope (fewer systems handle real card data).

* Enhances security — tokens are useless to attackers.

* Supports business processes like recurring payments without storing PANs.

* Simplifies compliance and lowers audit costs.

## Types of SAQ forms

There are 9 Self Assessment Questionnaires (SAQs) under PCI DSS.
They are designed for different merchant environments depending on how you accept and process cardholder data:

* **SAQ A** applies to card-not-present (CNP) merchants, including e-commerce and mail/telephone order (MOTO), who fully outsource all payment processing to a PCI DSS-compliant third-party service provider. These merchants do not electronically store, process, or transmit cardholder data on their systems.

* **SAQ A-EP** targets e-commerce merchants who outsource payment processing but maintain websites or elements (like payment forms) that could impact transaction security. Unlike SAQ A, these merchants have partial control over the payment page, though they still avoid direct electronic handling of cardholder data.

* **SAQ B** applies to merchants processing cardholder data only via imprint machines or standalone, non-networked dial-out terminals, with no electronic transmission or storage of card data. It covers a limited set of PCI DSS requirements like physical access controls, policies, and restricting data access.

    Standalone dial-out terminals are independent payment devices, typically countertop credit card readers, that connect directly to a payment processor via a standard analogue phone line (dial-up) rather than the internet or a network. They process transactions offline by dialling out to authorize cards, ensuring no cardholder data enters your internal systems.

* **SAQ B-IP** targets merchants using standalone, PTS-approved point-of-interaction (POI) devices connected via IP (modern, standalone payment terminals) to process card data, but with no electronic storage or other non-terminal functions handling cardholder data. It includes more comprehensive requirements than SAQ B, such as network security and vulnerability management for the IP-connected devices.

* **SAQ C** applies to merchants and service providers using payment application systems connected to the internet or other public networks, where they process, store, or transmit cardholder data electronically. It covers most PCI DSS requirements, including firewalls, access controls, encryption, and monitoring, but excludes those fully addressed by validated payment applications.

    Payment application systems are comprehensive software platforms (often installed on merchant servers or devices) that handle full payment processing workflows, including card reading, authorization, settlement, and reporting—requiring broader PCI DSS scoping and PA-DSS validation. 

    Virtual terminal (VT) solutions, by contrast, are lightweight web-based interfaces hosted by payment providers where merchants manually key in card details for card-not-present (CNP) transactions like phone orders, minimizing merchant PCI burden to SAQ A or A-EP.

* **SAQ C-VT** is for merchants using only virtual terminal (VT) solutions provided by a PCI DSS-validated payment processor, where no electronic cardholder data storage occurs on merchant systems. It focuses on a subset of requirements like secure authentication, physical security, and transmission encryption, with fewer questions (around 79) than full SAQ C.

    Virtual terminal (VT) solutions are web-based or software payment interfaces that let merchants manually enter customer card details (via phone, email, or in-person) to process transactions without physical hardware. They appear as secure browser dashboards or apps on any internet-connected device like a laptop, tablet, or phone.

* **SAQ P2PE-HW SAQ** applies for merchants using only hardware payment terminals in a validated Point-to-Point Encryption (P2PE) solution listed by the PCI Security Standards Council (PCI SSC). Merchants qualify if all payment processing occurs via approved PCI P2PE hardware terminals, with no clear-text cardholder data accessible on any computer systems or electronic media outside these devices. The P2PE solution must encrypt data from capture to decryption, and no sensitive data is stored post-authorization.

    They encrypt card data instantly upon card read (chip, swipe, or tap), transmitting it in ciphertext directly to a decryption gateway without exposing cleartext PAN in the merchant environment—qualifying for reduced PCI SAQ P2PE-HW scope.

* **SAQ D** is the most comprehensive PCI DSS Self-Assessment Questionnaire, applicable separately to merchants and service providers that do not qualify for any other SAQ type.

    SAQ D covers all 12 PCI DSS requirements for entities that store, process, or transmit cardholder data using complex systems not fitting simpler SAQs, such as those with custom payment applications, internet-connected POS, or multi-tenant service providers. It serves as the default "catch-all" for ineligible cases like SAQ A through C-VT.

    Full scope (329 Questions) includes network security (firewalls, segmentation), data protection (encryption, masking), vulnerability management, access controls, monitoring, and policy maintenance.Involves detailed testing procedures, such as reviewing configurations, interviewing personnel, and examining logs across all system components.

**SAQ form summary**

| Payment Setup                                 | Recommended SAQ |
| --------------------------------------------- | --------------- |
| Fully outsourced CNP (no merchant page)       | SAQ A           |
| E-commerce with partial control               | SAQ A-EP        |
| Standalone dial-out terminals                 | SAQ B           |
| IP-connected POI devices                      | SAQ B-IP        |
| Internet-connected apps                       | SAQ C           |
| Virtual terminals only                        | SAQ C-VT        |
| Hardware payment terminals in a P2PE solution | SAQ P2PE HW     |
| All others/complex                            | SAQ D           |

## Non-Compliance

Failing to comply with PCI DSS can lead to severe financial penalties, reputational damage, increased risk of data breaches, and even loss of the ability to process credit card payments.

**Financial Penalties**

* Fines from payment brands (Visa, Mastercard, etc.) can range from $5,000 to $100,000 per month depending on the severity and duration of non-compliance.

* Increased transaction fees may be imposed by acquiring banks as a risk premium.

* Liability for fraud losses if a breach occurs due to non-compliance.

**Security Risks**

* Higher vulnerability to data breaches, exposing cardholder data and leading to massive cleanup costs.

* Legal liabilities from affected customers or partners, especially under data protection laws like GDPR or CCPA.

**Business Disruption**

* Loss of card processing privileges — banks or payment processors may revoke your ability to accept credit cards.

* Operational downtime during investigations and remediation efforts.

**Reputational Damage**

* Loss of customer trust due to perceived negligence in protecting sensitive data.

* Negative media coverage and long-term brand impact.

**Compliance Fallout**

* Audits and investigations triggered by non-compliance or breach.

*  Mandatory remediation plans and stricter oversight from payment processors.













