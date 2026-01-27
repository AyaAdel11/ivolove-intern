# Lab 9: Full-Stack Containerization with Docker Compose

##  Project Description
In this lab, I successfully containerized a Full-Stack application consisting of a Node.js backend and a MySQL database. Instead of managing containers individually, I used Docker Compose to orchestrate the entire stack, manage networking, and ensure data persistence.

## Architecture & Components
App Service: A Node.js application built from a custom Dockerfile using node:18-alpine.

Database Service: A MySQL:8.0 container initialized with a database named ivolve.

Networking: Automatic service discovery (The App communicates with the DB using the service name db).

Persistence: Used a Docker Named Volume (db_data) to protect database data from being lost when containers are removed.

---

## Execution Steps
### 1. Orchestrating the Stack
Run the following command to build the app image and start both services in detached mode:

```bash
docker-compose up -d
```
![Verification](../screenshots/compose-up.png)

### 2. Verification & Health Checks
I verified the application's status and its connection to the database using the following endpoints:

Health Check: curl localhost:3000/health (Checks if the server is running).

Ready Check: curl localhost:3000/ready (Checks if the DB connection is established).

![Verification](../screenshots/varify-everything.png)

### 3. Monitoring Logs
Checked the access logs generated inside the container to monitor incoming requests:

```bash
docker-compose exec app cat /app/logs/access.log
```

![Verification](../screenshots/varify-everything.png)

### 4. Push the Docker image into your DockerHub

![Verification](../screenshots/push.png)

---

## Key Takeaways
Learned how to use Environment Variables to securely pass DB credentials.

Understood the importance of depends_on to control service startup order.

Mastered Data Persistence using Docker Volumes.

Learned how to tag and push custom images to Docker Hub.
