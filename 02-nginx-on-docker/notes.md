# Port Mapping Notes

## Syntax
```
-p <host_port>:<container_port>
```

## Examples
```bash
docker run -p 8080:80 nginx      # localhost:8080 → container port 80
docker run -p 80:80 nginx        # localhost:80 → container port 80
docker run -P nginx              # Docker auto-assigns random host port
```

## How it works
- LEFT side  → Your machine (host)
- RIGHT side → Inside the container
- Traffic: Browser → host port → Docker → container port

## On AWS EC2
- Use EC2 Public IP instead of localhost
- Allow the host port in the Security Group Inbound Rules
