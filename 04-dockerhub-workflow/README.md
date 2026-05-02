# DockerHub Push Workflow from EC2

## Prerequisites
- Docker installed on EC2
- DockerHub account created at hub.docker.com
- Image already built locally

## Step-by-Step

### 1. Login to DockerHub
```bash
docker login
# Enter your DockerHub username and password/access token
```

### 2. Tag Your Image
```bash
docker tag <local-image>:latest <dockerhub-username>/<repo-name>:latest
```

### 3. Push to DockerHub
```bash
docker push <dockerhub-username>/<repo-name>:latest
```

### 4. Pull on Another Machine
```bash
docker pull <dockerhub-username>/<repo-name>:latest
```

## Security Tip
Use an Access Token instead of your password:
- Go to hub.docker.com → Account Settings → Security → New Access Token
- Use the token in `docker login` when prompted for password
