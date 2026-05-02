# 🐳 Docker: Zero to Production

A structured, hands-on Docker learning repository — from core CLI commands to deploying real images on AWS ECR.

## 📚 Learning Path

| Module | Topic | Key Skills |
|--------|-------|------------|
| 01 | Core CLI Commands | pull, run, ps, stop, rm, logs |
| 02 | Nginx on Docker | Port mapping (-p, -P), EC2 exposure |
| 03 | Image Management | build, tag, push, save, load, prune |
| 04 | DockerHub Workflow | login, tag, push, pull from hub |
| 05 | AWS ECR Workflow | ECR auth, IAM roles, private registry |
| 06 | Container Ops | exec, cp, logs, inspect, stats, commit |
| 07 | Dockerfile | Instructions, best practices, examples |

## 🚀 Projects

| Project | Description |
|---------|-------------|
| nginx-live-deployment | Run Nginx on EC2 and expose to internet |
| custom-image-to-ecr | Build custom image → push to AWS ECR |

## 🛠️ Prerequisites
- Ubuntu EC2 instance (t2.micro or t3.micro)
- Docker installed (`sudo apt install docker.io -y`)
- AWS CLI configured (`aws configure`)
- DockerHub account
- AWS account with ECR access

## 📁 Repository Structure
```
Docker-Zero-to-Production/
├── 01-core-commands/
│   └── commands-reference.md
├── 02-nginx-on-docker/
│   ├── README.md
│   └── notes.md
├── 03-image-management/
│   ├── README.md
│   └── notes.md
├── 04-dockerhub-workflow/
│   ├── README.md
│   └── notes.md
├── 05-aws-ecr-workflow/
│   ├── README.md
│   └── notes.md
├── 06-container-ops/
│   └── commands-reference.md
├── 07-dockerfile/
│   ├── README.md
│   ├── Dockerfile.nginx-custom
│   └── Dockerfile.node-app
└── projects/
    ├── nginx-live-deployment/
    │   └── README.md
    └── custom-image-to-ecr/
        └── README.md
```

## 🔗 Quick Reference
- [Docker Docs](https://docs.docker.com)
- [DockerHub](https://hub.docker.com)
- [AWS ECR Docs](https://docs.aws.amazon.com/ecr/)
