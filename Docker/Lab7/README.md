# Lab 7: Docker Volumes & Bind Mounts

## Project Overview
This lab demonstrates the difference between **Docker Volumes** (managed by Docker) and **Bind Mounts** (managed by the host user) using an Nginx web server.

## Objectives
1. Persist Nginx logs using a named volume.
2. Serve custom HTML content using a bind mount.
3. Observe real-time updates via bind mounts.

---

## Steps to Reproduce

### 1. Storage Setup
* **Create Volume:** `docker volume create nginx_logs`
* **Create Bind Directory:** `mkdir -p nginx-bind/html`
* **Create HTML File:** ```bash
  echo "<h1>Hello from Bind Mount</h1>" > nginx-bind/html/index.html
```

### 2. Run Container

```bash
docker run -d --name nginx-lab7 \
  -p 8085:80 \
  -v nginx_logs:/var/log/nginx \
  -v $(pwd)/nginx-bind/html:/usr/share/nginx/html \
  nginx
```
### 3. Verification
Initial Test: curl localhost:8085

Update Content: Change index.html on the host and run curl again to see immediate changes without restart.

Inspect Logs: ```bash docker run --rm -v nginx_logs:/logs busybox ls /logs ```

### 4. Cleanup

```bash 
docker rm -f nginx-lab7
docker volume rm nginx_logs
```
![image](../Lab5/screenshots/lab7.png)

---
