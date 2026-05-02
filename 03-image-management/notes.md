# Image Management Notes

## docker save vs docker export
| Command        | Saves               | Use Case                  |
|----------------|---------------------|---------------------------|
| docker save    | Full image + layers | Share image offline       |
| docker export  | Container filesystem| Snapshot running container|

## docker load vs docker import
| Command        | Works With     |
|----------------|----------------|
| docker load    | docker save output (.tar) |
| docker import  | docker export output      |

## Prune Commands
```bash
docker image prune          # Removes only <none> (dangling) images
docker image prune -a       # Removes ALL images not used by a container
docker system prune -f      # Removes containers, networks, images, cache
docker system prune --volumes  # Also removes volumes (careful!)
```

## Tagging Best Practices
- Always tag with version: v1.0, v1.1, latest
- `latest` tag does NOT auto-update — you must manually re-tag
