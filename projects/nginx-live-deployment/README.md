# Nginx Live Deployment on EC2

## Goal
Expose a Dockerized Nginx server to the internet via EC2 Public IP.

## Prerequisites
- EC2 instance running (Ubuntu 22.04 recommended)
- Security Group: Allow inbound TCP on port 80 (and 22 for SSH)
- SSH access to EC2

## Step 1 — Install Docker on EC2
```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ubuntu
# Log out and back in for group change to take effect
```

## Step 2 — Run Nginx Container
```bash
docker run -d --name nginx-live -p 80:80 nginx
```

## Step 3 — Verify
```bash
docker ps                          # Confirm container is running
curl http://localhost              # Test locally
```

## Step 4 — Access from Browser
```
http://<EC2-PUBLIC-IP>
```
You should see the Nginx welcome page.

## Step 5 — Clean Up
```bash
docker stop nginx-live
docker rm nginx-live
```
