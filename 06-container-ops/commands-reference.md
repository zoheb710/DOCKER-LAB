# Container Operations Reference

## Execute Commands Inside Container
```bash
docker exec -it <name> bash         # Open bash shell
docker exec -it <name> sh           # Open sh shell (Alpine images)
docker exec <name> <command>        # Run single command
docker exec -it <name> env          # List environment variables
```

## Copy Files
```bash
docker cp <src-file> <name>:/dest/path    # Host → Container
docker cp <name>:/src/path <dest-file>    # Container → Host
```

## Logs
```bash
docker logs <name>                  # All logs
docker logs -f <name>               # Follow (live tail)
docker logs --tail 50 <name>        # Last 50 lines
docker logs --since 1h <name>       # Logs from last 1 hour
```

## Inspect & Stats
```bash
docker inspect <name>               # Full JSON details (IP, mounts, config)
docker inspect <name> | grep IPAddress   # Get container IP
docker stats                        # Live CPU/Memory for all containers
docker stats <name>                 # Stats for specific container
docker top <name>                   # Processes running inside container
```

## Commit Container as Image
```bash
docker commit <container-name> <new-image-name>:<tag>
# Example: Save your customized Nginx as a new image
docker commit nginx-server my-custom-nginx:v1
```
