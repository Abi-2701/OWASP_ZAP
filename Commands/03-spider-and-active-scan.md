
### 1. Select the Target
In OWASP ZAP, select the local Juice Shop target:

```text
http://localhost:3000
```

### 2. Run Traditional Spider
1. Open the **Sites** panel.
2. Right-click the Juice Shop target.
3. Select **Attack → Spider**.
4. Start the scan and wait for it to complete.

### 3. Review Discovered URLs
Check the **Spider** tab and **Sites** tree for discovered paths.

### 4. Run Active Scan
1. Right-click the Juice Shop target.
2. Select **Attack → Active Scan**.
3. Confirm that the target is the local test application.
4. Start the scan and wait for completion.

### 5. Review Scan Alerts
Open the **Alerts** tab and review the reported risk levels, confidence levels, affected URLs, and evidence.

### 6. Validate Findings
Treat scanner alerts as potential findings until manually validated. Do not assume every alert is an exploitable vulnerability.
