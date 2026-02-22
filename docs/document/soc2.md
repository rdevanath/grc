---
tags:
  - Frameworks & Standards
---

# SOC 2 (Systems & Organization Controls)

## Introduction
The report is created and validated by _third-party auditors_, which is built to provide _independent assurance_ and verify that an organization is following specific best practices for business functions outsourced. 

SOC 2 reporting is based on **SSAE 18 attestation standard** which is a general framework for CPAs (Certified Public Accountants) to perform attestation engagements — where an independent auditor examines and reports on subject matter other than traditional financial statements.

> SSAE 18 (in 2017) which has superseded the AT 101 (previous standard), but the concepts from AT 101 still underpin SOC 2 reporting. AT 101 was not industry-specific framework (financial & non-financial) but it could be used for security, privacy, compliance, or other assurance topics.

The SOC 2 controls are not fixed checklist because the framework is principles-based (COSO) rather than prescriptive. Controls are derived from the five Trust Services Criteria (TSC), which are defined by the American Institute of Certified Public Accountants (AICPA).

!!! success "The 5 Trust Services criterias"
    Security, Availability, Processing integrity, Confidentiality, Privacy. Security controls testing is mandatory, while the rest (availability, processing integrity, confidentiality, and privacy) are optional.

Report Type

* Type I: Design of controls at a specific point in time.

* Type II: Design and operating effectiveness of controls over a period (typically 6–12 months).

## Stakeholders

### **Service Auditor** 

* An independent CPA firm or audit professional who performs the SOC 2 examination.

* They assess whether the service organization’s controls meet the Trust Services Criteria. They issue the final SOC 2 report, which includes their opinion on the design and/or operating effectiveness of control.

### **Service Organization**

* This is the company being audited in a SOC 2 report.

* It provides services to other businesses (user entities), often involving data processing, cloud hosting, SaaS platforms, or IT infrastructure.

### **Sub-Service Organization**

* A third-party vendor that the service organization relies on to deliver part of its service.

* Example: A SaaS company using AWS for cloud hosting — AWS is the sub-service organization.

There are two ways sub-service organization are handled in SOC 2:

* **Inclusive Method:** Their controls are included and tested in the SOC 2 report.

* **Carve-Out Method:** Their controls are excluded, but the service organization must describe what’s outsourced and what risks are involved.

### **User Entity**

* A client or customer of the service organization.

* They rely on the service organization’s systems and controls to protect their data and operations.

* Example: A bank using a third-party document management system.

### **CUECs (Complementary User Entity Controls)**

* These are controls that the user entity is responsible for.

* The service organization assumes these controls are in place at the user entity to ensure the overall system works securely.

* Example: If a service organization provides secure file sharing, the user entity must revoke access for terminated employees — the service org can’t do that on its own.

SOC 2 reports list CUECs so user entities know what they must do to uphold the shared security model.

## Report Components

A SOC 2 report has five main parts, focusing on an organization's security controls related to one or more of the AICPA's Trust Services Criteria. The sections provide details on the management's view of the audit, the auditor's official opinion, a description of the system under review, the testing results, and other information.

### Section I: Management's assertion

This section is drafted by the audited organization's management and outlines:

* A summary of the services and systems covered by the audit.

* A formal statement that the system description is presented fairly and that the controls were suitably designed.

* A declaration of the service commitments and requirements addressed in the report.

* Confirmation that management provided all relevant information to the auditor.

### Section II: Independent Service Auditor's report

This is the auditor's summary and opinion on the audit and is often the most important section for users of the report. It includes: 

* The scope and timeframe of the audit.

* A description of the responsibilities of both management and the auditor. 

* The auditor's opinion: The final grade on the audit. Opinions can be:

    * **Unqualified:** The highest assurance, meaning controls are designed and operating effectively.

    * **Qualified:** Indicates that the controls have some deficiencies but are generally effective.

    * **Adverse:** A failure of the audit, indicating that controls are not effective and the system is unreliable.

    * **Disclaimer of Opinion:** The auditor was unable to form an opinion due to a lack of evidence.

### Section III: System description

This part, written by the service organization, provides a detailed overview of the system being audited. It is often the longest section and typically includes: 

* **System components:** The infrastructure, software, procedures, people, and data that are part of the system.

* **System boundaries:** What is and is not included in the audit's scope.

* **Incidents and changes:** Any system incidents or significant changes that occurred during the audit period.

* **Controls and processes:** An explanation of the relevant security policies, risk management, and procedures.

### Section IV: Applicable Trust Services Criteria and test results

This section details how the organization addresses each of the applicable Trust Services Criteria (TSC). 

* **Trust Services Criteria:** All SOC 2 audits must cover the Security criterion, with other TSCs like Availability, Confidentiality, Processing Integrity, and Privacy being optional.

* **Controls and tests:** It lists the controls put in place by the organization for each criterion, the test procedures the auditor performed, and the results of that testing. For a Type 2 report, this section also shows whether the controls operated effectively over time and notes any exceptions. 

### Section V: Other information (optional)

In this final, non-audited section, management can provide additional context. It may be used to: 

* Explain the company's response to any exceptions or issues found by the auditor.

* Detail future plans for system improvements.

* Offer additional details about the company's control environment. 

## SOC 3:

* A public-facing version of a SOC 2 Type II that does not include confidential information.

* Provides a high-level summary for general customers without compromising or revealing details on the internal controls.

* Usually only utilized by organizations that have conducted many SOC reports in the past and have a robust and mature control environment.