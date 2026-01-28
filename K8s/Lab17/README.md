# Lab 17: Pod Resource Management (Requests & Limits)

## Objective

The goal of this lab is to implement Resource Management for the Node.js application. By defining CPU and Memory boundaries, we ensure that the application has the necessary resources to run (Requests) while preventing it from consuming excessive cluster resources (Limits).


## Implementation Evidence

### Resource Configuration

The Node.js Deployment was updated to include specific resource constraints for the nodejs-container:

Requests (Minimum Guaranteed): 1 vCPU and 1Gi Memory.

Limits (Hard Ceiling): 2 vCPUs and 2Gi Memory.

![Task Proof](./screenshots/varify.png)

---
