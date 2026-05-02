# Image Management Workflow

## Build an Image
```bash
docker build -t myimage:latest .
docker build -t myimage:v1.0 .
```

## Tag an Image
```bash
docker tag myimage:latest myusername/myimage:latest
docker tag myimage:latest myusername/myimage:v1.0
```

## Push to DockerHub
```bash
docker login
docker push myusername/myimage:latest
```

## Pull from DockerHub
```bash
docker pull myusername/myimage:latest
```

## Save Image to File (Offline Transfer)
```bash
docker save -o myimage.tar myimage:latest
```

## Load Image from File
```bash
docker load -i myimage.tar
```

## Remove Images
```bash
docker rmi myimage:latest
docker image prune        # Remove dangling images
docker image prune -a     # Remove ALL unused images
```
