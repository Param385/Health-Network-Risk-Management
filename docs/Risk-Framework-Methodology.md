# Risk Framework Methodology

This document describes the risk management methodology applied throughout the Health Network Risk Management project. The approach draws from multiple industry-recognized frameworks to create a comprehensive, defence-in-depth risk management programme appropriate for a healthcare-style organization that processes sensitive patient, financial, and payment card data.

---

## 1. Methodology Overview

The project follows a structured, iterative risk management lifecycle:

```
Identify Assets → Identify Threats & Vulnerabilities → Assess Risk →
Select Controls → Implement Controls → Monitor & Review
```

This lifecycle is aligned to the **NIST Risk Management Framework (RMF)** and is consistent with best practices from NIST SP 800-30, ISO/IEC 27001, and the NIST Cybersecurity Framework (CSF).

---

## 2. Frameworks Applied

### 2.1 NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments

**Role in this project:** Primary risk assessment methodology.

NIST SP 800-30 provides a structured approach to identifying threats, vulnerabilities, and the likelihood and impact of adverse events. The risk matrix used in this project (likelihood × impact on a 5×5 scale) is directly derived from NIST SP 800-30 Appendix G (Likelihood of Occurrence) and Appendix H (Level of Impact).

Key applications:
- Threat source and threat event identification for HNetExchange, HNetPay, Payroll, and Accounting
- Likelihood and impact scoring for each identified risk
- Risk prioritization using the NIST SP 800-30 risk level taxonomy (Critical, High, Medium, Low)

**Healthcare relevance:** HIPAA's Security Rule (45 CFR § 164.308(a)(1)) requires covered entities to conduct a risk analysis. NIST SP 800-30 is widely recognized as an acceptable methodology for meeting this requirement.

---

### 2.2 NIST Cybersecurity Framework (CSF) v1.1 / v2.0

**Role in this project:** Organizational security posture assessment and control mapping.

The NIST CSF provides a common language for describing cybersecurity activities organized around five core functions:

| Function | Description | Application in this project |
|----------|-------------|----------------------------|
| **Identify** | Understand assets, risks, and governance | IT asset inventory, risk assessment, governance structure |
| **Protect** | Implement safeguards | Access controls, encryption, patch management, security awareness |
| **Detect** | Identify cybersecurity events | Vulnerability scanning (GVM/OpenVAS), log monitoring |
| **Respond** | Take action on detected events | Incident response procedures, risk mitigation plans |
| **Recover** | Restore capabilities | Business continuity planning, RTO/RPO definition |

The CSF was used to map controls selected in the risk mitigation plan to recognized security categories, enabling gap analysis and prioritization.

---

### 2.3 PCI DSS (Payment Card Industry Data Security Standard) v4.0

**Role in this project:** Compliance framework for HNetPay payment processing system.

PCI DSS applies directly to the HNetPay system, which processes payment card transactions. The compliance review (Lab 2) mapped the organization's existing controls against all 12 PCI DSS requirements and identified gaps.

Key requirements assessed:
- **Requirement 1 & 2:** Network segmentation and secure configuration of HNetPay environment
- **Requirement 3 & 4:** Protection of stored cardholder data and encryption of data in transit
- **Requirement 6:** Secure development practices and patch management for payment applications
- **Requirement 7 & 8:** Access control and strong authentication (MFA) for cardholder data environment
- **Requirement 10 & 11:** Audit logging, monitoring, and regular vulnerability scanning
- **Requirement 12:** Organizational information security policy and risk management programme

**Healthcare relevance:** Healthcare organizations frequently handle payment card transactions, making PCI DSS compliance a dual regulatory obligation alongside HIPAA.

---

### 2.4 HIPAA Security Rule (45 CFR Part 164, Subpart C)

**Role in this project:** Regulatory compliance baseline for healthcare data protection.

Although the organizational scenario is fictional, it mirrors the regulatory environment of a real healthcare organization. The HIPAA Security Rule imposes requirements for protecting electronic Protected Health Information (ePHI).

Key HIPAA Security Rule standards applied:
- **§ 164.308(a)(1) — Risk Analysis:** Conduct an accurate and thorough assessment of potential risks and vulnerabilities to ePHI (addressed in Lab 4: Risk Assessment)
- **§ 164.308(a)(1)(ii)(B) — Risk Management:** Implement security measures to reduce risks to a reasonable and appropriate level (addressed in Lab 7: Risk Mitigation Planning)
- **§ 164.308(a)(7) — Contingency Plan:** Establish policies for responding to emergencies (addressed in Lab 8: Business Impact Analysis)
- **§ 164.312(a)(1) — Access Control:** Implement technical policies to allow only authorized access to ePHI (addressed through access control recommendations in the risk register)

**Relevance to this project:** The HNetExchange secure messaging system handles sensitive organizational communications that, in a real healthcare setting, would include ePHI subject to HIPAA protections.

---

### 2.5 ISO/IEC 27001:2022 — Information Security Management Systems

**Role in this project:** Management system framework for sustained risk governance.

ISO/IEC 27001 provides requirements for establishing, implementing, maintaining, and continually improving an Information Security Management System (ISMS). While NIST SP 800-30 drives the risk assessment methodology, ISO 27001 provides the management system context that ensures risk management is embedded into organizational governance.

Key ISO 27001 elements applied:
- **Clause 4.1 & 4.2:** Understanding the organization's context and the needs of interested parties (regulators, patients, payment card brands)
- **Clause 6.1:** Risk assessment and risk treatment planning (aligned to the risk register and mitigation plan)
- **Clause 6.1.3:** Risk treatment — selecting controls from Annex A and documenting the Statement of Applicability
- **Annex A Control Categories applied:** A.5 (Organizational), A.6 (People), A.7 (Physical), A.8 (Technological)

**Healthcare relevance:** ISO 27001 certification is increasingly recognized by healthcare regulators and business partners as evidence of a mature information security management programme.

---

## 3. Framework Integration Summary

The following table shows how the five frameworks complement each other in this project:

| Activity | NIST SP 800-30 | NIST CSF | PCI DSS | HIPAA | ISO 27001 |
|----------|---------------|---------|---------|-------|-----------|
| Asset Inventory | ✅ | ID.AM | Req. 2, 9 | Addressable | Annex A 5.9 |
| Risk Assessment | ✅ Primary | ID.RA | Req. 12.2 | § 164.308(a)(1) | Clause 6.1.2 |
| Vulnerability Management | ✅ | ID.RA, PR.IP | Req. 6, 11 | Addressable | Annex A 8.8 |
| Access Control | Supporting | PR.AC | Req. 7, 8 | § 164.312(a)(1) | Annex A 5.15 |
| Risk Treatment / Mitigation | ✅ | PR, RS | Req. 6, 12 | § 164.308(a)(1)(ii)(B) | Clause 6.1.3 |
| Business Continuity | Supporting | RC | Req. 12.10 | § 164.308(a)(7) | Annex A 5.29 |
| Compliance Monitoring | Supporting | DE.CM | Req. 10, 11 | § 164.308(a)(1) | Clause 9.1 |

---

## 4. Risk Scoring Methodology

Risks in this project are scored using the formula:

**Risk Level = Likelihood × Impact**

Both Likelihood and Impact are rated on a 1–5 scale:

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 1 | Very Low / Rare | Negligible |
| 2 | Low / Unlikely | Minor |
| 3 | Medium / Possible | Moderate |
| 4 | High / Likely | Major |
| 5 | Very High / Almost Certain | Catastrophic |

Resulting risk levels:
- **Critical (20–25):** Immediate action required — escalate to senior leadership
- **High (12–19):** Remediation required within 30 days
- **Medium (6–11):** Remediation required within 90 days
- **Low (1–5):** Accept or monitor; review at next risk cycle

---

## 5. References

- NIST SP 800-30 Rev. 1: https://csrc.nist.gov/publications/detail/sp/800-30/rev-1/final
- NIST Cybersecurity Framework: https://www.nist.gov/cyberframework
- PCI DSS v4.0: https://www.pcisecuritystandards.org/
- HIPAA Security Rule: https://www.hhs.gov/hipaa/for-professionals/security/
- ISO/IEC 27001:2022: https://www.iso.org/standard/82875.html
- NIST SP 800-53 Rev. 5: https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final
