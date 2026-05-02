# Dockerfile — Instructions & Best Practices

## Common Dockerfile Instructions

| Instruction | Purpose                                          |
|-------------|--------------------------------------------------|
| FROM        | Base image to build on                           |
| WORKDIR     | Set working directory inside container           |
| COPY        | Copy files from host to container                |
| ADD         | Like COPY but supports URLs and auto-extraction  |
| RUN         | Execute command during image build               |
| EXPOSE      | Document which port the container listens on     |
| ENV         | Set environment variables                        |
| ARG         | Build-time variables (not available at runtime)  |
| CMD         | Default command when container starts            |
| ENTRYPOINT  | Fixed command (CMD becomes its arguments)        |

## Best Practices
1. Use specific base image tags — avoid `latest` in production
2. Chain RUN commands with `&&` to reduce image layers
3. Copy `package.json` before source code (cache optimization)
4. Use `.dockerignore` to exclude node_modules, .git, etc.
5. Run as non-root user for security
6. Keep images small — prefer `alpine` variants

## .dockerignore Example
```
node_modules/
.git/
*.log
.env
dist/
```
