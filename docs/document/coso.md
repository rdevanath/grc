---
tags:
  - Frameworks & Standards
---

# COSO Framework (Internal Control – Integrated Framework)

* Developed by the Committee of Sponsoring Organizations of the Treadway Commission (COSO). It was first introduced in 1992 and updated in 2013.

* Provides a broad, principles-based framework for designing, implementing, and evaluating internal controls.

* Built around 5 components (Control Environment, Risk Assessment, Control Activities, Information & Communication, Monitoring) and 17 principles.

Widely used for financial reporting, compliance, and enterprise risk management (e.g., SOX compliance).

## Relationship between COSO Framework and Common Criteria

### 1. The five Core Components of COSO

* **Control Environment** – Ethical tone, governance, and accountability culture.

* **Control Activities** – Policies and procedures to mitigate risks.

* **Risk Assessment** – Identifying and analysing risks to objectives.

* **Information & Communication** – Sharing relevant, timely information internally and externally.

* **Monitoring Activities** – Ongoing evaluation of control effectiveness.

### 2. Common Criteria (SOC 2 – Trust Services Criteria)

* Defined by the AICPA for System and Organization Controls (SOC 2) reporting.

* Focuses on security, availability, processing integrity, confidentiality, and privacy.

* The Common Criteria are the baseline requirements that apply across all Trust Services Categories (TSC) and then and then each category (Security, Confidentiality, Processing Integrity, Availability & Privacy) has additional criteria layered on top.

* They are more specific to IT systems, service organizations, and SaaS providers.

### 3. How They Connect

* The AICPA Trust Services Criteria (Common Criteria) are explicitly aligned with COSO.

* COSO provides the foundational internal control principles, while the Common Criteria adapt those principles to IT and service organization contexts.

* For example: 

    * COSO Principle: Control Environment → Common Criteria: Commitment to integrity, ethical values, and competence.

    * COSO Principle: Risk Assessment → Common Criteria: Identifying and assessing risks to system objectives.

## Mandatory: Common Criteria (CC) for TSC

**CC1: Control Environment:** Defines the organization's ethical values, integrity, and commitment to oversight.

**CC2: Communication and Information:** Addresses how organization communicate policies, procedures, and responsibilities to staff and external parties.

**CC3: Risk Assessment:** Covers how organization identifies and analyzes risks to its objectives.

**CC4: Monitoring Activities:** Ensures org has procedures to track and evaluate the effectiveness of controls over time.

**CC5: Control Activities:** Refers to the specific controls and technologies you implement to mitigate risks. 

**CC6: Logical and Physical Access Controls:** Governs how your organization restricts logical (e.g., user credentials) and physical (e.g., server rooms) access to its systems and assets.

**CC7: System Operations:** Focuses on detecting and responding to system issues, including incident management and vulnerability monitoring.

**CC8: Change Management:** Covers the authorization, testing, and implementation of system changes.

**CC9: Risk Mitigation:** Deals with mitigating risks arising from business partners, vendors, and internal changes.

## SOC 2 Common Criteria – Sub-Classifications

### CC1: Control Environment

Focus: Governance, ethics, accountability, competence.

??? note "Sub-classifications include:"

    CC1.1 – Commitment to integrity and ethical values

    CC1.2 – Board independence and oversight

    CC1.3 – Establishes structure, authority, and responsibility

    CC1.4 – Commitment to competence

    CC1.5 – Accountability for internal control responsibilities

### CC2: Communication & Information

Focus: Internal and external communication of policies and responsibilities.

??? note "Sub-classifications include:"

    CC2.1 – Uses relevant, quality information

    CC2.2 – Communicates internally

    CC2.3 – Communicates externally

### CC3: Risk Assessment

Focus: Identifying and analyzing risks, including fraud and change.

??? note "Sub-classifications include:"

    CC3.1 – Specifies suitable objectives

    CC3.2 – Identifies and analyzes risks

    CC3.3 – Assesses fraud risk

    CC3.4 – Identifies and analyzes significant change

### CC4: Monitoring of Controls

Focus: Ongoing and separate evaluations of control effectiveness.

??? note "Sub-classifications include:"

    CC4.1 – Conducts ongoing and/or separate evaluations

    CC4.2 – Evaluates and communicates deficiencies

### CC5: Control Activities

Focus: Policies, procedures, and IT general controls.

??? note "Sub-classifications include:"

    CC5.1 – Selects and develops control activities

    CC5.2 – Selects and develops general controls over technology

    CC5.3 – Deploys control activities through policies and procedures

### CC6: Logical & Physical Access Controls

Focus: Restricting access to systems, data, and facilities.

??? note "Sub-classifications include:"

    CC6.1 – Logical access security software, infrastructure, and architectures

    CC6.2 – Registration and authorization of new/internal users

    CC6.3 – Removal of access when no longer authorized

    CC6.4 – Authentication mechanisms (e.g., MFA)

    CC6.5 – Restricting physical access to facilities

    CC6.6 – Securing workstations, laptops, and mobile devices

    CC6.7 – Encryption and protection of data in transit and at rest

### CC7: System Operations

Focus: Managing operations, detecting anomalies, incident response.

??? note "Sub-classifications include:"

    CC7.1 – Detects and monitors system components

    CC7.2 – Identifies and logs anomalies

    CC7.3 – Assesses security events and incidents

    CC7.4 – Responds to and mitigates incidents

    CC7.5 – Recovers from incidents and resumes operations

### CC8: Change Management

Focus: Controlling changes to infrastructure, applications, and data.

??? note "Sub-classifications include:"

    CC8.1 – Authorizes and documents changes

    CC8.2 – Tests, approves, and implements changes

    CC8.3 – Restricts emergency changes and documents them

    CC8.4 – Maintains version control and rollback procedures

### CC9: Risk Mitigation

Focus: Managing risks from vendors, partners, and external parties.

??? note "Sub-classifications include:"

    CC9.1 – Identifies and assesses risks from business partners and vendors

    CC9.2 – Implements risk mitigation strategies (e.g., contracts, monitoring)
    
    CC9.3 – Reviews and updates risk mitigation activities periodically

**Key Takeaway**

  * **CC1–CC5** = Broad governance and internal control principles (aligned with COSO).

  * **CC6–CC9** = IT and operational safeguards (access, operations, change, vendor risk).

## AICPA Trust Services Criteria 
Additional criteria layered on top of each TSC (Availability, Confidentiality, Processing Integrity, Privacy), also referred as the AICPA Trust Services Criteria .

### Availability

* Objective: Systems are available for operation and use as committed.
* Criteria:
    * Common Criteria (CC1–CC9)
    * Additional Availability Criteria (A-Series):
          *  A1.1: Availability commitments (e.g., uptime, SLAs)
          *  A1.2: Backup and disaster recovery procedures
          *  A1.3: Business continuity planning
      
### Confidentiality

* Objective: Information designated as confidential is protected.
* Criteria: 
    * Common Criteria (CC1–CC9)
    * Additional Confidentiality Criteria (C-Series):
          * C1.1: Identification and classification of confidential information
          * C1.2: Protection of confidential information during storage, transmission, and disposal.

### Processing Integrity

* Objective: System processing is complete, valid, accurate, timely, and authorized.
* Criteria: 
    * Common Criteria (CC1–CC9)
    * Additional Processing Integrity Criteria (PI-Series):
         * PI1.1: Input data validation
         * PI1.2: Processing accuracy and completeness
         * PI1.3: Output accuracy and completeness
         * PI1.4: Timeliness of processing
         * PI1.5: Authorization of processing activities

### Privacy

* Objective: Personal information is collected, used, retained, disclosed, and disposed of in line with commitments and privacy principles (adapted from GAPP).
* Note: Useful when Service Organization is a data controller.
* Criteria: 
    * Common Criteria (CC1–CC9)
    * Additional Privacy Criteria (P-Series):
         * P1.1: Notice and communication of privacy practices
         * P1.2: Choice and consent
         * P1.3: Collection of personal information
         * P1.4: Use, retention, and disposal
         * P1.5: Access to personal information
         * P1.6: Disclosure to third parties
         * P1.7: Security for privacy (overlaps with CC6)
         * P1.8: Quality and monitoring of personal information
