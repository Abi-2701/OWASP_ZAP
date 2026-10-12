

### 1. Check Docker Version
```bash
docker --version
```
Displays the installed Docker version.

### 2. Check Docker Service
```bash
systemctl status docker
```
Shows whether the Docker service is running.

### 3. List Docker Containers
```bash
docker ps -a
```
Lists running and stopped containers, including the Juice Shop container.

### 4. Check Local Juice Shop Response
```bash
curl -I http://localhost:3000
```
Checks whether the local Juice Shop web server responds to an HTTP request.

### 5. Open Juice Shop
```text
http://localhost:3000
```
Enter this URL in the browser to access the local test application.

### 6. ZAP Proxy Address
```text
127.0.0.1:8080
```
This is the proxy address configured for the browser during the assessment.
