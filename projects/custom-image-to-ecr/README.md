# Build → Tag → Push to AWS ECR

## Goal
Build a custom Docker image locally and push it to AWS ECR private registry.

## Project Structure
```
custom-image-to-ecr/
├── Dockerfile
├── index.html        (for Nginx) or index.js (for Node)
└── README.md
```

## Step 1 — Build the Image
```bash
docker build -t my-custom-app:latest .
docker images   # Confirm image exists
```

## Step 2 — Authenticate to ECR
```bash
aws ecr get-login-password --region ap-south-1 | \
  docker login --username AWS --password-stdin \
  <account-id>.dkr.ecr.ap-south-1.amazonaws.com
```

## Step 3 — Create ECR Repository (first time only)
```bash
aws ecr create-repository \
  --repository-name my-custom-app \
  --region ap-south-1
```

## Step 4 — Tag the Image
```bash
docker tag my-custom-app:latest \
  <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-custom-app:latest
```

## Step 5 — Push to ECR
```bash
docker push \
  <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-custom-app:latest
```

## Step 6 — Verify in AWS Console
- Go to: AWS Console → ECR → Repositories → my-custom-app
- You should see your image with the `latest` tag

## Step 7 — Pull on Another Machine
```bash
# Re-authenticate first
aws ecr get-login-password --region ap-south-1 | \
  docker login --username AWS --password-stdin \
  <account-id>.dkr.ecr.ap-south-1.amazonaws.com

docker pull <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-custom-app:latest
```
