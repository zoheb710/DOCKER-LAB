# Push Docker Image to AWS ECR (Private Registry)

## Prerequisites
- AWS CLI configured (`aws configure`)
- IAM Role with `AmazonEC2ContainerRegistryFullAccess` attached to EC2
- Docker installed on EC2

## Step-by-Step

### 1. Create ECR Repository
```bash
aws ecr create-repository \
  --repository-name my-app \
  --region ap-south-1
```

### 2. Authenticate Docker to ECR
```bash
aws ecr get-login-password --region ap-south-1 | \
  docker login --username AWS --password-stdin \
  <account-id>.dkr.ecr.ap-south-1.amazonaws.com
```

### 3. Build Your Image
```bash
docker build -t my-app .
```

### 4. Tag with ECR Format
```bash
docker tag my-app:latest \
  <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
```

### 5. Push to ECR
```bash
docker push <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
```

### 6. Pull from ECR (on another EC2 or ECS)
```bash
docker pull <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
```
