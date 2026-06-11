# Amazon ECR - Docker Image Repository

## Objective

Store Docker images securely in AWS Elastic Container Registry (ECR).

---

## Step 1: Create ECR Repository

1. Open AWS Console
2. Search for ECR
3. Click Repositories
4. Create Repository
5. Select Private Repository
6. Enter Repository Name

Example:

private-beauty

7. Click Create Repository

---

## Step 2: Create IAM User

1. IAM → Users
2. Create User
3. Attach Policy

AmazonEC2ContainerRegistryFullAccess

4. Create Access Key

Download:

- Access Key ID
- Secret Access Key

---

## Step 3: Configure AWS CLI

```bash
aws configure

Provide:
AWS Access Key ID
AWS Secret Access Key
Region
Output Format

Example:
us-east-1
json
```

### Step 4: Create Docker Image
#### Docker file

FROM nginx:latest

COPY . /usr/share/nginx/html/

EXPOSE 80

### Build image:

docker build -t private-beauty .

Verify:

docker images

### Step 5: Login to ECR

Copy login command from ECR.
<img width="1007" height="789" alt="Screenshot 2026-06-11 215303" src="https://github.com/user-attachments/assets/bed762dd-f6cb-43a9-bb24-c9b9e62129a7" />


Example: aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 800557027867.dkr.ecr.us-east-1.amazonaws.com

Login Succeeded

### Step 6: Tag Image

> docker tag private-beauty:latest 800557027867.dkr.ecr.us-east-1.amazonaws.com/private-beauty:latest


### Step 7: Push Image

> docker push 800557027867.dkr.ecr.us-east-1.amazonaws.com/private-beauty:latest

Verify image inside ECR Repository.

> docker images

AWS Console:

ECR → Repository → Images

Image should be visible.
<img width="1525" height="951" alt="Screenshot 2026-06-11 215932" src="https://github.com/user-attachments/assets/cf29b970-4a87-482a-a891-3ddc6828f052" />



### OUTPUT:
<img width="1875" height="981" alt="Screenshot 2026-06-11 215848" src="https://github.com/user-attachments/assets/005dc0a5-f07b-4fb8-9de0-ba3952a24df1" />
<img width="1761" height="939" alt="Screenshot 2026-06-11 220001" src="https://github.com/user-attachments/assets/3bd43b0f-b33b-4c10-a5dd-f43ba71506df" />

