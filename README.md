# Project 16: OWASP ZAP – Web Application Vulnerability Assessment

## 1. Project Overview

This project demonstrates a web application security assessment using OWASP ZAP (Zed Attack Proxy) against a locally hosted OWASP Juice Shop application.

The assessment covers browser traffic inspection, application resource discovery, automated security scanning, alert analysis, evidence collection, and HTML report generation. The objective is to understand how web application testing tools identify potential security weaknesses and how their results can be documented for further investigation and remediation.

**Project Type:** Web Application Security Testing  
**Security Tool:** OWASP ZAP 2.17.0  
**Target:** Local OWASP Juice Shop  
**Environment:** Kali Linux with Docker

## 2. Project Objectives

- Configure OWASP ZAP as a browser proxy.
- Capture and inspect HTTP/HTTPS application traffic.
- Discover application resources using the Traditional Spider.
- Perform an automated Active Scan against the local target.
- Review alerts and their reported risk levels.
- Capture evidence to support the assessment.
- Generate an HTML report and document recommended remediation.

## 3. Tools and Technologies

| Component | Details |
|---|---|
| Operating System | Kali Linux |
| Security Testing Tool | OWASP ZAP 2.17.0 |
| Target Application | OWASP Juice Shop |
| Deployment | Local Docker environment |
| ZAP Proxy | `127.0.0.1:8080` |
| Target URL | `http://localhost:3000` |
| Report Format | HTML |

## 4. Architecture and Workflow

The browser accesses the local Juice Shop application through the ZAP proxy. ZAP inspects the application traffic, discovers resources, and performs automated security checks. The resulting alerts are reviewed and recorded in the assessment report.

**Architecture diagram:** [View the project architecture](architecture/architecture.md)

### Workflow

1. Start the local OWASP Juice Shop application.
2. Configure the browser to route traffic through the ZAP proxy.
3. Browse the application and verify captured requests in ZAP History.
4. Run the Traditional Spider to discover application resources.
5. Execute the Active Scan against the local target.
6. Review alerts and their risk classifications.
7. Preserve screenshots and generate the HTML report.
8. Document observations, limitations, and remediation recommendations.

## 5. Evidence and Screenshot Analysis

The `evidence/` directory contains eight screenshots captured during the assessment.

| Evidence File | What It Demonstrates |
|---|---|
| `01-juice-shop-application.png` | The local Juice Shop target application was accessible. |
| `02-zap-alerts-overview.png` | Overview of alerts reported by OWASP ZAP. |
| `03-cors-misconfiguration.png` | The cross-domain configuration alert that requires validation. |
| `04-timestamp-disclosure.png` | The Unix timestamp disclosure alert. |
| `05-suspicious-comments.png` | The suspicious-comments information disclosure alert. |
| `06-modern-web-application.png` | The modern web application informational alert. |
| `07-zap-site-tree.png` | Application resources discovered during testing. |
| `08-automated-scan-completed.png` | Evidence of the automated scan completion. |

**Browse all evidence:** [Open the evidence directory](evidence/)

The screenshots provide visual evidence of the test environment, scan activity, and selected alert details. They should be interpreted alongside the HTML report rather than treated as independent proof of exploitability.

## 6. Scan Results Summary

The generated ZAP report contains six distinct alert types across Medium, Low, and Informational risk categories.

| Alert Type | Reported Risk | Observation and Recommended Action |
|---|---|---|
| Content Security Policy (CSP) Header Not Set | Medium | Review the affected response and implement an appropriate Content Security Policy where applicable. |
| Cross-Domain Misconfiguration | Medium | Review the CORS configuration and restrict allowed origins when required. |
| Timestamp Disclosure – Unix | Low | Determine whether the timestamp exposes meaningful implementation information; reduce unnecessary disclosure if appropriate. |
| Information Disclosure – Suspicious Comments | Informational | Inspect the flagged client-side content and remove sensitive comments if any are found. |
| Modern Web Application | Informational | Technology or application behavior detection; not necessarily a security weakness. |
| User Agent Fuzzer | Informational | Review the scanner details and validate whether any meaningful issue exists. |

### Interpretation of Findings

These entries represent automated scanner alerts, not six confirmed exploitable vulnerabilities. Their practical impact depends on the affected response, application behavior, configuration, and manual validation.

The Cross-Domain Misconfiguration alert, for example, should be assessed in context; a wildcard origin alone does not establish that sensitive information can be accessed. Similarly, a timestamp or suspicious comment does not automatically prove sensitive information exposure.

**Detailed findings:** [Read findings.md](findings.md)

## 7. HTML Assessment Report

The HTML report provides a consolidated view of the scan summary, alert categories, reported risk levels, and available alert details.

**Report file:** [`reports/2026-10-12-ZAP-Report-.html`](reports/2026-10-12-ZAP-Report-.html)

The report was generated using OWASP ZAP 2.17.0 against the local target `http://localhost:3000`.

The report should be used alongside the screenshots and detailed findings to review the scanner output. Any remediation should be followed by appropriate validation to determine whether the issue has been resolved.

## 8. Recommendations

- Define and test an appropriate Content Security Policy.
- Review cross-origin resource sharing rules and allow only required origins.
- Inspect flagged responses and client-side files for unnecessary information disclosure.
- Validate scanner alerts manually before assigning final severity.
- Re-test relevant behavior after implementing security fixes.
- Keep assessment evidence and reports organized for future review.

## 9. Limitations

- Testing was restricted to a locally hosted OWASP Juice Shop instance.
- Automated scanning can produce false positives and context-dependent findings.
- Informational alerts are not necessarily vulnerabilities.
- The assessment does not establish the security status of external or production applications.
- Manual validation and remediation testing are required for stronger conclusions.

## 10. Conclusion

This project provided practical experience with configuring OWASP ZAP, inspecting browser traffic, discovering web application resources, performing automated security scans, interpreting alerts, collecting evidence, and generating an HTML assessment report.

The organized architecture documentation, screenshots, scan report, and findings provide a record of the assessment workflow and a foundation for further manual testing and security hardening.

## 11. Disclaimer

This assessment was conducted in a controlled local lab against an intentionally vulnerable test application for educational and authorized security-testing purposes only.

