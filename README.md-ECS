
---

### Part 2: Amazon ECS (Elastic Container Service - Fargate)

```markdown
# Amazon ECS Fargate Deployment
```
### Objective

Deploy Docker images stored in ECR using ECS Fargate.

---

### ECS Components

#### Cluster

Logical grouping of services and tasks.

#### Task Definition

Blueprint that defines:

- Container Image
- CPU
- Memory
- Ports

#### Service

Maintains desired number of running tasks.

#### Task

Running instance of a container.

---

#### Step 1: Create ECS Cluster

1. Open ECS Console
2. Clusters
3. Create Cluster

Configuration:

```text
Infrastructure : AWS Fargate
Cluster Name   : beauty-cluster


Step 2: Create Task Definition
ECS → Task Definitions
Create New Task Definition

Configuration:

Launch Type : Fargate
CPU         : 0.5 vCPU
Memory      : 1 GB
```

### Step 3: Add Container

Container Details:

Container Name : beauty-container
Image URI      : ECR Image URI

Example:

800557027867.dkr.ecr.us-east-1.amazonaws.com/private-beauty:latest

Port Mapping:

80

Click Create.

### Step 4: Create ECS Service

Cluster → Services → Create

Configuration:

Launch Type      : Fargate
Task Definition  : beauty-task
Desired Count    : 1 or 2

Networking:

Assign Public IP : ENABLED

Keep remaining settings default.

Click Create Service.

### Step 5: Verify Deployment

Navigate:

Cluster → Services

Status should be:

Active

Navigate:

Cluster → Tasks

Task Status:

Running
<img width="1863" height="902" alt="Screenshot 2026-06-11 222948" src="https://github.com/user-attachments/assets/660404ef-260b-4f9f-924d-8ebd5dfe0ea9" />


### Step 6: Access Application

Open Task Details.

Copy:

Public IP

Access:

http://<Public-IP>

Example:

http://3.110.xxx.xxx

Website should load successfully.
<img width="1650" height="1015" alt="Screenshot 2026-06-11 222754" src="https://github.com/user-attachments/assets/33c9b1d3-a9b0-4a51-b495-1f61d1fb0645" />
<img width="1759" height="991" alt="Screenshot 2026-06-11 222804" src="https://github.com/user-attachments/assets/6ee8ec45-0123-4d88-a95e-8e0458665604" />


ECS automatically creates or removes tasks.

