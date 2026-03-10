# Risk Register — Health Network Organization

This risk register documents identified information security risks for the healthcare organization scenario. Risks are assessed using a qualitative likelihood × impact methodology aligned to NIST SP 800-30. Each risk entry includes a mitigation strategy and current treatment status.

## Risk Rating Scale

| Rating | Likelihood | Impact |
|--------|-----------|--------|
| 1 – Very Low | Rare (< 10% probability) | Negligible operational impact |
| 2 – Low | Unlikely (10–30%) | Minor impact, easily recoverable |
| 3 – Medium | Possible (30–50%) | Moderate impact, some disruption |
| 4 – High | Likely (50–70%) | Significant impact, major disruption |
| 5 – Very High | Almost Certain (> 70%) | Severe/catastrophic impact |

**Risk Level = Likelihood × Impact** (1–25 scale)
- **Critical (20–25):** Immediate action required
- **High (12–19):** Action required within 30 days
- **Medium (6–11):** Action required within 90 days
- **Low (1–5):** Monitor and review at next cycle

---

## Risk Register

| Risk ID | Risk Description | Asset / System | Likelihood | Impact | Risk Level | Mitigation Strategy | Status |
|---------|-----------------|----------------|-----------|--------|------------|--------------------|---------| 
| R-001 | Unauthorized access to sensitive patient messaging due to weak authentication on HNetExchange | HNetExchange | 4 – High | 5 – Very High | **Critical (20)** | Implement multi-factor authentication (MFA); enforce least-privilege access controls; conduct quarterly access reviews | In Progress |
| R-002 | Payment card data breach via HNetPay due to insufficient network segmentation and unencrypted cardholder data | HNetPay | 3 – Medium | 5 – Very High | **High (15)** | Segment HNetPay into a dedicated PCI DSS-compliant network zone; enforce TLS 1.2+ for all cardholder data in transit; implement tokenization | Open |
| R-003 | Payroll data exposure caused by excessive employee access privileges and lack of role-based access controls | Payroll System | 4 – High | 4 – High | **High (16)** | Implement role-based access control (RBAC); remove standing administrative access; enable audit logging for all payroll data access | Open |
| R-004 | Ransomware infection spreading across internal network due to unpatched operating system vulnerabilities | All Internal Systems | 4 – High | 5 – Very High | **Critical (20)** | Deploy a vulnerability management programme with 30-day patch SLA for High/Critical CVEs; implement network micro-segmentation; maintain tested offline backups | In Progress |
| R-005 | SQL injection attack against the Accounting system web application exposing financial records | Accounting System | 3 – Medium | 4 – High | **High (12)** | Implement a Web Application Firewall (WAF); conduct SAST/DAST application security testing; parameterize all database queries | Open |
| R-006 | Insider threat — malicious or negligent employee exfiltrating HR or financial data via removable media | Payroll / Accounting | 2 – Low | 5 – Very High | **High (10)** | Enforce DLP (Data Loss Prevention) controls; disable unauthorized USB ports via endpoint policy; implement user behaviour analytics (UBA) | Open |
| R-007 | Denial-of-service attack disrupting HNetExchange availability and impacting secure clinical messaging | HNetExchange | 3 – Medium | 4 – High | **High (12)** | Deploy DDoS mitigation and rate-limiting at the network perimeter; define and test RTO/RPO for HNetExchange in the BCP | Open |
| R-008 | Misconfigured FTP server exposing internal files to unauthenticated external access | Network / File Servers | 5 – Very High | 3 – Medium | **High (15)** | Disable anonymous FTP; migrate file transfer to SFTP with key-based authentication; conduct configuration baseline review | Remediated |

---

## Notes

- Risk levels are recalculated after each treatment cycle to reflect residual risk.
- This register should be reviewed at a minimum quarterly or following any significant change to the environment.
- Owner: Information Security Team / Risk Manager
- Last Reviewed: March 2026

> **Related documents:** [Risk Framework Methodology](../docs/Risk-Framework-Methodology.md) | [Final Risk Management Report](../Reports/final%20report.docx)
