# DockerHub Notes

## Login Options
```bash
docker login                          # Interactive (prompts username + password)
docker login -u <username>            # Specify username, prompts password
echo <token> | docker login -u <username> --password-stdin  # Non-interactive (CI/CD)
```

## Logout
```bash
docker logout
```

## Tag Format for DockerHub
```
<username>/<repository>:<tag>
Example: zoheb/my-nginx:latest
         zoheb/my-nginx:v1.0
```

## Common Errors
| Error                              | Fix                                      |
|------------------------------------|------------------------------------------|
| denied: access forbidden           | Re-run docker login                      |
| repository does not exist          | Create repo on hub.docker.com first      |
| tag name must be lowercase         | Rename tag to lowercase                  |
| unauthorized: authentication required | docker login before push              |
