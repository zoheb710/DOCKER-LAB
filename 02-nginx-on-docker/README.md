# Nginx on Docker — Port Mapping

## Goal
Run Nginx inside a Docker container and expose it to your browser or EC2 public IP.

## Steps

### 1. Pull Nginx Image
```bash
docker pull nginx:latest
```

### 2. Run with Port Mapping
```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

### 3. Verify Locally
```bash
curl http://localhost:8080
```

### 4. Verify on EC2
- Open EC2 Security Group → Add Inbound Rule: TCP port 8080
- Visit: `http://<EC2-PUBLIC-IP>:8080`

### 5. Stop and Clean Up
```bash
docker stop nginx-server
docker rm nginx-server
```
