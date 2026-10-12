
### 1. Launch OWASP ZAP
Open OWASP ZAP from the Kali Linux application menu.

### 2. Verify ZAP Proxy Address
```text
127.0.0.1:8080
```

### 3. Configure Browser Proxy
Set the browser's HTTP and HTTPS proxy to:

```text
Host: 127.0.0.1
Port: 8080
```

### 4. Open the Test Application
```text
http://localhost:3000
```

### 5. Verify the Target in ZAP
Check the **Sites** panel to confirm that the Juice Shop target appears after browsing through the proxy.

### 6. Review Captured Requests
Open the **History** tab and check the HTTP requests and responses captured by ZAP.
