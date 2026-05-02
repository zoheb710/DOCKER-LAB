# Docker CLI Commands Reference

## Images
```bash
docker pull <image>               # Download image from registry
docker images                     # List local images
docker rmi <image>                # Remove image
docker image prune                # Remove dangling images
docker system prune -f            # Remove all unused resources
```

## Containers
```bash
docker run -d --name <name> -p 80:80 <image>   # Run in background
docker ps                         # List running containers
docker ps -a                      # List all containers
docker start <name>
docker stop <name>
docker restart <name>
docker rm <name>                  # Remove stopped container
docker rm -f <name>               # Force remove running container
```

## Logs & Inspection
```bash
docker logs <name>
docker logs -f <name>             # Follow logs in real-time
docker inspect <name>
docker stats                      # Live resource usage
```

## Exec & Copy
```bash
docker exec -it <name> bash       # Enter running container
docker cp <file> <name>:/path     # Copy file into container
docker cp <name>:/path <file>     # Copy file out of container
```
