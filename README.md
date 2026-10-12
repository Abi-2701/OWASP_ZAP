# OWASP ZAP – Web Application Vulnerability Assessment

## 1. Project Overview
This project performs a security assessment of a locally hosted OWASP Juice Shop web application using OWASP ZAP (Zed Attack Proxy). The objective is to identify potential web security weaknesses, review scanner alerts, and document remediation recommendations in a controlled lab environment.

## 2. Objectives
- Configure OWASP ZAP to inspect browser traffic.
- Discover application endpoints using the traditional Spider.
- Perform an automated Active Scan against the local test application.
- Review and classify security alerts by risk level.
- Generate an HTML assessment report and document recommended mitigations.

## 3. Lab Environment

| Component | Details |
|---|---|
| Security testing tool | OWASP ZAP 2.17.0 |
| Operating system | Kali Linux |
| Target application | OWASP Juice Shop |
| Target URL | http://localhost:3000 |
| Proxy address | 127.0.0.1:8080 |
| Deployment | Local lab using Docker |

## 4. Methodology
1. Prepared the Kali Linux testing environment.
2. Started the OWASP Juice Shop application locally.
3. Configured the browser to route HTTP/HTTPS traffic through the ZAP proxy.
4. Browsed the target application and confirmed that requests appeared in ZAP History.
5. Ran the traditional Spider to discover application paths.
6. Performed an Active Scan against the local Juice Shop target.
7. Reviewed the resulting alerts and generated an HTML report.

## 5. Scan Findings

The scan reported six alert types. These are automated scanner findings and require appropriate validation before being treated as confirmed vulnerabilities.

| Alert | Reported Risk | Recommended Action |
|---|---|---|
| Content Security Policy (CSP) Header Not Set | Medium | Define and test a suitable Content Security Policy. |
| Cross-Domain Misconfiguration | Medium | Restrict cross-origin access to trusted origins where required. |
| Timestamp Disclosure – Unix | Low | Review whether timestamps expose unnecessary implementation information. |
| Information Disclosure – Suspicious Comments | Informational | Review comments and client-side files for unintended sensitive information. |
| Modern Web Application | Informational | Informational technology-detection alert; review in context. |
| User Agent Fuzzer | Informational | Review the alert details and validate whether any meaningful security issue exists. |

## 6. Report and Evidence
The generated HTML report is stored as:

`2026-10-12-ZAP-Report-.html`

The report contains the scan summary and alert details. Findings should be manually validated, and the report evidence should be reviewed before drawing conclusions about exploitability.

## 7. Limitations
- Testing was restricted to the locally hosted OWASP Juice Shop application.
- Automated scan results may include false positives or findings with limited practical impact.
- The results do not establish that every alert is exploitable.
- No conclusions are made about production systems or external targets.

## 8. Conclusion
The assessment demonstrated how OWASP ZAP can be used to proxy application traffic, discover endpoints, run automated security checks, and generate a vulnerability assessment report. The alerts provide a starting point for manual verification and security hardening.

## 9. Disclaimer
This assessment was conducted in a controlled local lab against an intentionally vulnerable test application for educational purposes.
